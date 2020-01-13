---
layout: post
title: "DropIt + InfranView"
subtitle: 'Images batch process'
date: 2099-01-09 11:00:00
author: "Mike Lyou"
#header-style: text
header-img: "img/post-bg-2015.jpg"
tags:
  - Template

#excerpt: Some tips.
---

<!-- more -->


## Catalog：
{:.no_toc}

*  
{:toc}


## 批量清除 EXIF 信息

我们需要在 DropIt 配置文件中新增一个协议，配置如下：

1. 名称：`批量清除 EXIF 信息`
2. 规则：`*.bmp;*.gif;*.hdr;*.ico;*.jpeg;*.jpg;*.png;*.psd;*.tif;*.tiff;`
3. 操作：`打开方式`
4. 目标程序：`"C:\Program Files\IrfanView\i_view64.exe" "%File%"/jpg_rotate=(0,1,0,1,0,0,1,0)/cmdexit`

说明一下最后这段命令的意思：`"C:\Program Files\IrfanView\i_view64.exe"` 是 IrfanView 的安装目录，如果你使用的是绿色版，需要修改到它的位置。`"%File%"` 是 DropIt 内置的变量，意思是「不包含扩展名的文件名」，这些内置变量是可以直接选择的，不用记住。`/jpg_rotate=(0,1,0,1,0,0,1,0)` 是 IrfanView 的提供选项，0 和 1 分别代表不同选项的开关。第 7 项的 1 是「清除全部标记」，第 8 项的 0 是「不保留 EXIF」。其他选项的意思可以在 `i_options.txt` 中查到，这里不做赘述。`cmdexit` 是指执行完操作后，自动关闭窗口。

保存这条协议，把图片拖到 DropIt 的图标上，即可实现批量清除图片 EXIF 了。这个操作会覆盖原图，所以在尝试执行前对照片做好备份。

Ref: [用 DropIt 打造全自动的 Windows 文件管理体系](https://sspai.com/post/45532)

## 尝试探索 `i_options.txt`




## References
- [用 DropIt 打造全自动的 Windows 文件管理体系](https://sspai.com/post/45532)


------------
>Statement:This note is posted only for personal studies and communication, and not allowed to be reproduced unless otherwise indicated. I do not own copyright of some of the content. If any post accidentally infringes your copyright, it will be removed shortly after being informed.
