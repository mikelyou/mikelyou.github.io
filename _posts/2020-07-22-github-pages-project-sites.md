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
excerpt: 本文记录了GitHub Pages项目站点的创建、子域名的DNS配置和绑定方法。
tags:
 - GitHub Pages

---

<!-- more -->

今天突发奇想，想要尝试在自己仅有的一个 GitHub 账号下创建多个 GitHub Pages，并将其部署在子域名上。没想到在网上搜索了一下后，发现真的可以做到。本文记录了配置的过程，希望能帮助到有同样需求的人。阅读本文前，请确保你已经创建过自己的 GitHub Pages，如果没有可以参考我的[这篇博文](https://blog.mikelyou.com/2019/12/27/hello-world/)。

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

这里我新建的项目为`mikelyou.github.io/acg`。可以看到这个地址有点丑，而且地址对大小写敏感。我希望通过`acg.mikelyou.com` 这样更加美观的地址访问，那么就需要设置和绑定子域名。

## 绑定子域名

通常，当我们购买一个域名后，就可以使用它的子域名。子域名的数量、子域名长度的限制各个域名商会有所不同，我所使用的 Godaddy 每个域名可以添加最多 100 个子域名，每个子域名最长可达 25 个字符。还可以添加多层子域名， 例如，可以添加 **info.blog.coolexample.com** 以深入网站中更加具体的兴趣区域。总之就是根本用不完。

以我为例，我的域名为`mikelyou.com`，我希望使用`acg.mikelyou.com` 这个子域名。

1.  在项目仓库里新建一个`CNAME`文件，并将不带协议名的裸域名写进去（`acg.mikelyou.com`而不是`https://acg.mikelyou.com/`）
2.  去DNS服务商的网站，给对应的二级域名添加`CNAME`解析到`<username>.github.io`（和个人主页的相同）
    我的DNS服务商不是 Godaddy 而是是没见有人提的 **Hurricane Electric**，下面放了一张截图供各位参考。有文章使用的方法是添加`A`记录，不过我只看到一篇文章这么做，最好还是不要用，不成功的话检查一下其他步骤有没有错
3.  等待DNS生效，具体时间和服务商有关（十几分钟到几小时都有可能，清除浏览器缓存有时会有奇效）。
4.  成功后，可以通过更好看的 `acg.mikelyou.com` 地址访问到了项目站点了。

![](https://raw.githubusercontent.com/mikelyou/image-public/master/DNS-he-project-github-pages.png)

## 从模板快速开始

成功建立项目站点后，我便去寻找新的主题了，心想着找个萌萌的二次元主题，谁知道......

在网上用`anime` `acg` `二次元` `moe` `cartoon` 等多种关键词检索后，我只找到一两个相关的 `jekyll` 主题，你看看我都用到什么关键词了，网络上的二次元主题几乎等于没有啊。虽然我最后也没有使用它们，我决定在这里列举一下，有兴趣的读者可以去康康：

- [梦白的二次元主题](http://www.whiteg.cn/)  [GitHub页面](https://github.com/moewhite19/about)
- [WuK的主题](https://wu-kan.cn)  [GitHub页面](https://github.com/wu-kan/jekyll-theme-WuK)

没有用的主要原因是，发现需要安装新的依赖，和我之前用的模板差别很大。所以我在想不如直接用现在的博客作为模板，从**模板创建一个新的仓库**好了，这样就省去了很多安装和使用上的麻烦，所有在现有博客上的习惯都可以套用到新的项目上。

1. 打开有的博客仓库，`Settings` &rarr;勾选 `Template repository`
2. 回到仓库主界面，点击 `Use this template` 创建新的仓库，取名为`acg` ，建立站点时的仓库已经完成使命了可以删掉
3. 将仓库里的内容更换为新的博客的内容，使用和之前一样的方法更新博客。

>[从模板创建仓库](https://docs.github.com/cn/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template)类似于创建仓库的复刻，但存在一些重要差异：
>
>- 新的复刻包含父仓库的整个提交历史记录，而从模板创建的仓库从一个提交开始记录。
>- 对复刻的提交不会显示在您的贡献图中，而对从模板创建的仓库的提交会显示在您的贡献图中。
>- 复刻可能是向现有项目贡献代码的临时方式，而从模板创建的仓库可以快速启动新项目。


## 如何开启 https

> 本段内容参考了 [这篇文章](https://tzhou2018.github.io/2018/04/为GitHub-Pages自定义域名并添加SSL-开启HTTPS强制/)。

建立`acg.mikelyou.com` 站点后，我把之前的博客地址修改为 `blog.mikelyou.com` ，使得他们放在一起比较和谐。不过随后我注意到一个问题——我的两个博客 `blog.mikelyou.com` 和 `acg.mikelyou.com` 无法同时开启 `https`，其中有一个站点会被 Chrome 提示 `“链接是不安全的”` 。我很快找到了原因，是GitHub Pages本身的限制。上面提到的这篇文章，我只把相关的内容在这里简述一下，如果有不清楚的地方请去看原文。

首先，为什么要使用 https 协议？因为 https 协议提高网站访问安全性、目前越来越多的浏览器会判断当前站点支不支持https协议。

默认情况下使用GitHub Pages的给定域名则支持http和https两种协议，但是如果使用自定义域名的话，则只能通过`http://`访问，也就是说我们在`Github上搭建 Hexo 或Jekyll 主题博客`后，通过`CNAME`绑定个人域名后，我们只能通过`http://`域名来访问。如果访问`https://XXX.github.io/`(即原来的GitHub Pages域名)将会被重定向到`我们的自定义域名`。但若直接访问`https://我们的自定义域名`，浏览器会报`SSL_DOMAIN_NOT_MATCHED`警告。

那么怎么给自己的域名加上`https`呢？这篇文章的作者使用了 [CloudFlare](https://www.cloudflare.com/) 的`免费的https服务`。

[CloudFlare](https://www.cloudflare.com/) 是一家CDN提供商，它提供了`免费的https服务`(但不是应用SSL证书)。实现模式就是，用户到CDN服务器的连接为`https`，而CDN服务器到GithubPage服务器的连接为`http`，就是在CDN服务器那里加上反向代理。

1. 注册并登录CloudFlare，并将自己域名下的`name server`修改为CloudFlare的`name server`。
2. 在CloudFlare的DNS设置域名匹配到自己的GithubPage(启用动态DNS加速)。
3. 在CloudFlare的`Crypto`设置SSL为`Flexible`(等待一定时间实现建立连接后，就可以通过`https`来访问自己的 GithubPage )。
4. 在CloudFlare的`Page Rules`中设置路由规则。一般情况下，利用`Always use https`设置规则，规则链接为`http://域名/*` , 这样就可以把 `http` 链接强制转换为 `https`。

![](https://raw.githubusercontent.com/mikelyou/image-public/master/cloudflare-page-rules.png)

> 上面第一条规则是因为我的 `blog` 站点原本使用的地址是 `mikelyou.com` 根域名，添加这条规则可以让原来的地址依然可以访问，直接跳转到新的博客地址。（一共三个免费规则正好被我用完）

![](https://raw.githubusercontent.com/mikelyou/image-public/master/cloudflare-dns.png)

上图为新的 DNS 配置，前文的 He 的 DNS 服务不再使用。

于是在这个过程中，我把 DNS 服务商也换了，然后发现 CloudFlare 比之前用的 [Hurricane Electric](https://dns.he.net/) 好用多了，而且还提供很多其他免费功能，我觉得 Google Analytics 也可以被这个替代了。

> 本文亦转载于 [知乎](https://zhuanlan.zhihu.com/p/183977963) 、[简书](https://www.jianshu.com/p/556e9b661064) 和 [微信公众号](https://mp.weixin.qq.com/s?__biz=MzAxMjgzMjUzMg==&mid=2652035251&idx=1&sn=fd4da473279fbb15fde61a5bd04207b7&chksm=804da2c8b73a2bded670e8e93fef0204f7a750ce22959d45f4d78f0f7da6a66b17fbf768da17&scene=126&sessionid=1597417045&key=afadcd447ba5fcc05abc2e99eaf8f59210ce306f36c44994f81af96f783603161c969d4a38e178af3a5e863adb8aefa37c5dfda0c3c8f9a86ea6b29f76a3c2ef7cc3c1d5bc6b1f7665cd4367540a9e557f3611fd10d1f01434aa23455dafb8b03183b99864eabec7f9c50cb07326ab82187524d1d59d7bcc580b8ddc9e2348e8&ascene=1&uin=MTU1MTU4MzkzNw%3D%3D)

## 参考文献 

1. [单个GitHub帐号下添加多个GitHub Pages的相关问题](https://segmentfault.com/a/1190000003946969)
2. [GitHub Pages 自定义域名实践整理](https://segmentfault.com/a/1190000018038675)
3. [About custom domains for GitHub Pages sites](https://help.github.com/articles/about-custom-domains-for-github-pages-sites/)
4. [User, Organization, and Project Pages](https://help.github.com/articles/user-organization-and-project-pages/)
5. [二级域名解析使用](https://blog.csdn.net/LD0807/article/details/54356876)(使用`A`记录的就是这篇)
6. [为GitHub-Pages自定义域名并添加SSL-开启HTTPS强制](https://tzhou2018.github.io/2018/04/为GitHub-Pages自定义域名并添加SSL-开启HTTPS强制/)


