---

layout: post
title: "Markdown 文章内链接"
subtitle: ''
date: 2020-10-25 16:00:00
author: "Mike Lyou"
#header-style: text
header-img: "img/post-bg-table.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC-SA
hidden: true
excerpt: 中文、英文、多级序号及混排多种情况
tags:
 - Markdown

---

<!-- more -->

## 简介

有时候我们需要指向文章内部的链接，这时候使用锚点会比使用超链接更好，因为它使用的是相对路径。

超链接的 markdown 格式为： `[示例网址](https://example.com)`

文章内链接的格式基本相同：`[示例](#示例)`

仅仅将小括号中的 `http(s)` 链接更换为以 `#` 开头的文章内链接。本文介绍的就是这种链接的使用方法。

## 使用方法

### 英文标题

大写全部变为小写，空格用 `-` 代替：

```markdown
## Section Title

[Section Title](#section-title)
```

### 中文标题

同理，而且因为没有空格和大小写的问题，更加简单：

```markdown
## 标题1

[标题1](#标题1) 
```

### 带有多级序号

如果带有 `1.4.2` 这种多级带点序号，只需保留数字，例如：

```markdown
### 1.4.2 三级目录

[1.4.2 三级目录](#142-三级目录)
```

### 中文、英文、数字混排

同理

```markdown
### 2.6.1 Markdown 三级目录 1

[2.6.1 Markdown 三级目录 1](#261-Markdown-三级目录-1)
```

## 参考文献

- [Github 中 Markdown 锚点链接如何写 ](https://my.oschina.net/antsky/blog/1475173)

- [html - Cross-reference (named anchor) in markdown - Stack Overflow](https://stackoverflow.com/questions/5319754/cross-reference-named-anchor-in-markdown)

***

**以下为测试区**

查看网址栏、或光标位置，就能看出来是否跳转成功了。



## Section Title


## 标题1

### 1.4.2 三级目录

### 2.6.1 Markdown 三级目录 1

[Section Title](#section-title)

[标题1](#标题1) 

[1.4.2 三级目录](#142-三级目录)

[2.6.1 Markdown 三级目录 1](#261-Markdown-三级目录-1)







