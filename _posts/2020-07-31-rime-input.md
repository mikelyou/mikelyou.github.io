---
layout: post
title: "Rime 输入法安装和使用指北"
subtitle: ''
date: 2020-07-31 16:37:00
author: "Mike Lyou"
#header-style: text
header-img: "img/post-bg-table.jpg"
mathjax: false
catalog: true
copyright-statement: CC BY-NC-SA
hidden: false
excerpt: 本文记录了 Rime（小狼毫）输入法的安装和调教方法，适合想要自己配置的用户。本文长期更新。
tags:
 - Software


---

<!-- more -->

**内容摘要**：本文全面、详细地介绍了 Rime（小狼毫）输入法的使用方法。

**适合的读者**：想要按照教程自己配置 Rime 输入法的用户。



![](https://i.imgur.com/3utln3J.png)

> 注：上图是 [@scomper](https://www.v2ex.com/member/scomper) 制作的效果示意图，原文请看 [这里](https://www.v2ex.com/t/303479)  
> 按照本文的指引，我们同样可以实现上面这些功能，且更加个性化。

## 1 Rime 输入法简介

**什么是 Rime 输入法？**

[RIME／中州韵输入法引擎](https://rime.im/download/)，是一个跨平台的输入法算法框架，它在不同平台上有不同的输入法前端实现。简单来说，Rime 是一个算法，基于这个产生了多个输入法实例，他们在不同平台上有不同的名字：

| 操作系统 | 名称 |
| ---- | ---- |
|    Windows  |  小狼毫    |
|    macOS   |   鼠须管、XIME   |
|   Linux   |   ibus-rime、fcitx-rime   |
|   Android   |   同文   |

**为什么使用 Rime 输入法？**

**Rime 输入法的优势在于它高度的可自定义化**。从外观，到按键设置、标点定制，还可以实现输入颜文字、希腊字母等奇葩操作。只要肯花一点时间，就可以让输入法变成我们想要的样子。

此外，我们不必再担心输入法的隐私问题，也不必和广告秦王绕柱了。总结起来就是三点：

- 高度可调教
- 保护隐私
- 无广告

Ps. 这里要吐槽一点， Rime 的帮助文档写的不是很好，让人一下子找不到要怎么配置和使用。我看了其他人写的介绍之后，才能看懂官方的文档。另外官方文档的语言是繁中和英文混杂，这让简中读者很痛苦，建议使用浏览器的翻译功能。

## 2 下载与安装

官方网站下载： [https://rime.im/](https://rime.im/)

RIME Github 页面：[https://github.com/rime](https://github.com/rime)

![](https://raw.githubusercontent.com/mikelyou/image-public/master/20200731195124.png)

在安装过程中，会依次弹出两个窗口，让我们选择输入方案和界面风格。这两个步骤以后也可以重新设置，所以不必过多纠结。选好了点击 `中` （所以这是河南话吗），再点击 `中`，然后就安装完成了。

安装成功后，理论上就已经可以使用了。 但是既然我们想要使用 Rime，一定是为了对齐进行自定义配置来提高使用体验。Rime 输入法具有很高的自由度，可以让我们在各方面进行自定义配置，让输入法无限贴近我们的需求。

下面我会先简要介绍 **繁简转换**、**添加输入方案** 和 **外观配置** 这几个多数人最急切需要了解的方法，然后再详细介绍各种其他配置方法。

## 3 基础配置

### 3.1 繁简转换

在启用输入法的情况下，按下 <kbd>Ctrl</kbd>+<kbd>~</kbd> 或 <kbd>F4</kbd> 调出 **方案选单**，选择想要进行繁简转换的输入法，然后选择 `漢字->汉字`可进行繁简切换。我们也可以选择 `中/半/漢` 对所有输入法进行繁简切换。

### 3.2 添加输入方案

Rime 默认的输入方案有很多，但如果你是五笔或双拼用户，就需要自己添加方案。以 *自然码双拼* 为例，方法如下：

1. 在 [Github](https://github.com/rime) 找到想要的方案，将其中的 `*.yaml` 文件下载下来，放到 **用户文件夹（见下）** 中
2. 在 **用户文件夹** 中新建 `default.custom.yaml` 文件并写入如下内容

```yaml
# default.custom.yaml
patch:
  schema_list:
    -schema: double_pinyin
```

> 注意：上述代码中，`patch:` 这一行在同一个文件中只需出现一次，如果有多处修改都包含此行，则只需保留一个，并按照相同缩进对其即可。**缩进很重要，请务必对齐。**

3. 通过开始菜单或托盘图标 **重新部署** 即可

其中，**用户文件夹** 的默认位置如下（如果你没有指定位置的话）：

```
【中州韻】 ~/.config/ibus/rime/
          ~/.config/fcitx/rime/
【小狼毫】 "%appdata%\Rime"
【鼠鬚管】 ~/Library/Rime/
```

### 3.3 外观设置

外观设置可以通过新建 `weasel.custom.yaml` 文件实现，放在 **用户文件夹** 目录下。

```yaml
# weasel.custom.yaml
patch:
  us_keyboard_layout: true                 # 键盘选项：应用美式键盘布局
  show_notifications_when: appropriate		# 状态通知，适当，也可设为全开（always）全关（never）

  style/color_scheme: luna                 # 选择配色方案
  style/horizontal: true                   # 候选窗横向显示
  style/inline_preedit: false              # 关闭内嵌编码，这样就可以显示首行的拼音
  style/corner_radius: 10                  # 窗口圆角半径
  style/border_height: 0                   # 窗口边界高度，大于圆角半径才有效果
  style/border_width: 0                    # 窗口边界宽度，大于圆角半径才有效果
  style/line_spacing: 1                    # 候选词的行间距
  style/spacing: 5                         # 在非内嵌编码模式下，预编辑和候选词之间的间距
  style/font_face: "Hiragino Sans GB W3"   # 字体名称
  style/font_point: 21                     # 字号
```

这个我没有详细研究，只修改了候选窗横向显示。

## 4 全局配置

### 2.1 候选词数量

Rime 默认的选词数量为 5，我们可以将其修改为其他数值。最多为10，十个候选词分别对应数字1~9和0。

在 **用户文件夹** 新建 `default.custom.yaml`文件，填写代码如下:

```yaml
# default.custom.yaml
patch:
  "menu/page_size": 10
```

### 2.2 方案选单热键

Rime 默认将 <kbd>Ctrl</kbd>+<kbd>~</kbd> 和 <kbd>F4</kbd> 作为方案选单的快捷键（或叫热键），这有时会和其他软件或游戏的快捷键发生冲突。为了解决这个让人裂开的问题，可以在 `default.custom.yaml` 中更改快捷键。（下文中 grave 键就是这个<kbd>~</kbd>或<kbd>\`</kbd>，也叫反引号键/Backquote键 ）

```yaml
# default.custom.yaml
patch:
  "switcher/hotkeys":
    - "Control+grave"
```

### 2.3 左<kbd>Shift</kbd> 键切换英文输入

这里直接参考的[致第一次安装RIME的你](https://www.zybuluo.com/eternity/note/81763)，讲道理没感觉有啥区别啊......但是肯定没有错！（其实完全不懂.jpg）

```yaml
# default.custom.yaml
patch:
  ascii_composer/good_old_caps_lock: true
  ascii_composer/switch_key:
    Caps_Lock: noop
    Shift_L: commit_code
    Shift_R: inline_ascii
    Control_L: clear
    Control_R: commit_text
```

### 2.4 以方括号 <kbd>[</kbd> <kbd>]</kbd> 来换页（有待补充所有快捷键）

```yaml
# default.custom.yaml
patch:
  key_binder/bindings:
    - when: paging
      accept: bracketleft
      send: Page_Up
    - when: has_menu
      accept: bracketright
      send: Page_Down
```

### 2.5 在特定程序里关闭中文输入

```yaml
# weasel.custom.yaml
patch:
    app_options/photoshop.exe:
      ascii_mode: true
    app_options/illustrator.exe:
      ascii_mode: true
```

## 5 输入方案配置

该部分以 *朙月拼音* 为例，其他输入方案同理。

举个例子，在下文中某处需要新建或修改 `luna_pinyin.custom.yaml` 文件，而我使用的是 *自然码双拼*，那么我需要操作的文件为 `double_pinyin.custom.yaml`。其他与特定输入法无关的文件，如 `mysymbols.yaml` ，则无需变动，直接按照文中所述进行操作即可。 [不知道输入方案对应的英文是什么？](https://gist.github.com/lotem/2309739)

### 5.1 定制标点符号

> [参考](https://github.com/rime/home/wiki/CustomizationGuide#%E4%B8%80%E4%BE%8B%E5%AE%9A%E8%A3%BD%E6%A8%99%E9%BB%9E%E7%AC%A6%E8%99%9F)

Rime 提供的标点符号非常全面，但是每个人的需求不同，一般用不到所有的符号，所以我们需要根据自己的需求进行定制。也有的用户习惯以 `/` 键输入标点「、」，这同样要通过定制标点符号实现。

以 *朙月拼音* 为例，输入方案中有以下设定：

```yaml
# luna_pinyin.schema.yaml
punctuator:
  import_preset: default
```

解释：

`punctuator` 是 Rime 中负责转换标点符号的组件。该组件会从设定中读取符号映射表，而知道该做哪些转换。  

`punctuator/import_preset` 是说，本方案要继承一组预设的符号映射表、要从另一个设定档 `default.yaml` 导入。

查看 `default.yaml` ，確有如下符号表：

```yaml
# default.yaml
punctuator:
  full_shape:
    "/" : [ ／, "/", ÷ ]
  half_shape:
    "/" : [ "/", ／, ÷ ]
```

可见按键 `/` 是被指定到 `"/", ／, ÷` 等一组符号了。 并且全角和半角状态下，符号有不同的定义。

欲令 `/` 键直接输出「、」，可如此定制 `luna_pinyin.custom.yaml`（如果没有需求的话，在全角状态和半角状态下使用相同的定义即可）:

```yaml
# luna_pinyin.schema.yaml
patch:
  punctuator/full_shape:
    "/" : "、"
  punctuator/half_shape:
    "/" : "、"
```

以上在输入方案设定中写入两组新值，合并后的输入方案成为：

```yaml
# luna_pinyin.schema.yaml
punctuator:
  import_preset: default
  full_shape:
    "/" : "、"
  half_shape:
    "/" : "、"
```

含义是，在由 `default` 导入的符号表之上，覆写对按键 `/` 的定义。

通过这种方法，既直接继承了大多数符号的默认定义，又做到了局部的个性化。

Ps. 如果要用 Backquote键（<kbd>\`</kbd>）输入 `·` ，会触发笔画什么东西（[参考](https://github.com/rime/squirrel/issues/102)），解决这个问题只需添加一行代码即可：

```yaml
# luna_pinyin.custom.yaml
patch:
    recognizer/patterns/reverse_lookup: {}
```

### 5.2 输入特殊符号

Rime 提供了极其丰富的特殊符号的输入方法，具体方案可以在 `symbols.yaml` 中查看。如果无法正常显示，尝试用浏览器或其他编辑器打开。

比如，使用 `/fh` 可以打出 ©, ⛽, ☈ 等许多或实用或意义不明的符号，使用 `/xl` 可以输出希腊字母 α，使用 `/mj` 可以输出麻将符号 🀅。~~可玩性极强~~

#### 5.2.1 解决 <kbd>/</kbd> 键与输入特殊符号的冲突

如果我们在 [定制标点符号](#定制标点符号) 定制了 <kbd>/</kbd> 的话，有可能会与特殊符号的输入冲突（如 `/fh ` ）：

- 如果这样定制 `"/" : "/"` ，那么由于按下 <kbd>/</kbd> 键后只有一个候选词 `/`，所以会直接上屏；
- 如果这样定制 `"/" : {commit: "/"}`，那么这段代码的意思就是 `/` 直接上屏.

无论哪种情况，都会造成 `/` 直接上屏而无法继续输入完整的 `/fh` ，因而也就无法输出特殊符号。我在查阅网络文章和 issues 时却很少见到有人提起这个问题，也不知道这是不是我自己的小众问题。

我找到的解决方法有两种：

##### 5.2.1.1 方法一：巧妙定义 <kbd>/</kbd> 键

这是我自己摸索出来的，也是较为推荐的方法。

在 `luna_pinyin.custom.yaml` 文件中按照如下方法定义 <kbd>/</kbd>：

```yaml
# luna_pinyin.schema.yaml
patch:
  punctuator/full_shape:
    "/": ["/","/"]
  punctuator/half_shape:
    "/": ["/","/"]
```

这样在打出 <kbd>/</kbd> 时就会出现候选框，但只有 `/` 一个选项。此时我们可以做两样事情：

1. 按空格即可输出单个字符 `/` ；
2. 继续输入  <kbd>f</kbd> <kbd>h</kbd> 即可使用 `/fh` 输出特殊符号。

![](https://raw.githubusercontent.com/mikelyou/image-public/master/20200809201131.png) ![](https://raw.githubusercontent.com/mikelyou/image-public/master/20200809201221.png)

##### 5.2.1.2 方法二：使用其他符号代替 `/` 作为开头

在这篇 [知乎专栏](https://zhuanlan.zhihu.com/p/91129641) 中，作者使用了不常用的 <kbd>i</kbd> 代替 <kbd>/</kbd>，使用 `ifh` 代替默认的 `/fh` 。同时需要在 `luna_pinyin.custom.yaml` 文件中将 `'recognizer/patterns/punct'` 的指向修改为 `"^i([A-Z|a-z]*|[0-9]|10)$"` :

```yaml
# luna_pinyin.schema.yaml
patch:
	"punctuator/import_preset": mysymbols
	'recognizer/patterns/punct': "^i([A-Z|a-z]*|[0-9]|10)$"
```

> 注1：上面两行中单引号与双引号作用相同，这里用不同的符号仅用作说明
>
> 注2：这 `^i([A-Z|a-z]*|[0-9]|10)$` 是一个正则表达式。[什么是正则表达式？](https://deerchao.cn/tutorials/regex/regex.htm)


同时还需要把 `mysymbols.yaml` 文件中将所有与 `/fh` 类似表达式中的 `/` 全部替换为 `i`，如下所示。因为实属大工程，作者提供了 [现成的代码](https://zhuanlan.zhihu.com/p/91301800) 供下载。

```yaml
# mysymbols.yaml
punctuator:
	symbols:
		'ifh': [ ©, ®, ℗, ℠, ™, ℡, ℻, ☇, ☈]
		#其他……
```

不过我总感觉姿势不太对。我也没有实践过~~，因为在折腾的途中就发现上面第一种方法了..~~.

### 5.3 添加自定义符号

由于 `symbols.yaml` 不能使用 `*.custom` 打补丁，我们需要这样操作：

1. 在 **用户文件夹** 新建文件 `mysymbols.yaml`（你可以自己决定）
2. 找到文件  `symbols.yaml` ，将文件内容全部粘贴至刚刚新建的 `mysymbols.yaml` 中
3. 将 `luna_pinyin.schema.yaml` 中 `'punctuator/import_preset'`指向改为 `mysymbols` （代码见下）
4. 按照已有的格式添加自定义内容

```yaml
# luna_pinyin.schema.yaml
patch:
	"punctuator/import_preset": mysymbols
```

> Ps. 其实也有人找到打补丁的方法，但似乎并不被推荐使用，[请看这里](https://github.com/rime/librime/issues/373)。

这是非常让人有成就感的部分，我们可以把能想到的任何东西添加进去。网络上应该也有很多现成的文档，可以搜索并选取喜欢的粘贴至文档中。



（有待补充...）

### 5.4 词库

> 请参考 [这篇文档](https://github.com/rime-aca/dictionaries)

#### 5.4.1 添加 Rime 的扩充词库

使用方法：

1.  下载词库 [https://github.com/rime-aca/dictionaries.git](https://github.com/rime-aca/dictionaries.git)

    注意到其中应该有六个文件：

    ```
    double_pinyin.custom.yaml
    luna_pinyin.custom.yaml
    luna_pinyin.hanyu.dict.yaml
    luna_pinyin.cn_en.dict.yaml
    luna_pinyin.extended.dict.yaml
    luna_pinyin.poetry.dict.yaml*
    ```

2.  将上述文件中后面五个移至你的 **用户文件夹** 底下

3.  若为双拼用户，请将 `double_pinyin.custom.yaml` 改名成你所使用的双拼方案的代码
    如 `double_pinyin_abc.custom.yaml`，并放入第二步所说的目录底下
    若该目录底下已有这个文件，那么将这两个文件中的内容 merge 即可

    附双拼方案与其对应的 id 一览表：

    | 输入方案    | id                  |
    | ----------- | ------------------- |
    | 自然码双拼  | double_pinyin       |
    | 智能ABC双拼 | double_pinyin_abc   |
    | 小鹤双拼    | double_pinyin_flypy |
    | MSPY双拼    | double_pinyin_mspy  |

4. 若为「朙月拼音」系列输入方案用户，请将补靪文档 `luna_pinyin.custom.yaml` 改名为你所使用的输入方案对应的 id。（比如朙月拼音·简化字方案，则将 `luna_pinyin.custom.yaml` 改名为 `luna_pinyin_simp.custom.yaml`）。

验证：切换到拼音或其他适用方案，输入「一介书生」（验证扩充词库之基本词库）、「一丈红」（验证扩充词库之汉语大词典词汇）、「疑是地上霜」（验证扩充词库之诗词词库）、输入「哆啦A梦（duo la a meng）」（验证扩充词库之西文词库，此子词库为朙月拼音系列方案专有，双拼方案不推荐使用）。

#### 5.4.2 增加自己的词库

在这个架构底下增加自己的词库相当容易，只需添加一个自订的 `*.dict.yaml` 文件，内容可以仿照 `luna_pinyin.extended.dict.yaml`，并于其中引入 `luna_pinyin.extended` 及相关字典档，例如：

```
# lazywei.dict.yaml
---
name: lazywei
version: "2015.1.10"
sort: by_weight
use_preset_vocabulary: true
import_tables:
  - luna_pinyin
  - luna_pinyin.extended
  - luna_pinyin.hanyu
  - luna_pinyin.poetry
...

这是我的词
```

接着再于 `*.schema.yaml` 或 `*.custom.yaml` 中将 `translator/dictionary` 设置成此字典档即可，例如：

```
patch:
  translator/dictionary: lazywei
```

如此，往后 `luna_pinyin.extended` 升级时并不会影响到这个 `lazywei.dict.yaml`，所以直接将所有文件覆盖即可。

### 5.5 同步

（有待补充...）

> - 同步词库和配置 
> - 安卓输入法
>
> https://www.zybuluo.com/eternity/note/81763

### 5.6 模糊音

（暂无需求，有待补充...）

## 6 工具和索引

这一部分列举了一些名词和链接，以供查询。这些内容如果放在正文中，则会导致篇幅过长，降低读者信心，故单独放在这里，并在必要时通过文内链接引用。

### 6.1 源文件目录和用户配置目录

软件文件和用户文件只会存放于 **源文件目录** 和 **用户配置目录(用户文件夹)** 两个地方，在配置过程中请注意不要混淆。

**源文件目录** 是位于软件安装目录下，升级或重装会被替换，用户不能修改，位置如下：

```
【中州韻】 /usr/share/rime\-data/
【小狼毫】 "安装目录\\data"
【鼠鬚管】 "/Library/Input Methods/Squirrel.app/Contents/SharedSupport/"
```

**用户配置目录**（本文使用 **用户文件夹** 这个称呼），是用来存放个人配置文件的地方，用户可以部分修改，位置可以由用户指定，默认位置如下：

```
【中州韻】 ~/.config/ibus/rime/
 ~/.config/fcitx/rime/
【小狼毫】 "%appdata%\\Rime"
【鼠鬚管】 ~/Library/Rime/
```

### 6.2  重新部署 

每当我们更改了配置文件，就要进行一次 **重新部署** 以使我们的更改生效，根据 [官方文档](https://github.com/rime/home/wiki/CustomizationGuide#重新佈署的操作方法) 的描述，重新部署的方法如下：

- 【中州韵】点击输入法状态栏上的 ⟲ (Deploy) 按钮 或：如果找不到状态栏，在终端输入以下命令，可触发自动部署：

```
touch ~/.config/ibus/rime/; ibus restart
```

- 【小狼毫】开始菜单→小狼毫输入法→重新布署；当开启托盘图标时，右键点选「重新布署」

- 【鼠须管】在系统语言文字选单中选择「重新布署」

对设置的修改于重新布署后生效。编译新的输入方案需要一段时间，此间若无法输出中文，请稍等片刻。

若部署完毕后，可以通过 <kbd>Ctrl</kbd>+<kbd>~</kbd> 或 <kbd>F4</kbd> 唤出方案选单，输入方案却仍无法正常使用，可能是输入方案未部署成功。请[查看日志文件](https://github.com/rime/home/wiki/RimeWithSchemata#%E9%97%9C%E6%96%BC%E8%AA%BF%E8%A9%A6)定位错误。

### 6.2 全角和半角字符

我们在中文环境下使用的`！` `？` `，` `。` `（` `）` 等都是全角字符，而英文的 `!` `?` `,` `.` `(` `)` 等为半角符号。

可能你不知道，英文字符也有全角的，比如 `Ｅｎｇｌｉｓｈ`。至于为什么，知乎上有[这个问题](https://www.zhihu.com/question/19605819) （~~及许多与其相似的重复问题~~）

要说有什么用的话，对于多数人来讲，已经没什么用了。

在打字界面按下 <kbd>Ctrl</kbd>+<kbd>`</kbd> 或 <kbd>F4</kbd> 即可进行全角和半角的切换

## 7 碎碎念

> 这段原本是开头来着，实在是 “赶动” 读者，就扔到最后了。搜狗还是比较好用的，如果没有广告的话。

我使用搜狗拼音很长时间了，也曾做过很多自定义的尝试，比如添加自定义词语、修改按键等，曾经还把希腊字母加入了输入方案。但是能够自定义的地方并不多，而且时不时弹出广告让人很烦，隐私问题则从来没有放过心，只能装作无事罢了。每次看到搜狗弹出广告，我就会去网上搜索一通，看看有没有解决方法。曾经看到过 “去广告版”的搜狗输入法，不过因为资源不多，而且资源是否安全也需要自行判断，一直都没有真正尝试过。

直到这两天，我又被弹广告了，然后灵光一闪——**为什么不找找开源的输入法看看呢？**

于是我找到了 Rime 输入法。

***

**本文长期更新。**

## 参考文献

1. [致第一次安装RIME的你](https://tieba.baidu.com/p/3288634121)（[排版较好的转载](https://www.zybuluo.com/eternity/note/81763) ）（[GitHub](https://github.com/halfmoonvic/Rime)）
2. [也致第一次安装Rime的你](https://xinlu.ink/tech/rime.html)
3. [中州韵（小狼毫，鼠须管）输入法设置](https://blog.yesmryang.net/rime-setting/)
4. [在Rime輸入方案選單中添加五筆、雙拼、粵拼、注音，保留你需要的](https://gist.github.com/lotem/2309739)
5. [安装及配置 Mac 上的 Rime 输入法——鼠鬚管 (Squirrel) ](https://www.dreamxu.com/install-config-squirrel/)
6. [「鼠须管」配置方案分享 - V2EX](https://www.v2ex.com/t/303479)

