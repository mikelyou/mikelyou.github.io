---
layout: post
title: "Python Learning #09 - Simple Application"
subtitle: 'learn to use, learn for use'
date: 2020-01-06 14:30:00
author: "Mike Lyou"
header-img: "img/post-bg-table.jpg"
copyright-statement: CC4.0
tags:
  - Python
  - Notes
---

After learning the [file operations](https://mikelyou.com/2020/01/03/python-learning-07-file-operations/) and [directory operations](https://mikelyou.com/2020/01/03/python-learning-08-directory-operations/), I eventually could use python to do some tasks.

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


## References

------------
