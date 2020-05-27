---
layout: post
title: "高级 Markdown 技巧"
subtitle: '注释、折叠、转义、公式'
date: 2020-04-08 21:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/dream-catcher-902508_1920.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC
hidden:
excerpt: 当你觉得 markdown 做不了一些事的时候，可能其实它可以做到。
tags:
 - Markdown
 - HTML
---

<!-- more -->

>本文介绍了本人从各处搜集到的 markdown 高级技巧，有一些可能使用起来并不高效，甚至有把简单的markdown复杂化的可能性，但这些用法真的很少人分享，我又想用，所以姑且分享一下我了解的。希望能帮到你。

**谁适用阅读本文**： 已经可以闭着眼写markdown的人 或 写markdown像写纯文本一样熟练自由的人。

## Markdown 入门

**如果你还不熟悉 markdown 语法**，推荐以下几个很好的教程：

- [菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)

- [GitHub Markdown语法](https://help.github.com/cn/github/writing-on-github/basic-writing-and-formatting-syntax#ignoring-markdown-formatting)

- [思否SegmentFault](https://segmentfault.com/markdown)（推荐这个，可玩性较高）

  

~~别人已经写得很好了，我就没必要再写啦~~


## 在 Markdown 中使用 HTML 元素

### Markdown 注释

学过点编程的人可能都有写注释的欲望，一段内容想删但又不舍得，纠结使人头大。而 markdown 本身作为轻量级语言，是没有注释语法的。想要写注释的话，需要使用 html 注释（[参考](https://stackoverflow.com/questions/4823468/comments-in-markdown)）：


```html
<!-- 这是 html 注释， 在 markdown 中也不会被编译， 可以作为注释的方法 -->
```

输出为：

<!-- 这是 html 注释， 在 markdown 中也不会被编译， 可以作为注释的方法 -->


### 折叠网页内容

有时候我们希望在博文中折叠部分细节的讨论，这时候可以使用 `<summary>` 来折叠内容，不过在纯 markdown 编辑器中大概不行。（[参考](https://blog.csdn.net/djzhao627/article/details/89977411)）

```
<details>
<summary>展开查看</summary>
啊啦~被你发现啦！
</details>
```

显示如下：

<details>
<summary>展开查看</summary>
啊啦~被你发现啦！
</details>

我喜欢搭配表格使用，这样可以清晰的现实哪些是折叠部分的内容（不过在markdown编辑器中似乎无法正常显示）：

```html
<details>
<summary><b>See what's inside &darr;</b></summary>
  <table border="1">
    <tr>
      <th><a href="https://www.runoob.com/html/html-quicklist.html">如何使用html元素添加表格</a></th>
    </tr>
    <tr>
      <td>
        这个样子<br>
        多行内容<br>
        不至于让分不清哪里是折叠内容的结束
      </td>
    </tr>
  </table>
</details>
```

输入如下：

<details>
<summary><b>See what's inside &darr;</b></summary>
  <table border="1">
    <tr>
      <th><a href="https://www.runoob.com/html/html-quicklist.html">如何使用html元素添加表格</a></th>
    </tr>
    <tr>
      <td>
        这个样子<br>
        多行内容<br>
        不至于让分不清哪里是折叠内容的结束
      </td>
    </tr>
  </table>
</details>

应该也可以定义 CSS 样式代替表格吧？回头试试，可以的话会好看很多。


### 其他 HTML 标签

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。（[参考](https://www.runoob.com/markdown/md-advance.html)）

目前支持的 HTML 元素有：`<kbd> <b> <i> <em> <sup> <sub> <br>`等 ，如：


```html
使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
```

使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑

```html
这是一句话，可以<b>粗体</b>或<i>斜体</i>或<em>强调文本</em>，<br>
还能使用<sup>上标</sup>和<sub>下标</sub>。使用<br>换行。
```

这是一句话，可以<b>粗体</b>或<i>斜体</i>或<em>强调文本</em>，<br>
还能使用<sup>上标</sup>和<sub>下标</sub>。使用<br>换行。

可以使用的应该还有很多，大家可以自己尝试。不过能用 markdown 自身语法实现的功能，比如粗体，就不要使用 html 标签了，否则有种本末倒置的感觉了。应该只有在 markdown 无法实现某个功能是再尝试使用 html 标签。

## 字符转义

Markdown 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用转义字符。Markdown 使用反斜杠转义特殊字符，支持以下这些符号：<code>\</code> <code>`</code> <code>*</code> <code>_</code> <code>{}</code> <code>[]</code> <code>#</code> <code>+</code> <code>-</code> <code>.</code> <code>!</code>.

至于我要怎么写才能把上面一行内容显示在网页上，这又是一个套娃问题，~~我知道怎么写但不知道怎么把怎么写写出来~~，看看[这个回答](https://segmentfault.com/q/1010000010302143)大家应该就清楚了。

## 插入公式

使用一对美元符号`$`可以显示公式，双美元符号`$$`会使公式单独占一行，公式的语法与 [LaTeX](https://www.caam.rice.edu/~heinken/latex/symbols.pdf) 一样。

不过这需要加载 Mathjax 进行渲染。并非所有 markdown 编辑器都拥有这个功能，我所了解的 **简书** 和 **马克飞象** 是可以支持公式渲染的。

本博客模板添加了 Mathjax 支持所以可以直接写公式。在 **Atom** 中需要安装插件，但公式渲染和同步滚动两个功能无法同时实现。

太过复杂的公式可能不太好办，比如那种箭头上下都有文字的化学反应，主要是很难写的好看；不过我觉得一般人都用不到那种，能写个表格矩阵的就够复杂了。我在[另一篇博文](https://mikelyou.com/2020/01/02/hodgepodge/#details-about-mathjax-lable-and-cite-equations)中讨论了更多关于在博客中的 LaTeX 写作的细节。

公式示例：

```
小明买了$m$ 跟铅笔，每根 $n$ 元， 那么他一共花了这么多元

$$y = m * n$$
```

输出如下：

小明买了$m$ 跟铅笔，每根 $n$ 元， 那么他一共花了这么多元

$$y = m * n$$

## 好用的小工具

- [拷贝猫](https://chrome.google.com/webstore/detail/copycat/khbjeknhjcdbijopmdbnjpncellpbjhf?hl=zh-CN)： 浏览器插件，可以方便地将网页内容以 markdown 或 html 格式复制下来，抄笔记利器。
- [Mathpix](https://mathpix.com/)：识别图片或手写公式，自动生成 LaTeX 代码，抄公式利器。

## 其他细节和注意事项

#### 多用空行

markdown编辑器千千万万，每个都有些区别。比如是否支持公式、是否需要空一行才能换行、有些粗体和斜体的写法不一样、在一个编辑器里插入的图片会在另一个地方编译为表格...



我总结出一个经验：不清楚要不要多空一行的时候，**要舍得用空行！**



有些编译器中，空一行（也就是指按一次<kbd>Enter</kbd> ）并不会换行，从而导致排版变丑，如果后面一行是双美元（`$$`）扩住的公式就更丑了，公式会贴在文字那一行。



单独成行的公式，双美元复合最好单独占一行，不要和公式内容挤在一行。不要在双美元那一行添加任何符号，比如引用`>`之类的，会导致奇怪的错误。正确的方法如下：

```latex
$$
C d C l_{2} \stackrel{N a C l}{\longrightarrow} C d_{N a}^{\bullet}+2 C l_{C l}^{*}+\mathbf{v}_{N a}^{\prime}
$$
```



~~不要这样~~（虽然区别不大，但建议不要）：

```latex
$$C d C l_{2} \stackrel{N a C l}{\longrightarrow} C d_{N a}^{\bullet}+2 C l_{C l}^{*}+\mathbf{v}_{N a}^{\prime}$$
```



不要为了让文章行数少一点，就不舍得用空行。空行可以减少很多意想不到的麻烦，很多时候是与想象不同的格式排版，少数情况出现奇怪的bug。



#### 避免使用有歧义的语法

此处的“歧义”是指，一种写法既可以理解为 markdown 语言，也可以理解为 LaTeX 语言，但在两种语言下意义不同。

比如下划线`_`在一些markdown编辑器中会被编译为斜体，而在 LaTeX 中则是下标的含义，在一行公式中出现两个下标，就有可能出现被markdown编辑器理解为斜体的bug。

再比如`*` `$` `{}` 这些符号，搞不好就被认为是 markdown 或 LaTeX 再或 HTML 语句，甚至`双花括号`会被识别为 Liquid 语句。在写笔记或文章时，能少用这些符号就少用。



建议在公式中使用 `\ast` 代替 `*`，使用 `\prime` 代替 `'`。

***

**本人水平有限，如有错误或更好的实现方法，欢迎指正**！
