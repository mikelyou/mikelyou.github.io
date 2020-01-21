---
layout: post
title: "Python Learning #07 - File Operations"
subtitle: '文件操作'
date: 2020-01-04 19:30:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
tags:
  - Python
  - Notes
---

Python 进阶的第一篇，决定学习文件操作，这应该和实际应用更近一些。

<!-- more -->

## 目录：
{:.no_toc}

*  
{:toc}

## 读写文本文件
现在只考虑对文本文件的操作。

#### 读取文本文件

###### 格式规范

最简单直接的写法为
```python
def main():
    f = open('致橡树.txt', 'r', encoding='utf-8')
    print(f.read())
    f.close()


if __name__ == '__main__':
    main()
```

但如果在文件不存在或无法打开，上述代码会报错。所以有以下改进版。
```python
def main():
    try:       
        with open('致橡树.txt', 'r', encoding='utf-8') as f:   
            print(f.read())
    except FileNotFoundError:
        print('无法打开指定的文件!')
    except LookupError:
        print('指定了未知的编码!')
    except UnicodeDecodeError:
        print('读取文件时解码错误!')


if __name__ == '__main__':
    main()
```
- 在`try`代码块的后面可以跟上一个或多个`except`来捕获可能出现的异常状况

- 通过`with`关键字指定文件对象的上下文环境并在离开上下文环境时自动释放文件资源

通常而言，读取文件有以下几种方式：

- 一次性读取所有内容，使用 `read()` 或 `readlines()`；
- 按字节读取，使用 `read(size)`；
- 按行读取，使用 `readline()`；


###### 读取所有内容
读取所有内容可以使用 `read()` 或 `readlines()`。在上面的例子已经使用了 `read()`。下面介绍`readlines()`。

`readlines()` 方法会把文件读入一个字符串列表，在列表中每个字符串就是一行。

假设有一个文件 `data.txt`，它的文件内容如下（数字之间的间隔符是`'\t'`）：
```
10  1   9   9
6   3   2   8
20  10  3   23
1   4   1   10
10  8   6   3
10  2   1   6
```

我们使用 `readlines()` 将文件读入一个字符串列表：
```python
with open('data.txt', 'r') as f:
    lines = f.readlines()   # 此处 lines 即为文档内容
    line_num = len(lines)
    print(lines)
    print(line_num)
```
执行结果：
```
['10\t1\t9\t9\n', '6\t3\t2\t8\n', '20\t10\t3\t23\n', '1\t4\t1\t10\n', '10\t8\t6\t3\n', '10\t2\t1\t6']
6
```

可以看到，列表中的每个元素都是一个字符串，刚好对应文件中的每一行。

###### 按字节读取
如果文件很大，比如有 100G，一次性读取所有内容会变得不太现实。这时，我们构造一个固定长度的缓冲区，来不断读取文件内容。

看看例子：

```python
with open('path/to/file', 'r') as f:
    while True:
        piece = f.read(1024)        # 每次读取 1024 个字节（即 1 KB）的内容
        if not piece:
            break
        print piece
```        
在上面，我们使用 `f.read(1024)` 来每次读取 1024 个字节（1KB） 的文件内容，将其存到 `piece`，再对 `piece` 进行处理。

事实上，我们还可以结合 `yield` 来使用：
```python
def read_in_chunks(file_object, chunk_size=1024):
    # Lazy function (generator) to read a file piece by piece.
    # Default chunk size: 1k.
    while True:
        data = file_object.read(chunk_size)
        if not data:
            break
        yield data

with open('path/to/file', 'r') as f:
    for piece in read_in_chunks(f):
        print piece
```

###### 逐行读取
在某些情况下，我们希望逐行读取文件，这时可以使用 `readline()` 方法。

看看例子：
```python
with open('data.txt', 'r') as f:
    while True:
        line = f.readline()     # 逐行读取
        if not line:
            break
        print(line,end=' ')             # 这里加了 end=' ' 是为了避免 print 自动换行
```
执行结果：
```
10  1   9   9
6   3   2   8
20  10  3   23
1   4   1   10
10  8   6   3
10  2   1   6
```

###### 文件迭代器
在 Python 中，文件对象是可迭代的，这意味着我们可以直接在 `for-in` 循环中使用它们，而且是逐行迭代的，也就是说，效果和 `readline()` 是一样的，而且更简洁。

看看例子：
```python
with open('data.txt', 'r') as f:
    for line in f:
        print(line,end=' ')
```
在上面的代码中，`f` 就是一个文件迭代器，因此我们可以直接使用 `for line in f`，它是逐行迭代的。



#### 写入文本文件

写文件使用 `write` 方法，如下：

```python
with open('E:/Program Datas/PycharmProjects/p1302/data2.txt', 'w', 'w') as f:    # 文件需和python程序在同个盘符下，盘符'E:/'可省略
    f.write('one\n')
    f.write('two')
```    

- 如果上述文件已存在，则会清空原内容并覆盖掉；
- 如果上述路径是正确的（比如存在 上述路径），但是文件不存在（`data2.txt` 不存在），则会新建一个文件，并写入上述内容；
- 如果上述路径是不正确的（比如将路径写成 `/PROGRAMDATAS/...` ），这时会抛出 `IOError`；

如果我们想往已存在的文件追加内容，可以使用 `'a'` 模式，如下：

```python
with open('E:/Program Datas/PycharmProjects/p1302/data2.txt', 'a') as f:
    f.write('three\n')
    f.write('four')
```

## References

- [Python-100-Days-文件和异常](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/11.文件和异常.md#文件和异常)
- [用Python读写文件，看这篇就够](https://juejin.im/post/5c720ff3f265da2d8e70ebef#heading-18)
- [ethan-funny/explore-python](https://github.com/ethan-funny/explore-python)

------------------


