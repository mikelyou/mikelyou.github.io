---
layout:     post
title:      "How to make the blog looks better"
subtitle:   "使博客更美更丰富"
date:       2019-12-28 20:30:00
author:     "Mike Lyou"
header-img: "img/post-bg-2015.jpg"
tags:
    - Blog
    - 教程

# excerpt_separator: <!--more-->      # 使自动获取摘要在 `<!--more-->`处停止
---

博客搭建好了，但是我的兴趣还不在写文章上，而在于如何让博客看起来更美。

> 不要停笔，生活还在继续。


###### 修复双重滚动条的bug
因为Hux自己的博客一直在修改，稳定的模板现在已经比他的博客落后很多个版本，而在这过程中发现甚至已经解决的问题依然存在在模板里。

这时候，有两种方法都可以尝试：一、看看Hux本人最新的模板添加了什么内容，看看版本更新日志；二、查看issue里有没有同样的问题。

双重滚动条的问题就在[#issues](https://github.com/Huxpro/huxpro.github.io/issues/123)被解决过了，解决方法也很简单。

###### 如何预览草稿

这里[官方文档](http://jekyllcn.com/docs/drafts/)讲的不够清楚。
我在这个 ~~[意义不明的文档](https://github.com/chesterchenn/blog/blob/a85ddb55d209de0db21b24684fa48914865b3d33/README.md)~~ 里找到了答案：

1. 你需要在网站根目录下创建一个名为` _drafts 的文件夹`，把草稿放入这个文件夹。

2. 然后运行`jekyll serve --drafts`即可

似乎`jekyll serve --drafts`命令与`jekyll serve`命令无法同时执行。
