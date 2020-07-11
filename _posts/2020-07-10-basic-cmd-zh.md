---
layout: post
title: "基础 Windows 命令行"
subtitle: '快速且实用的工具'
author: "Mike Lyou"
#header-style: text
header-img: "img/post-bg-matrix.jpg"
copyright-statement: CC BY-NC
catalog: true
tags:
  - Cmd
---

[See English Version &rarr;](https://mikelyou.com/2020/01/04/basic-cmd/)

本文简要介绍了常用的Windows 命令行。
<!-- more -->

在我搭建博客的过程中，我遇到了命令行 (command line 或 cmd)，因为好奇就简单学习了一下。学会简单的命令行操作，会对我们的学习工作有一定的帮助，接下来小火就和大家分享一下命令行的基础。

## 命令行简介

什么是命令行？

**命令行** (command line 或 cmd)是一个能让我们直接与计算机交流的实用工具，在处理一些任务时会十分高效，而有时则是处理问题的唯一途径。可能我们很多人第一次接触命令行是为了解决与电脑相关的问题，比如修改注册表。那个简陋的黑白窗口就是 **命令行界面**（Command Line Interface 或 CLI）

![image-20200710180249909](https://raw.githubusercontent.com/mikelyou/image-public/master/basic-cmd/image-20200710180249909.png)



## 打开命令行界面

要使用**命令行**，第一步就是找到并打开**命令行界面**的窗口。有两种方法：

- **方法 1.** 键盘输入<kbd>Win</kbd> + <kbd>R</kbd> 打开 `运行`界面 &rarr; 输入 `cmd` 并回车

![image-20200710175907440](https://raw.githubusercontent.com/mikelyou/image-public/master/basic-cmd/image-20200710175907440.png)

- **方法 2.** 键盘输入 <kbd>Win</kbd> 打开`开始`界面 &rarr;  直接键盘输入`cmd`&rarr; 打开 或 以管理员身份运行

![image-20200710181125255](https://raw.githubusercontent.com/mikelyou/image-public/master/basic-cmd/image-20200710181125255.png)

使用以上任意一种方法，我们就能够打开如下图所示的 **命令行界面**

![image-20200710180249909](https://raw.githubusercontent.com/mikelyou/image-public/master/basic-cmd/image-20200710180249909.png)

------------



现在我们已经打开命令行界面了，那么我们可以用它来做什么呢？下面我将简要介绍一下可以用命令行做的事情。


## 常用文件与文件夹命令

#### cd

默认情况下,  `cmd.exe` 在 `C:\WINDOWS\system32` 或 `C:\Users\用户名` 目录下. 我们在打开 `cmd.exe` 的时候就能看到它安装在哪个目录下.

如果我们想要在C盘以外的其他盘下 搜索文件 或 运行程序，首先需要更改路径。

使用`cd NEW_PATH` 将路径改变为 `NEW_PATH`. 例如，我们想要将路径改为 `E:\NEW_PATH`

```
E:              # change drive
cd E:\NEW_PATH  # change directory
```

Ps. 在同一个盘下，可以直接用 `cd` 命令更改路径；如果要目标在另一个盘，则是需要先更改盘符。


#### dir

列出当前目录下的所有文件和子目录。~~装x神器~~

#### mkdir

使用 `mkdir DIRNAME` 创建名为 `DIRNAME` 的文件夹。

#### rmdir

使用 `rmdir DIRNAME` 删除名为 `DIRNAME` 的文件夹。

注意：仅**空文件夹**可以删除。尝试删除非空文件夹会报错。

#### del

使用 `del FILENAME.extension` 删除名为 `FILENAME.extension` 的文件。

#### help

记不住这么多命令怎么办？使用 `help` 查看当前目录下的所有可用命令。


## 常用 Windows 系统命令

#### ping

使用 `ping` 检测你的电脑和指定网址或 IP地址的 ping

```
ping mikelyou.com
ping 185.199.110.153  # IP of mikelyou.com
```

顺便，我们也可以通过这个命令查询指定网址的 IP 地址。

![image-20200710191346277](https://raw.githubusercontent.com/mikelyou/image-public/master/basic-cmd/image-20200710191346277.png)

#### ipconfig

使用 `ipconfig` 查询 Windows IP 配置，如IPv4地址等。

![image-20200710191811168](https://raw.githubusercontent.com/mikelyou/image-public/master/basic-cmd/image-20200710191811168.png)

#### systeminfo

使用 `systeminfo` 查询 Windows 系统信息。例如，主机名、处理器、系统类型、内存、网卡。

#### shutdown

设置一定时间后自动关机，以及取消自动关机。~~并不知道有什么用处。~~

```
shutdown -s         # system will shutdown in 1 minute
shutdown -s -t 3600 # system will shutdown in 3600 seconds
shutdown -a         # cancel shutdown command
```

## 将命令另存为批处理文件

将经常使用的命令保存为 **批处理文件**(batch file) 可以免去重复输入命令的麻烦。将命令保存为批处理文件只需以下步骤：

1. **创建一个 `.txt` 文件**
2. **在里面粘贴我们的命令**
3. **保存文件，将后缀修改为 `.bat`.**

现在我们创建了一个批处理文件。双击它，就可以一键运行我们的命令。

举个栗子，每次写博客时我会用到下面的命令:

```
E:
cd E:\GitHub\mikelyou.github.io
jekyll serve
```

这些命令太长了，我不想每次重复手打，于是就保存为批处理文件。下次我只需双击这个批处理文件，就不必手打三行复杂的命令了。~~但是有一些bug，~~ 这里仅作为示范。



## References

- [A Beginner’s Guide To The Windows Command Line](https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/)
- [cmd应用基础-扫盲教程](https://lellansin.wordpress.com/2012/12/15/cmd应用基础-扫盲教程/)
- [好玩的CMD命令行~](https://zhuanlan.zhihu.com/p/28838517)

> This article is Mike Lyou's original work and may not be reproduced without permission.