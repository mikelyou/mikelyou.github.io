---
layout: post
title: "如何拥有多个GitHub Pages"
subtitle: 'GitHub Pages 项目站点及绑定子域名的方法记录'
date: 2020-07-22 18:49:00
author: "Mike Lyou"
header-style: text
#header-img: "img/dream-catcher-902508_1920.jpg"
mathjax: false
catalog: true
copyright-statement: CC BY-NC-SA
hidden: false
excerpt: 本文记录了GitHub Pages项目站点的创建、子域名的DNS配和绑定方法。
tags:
 - GitHub Pages

---

<!-- more -->

今天突发奇想，想要尝试在自己仅有的一个GitHub账号下创建多个GitHub Pages，并将其部署在子域名上。没想到在网上搜索了一下后，发现真的可以做到。本文记录了配置的过程，希望能帮助到有同样需求的人。阅读本文前，请确保你已经创建过自己的 GitHub Pages，如果没有可以参考我的[这篇博文](https://mikelyou.com/2019/12/27/hello-world/)。

## 场景再现

搭建了自己的第一个GitHub Pages页面后，可能很多人会有和我一样的想法——**搭建多个GitHub Pages页面**。这些新的页面可以作为博客页面的demo，也可以用来放一些不想放在主要博客的内容（比如ACG相关、日常生活，当然也有人不介意放在一起）。

但是我以前一直以为，~~**每个GitHub账户只能拥有一个GitHub Pages页面**~~，所以这个想法一直没有实施。后来发现其实不是这样的。正确的说法是这样的——**我们只能为每个 GitHub 帐户创建一个用户或组织站点；而项目站点没有限制**。

我所认为的只能拥有一个的，是个人站点，也就是名为 `<user>.github.io` 的仓库。**想要创建更多的GitHub Pages页面，可以通过创建项目站点实现。**项目站点的数量没有限制。

[GitHub Pages 站点的类型](https://docs.github.com/cn/github/working-with-github-pages/about-github-pages#)对此有清晰的说明，这里我把关键段落抄了过来：

***

有三种类型的 GitHub Pages 站点：项目、用户和组织。 项目站点连接到 GitHub 上托管的特定项目。 用户和组织站点连接到特定的 GitHub 帐户。

要发布用户站点，必须创建名为 `<user>.github.io` 的用户帐户所拥有的仓库。 要发布组织站点，必须创建名为 `<organization>.github.io` 的组织所拥有的仓库。 除非您使用自定义域，否则用户和组织站点位于 `http(s)://<username>.github.io` 或 `http(s)://<organization>.github.io`。

项目站点的源文件与其项目存储在同一个仓库中。 除非您使用自定义域，否则项目站点位于 `http(s)://<user>.github.io/<repository>` 或 `http(s)://<organization>.github.io/<repository>`。

您只能为每个 GitHub 帐户创建一个用户或组织站点。 项目站点（无论是组织还是用户帐户拥有）没有限制。


## 创建项目

1. 新建一个仓库，名称随意。
2. 进入仓库主页，点击右面的`Settings`，找到**GitHub Pages**部分，选择`Launch automatic page generator`\>`Continue to layouts`\>`Publish page`即可。（注意这里需要选择一个主题，之后可以再改，不选择的话页面可能会无法加载，显示`“There isn't a GitHub Pages site here.”`）
3. 建议勾选 `Enforce HTTPS`，否则访问时会出现安全警告。
4. 没有出错的话，一个项目主页就建立完成了，可以通过`<username>.github.io/<projectname>`访问到了

这里我新建的项目为`mikelyou.github.io/ACG`。可以看到这个地址有点丑，而且地址对大小写敏感。我希望通过`acg.mikelyou.com` 这样更加美观的地址访问，那么就需要设置和绑定子域名。

## 绑定子域名

通常，当我们购买一个域名后，就可以使用它的子域名。子域名的数量、子域名长度的限制各个域名商会有所不同，我所使用的 Godaddy 每个域名可以添加最多 100 个子域名，每个子域名最长可达 25 个字符。还可以添加多层子域名， 例如，可以添加 **info.blog.coolexample.com** 以深入网站中更加具体的兴趣区域。总之就是根本用不完。

以我为例，我的域名为`mikelyou.com`，我希望使用`acg.mikelyou.com` 这个子域名。

1.  在项目仓库里新建一个`CNAME`文件，并将不带协议名的裸域名写进去（`acg.mikelyou.com`而不是`https://acg.mikelyou.com/`）
2.  去DNS服务商的网站，给对应的二级域名添加`CNAME`解析到`<username>.github.io`（和个人主页的相同）
    我的DNS服务商不是 Godaddy 而是是没见有人提的 **Hurricane Electric**，下面放了一张截图供各位参考。有文章使用的方法是添加`A`记录，不过我只看到一篇文章这么做，最好还是不要用，不成功的话检查一下其他步骤有没有错
3.  等待DNS生效，具体时间和服务商有关（十几分钟到几小时都有可能，清除浏览器缓存有时会有奇效）。
4.  成功后，可以通过更好看的 `acg.mikelyou.com` 地址访问到了项目站点了。

![](https://raw.githubusercontent.com/mikelyou/image-public/master/DNS-he-project-github-pages.png)

## 参考文献

1. [单个GitHub帐号下添加多个GitHub Pages的相关问题](https://segmentfault.com/a/1190000003946969)
2. [GitHub Pages 自定义域名实践整理](https://segmentfault.com/a/1190000018038675)
3. [About custom domains for GitHub Pages sites](https://help.github.com/articles/about-custom-domains-for-github-pages-sites/)
4. [User, Organization, and Project Pages](https://help.github.com/articles/user-organization-and-project-pages/)
5. [二级域名解析使用](https://blog.csdn.net/LD0807/article/details/54356876)(使用`A`记录的就是这篇)
