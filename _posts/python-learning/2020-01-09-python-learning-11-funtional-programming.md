---
layout: post
title: "Python Learning #11 - Functional Programming"
subtitle: '函数式编程'
date: 2020-01-09 16:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
#header-img: "img/post-bg-2015.jpg"
tags:
  - Python
  - Notes

#excerpt: List, tuple, string, dict and set.
---

<!-- more -->

## Catalog：
{:.no_toc}

*  
{:toc}

**函数式编程（functional programming** 是一种编程范式（Programming paradigm），或者说编程模式，比如我们常见的过程式编程是一种编程范式，面向对象编程又是另一种编程范式。

函数式编程的一大特性就是：可以把函数当成变量来使用，比如将函数赋值给其他变量、把函数作为参数传递给其他函数、函数的返回值也可以是一个函数等等。

Python 不是纯函数式编程语言，但它对函数式编程提供了一些支持。本章主要介绍 Python 中的函数式编程，主要包括以下几个方面：

## 高阶函数

在函数式编程中，我们可以将函数当作变量一样自由使用。一个函数接收另一个函数作为参数，这种函数称之为高阶函数（Higher-order Functions）。

## 匿名函数

当我们需要一些临时性的、小巧的函数，匿名函数可以满足我们的需求。

Python 提供了一个关键字 lambda，让我们可以创建一个匿名函数，也就是没有名称的函数。它的形式如下：
```
lambda 参数: 表达式
```

匿名函数的应用形式如下：
```python
>>> (lambda x: 2 * x)(8)
16
```

匿名函数在高阶函数中可以使表达更为简洁。举个栗子：
```python
arr = func(lambda x: x + 1, [1, 2, 3, 4])
```

匿名函数本质上是一个函数，没有函数名称，因此使用匿名函数不用担心函数名冲突


## map/reduce/filter

map/reduce/filter 是 Python 中较为常用的内建高阶函数，它们为函数式编程提供了不少便利。

#### map

`map` 函数的使用形式如下：

```
map(function, sequence)
```

**解释**：对 sequence 中的 item 依次执行 function(item)，并将结果组成一个 List 返回（很像MMA中的`Map[]`），也就是：

```
[function(item1), function(item2), function(item3), ...]
```

看一些简单的例子。

```python
>>> def square(x):
...     return x * x

>>> map(square, [1, 2, 3, 4])
[1, 4, 9, 16]

>>> map(lambda x: x * x, [1, 2, 3, 4])   # 使用 lambda
[1, 4, 9, 16]

>>> map(str, [1, 2, 3, 4])
['1', '2', '3', '4']

>>> map(int, ['1', '2', '3', '4'])
[1, 2, 3, 4]
```

再看一个例子：

```python
def double(x):
    return 2 * x

def triple(x):
    return 3 *x

def square(x):
    return x * x

funcs = [double, triple, square]  # 列表元素是函数对象

# 相当于 [double(4), triple(4), square(4)]
value = list(map(lambda f: f(4), funcs))

print value

# output
[8, 12, 16]
```

上面的代码中，我们加了 list 转换，是为了兼容 Python3，在 Python2 中 map 直接返回列表，Python3 中返回迭代器。

#### reduce

`reduce` 函数的使用形式如下：

```
reduce(function, sequence[, initial])
```

**解释**：先将 sequence 的前两个 item 传给 function，即 function(item1, item2)，函数的返回值和 sequence 的下一个 item 再传给 function，即 function(function(item1, item2), item3)，如此迭代，直到 sequence 没有元素，如果有 initial，则作为初始值调用。（这让我想到秦九韶算法）

也就是说：

```
reduece(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```

看一些例子，就能很快理解了。

```python
>>> reduce(lambda x, y: x * y, [1, 2, 3, 4])  # 相当于 ((1 * 2) * 3) * 4
24
>>> reduce(lambda x, y: x * y, [1, 2, 3, 4], 5) # ((((5 * 1) * 2) * 3)) * 4
120
>>> reduce(lambda x, y: x / y, [2, 3, 4], 72)  #  (((72 / 2) / 3)) / 4
3
>>> reduce(lambda x, y: x + y, [1, 2, 3, 4], 5)  # ((((5 + 1) + 2) + 3)) + 4
15
>>> reduce(lambda x, y: x - y, [8, 5, 1], 20)  # ((20 - 8) - 5) - 1
6
>>> f = lambda a, b: a if (a > b) else b   # 两两比较，取最大值
>>> reduce(f, [5, 8, 1, 10])
10
```

#### filter

`filter` 函数用于过滤元素，它的使用形式如下：

```
filter(function, sequnce)
```

**解释**：将 function 依次作用于 sequnce 的每个 item，即 function(item)，将返回值为 True 的 item 组成一个 List/String/Tuple (取决于 sequnce 的类型，python3 统一返回迭代器) 返回。

看一些例子。

```python
>>> even_num = list(filter(lambda x: x % 2 == 0, [1, 2, 3, 4, 5, 6]))
>>> even_num
[2, 4, 6]
>>> odd_num = list(filter(lambda x: x % 2, [1, 2, 3, 4, 5, 6]))
>>> odd_num
[1, 3, 5]
>>> filter(lambda x: x < 'g', 'hijack')
'ac'        # python2
>>> filter(lambda x: x < 'g', 'hijack')
<filter object at 0x1034b4080>   # python3
```

## 闭包

暂时跳过。

## 装饰器

暂时跳过。

## partial 函数

Python 提供了一个 functools 的模块，该模块为高阶函数提供支持，partial 就是其中的一个函数，该函数的形式如下：

```python
functools.partial(func[,*args][, **kwargs])
```

这里先举个例子，看看它是怎么用的。

假设有如下函数：

```python
def multiply(x, y):
    return x * y
```

现在，我们想返回某个数的双倍，即：

```
>>> multiply(3, y=2)
6
>>> multiply(4, y=2)
8
>>> multiply(5, y=2)
10
```

上面的调用有点繁琐，每次都要传入 `y=2`，我们想到可以定义一个新的函数，把 `y=2` 作为默认值，即：

```python
def double(x, y=2):
    return multiply(x, y)
```

现在，我们可以这样调用了：

```
>>> double(3)
6
>>> double(4)
8
>>> double(5)
10
```

事实上，我们可以不用自己定义 `double`，利用 `partial`，我们可以这样：

```python
from functools import partial

double = partial(multiply, y=2)
```

`partial` 接收函数 `multiply` 作为参数，固定 `multiply` 的参数 `y=2`，并返回一个新的函数给 `double`，这跟我们自己定义 `double` 函数的效果是一样的。

所以，简单而言，`partial` 函数的功能就是：把一个函数的某些参数给固定住，返回一个新的函数。

需要注意的是，我们上面是固定了 `multiply` 的关键字参数 `y=2`，如果直接使用：

```python
double = partial(multiply, 2)
```

则 `2` 是赋给了 `multiply` 最左边的参数 `x`，不信？我们可以验证一下：

```python
from functools import partial

def subtraction(x, y):
    return x - y

f = partial(subtraction, 4)  # 4 赋给了 x
>>> f(10)   # 4 - 10
-6
```

#### 小结

- partial 的功能：固定函数参数，返回一个新的函数。
- 当函数参数太多，需要固定某些参数时，可以使用 `functools.partial` 创建一个新的函数。





------------
