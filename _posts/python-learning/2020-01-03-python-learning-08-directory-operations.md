---
layout: post
title: "Python Learning #08 - Directory Operations"
subtitle: '文件夹操作'
date: 2020-01-04 20:30:00
author: "Mike Lyou"
header-style: text
copyright-statement: python-series
tags:
  - Python
  - Notes
---

> 本文为个人Notes，原文为 [《Python文件操作，看这篇就足够》](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-38)，其翻译原文为 [Working With Files in Python](https://realpython.com/working-with-files-in-python/)。本文不允许转载。

<!-- more -->

（有时间的话写成英文版本，熟悉一下英文术语）

## 目录：
{:.no_toc}


*  
{:toc}

## 前往指定目录

使用`os`包的`chdir`函数能够改变当前工作路径（待验证）

```python
import os


os.getcwd()  #获取当前工作目录

os.chdir('d:\\')  #更改当前工作目录
os.getcwd()
```

## 获取目录列表

假设你当前的工作目录有一个叫 `my_directory` 的子目录，该目录包含如下内容：

```
.
├── file1.py
├── file2.csv
├── file3.txt
├── sub_dir
│   ├── bar.py
│   └── foo.py
├── sub_dir_b
│   └── file4.txt
└── sub_dir_c
    ├── config.py
    └── file5.txt
```

#### 使用现代Python版本获取目录列表
在现代Python版本中，可以使用 `os.scandir()` 和 `pathlib.Path` 来替代旧版本中的 ~~`os.listdir()`~~

`os.scandir()` 调用时返回一个迭代器而不是一个列表。_其(小火的理解)_ （`ScandirIterator`）指向了当前目录中的所有条目。你可以遍历迭代器的内容，并打印文件名。

```python
import os
with os.scandir('my_directory') as entries:
    for entry in entries:
        print(entry.name)
```
运行结果为

```
file1.py
file2.csv
file3.txt
sub_dir
sub_dir_b
sub_dir_c
```

另一个获取目录列表的方法是使用 `pathlib` 模块：[前往原文 &rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-3)

#### 列出目录中所有文件

如果不希望列出目录，而仅列出文件，要使用 `os.path` ：

```python
import os

basepath = 'my_directory'
for entry in os.listdir(basepath):
    # 使用os.path.isfile判断该路径是否是文件类型
    if os.path.isfile(os.path.join(base_path, entry)):
        print(entry)
```

在这里调用 `os.listdir()` 返回指定路径中所有内容的列表，接着使用 `os.path.isfile()` 过滤列表让其只显示文件类型而非目录类型。代码执行结果如下：

```
file1.py
file2.csv
file3.txt
```

一个更简单的方式来列出一个目录中所有的文件是使用 `os.scandir()` 或 `pathlib.Path()` :

```python
import os

basepath = 'my_directory'
with os.scandir(basepath) as entries:
    for entry in entries:
        if entry.is_file():
            print(entry.name)
```

使用 `os.scandir()` 比起 `os.listdir()` 看上去更清楚和更容易理解。对 `ScandirIterator` 的每一项调用 `entry.isfile()` ，如果返回 `True` 则表示这一项是一个文件。上述代码的输出如下：

```
file1.py
file2.csv
file3.txt
```
如何使用 `pathlib.Path()` 列出一个目录中的文件：[前往原文 &rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-3)

#### 列出所有子目录

与上面讨论的相反，如果希望列出子目录，而不列出文件：[前往原文 &rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-5)



## 获取文件属性

Python可以很轻松的获取文件大小和修改时间等文件属性。

`os.scandir()` 和 `pathlib.Path()` 能直接获取到包含文件属性的目录列表。这可能比使用 `os.listdir()` 列出文件然后获取每个文件的文件属性信息更加有效。

下面的例子显示了如何获取 `my_directory` 中文件的最后修改时间。以时间戳的方式输出：

```python
import os

with os.scandir('my_directory') as entries:
    for entry in entries:
        info = entry.stat()
        print(info.st_mtime)

"""
1548163662.3952665
1548163689.1982062
1548163697.9175904
1548163721.1841028
1548163740.765162
1548163769.4702623
"""
```

`os.scandir()` 返回一个 `ScandirIterator` 对象。`ScandirIterator` 对象中的每一项有 `.stat()` 方法能获取关于它指向文件或目录的信息。`.stat()` 提供了例如文件大小和最后修改时间的信息。在上面的示例中，代码打印了 `st_time` 属性，该属性是上次修改文件内容的时间。

`pathlib `模块具有相应的方法。略。



## 创建目录
暂时跳过：[原文 &rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-7)

#### 创建单个目录

#### 创建多个目录



## 文件名模式匹配

使用上述方法之一获取目录中的文件列表后，你可能希望搜索和特定的模式匹配的文件。

本小节的示例将在名为 `some_directory` 的目录下执行，该目录具有以下的结构：
```
.
├── admin.py
├── data_01_backup.txt
├── data_01.txt
├── data_02_backup.txt
├── data_02.txt
├── data_03_backup.txt
├── data_03.txt
├── sub_dir
│   ├── file1.py
│   └── file2.py
└── tests.py
```

可以使用 Bash shell，你可以使用以下的命令创建上述目录结构。（跳过）

#### 字符串方法匹配

Python有几个内置 修改和操作字符串 的方法。当在匹配文件名时，其中的两个方法 `.startswith()` 和 `.endswith()` 非常有用。要做到这点，首先要获取一个目录列表，然后遍历。

```python
import os

for f_name in os.listdir('some_directory'):
    if f_name.endswith('.txt'):
        print(f_name)
```        

上述代码找到 `some_directory` 中的所有文件，遍历并使用 `.endswith()` 来打印所有扩展名为 `.txt` 的文件名。运行代码在我的电脑上输出如下:

```
data_01.txt
data_01_backup.txt
data_02.txt
data_02_backup.txt
data_03.txt
data_03_backup.txt
```

#### 使用 `fnmatch` 进行简单文件名模式匹配

字符串方法匹配的能力是有限的。`fnmatch` 有对于模式匹配有更先进的函数和方法。我们将考虑使用 `fnmatch.fnmatch()` ，这是一个支持使用 `*` 和 `?` 等通配符的函数。例如，使用 `fnmatch` 查找目录中所有 `.txt` 文件，你可以这样做:

```python
import os
import fnmatch

for f_name in os.listdir('some_directory'):
    if fnmatch.fnmatch(f_name, '*.txt'):
        print(f_name)
```        

- 迭代 `some_directory` 中的文件列表，并使用 `.fnmatch()` 对扩展名为 `.txt` 的文件执行通配符搜索。

- 据我查阅的资料，`*`匹配任意多个字符，而`?`匹配任意单个字符。此处字符为 `a~z`，`A~Z`和`0~9`共 36 个字符。

- `fnmatch()` 函数匹配能力介于简单的字符串方法和强大的正则表达式之间。 如果在数据处理操作中只需要简单的通配符就能完成的时候，这通常是一个比较合理的方案。


更复杂地，如果想要搜索类似于 `data_01_backup`这类文件，你可以这样使用 `fnmatch.fnmatch()`
```python
import os
import fnmatch

for f_name in os.listdir('some_directory'):
    if fnmatch.fnmatch(f_name, 'data_*_backup.txt'):
        print(f_name)
```  

输出如下 :

```
data_01_backup.txt
data_02_backup.txt
data_03_backup.txt
```

#### 使用 `glob` 进行文件名模式匹配

另一个有用的模式匹配模块是 `glob` 。

`.glob()` 在 `glob` 模块中的左右就像 `fnmatch.fnmatch()`，但是与 `fnmach.fnmatch()` 不同的是，它将以 `.` 开头的文件视为特殊文件。

UNIX和相关系统在文件列表中使用通配符像 `?` 和 `*` 表示全匹配。

例如，在UNIX shell中使用 `mv *.py python_files` 移动所有 `.py` 扩展名 的文件从当前目录到 `python_files` 。这 `*` 是一个通配符表示任意数量的字符，`*.py` 是一个全模式。Windows 操作系统中不提供此 shell 功能。但 `glob` 模块在 Python 中添加了此功能，使得 Windows 程序可以使用这个特性。

这里有一个使用 `glob` 模块在当前目录下查询所有 Python 代码文件:

```python
import glob

print(glob.glob('*.py'))
```

`glob.glob('*.py')` 搜索当前目录中具有 `.py` 扩展名的文件，并且将它们以列表的形式返回。 `glo`b 还支持 shell 样式的通配符来进行匹配 :

```python
import glob

for name in glob.glob('*[0-9]*.txt'):
    print(name)
```

这将找到所有文件名中包含数字的文本文件(.txt) :

```
data_01.txt
data_01_backup.txt
data_02.txt
data_02_backup.txt
data_03.txt
data_03_backup.txt
```

`glob` 也很容易在子目录中递归的搜索文件:

```python
import glob

for name in glob.iglob('**/*.py', recursive=True):
    print(name)
```

这里例子使用了 `glob.iglob()` 在当前目录和子目录中搜索所有的 `.py` 文件。传递 `recursive=True` 作为 `.iglob()` 的参数使其搜索当前目录和子目录中的 `.py` 文件。`glob.glob()` 和 `glob.iglob()` 不同之处在于，`iglob()` 返回一个迭代器而不是一个列表。

运行上述代码会得到以下结果:

```
admin.py
tests.py
sub_dir/file1.py
sub_dir/file2.py
```

`pathlib` 也包含类似的方法来灵活的获取文件列表。（略）



## 遍历目录和处理文件

一个常见的编程任务是遍历目录树并处理目录树中的文件。让我们来探讨一下如何使用内置的 Python 函数 `os.walk()` 来实现这一功能。`os.walk()` 用于通过从上到下或从下到上遍历树来生成目录树中的文件名。处于本节的目的，我们想操作以下的目录树:

```
├── folder_1
│   ├── file1.py
│   ├── file2.py
│   └── file3.py
├── folder_2
│   ├── file4.py
│   ├── file5.py
│   └── file6.py
├── test1.txt
└── test2.txt
```

以下是一个示例，演示如何使用 `os.walk()` 列出目录树中的所有文件和目录。

`os.walk()` 默认是从上到下遍历目录:

```python
import os
for dirpath, dirname, files in os.walk('.'):
   print(f'Found directory: {dirpath}')
   for file_name in files:
       print(file_name)

```       
`os.walk()` 在每个循环中返回三个值：

- 当前文件夹的名称
- 当前文件夹中子文件夹的列表
- 当前文件夹中文件的列表

在每次迭代中，会打印出它找到的子目录和文件的名称：

```
Found directory: .
test1.txt
test2.txt
Found directory: ./folder_1
file1.py
file3.py
file2.py
Found directory: ./folder_2
file4.py
file5.py
file6.py
```

要以自下而上的方式遍历目录树，则将 `topdown=False` 关键字参数传递给 `os.walk()` ：

```python
for dirpath, dirnames, files in os.walk('.', topdown=False):
    print(f'Found directory: {dirpath}')
    for file_name in files:
        print(file_name)
```

传递 `topdown=False` 参数将使 `os.walk()` 首先打印出它在子目录中找到的文件:

```
Found directory: ./folder_1
file1.py
file3.py
file2.py
Found directory: ./folder_2
file4.py
file5.py
file6.py
Found directory: .
test1.txt
test2.txt
```

如你看见的，程序在列出根目录的内容之前列出子目录的内容。 这在在你想要递归删除文件和目录的情况下非常有用。 你将在以下部分中学习如何执行此操作。 ~~默认情况下，`os.walk` 不会访问通过软连接创建的目录。 可以通过使用 `followlinks = True` 参数来覆盖默认行为。（听不懂）~~

## 创建临时文件和目录
跳过。[&rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-16)


## 删除文件和目录
跳过。[&rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-17)


## 复制、移动和重命名文件和目录
跳过。[&rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-21)


## 归档
归档是将多个文件打包成一个文件的便捷方式。 两种最常见的存档类型是ZIP和TAR。 你编写的Python程序可以创建存档文件，读取存档文件和从存档文件中提取数据。跳过。[&rarr;](https://juejin.im/post/5c57afb1f265da2dda6924a1#heading-26)


## References
- [Python文件操作，看这篇就足够](https://juejin.im/post/5c57afb1f265da2dda6924a1)

------------

