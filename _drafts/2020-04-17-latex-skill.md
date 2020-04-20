---
layout: post
title: "LaTeX公式的技巧和注意事项"
subtitle: '一些个人经验'
date: 2020-04-17 23:02:00
author: "Mike Lyou"
header-style: text
#header-img: "img/dream-catcher-902508_1920.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC
hidden:
excerpt: 
tags:
 - LaTeX

---



使用LaTeX语法输入公式在很多地方都可以使用，包括 Word 和一些支持渲染公式的markdown编辑器。学会使用LaTeX语法输入公式，可以说是对于理工科学生是很有帮助的。



本文主要罗列了一些相关的小技巧和个人经验。**注意本文内容不是LaTeX写作**，而仅仅是用借用LaTeX语法输入公式。下文中，“LaTeX语法” 都特指用来写公式的LaTeX语法，不包括`/includegraphics{}`之类的其他语法。



<!-- more -->



## 基础 LaTeX 语法

L<span style="text-transform: uppercase; font-size: 57.851%; vertical-align: 0.205em; margin-left: -0.36em; margin-right: -0.15em; line-height: 0">a</span>T<span style="text-transform: uppercase; vertical-align: -0.2155em; margin-left: -0.125em; margin-right: -0.1667em; line-height: 0">e</span>X



## 容易混淆的细节

不要混淆`\bullet`与` \cdot`：前者显示为 $\bullet$，可以在[Kröger-Vink记号](https://en.wikipedia.org/wiki/Kröger–Vink_notation)中表示相对带正电； 后者显示为 $\cdot$，常用来表示[点乘](https://zh.wikipedia.org/wiki/点积)。



不要混淆`\star`与`\ast`：前者显示为五角星 $\star$，我是没有用过的，敲公式时想当然打出来才发现不一样；后者是常见的六角形 $\ast$。

不要混淆`\varepsilon`与`\epsilon`：在数学公式中通常用到的是前者，显示为 ε 或 $\varepsilon$；后者显示为 ϵ 或 $\epsilon$。有些教科书或教授的PPT不太严谨，不区分这两种符号，甚至混在一起用......我们还是严谨一些。大家可以参看这篇 [知乎回答](https://www.zhihu.com/question/31807987/answer/279159464)



\star \ast

`\prime`似乎可以直接用`'`代替，不过用于个编译器的差异，容易出bug，不建议使用。

## 几个好习惯

使用`\sin`来表示正弦函数，不要直接写`sin`，那样会变成斜体。看看区别，`\sin x = sin x` 显示为 $\sin x = sin x $.



贴一个总结得挺好的 [LaTeX符号列表](https://www.caam.rice.edu/~heinken/latex/symbols.pdf)。没事多看两眼，总没坏处，~~虽然里面很多符号可能一辈子也用不到~~。



## 使用 MathPix

这玩意可以识别图片中的公式，并转为 LaTeX 代码。很强的工具，我多年前刚接触 LaTeX 的时候就听说了，但那时没这方面需求，没有用过。现在要收费了，功能也更强了。



免费用户每月可以识别30个公式，够用了。不要因为手抖而浪费识别次数就好。

即使真的需求量大，你可以多个账户轮流用，注册一个账户只需要一个邮箱而已。~~等于免费~~

## 后记

基本上就是我目前能想到的全部内容了，不是很多，但每个都是我“浪费”了一定时间精力才搞懂的，希望能帮到你。



还有就是，不同平台总会出现“同样的文件，不一样的显示”的问题。这个很难彻底解决。一方面尽量使用通用的没有歧义的语法，另一方面可以先完成主题内容，然后在细微修改。