---
layout: post
title: "Python Learning #07 - File Operations"
subtitle: '文件操作'
author: "Mike Lyou"
header-style: text
tags:
  - Python
  - 学习笔记
---

Ref:

- [Python-100-Days](https://github.com/jackfrued/Python-100-Days/blob/master/Day01-15/11.文件和异常.md#文件和异常)
- [用Python读写文件，看这篇就够](https://juejin.im/post/5c720ff3f265da2d8e70ebef#heading-18)

Python 进阶的第一篇，决定学习文件操作，这应该和实际应用更近一些。

现在只考虑对文本文件的操作。

###### 读取文本文件
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

除了使用文件对象的`read`方法读取文件之外，还可以使用`for-in`循环逐行读取或者用`readlines`方法将文件按行读取到一个列表容器中，代码如下所示。

```python
# 此程序报错
import time


def main():
    # 一次性读取整个文件内容
    with open('致橡树.txt', 'r', encoding='utf-8') as f:
        print(f.read())

    # 通过for-in循环逐行读取
    with open('致橡树.txt', mode='r') as f:
        for line in f:
            print(line, end='')
            time.sleep(0.5)
    print()

    # 读取文件按行读取到列表中
    with open('致橡树.txt') as f:
        lines = f.readlines()
    print(lines)


if __name__ == '__main__':
    main()
```




------------
**Friendly reminder:** This series are my own study notes of **[Python-100-Days](https://github.com/jackfrued/Python-100-Days)**. I do not own copyright of some of the content. Nor is this a good tutorial of Python. I really appreciate it if you notice any mistakes or errors and tell me. Sorry that things copied from [Python-100-Days](https://github.com/jackfrued/Python-100-Days) will not be noted due to huge workload. **The whole series are not allowed to be reproduced**. View **[python-learning-readme](https://mikelyou.com/2020/01/02/python-learning-00-readme/)**.
