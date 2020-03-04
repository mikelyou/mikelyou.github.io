---
layout: post
title: "Python Learning #04 - Loop Structure"
subtitle: '循环结构'
date: 2020-01-02 16:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
tags:
  - Python
  - Notes
---

在Python中同样有两种循环：`for-in`循环和`while`循环

<!-- more -->

## for-in 循环
```python
"""
用for循环实现1~100求和
"""

sum = 0
for x in range(101):
    sum += x
print(sum)
```
其中，`range()`函数可以更灵活：

- `range(101)`可以产生一个0到100的整数序列。
- `range(1, 100)`可以产生一个1到99的整数序列。
- `range(1, 100, 2)`可以产生一个1到99的奇数序列，其中2是步长，即数值序列的增量。

**注意： `range(n)`产生的是`0`至`n-1`的序列！**

## while 循环

```python
"""
用while循环实现1~100求和
"""

i = 1
sum = 0
while i <= 100 :
    i = i + 1
    sum =sum + i
print(sum)
```

在`while`循环中，可以使用`break`强制结束循环，以及使用`continue`函数直接跳到下一次循环的开始。

## 循环的嵌套
举个栗子，九九乘法表
```python
"""
九九乘法表
"""

for i in range(1, 9 + 1):
    for j in range(1, i + 1):
        print('%d*%d=%d' % (i, j, i * j), end='\t')
    print()
```
>关于逗号`,`的作用，可以参考[这篇文章](https://blog.csdn.net/liuzx32/article/details/7831247)，应该是对的

## References
- [Python-100-Days](https://github.com/jackfrued/Python-100-Days)

------------
