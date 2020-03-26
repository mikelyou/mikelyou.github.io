---
layout: post
title: "印象笔记第三方应用的简单评测"
subtitle: 'Joplin, Tusk 与马克飞象'
date: 2020-02-19 11:00:00
author: "Mike Lyou"
#header-style: text
header-img: "img/post-bg-2015.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC
#hidden: true
#excerpt: Some tips.
tags:
  - Software
  - 印象笔记
---


> 本文简单介绍了三个印象笔记的第三方应用：Joplin, Tusk 与马克飞象。

<!-- more -->



## 寻找第三方工具

从2016年接触 **[印象笔记](https://staging.yinxiang.com)** 以来，我逐渐依赖上这款笔记软件。我习惯于用它记录想法，写随笔，也用来保存一些文件，保存一些容易遗忘的数据。

不过随着我的印象笔记里的内容越来越多，很多问题浮现出来：

- **搜索延迟较大**，2s ~ 5s 不等
- **无法批量编辑**，进行小修改会显得很麻烦，比如统一几个笔记的题目格式
- **数据比较封闭**，难以使用第三方工具直接修改数据

为了解决上述问题，我开始寻找一个强有力的第三方工具，甚至是印象笔记的替代产品。这样一个工具，我希望它具有以下特征：

- **可以使用一些命令**，比如：
  - 在笔记内使用`#tag`直接添加标签、使用`nb:notebook`设定归属笔记本
  - 可以批量修改笔记标题、笔记内容
- 最好 **可以支持第三方程序** （如python）的处理
- 如果是第三方工具，那么应该与印象笔记自由通信，至少可以 **互相导入与导出**
- 如果是替代产品，在 **稳定性、安全性、同步速度和价格** 上都不能太差

当然我还希望有一些其他特征，不过这些并不属于我的核心需求：

- 可以导入和导出 **多种文件格式**，如markdown。
- 有可靠的 **提醒功能**、**待办事项功能**，无论是内置功能还是借助第三方工具。目前的情况是，印象笔记内创建提醒 = 没有提醒，根本不会提醒我。

下面是我发现的一些其他第三方应用或工具。

## 马克飞象

[马克飞象](https://maxiang.io/)是印象笔记官方推荐的一款第三方工具，是专为印象笔记打造的 Markdown 编辑器。

#### 亮点
- 舒适的 Markdown 写作环境， 笔记同步至印象笔记
- 支持 LaTeX 公式，支持同步滚动（在 Atom 中这两个功能就无法同时实现）
- 可以通过 `@(示例笔记本)[示例标签1|示例标签2]` 来指定笔记本和标签
- 只需 79 元 / 年

#### 不足
- 由马克飞象创建的笔记，不能再印象笔记中修改，否则会出错
- 同步略慢，插入图片时尤其明显

如果你同时是印象笔记和 Markdown 的重度用户，那么马克飞象应该会得到你的喜欢。这款软件可以免费试用十天，之后的收费是 79元 / 年，这个价格对于适合的用户可以说是白菜价了，如果你觉得这个价格贵，那么你可能不是这款软件面向的用户。

## Tusk

[Tusk](https://klaussinani.tech/tusk/) 是一款**精致**的、**免费开源**的**第三方客户端**，可以给我们创造一个简洁舒适，又方便快捷的写作环境。在桌面客户端也可以拥有在 Web 端写作的体验。

Tusk 本身只作为官方客户端的替代品，使用时依然需要登录印象笔记账户。

#### 亮点
- 整洁漂亮的界面
- 丰富的快捷键
-  可以导出为 PDF, HTML 和 Markdown

#### 不足
无法导出中文笔记。这是一大硬伤，直接迫使我放弃这款软件。大家可以前往其 [GitHub 页面](https://github.com/klaussinani/tusk) 对其开发做出贡献。


## Joplin

我找到的 **[Joplin](https://github.com/laurent22/joplin)** 这款软件，是一款 **免费、开源、支持中文** 的笔记软件和代办清单软件。

#### 亮点
- 功能齐全，可以独立使用、完全替代印象笔记
- 支持 Nextcloud, Dropbox, WebDAV and OneDrive 或其他同步工具
- 增强的搜索工具
- 可以使用外部编辑器编辑笔记
- 拥有开发者模式，你可以自己倒腾

#### 不足

- 印象笔记文件`*.enex`可以导入 Joplin, 但 Joplin 内的笔记无法导入印象笔记。
  这就意味着，我无法在 Joplin 修改笔记后重新放回印象笔记，而只能在 Joplin 中查看。
- 在 Windows 下，如果使用的不是便携版，将会很难更改笔记存储位置，而且默认存储位置在 C盘。（在[这里](https://github.com/laurent22/joplin/issues/42#issuecomment-348338177)有处理方法，但我一直弄不成。）


## 未体验列表

下面是我发现的一些其他第三方应用或工具，但因为没有相关需求没有进行尝试，在此列举以供读者或自己未来查询。

- [geeknote](https://github.com/VitaliyRodnenko/geeknote) :Geeknote is a command line client for Evernote that can be use on Linux, FreeBSD and OS X. Written in Python.

- [leanote](https://github.com/leanote/leanote)：一款受Evernote启发并提供比Everote更丰富体验的笔记和分享软件

- [evernote-alfred](https://github.com/buginux/evernote-alfred)：使用Alfred搜索印象笔记


## 后记

适合自己的工具才是最好的。我们在选择一个工具时，要考虑它是否能提高我的工作效率，投入的时间成本是否值得。

印象笔记由于拥有数量庞大的用户群体，相关的软件和工具在未来一段时间内依然会不断发展。希望你能够找到自己需要的那一款。如果你发现比较好的软件，请务必告诉我，非常感谢！

由于本文具有一定的时效性，我没有添加更多的图片和详细说明。如果有人阅读这篇文章，觉得有帮助的话，我再补充一下内容。

>本文首发于：https://mikelyou.com/2020/02/19/evernote-third-party-apps/ 转载请保留此链接，并且希望您能够告知我将此文转载于何处。