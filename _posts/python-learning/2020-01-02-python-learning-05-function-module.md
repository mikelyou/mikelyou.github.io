---
layout: post
title: "Python Learning #05 - Founction and Module"
subtitle: '函数和模块'
date: 2020-01-02 17:00:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
hidden: true
tags:
  - Python
  - Notes
---

<!-- more -->

## 函数

#### 定义函数

使用`def`关键字来定义函数，通过`return`关键字来返回一个值，举个栗子：

```python
def fac(num):   # 阶乘，实际上Python的math模块中有factorial函数，这里仅做演示
    result = 1
    for n in range(1, num + 1):
        result *= n
    return result
```

- Python 函数与其他语言的区别在于，**在Python中，函数的参数可以有默认值，也支持使用可变参数**，~~所以Python并不需要像其他语言一样支持函数的重载，因为我们在定义一个函数的时候可以让它有多种不同的使用方式（听不懂）~~
- 如果在调用函数的时候，没有传入对应参数的值，将使用该参数的默认值（如果有的话）

## 模块

由于Python没有函数重载的概念，那么后面的定义会覆盖之前的定义，也就意味着两个函数同名函数实际上只有一个是存在的。

```python
def foo():
    print('hello, world!')

def foo():
    print('goodbye, world!')

# 下面的代码会输出什么呢？
foo()   # goodbye, world!
```

## 使用模块管理函数

不是hin懂，以后再看。前往 [课件](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/06.函数和模块的使用.md#用模块管理函数).

## 新的代码书写方式

有了函数的概念，我们今后将以下面的格式书写代码。
```python
def main():
    # Todo: Add your code here
    pass


if __name__ == '__main__':
    main()
```

## References
- [Python-100-Days](https://github.com/jackfrued/Python-100-Days)

------------
