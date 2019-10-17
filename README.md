# Raku 官方文档中英文对照野生翻译

English-Chinese Raku documentation

Official documentation address: https://rakudocs.github.io/language.html

IT 类翻译文章往往中文太生硬，英文太难懂。何不对照看。

# `目录`

- [基础主题 - Fundamental topics](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/tree/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics)
    - [集合、背包和混合 - Sets, bags, and mixes](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E9%9B%86%E5%90%88%E3%80%81%E8%83%8C%E5%8C%85%E5%92%8C%E6%B7%B7%E5%90%88%20-%20Sets%2C%20bags%2C%20and%20mixes.md)
    - [枚举 - Enumeration](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E6%9E%9A%E4%B8%BE%20-%20Enumeration.md)
    - [正则 - Regexes](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E6%AD%A3%E5%88%99%20-%20Regexes.md)
    - [数值 - Numerics](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E6%95%B0%E5%80%BC%20-%20Numerics.md)
    - [控制流 - Control Flow](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E6%8E%A7%E5%88%B6%E6%B5%81%20-%20Control%20Flow.md)
    - [数据结构 - Data Structures](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%20-%20Data%20Structures.md)
    - [上下文以及上下文语境化器 - Contexts and contextualizers](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E4%B8%8A%E4%B8%8B%E6%96%87%E4%BB%A5%E5%8F%8A%E4%B8%8A%E4%B8%8B%E6%96%87%E8%AF%AD%E5%A2%83%E5%8C%96%E5%99%A8%20-%20Contexts%20and%20contextualizers.md)
    - [下标 - Subscripts](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E4%B8%8B%E6%A0%87%20-%20Subscripts.md)
    - [Unicode 与 ASCII 符号 - Unicode versus ASCII symbols](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/Unicode%20%E4%B8%8E%20ASCII%20%E7%AC%A6%E5%8F%B7%20-%20Unicode%20versus%20ASCII%20symbols.md)
    - [输入输出权威指南 - Input/Output the definitive guide](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E8%BE%93%E5%85%A5%E8%BE%93%E5%87%BA%E6%9D%83%E5%A8%81%E6%8C%87%E5%8D%97%20-%20IO%20the%20definitive%20guide.md)
    - [相位器 - Phasers](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E7%9B%B8%E4%BD%8D%E5%99%A8%20-%20Phasers.md)
    - [万国码 - Unicode](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E4%B8%87%E5%9B%BD%E7%A0%81%20-%20Unicode.md)
    - [日期与时间函数 - Date and time functions](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E6%97%A5%E6%9C%9F%E4%B8%8E%E6%97%B6%E9%97%B4%E5%87%BD%E6%95%B0%20-%20Date%20and%20time%20functions.md)
    - [原生调用接口 - Native calling interface](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%8E%9F%E7%94%9F%E8%B0%83%E7%94%A8%E6%8E%A5%E5%8F%A3%20-%20Native%20calling%20interface.md)
    - [元对象协议 - Meta-object protocol (MOP)](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%85%83%E5%AF%B9%E8%B1%A1%E5%8D%8F%E8%AE%AE%20-%20Meta-object%20protocol%20(MOP).md)
    - [运算符 - Operators](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E8%BF%90%E7%AE%97%E7%AC%A6%20-%20Operators.md)
    - [面向物件编程 - Object orientation](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E9%9D%A2%E5%90%91%E7%89%A9%E4%BB%B6%E7%BC%96%E7%A8%8B%20-%20Object%20orientation.md)
    - [Raku 原生类型 - Raku native types](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/Perl%206%20%E5%8E%9F%E7%94%9F%E7%B1%BB%E5%9E%8B%20-%20Perl%206%20native%20types.md)
    - [包 - Packages](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%8C%85%20-%20Packages.md)
    - [语句前缀 - Statement prefixes](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E8%AF%AD%E5%8F%A5%E5%89%8D%E7%BC%80%20-%20Statement%20prefixes.md)
    - [类型系统 - Type system](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E7%B1%BB%E5%9E%8B%E7%B3%BB%E7%BB%9F%20-%20Type%20system.md)
    - [列表、序列和数组 - Lists, sequences, and arrays](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%88%97%E8%A1%A8%E3%80%81%E5%BA%8F%E5%88%97%E5%92%8C%E6%95%B0%E7%BB%84%20-%20Lists%2C%20sequences%2C%20and%20arrays.md)
    - [句法 - Syntax](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%8F%A5%E6%B3%95%20-%20Syntax.md)
    - [哈希和映射 - Hashes and maps](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%93%88%E5%B8%8C%E5%92%8C%E6%98%A0%E5%B0%84%20-%20Hashes%20and%20maps.md)
    - [语法 - Grammars](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E8%AF%AD%E6%B3%95%20-%20Grammars.md)
    - [异常 - Exceptions](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%BC%82%E5%B8%B8%20-%20Exceptions.md)
    - [换行处理 - Newline handling](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/Perl%206%20%E4%B8%AD%E7%9A%84%E6%8D%A2%E8%A1%8C%E5%A4%84%E7%90%86%20-%20Newline%20handling%20in%20Perl%206.md)
    - [函数 - Functions](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%87%BD%E6%95%B0%20-%20Functions.md)
    - [容器 - Containers](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%AE%B9%E5%99%A8%20-%20Containers.md)
    - [变量 - Variables](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E5%9F%BA%E7%A1%80%E4%B8%BB%E9%A2%98%20-%20Fundamental%20topics/%E5%8F%98%E9%87%8F%20-%20Variables.md)
