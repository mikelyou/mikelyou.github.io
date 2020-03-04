---
layout: post
title: "Python Learning #02 - Input, Output and Assignment"
subtitle: '输入，输出，赋值'
date: 2020-01-02 14:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
tags:
  - Python
  - Notes
---

<!-- more -->

## 赋值
```python
a = 10
b = 3
a += b # 相当于：a = a + b
a *= a + 2 # 相当于：a = a * (a + 2)
```

## 输入`input`
```python
a = int(input('a = ')) #读取为int类型
f = float(input('请输入华氏温度: ')) #显示输入提示
a, b = map(int, input().split()) #读取在同一行的多个数字
```

## 输出`print`
```python
print(a)
print(a + b)
print(a,b) #输出结果会以空格隔开
print('%.1f' % a) #输出float型变量a,保留一位小数
```
> [Python格式化输出](https://www.cnblogs.com/fat39/p/7159881.html)

- 使用`end`函数使`print`不换行
```python
for i in range(1, 5+1):
    print (i, end = " ")  #1 2 3 4 5
```

## References
- [Python-100-Days](https://github.com/jackfrued/Python-100-Days)

------------
