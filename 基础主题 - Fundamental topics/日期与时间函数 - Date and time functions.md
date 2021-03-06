原文：https://docs.raku.org/language/temporal

# 日期与时间函数 / Date and time functions

使用 Raku 处理日期与时间

Processing date and time in Raku

Raku 包含几个处理时间信息的类： [Date](https://docs.raku.org/type/Date)、 [DateTime](https://docs.raku.org/type/DateTime)、 [Instant](https://docs.raku.org/type/Instant) 和 [Duration](https://docs.raku.org/type/Duration)。它们具有 [Dateish](https://docs.raku.org/type/Dateish) 角色，该角色定义了处理日期的类应有的所有方法和属性。它还包括以 [X::Temporal](https://docs.raku.org/type/X::Temporal) 为根的异常类层次结构。

Raku includes several classes that deal with temporal information: [Date](https://docs.raku.org/type/Date), [DateTime](https://docs.raku.org/type/DateTime), [Instant](https://docs.raku.org/type/Instant) and [Duration](https://docs.raku.org/type/Duration). The three first are *dateish*, so they mix in the [Dateish](https://docs.raku.org/type/Dateish) role, which defines all methods and properties that classes that deal with date should assume. It also includes a class hierarchy of exceptions rooted in [X::Temporal](https://docs.raku.org/type/X::Temporal).

我们将在下一个（稍微有些扩展）示例中演示这些类，该示例可用于处理目录中具有特定扩展名（默认为 `.`）的所有文件（默认为 `.p6`），根据它们的存在时间对它们进行排序，并计算每个月创建了多少个文件，以及在特定时期修改了多少个文件。以月为单位表示：

We will try to illustrate these classes in the next (somewhat extended) example, which can be used to process all files in a directory (by default `.`) with a particular extension (by default `.p6`) in a directory, sort them according to their age, and compute how many files have been created per month and how many were modified in certain periods expressed in ranges of months:

```Raku
sub MAIN( $path = ".", $extension = "p6" ) {
    my DateTime $right = DateTime.now;
    my %metadata;
    my %files-month;
    my %files-period;
    for dir($path).grep( / \.$extension $/ ) -> $file {
        CATCH {
            when X::Temporal { say "Date-related problem", .payload }
            when X::IO { say "File-related problem", .payload }
            default { .payload.say }
        }
        my Instant $modified = $file.modified;
        my Instant $accessed = $file.accessed;
        my Duration $duration = $accessed - $modified;
        my $age = $right - DateTime($accessed);
        my $time-of-day = $file.changed.DateTime.hh-mm-ss but Dateish;
        my $file-changed-date =  $file.changed.Date;
        %metadata{$file} = %( modified => $modified,
                              accessed => $accessed,
                              age => $age,
                              difference => $duration,
                              changed-tod => $time-of-day,
                              changed-date => $file-changed-date);
        %files-month{$file-changed-date.month}++;
        given $file-changed-date {
            when Date.new("2018-01-01")..^Date.new("2018-04-01") { %files-period<pre-grant>++}
            when Date.new("2018-04-01")..Date.new("2018-05-31") { %files-period<grant>++}
            default { %files-period<post-grant>++};
        }
    }
 
    %metadata.sort( { $^a.value<age> <=> $^b.value<age> } ).map: {
        say $^x.key, ", ",
        $^x.value<accessed modified age difference changed-tod changed-date>.join(", ");
    };
    %files-month.keys.sort.map: {
        say "Month $^x → %files-month{$^x}"
    };
 
    %files-period.keys.map: {
        say "Period $^x → %files-period{$^x}"
    };
}
```

`DateTime` 在第 2 行中用于包含由 [`now`](https://docs.raku.org/routine/now) 返回的当前日期和时间。

`DateTime` is used in line 2 to contain the current date and time returned by [`now`](https://docs.raku.org/routine/now).

在第 7 到 11 行中声明了一个 CATCH 相量。它的主要任务是区分 `DateTime` 相关的异常和其他类型的异常。这些异常可能来自 [invalid formats](https://docs.raku.org/type/X::Temporal::InvalidFormat) 或 [timezone clashes](https://docs.raku.org/type/X::DateTime::TimezoneClash)。除非文件属性出现某些损坏，否则这两者都是不可能的，但无论如何，它们都应该被捕获并与其他类型的异常分开。

A CATCH phaser is declared in lines 11 to 15. Its main mission is to distinguish between `DateTime`-related exceptions and other types. These kind of exception can arise from [invalid formats](https://docs.raku.org/type/X::Temporal::InvalidFormat) or [timezone clashes](https://docs.raku.org/type/X::DateTime::TimezoneClash). Barring some corruption of the file attributes, both are impossible, but in any case they should be caught and separated from other types of exceptions.

我们在 12-13 行使用 [Instant](https://docs.raku.org/type/Instant) 代表文件访问和修改的时刻。Instant 通过原子秒来衡量，是时间事件非常底层的描述；然而，在第 14 行 [Duration](https://docs.raku.org/type/Duration) 表示两个不同 `Instant` 之间的时间，我们将使用它代表年龄。

We use [Instant](https://docs.raku.org/type/Instant)s in lines 16-17 to represent the moment in which the files where accessed and modified. An Instant is measured in atomic seconds, and is a very low-level description of a time event; however, the [Duration](https://docs.raku.org/type/Duration) declared in line 18 represent the time transcurred among two different `Instant`s, and we will be using it to represent the age.

对于某些变量，我们可以用 *dateish* 特性来处理它们。`$time-of-day` 是文件更改那天的时间；`changed` 方法返回一个 Instant 对象，但它被转换为日期（即 `Dateish` 而非 `Instant`），然后从中提取时间。`$time-of-day` 将有 `«Str+{Dateish}␤» ` 类型。

For some variables we might be interested in dealing with them with some *dateish* traits. `$time-of-day` contains the time of the day the file was changed; `changed` will return an Instant, but it is converted into a Date (which is `Dateish` while `Instant` is not) and then the time of day is extracted from that. `$time-of-day` will have `«Str+{Dateish}␤» `type.

我们将借助这个变量算出文件被改变的时间段。

We will use the date in this variable to find out the period when the files were changed.

```Raku
Date.new("2018-01-01")..^Date.new("2018-04-01")
```

这行代码创建出一个日期 [Range](https://docs.raku.org/type/Range)，`$file-changed-date` 变量智能匹配这个日期范围。 日期范围也可以使用 `^` 符号来排除最后那个元素。

creates a date [Range](https://docs.raku.org/type/Range) and `$file-changed-date` is smartmatched against it. Dates can be used this way; in this case it creates a `Range` that excludes its last element.

这个变量也可以用来计算文件被修改时的月份。 [Date](https://docs.raku.org/type/Date) 显然具有 `Dateish` 角色，可以使用 `month` 方法从中提取那个属性。

This very variable is also used to compute the month of the year when the file was modified. [Date](https://docs.raku.org/type/Date) is obviously `Dateish` and then has the `month` method to extract that property from it.

`Duration` 对象可以被比对。在下面代码

`Duration` objects can be compared. This is used in

```Raku
%metadata.sort({
    $^a.value<age> <=> $^b.value<age>
});
```

中用来按存在时间排序文件。

to sort the files by age.
