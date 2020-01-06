---
layout: post
title: "Python Learning #03 - Branch Structure"
subtitle: '分支结构 - if 语句'
date: 2020-01-02 15:00:00
author: "Mike Lyou"
header-style: text
tags:
  - Python
  - 学习笔记
---

<!-- more -->

#### 两分支 `If-Else` 语句
```python
if username == 'admin' and password == '123456':
    print('身份验证成功!')
else:
    print('身份验证失败!')
```

#### 多分支 `If-Elseif-Else` 语句
```python
x = float(input('x = '))
if x > 1:
    y = 3 * x - 5
elif x >= -1:
    y = x + 2
else:
    y = 5 * x + 3
```

#### 悬空Else分支
使用`pass`命令执行“不执行任何操作”
```python
x = float(input('x = '))
if x > 1:
    print(x)
else
    pass
```
**Attention**：尽量避免没有必要的嵌套，嵌套既影响可读性也增加bug出现概率

**Attention**: 同时注意，与Pascal不同，if和else语句末尾有冒号":"

------------
**Friendly reminder:** This series are my own study notes of **[Python-100-Days](https://github.com/jackfrued/Python-100-Days)**. I do not own copyright of some of the content. Nor is this a good tutorial of Python. I really appreciate it if you notice any mistakes or errors and tell me. Sorry that things copied from [Python-100-Days](https://github.com/jackfrued/Python-100-Days) will not be noted due to huge workload. **The whole series are not allowed to be reproduced**. View **[python-learning-readme](https://mikelyou.com/2020/01/02/python-learning-00-readme/)**.
