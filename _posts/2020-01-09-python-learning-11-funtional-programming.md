---
layout: post
title: "Python Learning #11 - Functional Programming"
subtitle: '函数式编程'
date: 2020-01-09 16:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/post-bg-2015.jpg"
tags:
  - Python
  - Notes

#excerpt: List, tuple, string, dict and set.
---

<!-- more -->

>Note: From this section(\#10), the reference is no longer [Python-100-Days](https://github.com/jackfrued/Python-100-Days), but **[ethan-funny/explore-python](https://github.com/ethan-funny/explore-python)**. This two series may overlap. Depending on the necessity, these two series may be merged into one, and old posts may be deleted.


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



## 闭包



## 装饰器



## partial 函数



------------
>Statement:This python learning series are posted only for personal studies and communication. The whole series are not allowed to be reproduced unles otherwise indicated. I do not own copyright of some of the content. If any post accidentally infringes your copyright, it will be removed shortly after being informed. View **[python-learning-readme](https://mikelyou.com/2020/01/02/python-learning-00-readme/)** for more information.

>Note: From this section(\#10), the reference is no longer [Python-100-Days](https://github.com/jackfrued/Python-100-Days), but **[ethan-funny/explore-python](https://github.com/ethan-funny/explore-python)**. This two series may overlap. Depending on the necessity, these two series may be merged into one, and old posts may be deleted.
