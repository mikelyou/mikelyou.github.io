---
layout:     post
title:      "Hodgepodge"
subtitle:   "一些杂乱的笔记"
date:       2020-01-02 10:30:00
author:     "Mike Lyou"
header-img: "img/post-bg-2015.jpg"
#excerpt: Some tips.
mathjax: true
catalog: true
tags:
  - Blog
---

Some tips discoverd. Write down for later usage. You maybe find something not clear, it is normal since it is for myself. If something is good, a new post will be published.

<!-- more -->

## Hide posts at homepage

Using `hidden: true` at post head can hide the post at homepage, but it's still aviable at archive, and can be reached through link from neighboring posts.

Using `published: false` can totally exclude it from website.

## Image caption

I want to write credit when I use images from elsewhere, which includes author and url. This issue was partly solved by [this post](https://superdevresources.com/image-caption-jekyll/).

Includes a new file named `image.html` which presents as below

<!-- {% raw %} -->
```
<!-- _includes/image.html -->
<div class="image-wrapper" >
    {% if include.url %}
    <a href="{{ include.url }}" title="{{ include.title }}" target="_blank">
    {% endif %}
        <img src="{{ site.url }}/{{ include.img }}" alt="{{ include.title }}"/>
    {% if include.url %}
    </a>
    {% endif %}
    {% if include.caption %}
        <p class="image-caption">{{ include.caption }}</p>
    {% endif %}
</div>
```
<!-- {% endraw %} -->

Add new ccs style
```
.image-wrapper {
    text-align: center;

    .image-caption {
        color: $grey-color;
        margin-top: $spacing-unit / 3;
    }
}
```

And write in post like This
<!-- {% raw %} -->
```
{% include image.html
            img="images/myimage.jpg"
            title="title for image"
            caption="caption for image"
            url="http://example.com" %}
```
<!-- {% endraw %} -->

Many answers I found think for sure that I know how css files work, but I didn't. Now I kinda understand.

You can find `bootstrap.css` and `bootstrap.min.css` under `/css` directory. If you use theme from others, there may be another two `sometheme.css` and `sometheme.min.css`. You can add the css style directly into one of the `*.css` file, or create a new `sample.css` and add it.

You maybe notice `*.min.css` is hard to read, that is because`*.min.css` file is minified `*.css` file, which removes unassary space and other stuffs. Their functions are identical, but `*.min.css` has better efficiency. If you use theme from others, they usually use `*.min.css` rather than `*.css`. So you when you have made up your `*.css` file, you should use [css minifier](https://cssminifier.com) or other tools to generate a `*.min.css` file.

If you create a new `*.css` file, you should also include it in `head.html`.
<!-- {% raw %} -->
```
<link rel="stylesheet" href="{{ "/css/sample.min.css" | prepend: site.baseurl }}">
```
<!-- {% endraw %} -->

Things have'n solved are:

1. Not work for header images.
2. Need to use Liquid.


Here is [another method](https://stackoverflow.com/questions/19331362/using-an-image-caption-in-markdown-jekyll/48137036#48137036), not beautiful though.

## Enable Catalog

Trying to add catalog myself for so long, I should found that this function was already achieved in Hux's blog too. (Orz...) It is written in `post.html`

Just add the follwing line can enable catalog, which floats at right side.
```
catalog: true
```

However, when the catalog is too long, a scroll bar will appear, which is not beautiful.

And the 1,2,3 heading has the same style, 4-6 has the same as well.

By the way, the style of link inside posts is [Enable Catalog](#enable-catalog)

```
[Enable Catalog](#enable-catalog)
```

## How to write math using Latex grammar (mathjax)

It is already embaded in Hux's blog. Add `mathjax: true` to enable it.

Note that this effect is different from `## Atom plugin (irrelavent)`. That one aims to write math directly in atom, and read, has nothing to do with blog.

Using the following line
```
$$ S = \int_{a}^b f(x) \mathrm{d}x = F(b) - F(a) $$
```
to show

$$ S = \int_{a}^b f(x) \mathrm{d}x = F(b) - F(a) $$

[temp-post-test-math](https://mikelyou.com/2016/05/19/test-math/)

## 右键管理（无关话题）
顺路看到的，顺手收拾了一下右键餐单。

有机会也许可以自己总结一下。目前没有看到可以直接收藏的文章。

参考：

- [自己就是右键管家](https://blog.csdn.net/win_turn/article/details/75212969) （这篇主要讲如何删除`新建`餐单内容）
- [zhihu](https://www.zhihu.com/question/55836048/answer/695435047)（主要讲主要菜单）
- [CSDN](https://blog.csdn.net/Sdnu08gis/article/details/99691621)（讲到如何添加新的`新建`）


## Atom plugin (irrelavent)
Added `markdown-preview-plus` to enable writing math equations with LaTeX. Eg. $\mu$

$$ S = \int_{a}^b f(x) \mathrm{d}x = F(b) - F(a) $$

But keep in mind, that this only enables math equations, sentences such as `\begin{equation}` has no function.

If you don't need the equation numbers, just use `$+symbol+$` or `$$the equation$$` to have the same outcomes at both Atom and website.

Ref: [&rarr;简书](https://www.jianshu.com/p/6b54e2eb9ae2)

By the way, I found another article, which proved irrelavent with my concern. It can make you write pure LaTeX document in `Plan Text`. The article [&rarr;知乎](https://zhuanlan.zhihu.com/p/35929936)

## Copyright statement

Since every posts may have different copyright statements. I added the `copyright-statement.html`. By this way, it is easier to make statement and make updates. Detailed changes are as below.

- Added `copyright-statement.html`.
- Included `copyright-statement.html` in `post.html`.
- New variable at post head. Example:

```
copyright-statement: CC BY-NC
```

If not stated, it shows default statement.

## Back-to-top button

Powered by [vanilla-back-to-top](https://github.com/vfeskov/vanilla-back-to-top/tree/v7.2.1). Thanks for that.

- Included `back-to-top.html` in `default.html`.

- Downloaded `vanilla-back-to-top.min.js`.


## 解决花括号在 Jekyll 被识别成 Liquid 代码的问题

在解决 [#Add Valine comment block](#Add-Valine-comment-block) 时遇到的。

最简单的方法
![](\img\in-post\post-liquid-raw-01.png)

更好的方法（？）
![](\img\in-post\post-liquid-raw-02.png)

为什么上面直接放图了呢？因为我直接这样写的话 `raw` 和 `endraw` 并不会显示，  
那么要怎么写才能显示上面的代码呢？（[禁止禁止禁止禁止禁止禁止禁止禁止套娃！](https://zh.moegirl.org/zh-hans/禁止套娃)）

Ref:
- [在Jekyll的markdown代码块中转义双大括号](https://stackoom.com/question/1d89y/在Jekyll的markdown代码块中转义双大括号)


## Add Valine comment block

I've struggled adding Disqus for a long time, but still nothing achieved. Though not decide to give up Disqus, I found Valine, and sucessfully add it to my blog in only one hour.

In `_config.yml` write this
```
# Valine settings
valine_appId: your AppID
valine_appKey: your AppKey
```

In `_post.html` write this

<!-- {% raw %} -->
```
{% if site.valine_appId %}
  {% if page.comments %}
  <!--valine comment function (mikelyou)-->
  <script src="//cdn1.lncld.net/static/js/3.0.4/av-min.js"></script>
  <script src='//unpkg.com/valine/dist/Valine.min.js'></script>
  <div id="comment"></div>
  <!--valine comment function end (mikelyou)-->
  {% endif %}
{% endif %}
```
<!-- {% endraw %} -->

and

{% raw %}
```
{% if site.valine_appId %}
<!--载入js，在</body>之前插入即可-->
<script>
    var valine = new Valine();
    valine.init({
        el:'#comment',
        appId:'{{site.valine_appId}}',
        appKey:'{{site.valine_appKey}}',
        notify:false,
        path: '{{ page.url }}',
        placeholder:'Write comments here~'
    })
</script>
<!--valine comment function end-->
{% endif %}
```
{% endraw %}

where Disqus and netease_comment code appears.

And we can enable it by insert the following line at the post's head.
```
---
comments: true  # defalut == false
---
```

Ref:
- [Valine Official](https://valine.js.org)
- [jekyll 添加 Valine 评论](https://blog.csdn.net/lindexi_gd/article/details/83176116) (brief and effective)
- [Valine: 独立博客评论系统](https://deserts.io/diy-a-comment-system/)
- [Valine Admin 配置手册](https://deserts.io/valine-admin-document/)
- [Valine评论系统](https://www.oukohou.wang/2018/12/18/notices-for-jekyll-themes-fork/#4-valine评论系统) (good example)


## Insert catalog

Solved in [#Enable Catalog](#enable-catalog). No need to read this part.

It is eazy to insert catalog in jekyll.

Simply write the following line where you want to display the catalog:
```
*  
{:toc}
```

If you don't want some heading to show. Add the following line below that heading.

```
## Catalog <!--I dont want it appears in itself-->
{:.no_toc}

*  
{:toc}
```

Ref:
- [给JEKYLL的文章添加目录](http://www.zhengjiachao.com/topics/github.io/add-outline-on-jekyll-post.html)


## Customized excerpts

The excerpts (or abstract) will appear at the list of posts, and those auto-generated excerpts are not so beautiful.
Here are two ways to customize the excerpts.

#### Way-1: Adding `excerpt` variable.

Adding the following line in `_config.yml`.

```
excerpt_separator:  '<!-- more -->'
```

<!-- {% raw %} -->
Go to `index.html`, change `{{ post.content }}` to

```
{{ post.excerpt }}
```
<!-- {% endraw %} -->

Now we can set the end of auto-generated excerprt by adding `<!-- more -->` in our posts，like this:

```
---
layout:     post
title:      "Tips"
<!-- And Many things -->
#excerpt: Write your excerpt here.
---

The excerpt.

<!-- more -->

The main content.
```

The excerpt shows at homepage will be:
```
The excerpt.
```
#### Way-2: Write it directly in posts.

You may notice there is an `excerpt` variable in the head of the example post above.

We can simply write our excerpts there. And this will **disable auto-generated excerpts**.

```
excerpt: Write your excerpt here.
```

And it will show like this:

```
Write your excerpt here.
```

#### Trivia

If you declear `excerpt_separator` at `_config.yml`, and declear `excerpt` at head of posts at the same time, the later one will be in effect.

Ref:
- [使用Jekyll官方的ReadMore摘要功能](https://blog.coderzh.com/2015/08/15/JekyllReadMore/)
- [Jekyll文章列表摘要设置](https://moonagic.com/configure-the-jekyll-article-list-summary/)


## 修复双重滚动条的bug
因为Hux自己的博客一直在修改，稳定的模板现在已经比他的博客落后很多个版本，而在这过程中发现甚至已经解决的问题依然存在在模板里。

这时候，有两种方法都可以尝试：一、看看Hux本人最新的模板添加了什么内容，看看版本更新日志，如果版本差异太大，考虑直接复制新模板；二、查看issue里有没有同样的问题。

双重滚动条的问题就在[#issues](https://github.com/Huxpro/huxpro.github.io/issues/123)被解决过了，解决方法也很简单。

## 如何预览草稿

这里直接参见[官方文档](http://jekyllcn.com/docs/drafts/)。如果看不太懂，我来翻译一下：


- 第一步：你需要在网站根目录下创建一个名为`_drafts`文件夹（因为`_posts`也是在根目录下的，所以`_drafts`理应与`_posts`同级），把草稿放入这个文件夹下。

```
|-- _posts/
|-- _drafts/
|   |-- a-draft-post.md
```

- 第二步：运行`jekyll serve --drafts`即可（或`jekyll build --drafts`）

```
jekyll serve            # 普通的 jekyll 服务器搭建
jekyll serve --drafts   # 显示草稿的 jekyll 服务器搭建
```
