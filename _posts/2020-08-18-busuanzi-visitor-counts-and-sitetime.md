---
layout: post
title: "使用不蒜子添加访客统计"
subtitle: '以及添加建站时长'
date: 2020-08-18 21:37:00
author: "Mike Lyou"
header-style: text
#header-img: "img/dream-catcher-902508_1920.jpg"
mathjax: false
catalog: true
copyright-statement: CC BY-NC-SA
hidden: false
excerpt:
tags:
 - GitHub Pages

---

<!-- more -->

## 不蒜子简介
> 评论有 “多说”，计数有 “不蒜”！ （虽然多说已经没了）

静态网站建站现在有很多快速的技术和平台，静态的缺点是，一些动态的内容如评论、计数等等模块就需要借助外来平台。不蒜子就是一款优秀的极简计数模块。

**不蒜子** 与百度统计谷歌分析等有区别：不蒜子可直接将访问次数显示在您在网页上（也可不显示）；对于已经上线一段时间的网站，不蒜子允许您初始化首次数据。

[不蒜子 - 极简网页计数器](http://busuanzi.ibruce.info/)

[不蒜子的使用方法](http://ibruce.info/2015/04/04/busuanzi/)

## 不蒜子的使用方法

### 第一步、安装脚本（必选）

将不蒜子的 JS 引入到 `footer.html` 中（本站使用的是 jekyll）

```html
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js">
</script>
```
### 第二步、站点总访问量（可选）

只需要复制相应的html标签到你的网站要显示访问量的位置即可。我将其添加至 `footer.html`.

站点的访问量有两种算法可选：

算法a：pv 的方式，单个用户连续点击 n 篇文章，记录 n 次访问量。

```html
<span id="busuanzi\_container\_site\_pv">
 本站总访问量<span id="busuanzi\_value\_site\_pv"></span>次
</span>
```

算法b：uv 的方式，单个用户连续点击 n 篇文章，只记录 1 次访客数。

```html
<span id="busuanzi\_container\_site\_uv">
 本站访客数<span id="busuanzi\_value\_site\_uv"></span>人次
</span>
```
> 代码中文字是可以修改的，只要保留id正确即可。

### 第三步、单页访问量（可选）

要显示每篇文章的访问量，复制以下代码添加到你需要显示的位置。

仅有一种算法：pv 的方式，单个用户点击 1 篇文章，本篇文章记录 1 次阅读量。

```html
<span id="busuanzi_container_page_pv">
  本文总阅读量<span id="busuanzi_value_page_pv"></span>次
</span>
```

我希望将其添加至每篇文章的头部、放在作者和发表时间之后，查看 `post.html` 后可以发现，对应的代码位置在 `intro-header.html` 中。

### 其他事项
- 使用 `jekyll serve` 部署在本地预览效果的时候，`uv`数和`pv`数会过大，这是由于不蒜子用户使用一个存储空间，所以使用 `localhost:4000` 进行本地预览的时候会导致数字异常，这是正常现象，只需要将博客部署至云端即可恢复正常。[参考](https://chrischen0405.github.io/2018/09/11/post20180911/)
- 据说登陆后可以初始化访问次数一次，但是目前显示无法注册
- 本想打笔（一块）巨款，谁知目前微信支付宝在境外不太方便，插个眼，以后想起来了再打。

### 我的代码

```html
<span id="busuanzi_container_site_uv">
  👤Total Visitors <span id="busuanzi_value_site_uv"></span> |
</span>
<span id="busuanzi_container_site_pv">
  👁️Total Views <span id="busuanzi_value_site_pv"></span>
</span>
```

顺便贴一个我喜欢的 emoji 查询网站 [🤣 EmojiXD](https://emojixd.com/).

## 添加建站时长

添加以下代码至需要显示的地方即可：

```html
<span id="sitetime"></span> <!--显示建站时间的地方放置此代码 可以加上其他代HTML代码加粗颜色等-->
<script language=javascript>
    function siteTime(){
        window.setTimeout("siteTime()", 1000);
        var seconds = 1000;
        var minutes = seconds * 60;
        var hours = minutes * 60;
        var days = hours * 24;
        var years = days * 365;
        var today = new Date();
        var todayYear = today.getFullYear();
        var todayMonth = today.getMonth()+1;
        var todayDate = today.getDate();
        var todayHour = today.getHours();
        var todayMinute = today.getMinutes();
        var todaySecond = today.getSeconds();
        var t1 = Date.UTC(2019,12,27,17,46,00);  //此处填写建站时间 依次为 年,月,日,时,分,秒注意格式 半角,
        var t2 = Date.UTC(todayYear,todayMonth,todayDate,todayHour,todayMinute,todaySecond);
        var diff = t2-t1;
        var diffYears = Math.floor(diff/years);
        var diffDays = Math.floor((diff/days)-diffYears*365);
        var diffHours = Math.floor((diff-(diffYears*365+diffDays)*days)/hours);
        var diffMinutes = Math.floor((diff-(diffYears*365+diffDays)*days-diffHours*hours)/minutes);
        var diffSeconds = Math.floor((diff-(diffYears*365+diffDays)*days-diffHours*hours-diffMinutes*minutes)/seconds);
        document.getElementById("sitetime").innerHTML="🕓Mike Lyou's Blog 已开通 "+diffYears+" 年 "+diffDays+" 天 "+diffHours+" 小时 "+diffMinutes+" 分钟 "+diffSeconds+" 秒"; //此处为显示的内容
    }
    siteTime();
</script>
```

我觉得其实精确到天就足够了，不过还是查了一下我的具体建站时间，以第一篇文章发表的时间作为建站时间（[这里](https://github.com/mikelyou/old_mikelyou.github.io/runs/365551118)）。


## 参考文献
1. [不蒜子 - 极简网页计数器](http://busuanzi.ibruce.info/)
2. [不蒜子 - 不如](http://ibruce.info/2015/04/04/busuanzi/)
3. [静态博客添加访问统计功能 - 姑苏流白](https://blog.hgtweb.com/2018/busuanzi/)
4. [hexo页脚添加访客人数和总访问量 - Chris的博客](https://chrischen0405.github.io/2018/09/11/post20180911/)
5. [为博客增加建站时间显示](https://sillyli.com/webtime/)
