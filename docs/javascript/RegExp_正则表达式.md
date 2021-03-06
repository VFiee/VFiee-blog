---
sidebar: "auto"
---

# 正则表达式：RegExp
正则表达式可以从一个基础字符串中根据一定的匹配模式替换文本中的字符串、验证表单、提取字符串等等.


## 正则表达式中的特殊字符

    \   转义字符,用于匹配一些保留的字符 [ ] ( ) { } . * + ? ^ $ \ |


    ^   匹配输入的开始。如果多行标志被设置为true，那么也匹配换行符后紧跟的位置。


    $   匹配输入的结束。如果多行标示被设置为true，那么也匹配换行符前的位置。


    .   （小数点）匹配除换行符之外的任何单个字符
        例如，/.n/将会匹配 "nay, an apple is on the tree" 中的 'an' 和 'on'，但是不会匹配 'nay'。


    *   匹配前一个表达式0次或多次。等价于 {0,}。


    +   匹配前面一个表达式1次或者多次。等价于 {1,}。


    ?   匹配前面一个表达式0次或者1次。等价于 {0,1}。


    (xyz)   字符集, 匹配与 xyz 完全相等的字符串.  捕获


    [z-aA-Z0-9_]  字符种类. 匹配方括号内的任意字符.


    [^] 否定的字符种类. 匹配除了方括号里的任意字符


    {n,m}   n 和 m 都是整数。匹配前面的字符至少n次，最多m次。如果 n 或者 m 的值是0， 这个值被忽略。


    |	或运算符,匹配符号前或后的字符.


## 正则表达式的简写字符集
    . 匹配除换行符之外的任意字符



    \w 匹配所有的字母数字，等价于[a-zA-Z0-9_]
    \W 匹配所有的非字母数字，等价于[^\w]



    \d  匹配数字。等价于[0-9]。
    \D  匹配非数字字符。等价于[^\d]。



    \s  匹配所有空格字符，包括空格、制表符、换页符和换行符。  等价于[\t\n\f\r\p{Z}]
    \S  匹配所有非空格字符，等价于[^\s]


    \f 匹配一个换页符 ----formfeed
    \n 匹配一个换行符 (U+000A)。----newline
    \r 匹配一个回车符 (U+000D)。----return
    \t 匹配一个制表符  ----tab
    \v 匹配一个垂直制表符 ----vertical tabulation character
    \p 匹配CR\LF（等同于\r\n），用来匹配DOS行终止符。



## 使用正则表达式的方法

    方法	    描述
    exec	    一个在字符串中执行查找匹配的RegExp方法，它返回一个数组（未匹配到则返回 null）。
    test	    一个在字符串中测试是否匹配的RegExp方法，它返回 true 或 false。
    match	    一个在字符串中执行查找匹配的String方法，它返回一个数组，在未匹配到时会返回 null。
    matchAll    一个在字符串中执行查找匹配的String方法，它返回包含所有匹配项的迭代器，包括捕获组。
    search	    一个在字符串中测试匹配的String方法，它返回匹配到的位置索引，或者在失败时返回-1。
    replace	    一个在字符串中执行查找匹配的String方法，并且使用替换字符串替换掉匹配到的子字符串。
    split	    一个使用正则表达式或者一个固定字符串分隔一个字符串，并将分隔后的子字符串存储到数组中的 String 方法。


## 正则表达式的标志

    i	忽略大小写.  Case Insensitive
    g	全局搜索.  Global search
    m	多行搜索。锚点元字符 ^ $ 工作范围在每行的起始.   Multiline


## 零宽度断言

    正即存在或满足，负即排除或不满足。
    先行即都满足条件的情况下取前面的，后发即都满足条件的情况下取后面的。

    ?=	正（满足）先行断言-存在  (?=前后表达式都满足，返回?=之前匹配的内容)
        x(?=y)  匹配'x'仅仅当'x'后面跟着'y'.这种叫做先行断言。
        "(T|t)he(?=\sfat)" => The fat cat sat on the mat. [fat]


    ?!	负（不满足）先行断言-排除
        x(?!y)  仅仅当'x'后面不跟着'y'时匹配'x'，这被称为正向否定查找。
        "(T|t)he(?!\sfat)" => The fat cat sat on the mat. [the]


    ?<=	正（满足）后发断言-存在
        (?<=y)x 匹配'x'仅仅当'x'前面是'y'.这种叫做后行断言。
        "(?<=(T|t)he\s)(fat|mat)" => The fat cat sat on the mat. [fat,mat]


    ?<!	负（不满足）后发断言-排除
        (?<!y)x 匹配'x'仅仅当'x'前面不是'y'.这种叫做反向否定查找。
        "(?<!(T|t)he\s)(cat)" => The cat sat on cat. [cat(last)]














