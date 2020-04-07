---
layout: post
title: "如何使网页变为黑白页面"
subtitle: '灰度滤镜'
date: 2020-04-04 10:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/dream-catcher-902508_1920.jpg"
mathjax: false
catalog: false
copyright-statement: CC BY-NC
hidden:
excerpt: 深切哀悼全国各族人民对抗击新冠肺炎疫情斗争牺牲烈士和逝世同胞
tags:
 - HTML
 - CSS
---

<style type="text/css"> html{filter: grayscale(100%); -webkit-filter: grayscale(100%); -moz-filter: grayscale(100%); -ms-filter: grayscale(100%); -o-filter: grayscale(100%); -webkit-filter: grayscale(1);}</style>

<!-- more -->

2020 年 4 月 4 日，清明节，国家公祭日。全国哀悼为抗击新冠肺炎疫情斗争牺牲烈士和逝世同胞。

诸多网站都换上了黑白页面以示哀悼。如果你也想要将自己的网站呈现黑白效果，可以通过修改 CSS 样式实现。


```html
<style type="text/css">
    html {
        filter: grayscale(100%);
        -webkit-filter: grayscale(100%);
        -moz-filter: grayscale(100%);
        -ms-filter: grayscale(100%);
        -o-filter: grayscale(100%);
        -webkit-filter: grayscale(1);
    }
</style>
```

可以使用 [HTML Minifier](https://www.willpeavy.com/tools/minifier/) 将上述代码压缩。压缩后的代码与原代码作用相同，只是将原本易于阅读的多行代码，转换为了只有一行的“浓缩”代码。

```
<style type="text/css"> html{filter: grayscale(100%); -webkit-filter: grayscale(100%); -moz-filter: grayscale(100%); -ms-filter: grayscale(100%); -o-filter: grayscale(100%); -webkit-filter: grayscale(1);}</style>
```

把代码加在网站的 CSS 文件或者 `<head></head>` 之间任意部分即可。

代码释义：`filter` 是滤镜的意思，`filter:gray` 的意思就是说给页面加上一个灰度的滤镜，所以 html 里面的所有内容都会变成黑白的了。不过这个滤镜对于 Chrome 和 Safari 浏览器是无效的，所以下面会有一行 `-webkit-filter: grayscale(100%); `这个样式是专属于使用 webkit 内核的浏览器的，意思和 `filter: gray;` 差不多，只是写法不同罢了。

参考[1]:[https://oldtang.com/2793.html](https://oldtang.com/2793.html)  
参考[2]:[https://www.cxyxiaowu.com/8933.html](https://www.cxyxiaowu.com/8933.html)

![](http://www.xinhuanet.com/politics/2020-04/03/1125807657_15858737649811n.jpg)

>新华社北京4月3日电 为表达全国各族人民对抗击新冠肺炎疫情斗争牺牲烈士和逝世同胞的深切哀悼，国务院今天发布公告，决定2020年4月4日举行全国性哀悼活动。在此期间，全国和驻外使领馆下半旗志哀，全国停止公共娱乐活动。4月4日10时起，全国人民默哀3分钟，汽车、火车、舰船鸣笛，防空警报鸣响。

原文：[http://www.xinhuanet.com/politics/2020-04/03/c_1125807657.htm](http://www.xinhuanet.com/politics/2020-04/03/c_1125807657.htm)



**致敬英雄，缅怀同胞。清明追思，家国永念。**
