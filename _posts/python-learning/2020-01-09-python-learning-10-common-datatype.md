---
layout: post
title: "Python Learning #10 - Common Datatype"
subtitle: '常用数据类型'
date: 2020-01-09 11:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
#header-img: "img/post-bg-2015.jpg"
tags:
  - Python
  - Notes

excerpt: List, tuple, string, dict and set.
comments: true
---

<!-- more -->

>Note: From this section(\#10), the main reference is no longer [Python-100-Days](https://github.com/jackfrued/Python-100-Days), but **[ethan-funny/explore-python](https://github.com/ethan-funny/explore-python)**. This two series may overlap. Depending on the necessity, these two series may be merged into one, and old posts may be deleted.


## Catalog：
{:.no_toc}

*  
{:toc}



## 常用数据类型

本节将介绍 Python 中常用的几种数据类型：

- 列表 List
- 元组 Tuple
- 字符串 String
- 字典 Dict
- 集合 Set

其中，
- 列表、元组和字符串都属于 **序列** 类型。  
序列（Sequence）是 Python 中最基本的数据结构，其特点是根据索引（index）来获取序列中的元素。序列类型的变量可以进行一些通用的操作。

- 字典属于 **映射** 类型，每个元素由键（key）和值（value）构成；

- 集合是一种特殊的类型，它所包含的元素是不重复的。


## 通用的序列操作

#### 索引

序列中的元素可以通过索引获取，索引从 0 开始，-1 则代表序列的最后一个元素，-2 代表倒数第二个元素，以此类推。如下：

```python
>>> nums = [1, 2, 3, 4, 5]   # 列表
>>> nums[0]
1
>>> nums[1]
2
>>> nums[-1]                 # 索引 -1 表示最后一个元素
5
>>> s = 'abcdef'             # 字符串
>>> s[0]
'a'
>>> s[1]
'b'
>>>
>>> a = (1, 2, 3)            # 元组
>>> a[0]
1
>>> a[1]
2
```

#### 分片

**索引** 用于获取序列中的单个元素，而 **分片** 则用于获取序列的部分元素。分片操作需要提供两个索引作为边界，中间用冒号相隔。

这里需要 **特别注意** 的是，分片有两个索引，**第 1 个索引的元素是包含在内的，而第 2 个元素的索引则不包含在内**。比如：
```python
>>> numbers = [1, 2, 3, 4, 5, 6]
>>> numbers[0:2]                   # 列表分片
[1, 2]
>>> numbers[2:5]
[3, 4, 5]
>>> s = 'hello, world'             # 字符串分片
>>> s[0:5]
'hello'
>>> a = (2, 4, 6, 8, 10)           # 元组分片
>>> a[2:4]
(6, 8)
```
###### 访问最后几个元素

假设需要访问序列的最后 3 个元素，最好的方法是这样：
```python
>>> numbers = [1, 2, 3, 4, 5, 6, 7, 8]
>>> numbers[-3:]
[6, 7, 8]
>>> numbers[5:]
[6, 7, 8]
```
也就是说，如果希望分片包含最后一个元素，可将第 2 个索引置为空。  

如果要复制整个序列，可以将两个索引都置为空：
```python
>>> numbers = [1, 2, 3, 4, 5, 6, 7, 8]
>>> nums = numbers[:]
>>> nums
[1, 2, 3, 4, 5, 6, 7, 8]
```

###### 使用步长

使用分片的时候，步长默认是 1，即逐个访问，我们也可以自定义步长，比如：
```python
>>> numbers = [1, 2, 3, 4, 5, 6, 7, 8]
>>> numbers[0:4]
[1, 2, 3, 4]
>>> numbers[0:4:1]    # 步长为 1，不写也可以，默认为 1
[1, 2, 3, 4]
>>> numbers[0:4:2]    # 步长为 2，取出 numbers[0], numbers[2]
[1, 3]
>>> numbers[::3]      # 等价于 numbers[0:8:3]，取出索引为 0, 3, 6 的元素
[1, 4, 7]
```
另外，步长也可以是负数，表示从右到左取元素：
```python
>>> numbers = [1, 2, 3, 4, 5, 6, 7, 8]
>>> numbers[0:4:-1]
[]
>>> numbers[4:0:-1]       # 取出索引为 4, 3, 2, 1 的元素
[5, 4, 3, 2]
>>> numbers[4:0:-2]       # 取出索引为 4, 2 的元素
[5, 3]
>>> numbers[::-1]         # 从右到左取出所有元素
[8, 7, 6, 5, 4, 3, 2, 1]
>>> numbers[::-2]         # 取出索引为 7, 5, 3, 1 的元素
[8, 6, 4, 2]
>>> numbers[6::-2]        # 取出索引为 6, 4, 2, 0 的元素
[7, 5, 3, 1]
>>> numbers[:6:-2]        # 取出索引为 7 的元素
[8]
```

#### 加
序列可以进行「加法」操作，如下：
```python
>>> [1, 2, 3] + [4, 5, 6]     # 「加法」效果其实就是连接在一起
[1, 2, 3, 4, 5, 6]
>>> (1, 2, 3) + (4, 5, 6)
(1, 2, 3, 4, 5, 6)
>>> 'hello, ' + 'world!'
'hello, world!'
>>> [1, 2, 3] + 'abc'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate list (not "str") to list
这里需要注意的是：两种相同类型的序列才能「加法」操作。
```

#### 乘
序列可以进行「乘法」操作，比如：
```python
>>> 'abc' * 3
'abcabcabc'
>>> [0] * 3
[0, 0, 0]
>>> [1, 2, 3] * 3
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

#### in
为了检查一个值是否在序列中，可以使用 in 运算符，比如：
```python
>>> 'he' in 'hello'
True
>>> 'hl' in 'hello'
False
>>> 10 in [6, 8, 10]
True
```

## 列表


字符串和元组是不可变的，而列表是可变（mutable）的，可以对它进行随意修改。我们还可以将字符串和元组转换成一个列表，只需使用 `list` 函数，比如：

```python
>>> s = 'hello'
>>> list(s)
['h', 'e', 'l', 'l', 'o']
>>> a = (1, 2, 3)
>>> list(a)
[1, 2, 3]
```

本文主要介绍常用的列表方法。

#### index

index 方法用于从列表中找出某个元素的位置，如果有多个相同的元素，则返回第一个元素的位置。

看看例子：

```python
>>> numbers = [1, 2, 3, 4, 5, 5, 7, 8]
>>> numbers.index(5)        # 列表有两个 5，返回第一个元素的位置
4
>>> numbers.index(2)
1
>>> words = ['hello', 'world', 'you', 'me', 'he']
>>> words.index('me')
3
>>> words.index('her')       # 如果没找到元素，则会抛出异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: 'her' is not in list
```

#### count

count 方法用于统计某个元素在列表中出现的次数。

看看例子：

```python
>>> numbers = [1, 2, 3, 4, 5, 5, 6, 7]
>>> numbers.count(2)   # 出现一次
1
>>> numbers.count(5)   # 出现了两次
2
>>> numbers.count(9)   # 没有该元素，返回 0
0
```

#### append

append 方法用于在列表末尾增加新的元素。

看看例子：

```python
>>> numbers = [1, 2, 3, 4, 5, 5, 6, 7]
>>> numbers.append(8)         # 增加 8 这个元素
>>> numbers
[1, 2, 3, 4, 5, 5, 6, 7, 8]
>>> numbers.append([9, 10])   # 增加 [9, 10] 这个元素
>>> numbers
[1, 2, 3, 4, 5, 5, 6, 7, 8, [9, 10]]
```

#### extend

extend 方法将一个新列表的元素添加到原列表中。

看看例子：

```python
>>> a = [1, 2, 3]
>>> b = [4, 5, 6]
>>> a.extend(b)
>>> a
[1, 2, 3, 4, 5, 6]
>>>
>>> a.extend(3)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'int' object is not iterable
>>> a.extend([3])
>>> a
[1, 2, 3, 4, 5, 6, 3]
```

注意到，虽然 append 和 extend 可接收一个列表作为参数，但是 append 方法是将其作为一个元素添加到列表中，而 extend 则是将新列表的元素逐个添加到原列表中。

#### insert

insert 方法用于将某个元素添加到某个位置。括号内第一个值为索引，第二个为要插入的元素。

看看例子：

```python
>>> numbers = [1, 2, 3, 4, 5, 6]
>>> numbers.insert(3, 9)
>>> numbers
[1, 2, 3, 9, 4, 5, 6]
```

#### pop

pop 方法用于移除列表中的一个元素（默认是最后一个），并且返回该元素的值。如果括号中有值，则为索引。

看看例子：

```python
>>> numbers = [1, 2, 3, 4, 5, 6]
>>> numbers.pop()
6
>>> numbers
[1, 2, 3, 4, 5]
>>> numbers.pop(3)
4
>>> numbers
[1, 2, 3, 5]
```

#### remove

remove 方法用于移除列表中的某个匹配元素，如果有多个匹配，则移除第一个。

看看例子：

```python
>>> numbers = [1, 2, 3, 5, 6, 7, 5, 8]
>>> numbers.remove(5)          # 有两个 5，移除第 1 个
>>> numbers
[1, 2, 3, 6, 7, 5, 8]
>>> numbers.remove(9)          # 没有匹配的元素，抛出异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list
```

#### reverse

reverse 方法用于将列表中的元素进行反转。

看看例子：

```python
>>> numbers = [1, 2, 3, 5, 6, 7, 5, 8]
>>> numbers.reverse()
>>> numbers
[8, 5, 7, 6, 5, 3, 2, 1]
```

#### sort

sort 方法用于对列表进行排序，**注意** ：该方法会改变原来的列表，而不是返回新的排序列表，另外，sort 方法的返回值是空。

看看例子：

```python
>>> a = [4, 3, 6, 8, 9, 1]
>>> b = a.sort()
>>> b == None         # 返回值为空
True
>>> a
[1, 3, 4, 6, 8, 9]    # 原列表已经发生改变
```

如果我们不想改变原列表，而是希望返回一个排序后的列表，可以使用 sorted 函数，如下：

```python
>>> a = [4, 3, 6, 8, 9, 1]
>>> b = sorted(a)          # 返回一个排序后的列表
>>> a
[4, 3, 6, 8, 9, 1]         # 原列表没有改变
>>> b
[1, 3, 4, 6, 8, 9]         # 这是对原列表排序后的列表
```

注意到，不管是 sort 方法还是 sorted 函数，**默认排序都是升序排序**。如果你想要降序排序，就需要指定排序参数了。比如，对 sort 方法，可以添加一个 reverse 关键字参数，如下：

```python
>>> a = [4, 3, 6, 8, 9, 1]
>>> a.sort(reverse=True)    # 反向排序
>>> a
[9, 8, 6, 4, 3, 1]
```

该参数对 sorted 函数同样适用：

```python
>>> a = [4, 3, 6, 8, 9, 1]
>>> sorted(a, reverse=True)
[9, 8, 6, 4, 3, 1]
```

除了 reverse 关键字参数，还可以指定 key 关键字参数，它为每个元素创建一个键，然后所有元素按照这个键来排序，比如我们想根据元素的长度来排序：

```python
>>> s = ['ccc', 'a', 'bb', 'dddd']
>>> s.sort(key=len)          # 使用 len 作为键函数，根据元素长度排序
>>> s
['a', 'bb', 'ccc', 'dddd']
```

另外，我们还可以使用 sorted 进行多列（属性）排序。

看看例子：

```python
>>> students = [
        ('john', 'B', 15),
        ('jane', 'A', 12),
        ('dave', 'B', 10),
        ('ethan', 'C', 20),
        ('peter', 'B', 20),
        ('mike', 'C', 16)
    ]
>>>
# 对第 3 列排序 (从小到大)
>>> sorted(students, key=lambda student: student[2])
[('dave', 'B', 10),
 ('jane', 'A', 12),
 ('john', 'B', 15),
 ('mike', 'C', 16),
 ('ethan', 'C', 20),
 ('peter', 'B', 20)]

# 对第 2 列排序（从小到大），再对第 3 列从大到小排序
>>> sorted(students, key=lambda student: (student[1], -student[2]))
[('jane', 'A', 12),
 ('peter', 'B', 20),
 ('john', 'B', 15),
 ('dave', 'B', 10),
 ('ethan', 'C', 20),
 ('mike', 'C', 16)]
```

如果你想了解更多关于排序的知识，可以参考[此文](https://wiki.python.org/moin/HowTo/Sorting)。

## 元组

在 Python 中，**元组是一种不可变序列**，它使用圆括号来表示：

```python
>>> a = (1, 2, 3)    # a 是一个元组
>>> a
(1, 2, 3)
>>> a[0] = 6         # 元组是不可变的，不能对它进行赋值操作
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

#### 空元组

创建一个空元组可以用没有包含内容的圆括号来表示：

```python
>>> a = ()
>>> a
()
```

#### 一个值的元组

创建一个值的元组需要在值后面再加一个逗号，这个比较特殊，需要牢牢记住：

```python
>>> a = (12,)   # 在值后面再加一个逗号
>>> a
(12,)
>>> type(a)
<type 'tuple'>
>>>
>>> b = (12)    # 只是使用括号括起来，而没有加逗号，不是元组，本质上是 b = 12
>>> b
12
>>> type(b)
<type 'int'>
```

#### 元组操作

元组也是一种序列，因此也可以对它进行索引、分片等。由于它是不可变的，因此就没有类似列表的 append, extend, sort 等方法。


## 字符串

字符串也是一种序列，因此，通用的序列操作，比如索引，分片，加法，乘法等对它同样适用。比如：

```python
>>> s = 'hello, '
>>> s[0]            # 索引
'h'
>>> s[1:3]          # 分片
'el'
>>> s + 'world'     # 加法
'hello, world'
>>> s * 2           # 乘法
'hello, hello, '
```

但需要注意的是，字符串和元组一样，也是 **不可变** 的，所以你不能对它进行赋值等操作：

```python
>>> s = 'hello'
>>> s[1] = 'ab'    # 不能对它进行赋值
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```

除了通用的序列操作，字符串还有自己的方法，比如 join, lower, upper 等。字符串的方法特别多，这里只介绍一些常用的方法。

#### find

find 方法用于在一个字符串中查找子串，它返回子串所在位置的最左端索引，如果没有找到，则返回 -1。

看看例子：

```python
>>> motto = "to be or not to be, that is a question"
>>> motto.find('be')            # 返回 'b' 所在的位置，即 3
3
>>> motto.find('be', 4)         # 指定从起始位置开始找，找到的是第 2 个 'be'
16
>>> motto.find('be', 4, 7)      # 指定起始位置和终点位置，没有找到，返回 -1
-1
```

#### split

split 方法用于将字符串分割成序列。

看看例子：

```python
>>> '/user/bin/ssh'.split('/')         # 使用 '/' 作为分隔符
['', 'user', 'bin', 'ssh']
>>> '1+2+3+4+5'.split('+')             # 使用 '+' 作为分隔符
['1', '2', '3', '4', '5']
>>> 'that    is a   question'.split()  # 没有提供分割符，默认使用所有空格作为分隔符
['that', 'is', 'a', 'question']
```

需要注意的是，如果不提供分隔符，则默认会使用所有空格作为分隔符（空格、制表符、换行等）。

#### join

join 方法可以说是 split 的逆方法，它用于将序列中的元素连接起来。

看看例子：

```python
>>> '/'.join(['', 'user', 'bin', 'ssh'])
'/user/bin/ssh'
>>>
>>> '+'.join(['1', '2', '3', '4', '5'])
'1+2+3+4+5'
>>> ' '.join(['that', 'is', 'a', 'question'])
'that is a question'
>>> ''.join(['h', 'e', 'll', 'o'])
'hello'
>>> '+'.join([1, 2, 3, 4, 5])          # 不能是数字
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: sequence item 0: expected string, int found
```

#### strip

strip 方法用于移除字符串左右两侧的空格，但不包括内部，当然也可以指定需要移除的字符串。

看看例子：

```python
>>> '  hello world!   '.strip()                # 移除左右两侧空格
'hello world!'
>>> '%%%   hello world!!!  ####'.strip('%#')   # 移除左右两侧的 '%' 或 '#'
'   hello world!!!  '
>>> '%%%   hello world!!!  ####'.strip('%# ')  # 移除左右两侧的 '%' 或 '#' 或空格
'hello world!!!'
```

#### replace

replace 方法用于替换字符串中的 **所有** 匹配项。

看看例子：

```python
>>> motto = 'To be or not To be, that is a question'
>>> motto.replace('To', 'to')        # 用 'to' 替换所有的 'To'，返回了一个新的字符串
'to be or not to be, that is a question'
>>> motto                            # 原字符串保持不变
'To be or not To be, that is a question'
```

#### translate

translate 方法和 replace 方法类似，也可以用于替换字符串中的某些部分，但 **translate 方法只处理单个字符**。

translate 方法的使用形式如下：

```python
str.translate(table[, deletechars]);
```

其中，table 是一个包含 256 个字符的转换表，可通过 maketrans 方法转换而来，deletechars 是字符串中要过滤的字符集。

看看例子：

```python
>>> from string import maketrans
>>> table = maketrans('aeiou', '12345')
>>> motto = 'to be or not to be, that is a question'
>>> motto.translate(table)
't4 b2 4r n4t t4 b2, th1t 3s 1 q52st34n'
>>> motto
'to be or not to be, that is a question'
>>> motto.translate(table, 'rqu')        # 移除所有的 'r', 'q', 'u'
't4 b2 4 n4t t4 b2, th1t 3s 1 2st34n'
```

可以看到，maketrans 接收两个参数：两个等长的字符串，表示第一个字符串的每个字符用第二个字符串对应位置的字符替代，在上面的例子中，就是 'a' 用 '1' 替代，'e' 用 '2' 替代，等等，注意，是单个字符的代替，而不是整个字符串的替代。因此，motto 中的 o 都被替换为 4，e 都被替换为 2，等等。

#### lower/upper

lower/upper 用于返回字符串的大写或小写形式。

看看例子：

```python
>>> x = 'PYTHON'
>>> x.lower()
'python'
>>> x
'PYTHON'
>>>
>>> y = 'python'
>>> y.upper()
'PYTHON'
>>> y
'python'
```

小结:

- 字符串是不可变对象，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回。
- translate 针对单个字符进行替换。

## 字典

有点复杂，先跳过。[&rarr;](https://github.com/ethan-funny/explore-python/blob/master/Datatypes/dict.md)

## 集合

集合（set）和字典（dict）类似，它是一组 key 的集合，但不存储 value。集合的特性就是：key 不能重复。

集合具有以下常用操作。

#### 创建集合

set 的创建可以使用 `{}` 也可以使用 set 函数：

```python
>>> s1 = {'a', 'b', 'c', 'a', 'd', 'b'}   # 使用 {}
>>> s1
set(['a', 'c', 'b', 'd'])
>>>
>>> s2 = set('helloworld')                # 使用 set()，接收一个字符串
>>> s2
set(['e', 'd', 'h', 'l', 'o', 'r', 'w'])
>>>
>>> s3 = set(['.mp3', '.mp4', '.rmvb', '.mkv', '.mp3'])   # 使用 set()，接收一个列表
>>> s3
set(['.mp3', '.mkv', '.rmvb', '.mp4'])
```

#### 遍历集合

```python
>>> s = {'a', 'b', 'c', 'a', 'd', 'b'}
>>> for e in s:
... 	print e
...
a
c
b
d
```

#### 添加元素

`add()` 方法可以将元素添加到 set 中，可以重复添加，但没有效果。

```python
>>> s = {'a', 'b', 'c', 'a', 'd', 'b'}
>>> s
set(['a', 'c', 'b', 'd'])
>>> s.add('e')
>>> s
set(['a', 'c', 'b', 'e', 'd'])
>>> s.add('a')
>>> s
set(['a', 'c', 'b', 'e', 'd'])
>>> s.add(4)
>>> s
set(['a', 'c', 'b', 4, 'd', 'e'])
```

#### 删除元素

`remove()` 方法可以删除集合中的元素, 但是删除不存在的元素，会抛出 KeyError，可改用 `discard()`。

看看例子：

```python
>>> s = {'a', 'b', 'c', 'a', 'd', 'b'}
>>> s
set(['a', 'c', 'b', 'd'])
>>> s.remove('a')           # 删除元素 'a'
>>> s
set(['c', 'b', 'd'])
>>> s.remove('e')           # 删除不存在的元素，会抛出 KeyError
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'e'
>>> s.discard('e')          # 删除不存在的元素, 不会抛出 KeyError
```

#### 交集/并集/差集

Python 中的集合也可以看成是数学意义上的无序和无重复元素的集合，因此，我们可以对两个集合作交集、并集等。

看看例子：

```python
>>> s1 = {1, 2, 3, 4, 5, 6}
>>> s2 = {3, 6, 9, 10, 12}
>>> s3 = {2, 3, 4}
>>> s1 & s2            # 交集
set([3, 6])
>>> s1 | s2            # 并集
set([1, 2, 3, 4, 5, 6, 9, 10, 12])
>>> s1 - s2            # 差集
set([1, 2, 4, 5])
>>> s3.issubset(s1)    # s3 是否是 s1 的子集
True
>>> s3.issubset(s2)    # s3 是否是 s2 的子集
False
>>> s1.issuperset(s3)  # s1 是否是 s3 的超集
True
>>> s1.issuperset(s2)  # s1 是否是 s2 的超集
False
```





------------


>Note: From this section(\#10), the reference is no longer [Python-100-Days](https://github.com/jackfrued/Python-100-Days), but **[ethan-funny/explore-python](https://github.com/ethan-funny/explore-python)**. This two series may overlap. Depending on the necessity, these two series may be merged into one, and old posts may be deleted.
