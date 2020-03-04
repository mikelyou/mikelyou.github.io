---
layout: post
title: "Python Learning #01 - Notes, Variables and Operators"
subtitle: '注释，变量，运算符'
date: 2020-01-02 13:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
tags:
  - Python
  - Notes
---

<!-- more -->

## 注释


- 单行注释：以`# `开头的部分

```python
a = b + c # 这是一条注释
```
- 多行注释：同时以`"""`或`'''`开头和结尾  (单引号与双引号仅有微小区别，可以忽略)

```python
print("下面是多行注释")
"""
print("注释")
print("注释不会编译")
print("可以看到print的字体颜色改变了")
"""
```


## 数据类型

#### 常用数据类型：

- 整形 int
- 浮点型 float
- 字符串型 'hello' or "hello"  (单引号与双引号仅有微小区别，可以忽略)
- 布尔型 True or False

#### 变量

- 变量命名：建议采用 **全小写加下划线** 的拼写，不能以数字开头，大小写敏感，见名识义。
- 使用`type`函数检查变量的类型
```python
a = 100
b = 12.345
c = 1 + 5j
d = 'hello, world'
e = True
print(type(a)) # <class 'int'>
print(type(b)) # <class 'float'>
print(type(c)) # <class 'complex'>
print(type(d)) # <class 'str'>
print(type(e)) # <class 'bool'>
```
- 使用Python内置函数转换变量类型
  - `int()`：将一个数值或字符串转换成整数，可以指定进制。
  - `float()`：将一个字符串转换成浮点数。
  - `str()`：将指定的对象转换成字符串形式，可以指定编码。
  - `chr()`：将整数转换成该编码对应的字符串（一个字符）。
  - `ord()`：将字符串（一个字符）转换成对应的编码（整数）。

#### 运算符

| 运算符                                                       | 描述                           |
| ------------------------------------------------------------ | ------------------------------ |
| `[]` `[:]`                                                   | 下标，切片                     |
| `**`                                                         | 指数                           |
| `~` `+` `-`                                                  | 按位取反, 正负号               |
| `*` `/` `%` `//`                                             | 乘，除，模，整除               |
| `+` `-`                                                      | 加，减                         |
| `>>` `<<`                                                    | 右移，左移                     |
| `&`                                                          | 按位与                         |
| `^` `\|`                                                      | 按位异或，按位或               |
| `<=` `<` `>` `>=`                                            | 小于等于，小于，大于，大于等于 |
| `==` `!=`                                                    | 等于，不等于                   |
| `is`  `is not`                                               | 身份运算符                     |
| `in` `not in`                                                | 成员运算符                     |
| `not` `or` `and`                                             | 逻辑运算符                     |
| `=` `+=` `-=` `*=` `/=` `%=` `//=` `**=` `&=` `|=` `^=` `>>=` `<<=` | （复合）赋值运算符             |

>**说明：** 在实际开发中，如果搞不清楚运算符的优先级，可以使用括号来确保运算的执行顺序。

## References
- [Python-100-Days](https://github.com/jackfrued/Python-100-Days)

-------------