- [起步 - At the beginning](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/tree/master/%E8%B5%B7%E6%AD%A5%20-%20At%20the%20beginning)
    - [Raku 的例子 - Raku by example](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E8%B5%B7%E6%AD%A5%20-%20At%20the%20beginning/Perl%206%20%E7%9A%84%E4%BE%8B%E5%AD%90%20-%20Perl%206%20by%20example%20P6-101.md)
    - [简介 - Brief introduction](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E8%B5%B7%E6%AD%A5%20-%20At%20the%20beginning/%E7%AE%80%E4%BB%8B%20-%20Brief%20introduction.md)
- [教程 - Tutorials](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/tree/master/%E6%95%99%E7%A8%8B%20-%20Tutorials)
    - [类和对象 - Classes and Objects](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E6%95%99%E7%A8%8B%20-%20Tutorials/%E7%B1%BB%E5%92%8C%E5%AF%B9%E8%B1%A1%20-%20Classes%20and%20Objects.md)
    - [并发 - Concurrency](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E6%95%99%E7%A8%8B%20-%20Tutorials/%E5%B9%B6%E5%8F%91%20-%20Concurrency.md)
    - [输入 Unicode 字符 - Entering unicode characters](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E6%95%99%E7%A8%8B%20-%20Tutorials/%E8%BE%93%E5%85%A5%20unicode%20%E5%AD%97%E7%AC%A6%20-%20Entering%20unicode%20characters.md)
    - [输入与输出 - Input and Output](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E6%95%99%E7%A8%8B%20-%20Tutorials/%E8%BE%93%E5%85%A5%E4%B8%8E%E8%BE%93%E5%87%BA%20-%20Input%20and%20Output.md)
- [类型 - Type](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/tree/master/%E7%B1%BB%E5%9E%8B%20-%20Type)
    - [基础 - Basic](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/tree/master/%E7%B1%BB%E5%9E%8B%20-%20Type/%E5%9F%BA%E7%A1%80%20-%20Basic)
        - [签名 - Signature](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E7%B1%BB%E5%9E%8B%20-%20Type/%E5%9F%BA%E7%A1%80%20-%20Basic/%E7%AD%BE%E5%90%8D%20-%20Signature.md)
    - [特定领域 - Domain-specific](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/tree/master/%E7%B1%BB%E5%9E%8B%20-%20Type/%E7%89%B9%E5%AE%9A%E9%A2%86%E5%9F%9F%20-%20Domain-specific)
        - [承诺 - Promise](https://github.com/sztanyi/English-Chinese-Doc-of-Raku/blob/master/%E7%B1%BB%E5%9E%8B%20-%20Type/%E7%89%B9%E5%AE%9A%E9%A2%86%E5%9F%9F%20-%20Domain-specific/%E6%89%BF%E8%AF%BA%20-%20Promise.md)

