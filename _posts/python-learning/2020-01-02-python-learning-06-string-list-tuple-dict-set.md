---
layout: post
title: "Python Learning #06 - String, List, Tuple, Dict and Set"
subtitle: '字符串，列表，元组，字典，集合'
date: 2020-01-02 18:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
tags:
  - Python
  - Notes
---

<!-- more -->

[本节讲义 &rarr;](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/07.%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%92%8C%E5%B8%B8%E7%94%A8%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md)

## 目录
- [字符串](#字符串)
- [列表](#列表)
- [元组](#元组)
- [字典](#字典)
- [集合](#集合)

## 字符串

###### 表示方法

由单引号或双引号括起来的单个或多个字符称为字符串，以三个双引号或单引号开头的字符串可以折行。

```python
s1 = 'hello, world!'
s2 = "hello, world!"
s3 = """
hello,
world!
"""

print(s1, s2, s3, end='')
```

###### 转义

例如： `\n`表示换行，`\'`表示字符`'`，`\\`表示字符`\`

`\`后面还可以跟一个八进制或者十六进制数来表示字符，例如`\141`和`\x61`分别为八进制和十六进制的小写字母`a`

`\`后面还可以跟Unicode字符编码来表示字符（大大提高了可玩性）

```python
print('\u00A2\u132B\u26BD\u2F5B\u3093') #¢ጫ⚽⽛ん
```

若不希望转义，可以通过在字符串的最前面加上字母`r`来实现。

```python
s1 = r'\'hello, world!\''   # \'hello, world!\'
```

###### 字符串的运算

Python为字符串类型提供了非常丰富的运算符:

```python
s1 = 'hello ' * 3
print(s1) # hello hello hello

s2 = 'world'
s1 += s2
print(s1) # hello hello hello world

print('ll' in s1) # True
print('good' in s1) # False


str2 = 'abc123456'

# 从字符串中取出指定位置的字符(下标运算)
print(str2[2]) # c

# 字符串切片(从指定的开始索引到指定的结束索引)
#index 从 0 至 n-1，str2[l:r] 包含 l 不包含 r
print(str2[2:5]) # c12
print(str2[2:]) # c123456
print(str2[2::2]) # c246
print(str2[::2]) # ac246
print(str2[::-1]) # 654321cba
print(str2[-3:-1]) # 45
```

在Python中，我们还可以通过一系列的方法来完成对字符串的处理:
```python
str1 = 'hello, world!'

# 通过内置函数len计算字符串的长度
print(len(str1)) # 13

# 获得字符串首字母大写的拷贝
print(str1.capitalize()) # Hello, world!

# 获得字符串每个单词首字母大写的拷贝
print(str1.title()) # Hello, World!

# 获得字符串变大写后的拷贝
print(str1.upper()) # HELLO, WORLD!

# 从字符串中查找子串所在位置
print(str1.find('or')) # 8
print(str1.find('shit')) # -1
# 与find类似但找不到子串时会引发异常
# print(str1.index('or'))
# print(str1.index('shit'))

# 检查字符串是否以指定的字符串开头
print(str1.startswith('He')) # False
print(str1.startswith('hel')) # True

# 检查字符串是否以指定的字符串结尾
print(str1.endswith('!')) # True

# 将字符串以指定的宽度居中并在两侧填充指定的字符
print(str1.center(50, '*'))
# 将字符串以指定的宽度靠右放置左侧填充指定的字符
print(str1.rjust(50, ' '))


str2 = 'abc123456'
# 检查字符串是否由数字构成
print(str2.isdigit())  # False

# 检查字符串是否以字母构成
print(str2.isalpha())  # False

# 检查字符串是否以数字和字母构成
print(str2.isalnum())  # True


str3 = '  jackfrued@126.com '
print(str3)

# 获得字符串修剪左右两侧空格之后的拷贝
print(str3.strip())
```

我们之前讲过，可以用下面的方式来格式化输出字符串：

```python
a, b = 5, 10
print('%d * %d = %d' % (a, b, a * b))
```

当然，我们也可以用字符串提供的方法来完成字符串的格式：

```python
a, b = 5, 10
print('{0} * {1} = {2}'.format(a, b, a * b))
```

Python 3.6以后，格式化字符串还有更为简洁的书写方式，就是在字符串前加上字母f，我们可以使用下面的语法糖来简化上面的代码。

```python
a, b = 5, 10
print(f'{a} * {b} = {a * b}')
```

## 列表

列表（list），与字符串类似，也是一种结构化的、非标量类型，它是值的有序序列，每个值都可以通过索引进行标识，定义列表可以将列表的元素放在`[]`中，多个元素用`,`进行分隔，可以使用`for`循环对列表元素进行遍历，也可以使用`[]`或`[:]`运算符取出列表中的一个或多个元素

下面的代码演示了如何定义列表、如何遍历列表以及列表的下标运算。

```python
list1 = [1, 3, 5, 7, 100]
print(list1) # [1, 3, 5, 7, 100]

# 乘号表示列表元素的重复
list2 = ['hello'] * 3
print(list2) # ['hello', 'hello', 'hello']

# 计算列表长度(元素个数)
print(len(list1)) # 5

# 下标(索引)运算
print(list1[0]) # 1
print(list1[4]) # 100

# print(list1[5])  # IndexError: list index out of range
print(list1[-1]) # 100
print(list1[-3]) # 5

list1[2] = 300
print(list1) # [1, 3, 300, 7, 100]

# 通过循环用下标遍历列表元素
for index in range(len(list1)):
    print(list1[index])

# 通过for循环遍历列表元素
for elem in list1:
    print(elem)

# 通过enumerate函数处理列表之后再遍历可以同时获得元素索引和值
for index, elem in enumerate(list1):
    print(index, elem)
```

下面的代码演示了如何向列表中添加元素以及如何从列表中移除元素。

```python
list1 = [1, 3, 5, 7, 100]

# 添加元素
list1.append(200)
list1.insert(1, 400)

# 合并两个列表
# list1.extend([1000, 2000])
list1 += [1000, 2000]
print(list1) # [1, 400, 3, 5, 7, 100, 200, 1000, 2000]
print(len(list1)) # 9

# 先通过成员运算判断元素是否在列表中，如果存在就删除该元素
if 3 in list1:
	list1.remove(3)
if 1234 in list1:
    list1.remove(1234)
print(list1) # [1, 400, 5, 7, 100, 200, 1000, 2000]

# 从指定的位置删除元素
list1.pop(0)
list1.pop(len(list1) - 1)
print(list1) # [400, 5, 7, 100, 200, 1000]

# 清空列表元素
list1.clear()
print(list1) # []
```

和字符串一样，列表也可以做切片操作，通过切片操作我们可以实现对列表的复制或者将列表中的一部分取出来创建出新的列表，代码如下所示。

```python
fruits = ['grape', 'apple', 'strawberry', 'waxberry']
fruits += ['pitaya', 'pear', 'mango']

# 列表切片
fruits2 = fruits[1:4]
print(fruits2) # apple strawberry waxberry

# 可以通过完整切片操作来复制列表
fruits3 = fruits[:]
print(fruits3) # ['grape', 'apple', 'strawberry', 'waxberry', 'pitaya', 'pear', 'mango']
fruits4 = fruits[-3:-1]
print(fruits4) # ['pitaya', 'pear']

# 可以通过反向切片操作来获得倒转后的列表的拷贝
fruits5 = fruits[::-1]
print(fruits5) # ['mango', 'pear', 'pitaya', 'waxberry', 'strawberry', 'apple', 'grape']
```

下面的代码实现了对列表的排序操作。

```python
list1 = ['orange', 'apple', 'zoo', 'internationalization', 'blueberry']

list2 = sorted(list1)
# sorted函数返回列表排序后的拷贝不会修改传入的列表
# 函数的设计就应该像sorted函数一样尽可能不产生副作用

list3 = sorted(list1, reverse=True)
# 通过key关键字参数指定根据字符串长度进行排序而不是默认的字母表顺序

list4 = sorted(list1, key=len)

print(list1)
print(list2)
print(list3)
print(list4)

# 给列表对象发出排序消息直接在列表对象上进行排序
list1.sort(reverse=True)
print(list1)
```

###### [使用生成式和生成器创建列表](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/07.%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%92%8C%E5%B8%B8%E7%94%A8%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md#%E7%94%9F%E6%88%90%E5%BC%8F%E5%92%8C%E7%94%9F%E6%88%90%E5%99%A8)

## [元组](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/07.%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%92%8C%E5%B8%B8%E7%94%A8%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md#%E4%BD%BF%E7%94%A8%E5%85%83%E7%BB%84)

## [字典](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/07.%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%92%8C%E5%B8%B8%E7%94%A8%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md#%E4%BD%BF%E7%94%A8%E5%AD%97%E5%85%B8)

## [集合](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/07.%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%92%8C%E5%B8%B8%E7%94%A8%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md#%E4%BD%BF%E7%94%A8%E9%9B%86%E5%90%88)



## References
- [Python-100-Days](https://github.com/jackfrued/Python-100-Days)

------------
