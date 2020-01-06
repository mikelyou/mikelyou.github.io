---
layout: post
title: "Python Learning #09 - Simple Application"
subtitle: 'learn to use, learn for use'
date: 2020-01-06 14:30:00
author: "Mike Lyou"
header-img: "img/post-bg-table.jpg"
tags:
  - Python
  - Notes
---

After learning the file and directory operations, I eventually could try to use python to solve some tasks.

<!-- more -->

This article may be updated for a long time, recording useful applications.


## Catalog：
{:.no_toc}

*  
{:toc}

## Replace single string in multiple markdown files

The first thing I wanna do is replacing all Chinese tags in my posts to English ones. In particular, I wanna replace all `学习笔记` with `Notes` in 10 posts.

The code is posted below.

```python
# Ref: https://blog.csdn.net/shenxian1021/article/details/81873845
import os
import io
import fnmatch


def alter(file,old_str,new_str):  # replace string in a file
    file_data = ""
    with io.open(file, "r", encoding="utf-8") as f:
        for line in f:
            if old_str in line:
                line = line.replace(old_str,new_str)
            file_data += line
    with io.open(file,"w",encoding="utf-8") as f:
        f.write(file_data)

def main():
    basepath = "E:/GitHub/mikelyou.github.io/_posts"  # Attention: '/', not '\'
    with os.scandir(basepath) as entries:
        for entry in entries:
            if fnmatch.fnmatch(entry,'*.md'):         # select all *.md files
                    alter(entry,"学习笔记","Notes")   # the string to replace

if __name__ == '__main__':
    main()
```

Here is the results. I successfully replace all `学习笔记` tags with `Notes`.

![](/img/in-post/post-python-replace-strings.png)

This would be a very useful tool. Oh my god, I finally made it!

------------
>Statement:This python learning series are posted only for personal studies and communication. The whole series are not allowed to be reproduced.I do not own copyright of some of the content. If any post accidentally infringes your copyright, it will be removed shortly after being informed. View **[python-learning-readme](https://mikelyou.com/2020/01/02/python-learning-00-readme/)** for more information.
