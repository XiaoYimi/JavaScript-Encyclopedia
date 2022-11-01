<h1 align="center">JavaScript String 类型</h1>



## String 类型总述

JavaScript String 类型，无符号 16 位值有序序列，用于表示字符串。JavaScript String 使用 Unicode 字符集的 UTF-16 编码的码点来存储值。当字符串的码点超出 Unicode 字符集码点时，将使用 2 个 16  位值的有序序列来表示，即代理对。所以，一个 Unicode 字符可以由 2 个 16位值的有序序列来表示。字符串属性 length 值表示字符串所包含的 16 位值的个数。JavaScript String 基于 0 的索引来读取 16 位值。



## 字符串符号

- [x] 双引号： ""，用于标签一般严格场景(XML，DOM 属性)
- [x] 单引号：''，用于 JavaScript 习惯
- [x] 反引号：``，ES6特性，用于多行字符表示



## 字符与16位值

在 JavaScript 的字符串操作中，本质上是对16位值进行操作的；而在 ES6 的迭代遍历中，是对于字符进行操作的。

```nginx
# 举栗子： 吉祥的 吉，与变体字 𠮷

var a = '吉';
var b = '𠮷';

# 字符串属性 length 是根据字符串所包含 16位值 的个数得出的 
a.length;  // 1
b.length;  // 2

# 基于索引 0 的字符串，操作的是 16位值
a[0]; // '吉'
b[0]; // '\uD842'

# for-of 进行迭代，操作的是 字符
for (const k of a) { console.log(k)； } // '吉'
for (const k of b) { console.log(k)； } // ‘𠮷’

# ... 展开运算操作，操作的是 字符
[...a]; // ['吉']
[...b]; // [‘𠮷’]
```



## 字符转义序列

| 转义序列 | 转义字符                                                   |
| -------- | ---------------------------------------------------------- |
| \0       | NULL字符(\u0000)                                           |
| \b       | 退格符号(\u0008)                                           |
| \t       | 水平制表符(\u0009)                                         |
| \n       | 换行符(\u000A)                                             |
| \v       | 垂直制表符(\u000B)                                         |
| \f       | 进纸符(\u000C)                                             |
| \r       | 回车符(\u000D)                                             |
| \\"      | 双引号(\u0022)                                             |
| \\'      | 单引号(\u0027)                                             |
| \\\      | 反斜杠(\u005C)                                             |
| \xnn     | 由 2 位 16进制数字 nn 指定 Unicode 字符                    |
| \unnnn   | 由 4 位 16进制数字 nnnn 指定 Unicode 字符                  |
| \u{n}    | 由码点 n 指定 Unicode 字符，n 介于 0 - 10FFFF 16进制数字值 |
|          |                                                            |



## 字符串方法

- [x] 检测字符串是否以指定字符开始：str.startsWith(char)
- [x] 检测字符串是否以指定字符结束：str.endsWith(char)
- [x] 检测字符串是否包含子字符串：str.includes(char)
- [x] 根据索引位置获取(16位值)字符：str.charAt(index)
- [x] 指定位置字符对应的 16位值：str.charCodeAt(index)
- [x] 指定位置字符对应的进制位值：str.codePointAt(index)
- [x] 字符串截取：str.substring(start, end)
- [x] 字符串截取：str.slice(start, end)
- [x] 字符串拼接：str.concat(str1, str...)
- [x] 根据字符串长度往左侧添加指定字符：str.padStart(length, char)
- [x] 根据字符串长度往右侧添加指定字符：str.padEnd(length, char)
- [x] 从指定索引位置起搜索字符串：str.indexOf(char, index)
- [x] 从指定索引位置起搜素字符串：str.lastIndexOf(char, index)
- [x] 根据规则匹配进行替换字符：str.replace(regexp, newStr)
- [x] 根据界定符拆分字符串：str.split(separator)
- [x] 移除字符串左右两侧空格字符：str.trim()
- [x] 移除字符串左侧空格字符：str.trimStart()
- [x] 移除字符串右侧空格字符：str.trimEnd()
- [x] 生成重复次数的当前字符串：str.repeat(count)
- [x] 字符串转换为大写字母字符串：str.toUpperCase()
- [x] 字符串转换为小写字母字符串：str.toLowerCase()
- [x] 根据字符串匹配模式搜索字符：str.search(regexp)
- [x] 根据字符串匹配模式获取匹配集：str.match(regexp)