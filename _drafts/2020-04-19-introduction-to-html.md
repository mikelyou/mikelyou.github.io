---
layout: post
title: "基础 HTML 教程"
subtitle: '也是个人学习笔记'
date: 2020-04-19 21:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/dream-catcher-902508_1920.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC
hidden:
excerpt: HTML 挺简单的，我半个小时就学会了
tags:
 - HTML
 - Tutorial
 - Notes
---

<!-- more -->

>HTML 很容易学习！相信您能很快学会它！——菜鸟教程



**写在写在前面前面**： 菜鸟教程写的太好的，讲的清楚又没多余内容，搞得我很难写出不一样的东西。还是去打机好了



**写在前面**：本文内容大量参考了 [菜鸟教程](https://www.runoob.com/html/html-tutorial.html)，本人仅对内容进行了少量修改和内容重排，删除了一些本人用不到的内容（如HTML版本）。菜鸟教程上的内容是完全免费的，引用或转载请使用源站网址。菜鸟教程上还有参考手册和大量实例，可以帮助大家更好的理解和学习HTML。

至于我为什么会想到学HTML，是因为在 [高级Markdown技巧]() 中遇到了HTML标签，就顺便来学HTML了。确实挺简单的，我半个小时就看完了菜鸟教程上的全部内容，**相信你也可以的！**



## 什么是 HTML

超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言。

您可以使用 HTML 来建立自己的 WEB 站点，HTML 运行在浏览器上，由浏览器来解析。

在本教程中，您将学习如何使用 HTML 来创建站点。

HTML 很容易学习！相信您能很快学会它！



## HTML 实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Mike Lyou Blog(mikelyou.com)</title>
</head>
<body>
    <h1>我的第一个标题</h1>
    <p>我的第一个段落。</p>
</body>
</html>
```

## 实例解析

- `<!DOCTYPE html>` 声明为 HTML5 文档
-  `<html>` 元素是 HTML 页面的根元素
-   `<head>` 元素包含了文档的元（meta）数据，如 <meta charset="utf\-8"> 定义网页编码格式为 `utf\-8`。
-   `<title>` 元素描述了文档的标题
-   `<body>` 元素包含了可见的页面内容
-   `<h1>` 元素定义一个大标题
-   `<p>` 元素定义一个段落

**注：**在浏览器的页面上使用键盘上的 F12 按键开启调试模式，就可以看到组成标签（当然）。

## 什么是HTML?

HTML 是用来描述网页的一种语言。

-   HTML 指的是超文本标记语言: **H**yper**T**ext **M**arkup **L**anguage
-   HTML 不是一种编程语言，而是一种**标记**语言
-   标记语言是一套**标记标签** (markup tag)
-   HTML 使用标记标签来**描述**网页
-   HTML 文档包含了HTML **标签**及**文本**内容
-   HTML文档也叫做 **web 页面**

---

## HTML 标签

HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

* HTML 标签是由*尖括号*包围的关键词，比如`<html>`

* HTML 标签通常是*成对出现*的，比如 `<b>`和 `</b>`

* 标签对中的第一个标签是*开始标签*，第二个标签是*结束标签*

* 开始和结束标签也被称为*开放标签*和*闭合标签*

  ```
  <标签>内容</标签>
  ```

  **"HTML 标签"** 和 **"HTML 元素"** 通常都是描述同样的意思.

  但是严格来讲, 一个 HTML 元素包含了开始标签与结束标签

## `<!DOCTYPE>` 声明
`<!DOCTYPE>`声明有助于浏览器中正确显示网页。


网络上有很多不同的文件，如果能够正确声明HTML的版本，浏览器就能正确显示网页内容。查看完整网页声明类型 [DOCTYPE 参考手册](https://www.runoob.com/tags/tag-doctype.html)。

**对于中文网页**：需要使用 `<meta charset="utf-8"> `声明编码，否则会出现乱码。有些浏览器(如 360 浏览器)会设置 `GBK` 为默认编码，则你需要设置为 `<meta charset="gbk">`。

目前在大部分浏览器中，直接输出中文会出现中文乱码的情况，这时候需要在头部将字符声明为 `UTF-8`

## HTML 编辑器（略）

本人只是用 HTML 标签来更加灵活的进行 markdown 写作，这部分跳过。欢迎前往 [菜鸟教程](https://www.runoob.com/html/html-editors.html) 查看原文。