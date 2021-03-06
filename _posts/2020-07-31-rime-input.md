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

观前提示：本文部分内容可能过于详细，初次使用 Rime 的读者可以大胆跳过太长、太复杂的内容。读者亦可通过右侧目录和 Ctrl+F 搜索关键词，查找特定内容。

***



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

此外，我们不必再担心输入法的 ~~**隐私问题**~~ ，也不必和 ~~**广告**~~ 秦王绕柱了。

> Ps.  Rime 的帮助文档写的不是很好，让人一下子找不到要怎么配置和使用。我看了其他人写的教程之后，才能看懂官方的文档。另外官方文档的语言是繁中和英文混杂，这让简中读者很痛苦，建议使用浏览器的翻译功能。

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

**第一步**：在 [Github](https://github.com/rime) 找到想要的方案，将其中的 `*.yaml` 文件下载下来，放到 **用户文件夹（见下）** 中

第二步：在 **用户文件夹** 中新建 `default.custom.yaml` 文件并写入如下内容

```yaml
# default.custom.yaml
patch:
  schema_list:
    -schema: double_pinyin
```

> 注意：上述代码中，`patch:` 这一行在同一个文件中只需出现一次，如果有多处修改都包含此行，则只需保留一个，并按照相同缩进对其即可。**缩进很重要，请务必对齐。**

**第三步**：通过开始菜单或托盘图标 **重新部署** 即可

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

### 2.3 中英文切换

中西文切换键的默认设置写在 `default.yaml` 里面，我们可以通过 `default.custom.yaml` 在全局范围重定义该组快速键（请看 [官方示例](https://gist.github.com/lotem/2981316) ）.

**可用的按键**有 <kbd>Caps_Lock </kbd>  <kbd>Shift_L</kbd>  <kbd>Shift_R</kbd>  <kbd>Control_L</kbd>  <kbd>control_R</kbd>；而 Mac 系统上的鼠须管不能区分左、右，因此只有对<kbd>Shift_L</kbd>  <kbd>Control_L</kbd> 的设定起作用.

**已输入编码时按切换键**（也就是打字打了一半的时候，按上面列举的按键），可选的临时切换策略有三：

- `inline_ascii` 在输入法的 **临时西文编辑区** 内输入字母、数字、符号、空格等，回车上屏后 **自动复位** 到中文
- `commit_text` 已输入的 **候选文字** （也即中文）上屏并切换至西文输入模式
- `commit_code` 已输入的 **编码字符** （也即英文）上屏并切换至西文输入模式
- 设为 `noop`，屏蔽该切换键
- 设为 `clear`，清除已输入的编码

有的用户喜欢设置的比较复杂，把每个键位都用上。但对我来说，默认方案已经足够，如下：

```yaml
# default.yaml
  ascii_composer/good_old_caps_lock: true
  ascii_composer/switch_key:
    Caps_Lock: commit_code
    Control_L: noop
    Control_R: noop
    Shift_L: commit_code
    Shift_R: commit_code
```

上面第一行的意思是：按下 Caps Lock 会切换到英文模式，默认输出大写字母（值为 `false` 则默认输出小写字母，为 `noop` 则无操作）

下面几行的意思是，在已输入编码时，按下对应的按键有不同的效果：

- Caps Lock、左右Shift：已输入编码字符上屏，也就是英文字母上屏
- 左右Control 无操作

在这种设置下，我们在不同输入模式下按不同键的效果为（为了更加直观，表格中以 ENGLISH 和 english 表示英文大写和英文小写）：

| 输入模式 | 按键                  | 效果                                        |
| -------- | --------------------- | ------------------------------------------- |
| 中文     | <kbd>Caps_Lock </kbd> | 切换至 ENGLISH 输入模式，已输入编码直接上屏 |
| 中文     | <kbd>Shift </kbd>     | 切换至 english 输入模式，已输入编码直接上屏 |
| ENGLISH  | <kbd>Caps_Lock </kbd> | 切换至 **中文** 输入模式                    |
| ENGLISH  | <kbd>Shift </kbd>     | 无操作（注：希望能够切换大小写，之后研究）  |
| english  | <kbd>Caps_Lock </kbd> | 切换至 ENGLISH 输入模式                     |
| english  | <kbd>Shift </kbd>     | 切换至 **中文** 输入模式                    |

我顺便把另外几个按键也整理了以下：

| 输入模式 | 按键  | 效果                                     |
| -------- | ----- | ---------------------------------------- |
| 中文     | Space | 候选文字直接上屏（也即通常的打字模式）   |
| 中文     | Enter | 已输入编码直接上屏，保持中文输入模式不变 |
| 中文     | Esc   | 清除编码                                 |

设置好这一部分，我们就可以开心的随时切换中英文打字了。

### 2.4 以方括号 <kbd>[</kbd> <kbd>]</kbd> 来换页

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

在一些终端、代码编辑器或快速启动工具等程序中，中文很少会用到，那么我们可以在这些程序里默认关闭中文输入。还有在很多游戏中，默认关闭中文输入可以避免 “想前进，却在屏幕上打出一长串 W” 的窒息操作 。

比如下面的例子，我们希望在 Photoshop 和 Illustrator 中默认关闭中文输入。

```yaml
# weasel.custom.yaml
patch:
    app_options/photoshop.exe: # 程序名字全用小寫字母
      ascii_mode: true
    app_options/illustrator.exe: # 如果有多个程序，按照这个格式补充
      ascii_mode: true
```

程序的名称一般为 `*.exe`，如果不知道，可以通过快捷方式的右键菜单中的 “打开文件所在位置 ” 找到；也可以通过任务管理器查看正在运行的程序。

## 5 输入方案配置

该部分以 *朙月拼音* 为例。

**请读者注意：如果你使用的不是 *朙月拼音* ，那么下文中出现 `luna_pinyin.custom.yaml` 文件的地方，请替换为相应文件。** 搞清楚这一点很重要，因为你可能会同时拥有上述两种文件，如果对错误的文件进行了修改，可能就不起作用。[不知道输入方案对应的英文是什么？](https://gist.github.com/lotem/2309739)

举个例子，我使用 *自然码双拼*，对应的文件为 `double_pinyin.custom.yaml`。在下文中任何要修改 `luna_pinyin.custom.yaml` 的地方，操作对象换为 `double_pinyin.custom.yaml`。

其他文件则按照文中所述进行操作即可。 

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

- `punctuator` 是 Rime 中负责转换标点符号的组件。该组件会从设定中读取符号映射表，而知道该做哪些转换。  

- `punctuator/import_preset` 是说，本方案要继承一组预设的符号映射表、要从另一个设定档 `default.yaml` 导入。

查看 `default.yaml` ，確有如下符号表：

```yaml
# default.yaml
punctuator:
  full_shape:
    "/" : [ ／, "/", ÷ ]
  half_shape:
    "/" : [ "/", ／, ÷ ]
```

可见，在默认方案中，按键 `/` 是被指定到 `"/", ／, ÷` 等一组符号了。，并且全角和半角状态下，符号有不同的定义。

欲令 `/` 键直接输出「、」，我们要做的事情，是定制 `luna_pinyin.custom.yaml`：

```yaml
# luna_pinyin.custom.yaml （或相应文件）
patch:
  punctuator/full_shape:
    "/" : "、"
  punctuator/half_shape:
    "/" : "、"
```

其中，关于半角和全角符号，我个人只用半角符号，所以只需更改半角符号即可。或者为了避免迷惑，可以对半角和全角使用一致的定义。如果你忘记了，<kbd>Ctrl</kbd>+<kbd>\`</kbd> 可以设置半角/全角。

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
# luna_pinyin.custom.yaml  （或相应文件）
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

#### 5.2.2 emoji

[rtransformation/rime-opencc_emoji_symbols](https://github.com/rtransformation/rime-opencc_emoji_symbols) （双拼下部分emoji无法拼写）



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

4. 若为「朙月拼音」系列输入方案用户，请将补丁文档 `luna_pinyin.custom.yaml` 改名为你所使用的输入方案对应的 id。（比如朙月拼音·简化字方案，则将 `luna_pinyin.custom.yaml` 改名为 `luna_pinyin_simp.custom.yaml`）。

验证：切换到拼音或其他适用方案，输入「一介书生」（验证扩充词库之基本词库）、「一丈红」（验证扩充词库之汉语大词典词汇）、「疑是地上霜」（验证扩充词库之诗词词库）、输入「哆啦A梦（duo la a meng）」（验证扩充词库之西文词库，此子词库为朙月拼音系列方案专有，双拼方案不推荐使用）。

#### ~~5.4.2 增加自己的词库~~

> **本段暂时失效，本人按照 [5.4.3](#543-增加自己的词库) 方法操作。** 

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

#### 5.4.3 增加自己的词库

仿照已有词典，新建词典文件，如 `mikelyou.dict.yaml` ，写入以下代码和相应注释：

```yaml
# mikelyou.dict.yaml
---
name: mikelyou
version: "2020.08.27"
sort: by_weight
use_preset_vocabulary: true
...

词语一
词语二
词语三
```

并在 `luna_pinyin.extended.dict.yaml` 中添加此词库:

```yaml
# luna_pinyin.extended.dict.yaml
import_tables:
  - mikelyou
```

词语的格式为：

- 普通词语直接写， 如： `词语一`
- 若词语读音不规则，或不是汉字，则需要在后面写上拼音全拼，如：
  - `[旺柴]	wang chai` 
  - `🍋	ning meng`

其中拼音一定是全拼，即便你使用的是双拼方案等。

理论上我们可以把邮箱、网址、颜文字、英文词语都加入词库，但是这样做好不好有待思考。

#### 5.4.4 导出其他输入法的词库

请使用 [深蓝词库转换](https://github.com/studyzy/imewlconverter) 工具，这是一款开源免费的输入法词库转换程序，支持超过20种的输入法工具和词库。

该程序的说明文档写的非常清楚，在此不予赘述，仅记录一下本人导出搜狗 `bin` 格式词库的方法。

> 我使用的搜狗输入法版本：8.9正式版（8.9.0.2180）
> 深蓝词库转换版本：2.9

第一步、打开 `属性设置` &rarr; `词库` &rarr; `中文用户词库` &rarr; `导出/备份`。然后我们可以得到一份 `*.bin` 文件，这是加密的搜狗词库文件，但是没有关西，深蓝工具可以帮我们解密它。

![](https://raw.githubusercontent.com/mikelyou/image-public/master/rime-sougou-wordwook-transfer.png)

第二步、前往 [Release](https://github.com/studyzy/imewlconverter/releases) 或其他可靠来源下载 深蓝词库转换工具，运行 `exe` 程序，然后看到如下界面。选择想要转换的文件 &rarr; 目标格式 &rarr; 选择文件 &rarr; 点击转换，即可。

![](https://raw.githubusercontent.com/mikelyou/image-public/master/rime-imewlconverter.png)

第三步、将转换后的词库添加到 [自己的词库](#543-增加自己的词库) 中。

一直没找到时间做这件事，今天发现竟然一下子就可以解决，终于可以把搜狗彻底卸载掉了。在这台电脑上用了快三年了的搜狗，掰掰~

<img src="https://raw.githubusercontent.com/mikelyou/image-public/master/rime-sougou-inputcounting.png" style="zoom:33%;" />

#### 5.4.5 下载网络词库

使用了一段时间小狼毫之后发现，扩充词库还是很有必要的，毕竟很多诸如专业词汇、城市信息、网络用语等是 rime 基础词库无法覆盖的；很多词语我们使用频率不高，于是造成了 “半天拼好一个词，然后再也没用过” 的尴尬场面。

以下是两个大的词库来源，数量很多但比较旧，质量参差不齐。

- [搜狗细胞词库_词库下载](https://pinyin.sogou.com/dict/)

- [百度输入法-词库首页](https://shurufa.baidu.com/dict)

更多的以后有机会我会研究一下哪里有更好更新的词库。

下载好词库后使用深蓝转换工具即可，与上一步骤同理。



TODO...

[【图片】〔新手推荐敎程〕关于导入词库及「深蓝词库转换」的正确操作方法【rime吧】_百度贴吧](https://tieba.baidu.com/p/2757690418)这篇帖子中，提到了

- 词汇的格式：`词彚<tab>ci hui<tab>100`, 従左往右依次是词彚、编码、词频
- 楼主彂现部分用家在导入自订词库的时候没有对词库进行转繁処理，而是直接将帯简化字的词彚导入的。这是一穜不可取的做法。
- 出於压缩词典，提髙部署时候的效率的考虑，导入的词彚在用opencc转成rime用字标凖后，还応该与系统词库进行去重処理。

#### 5.4.6 扩充词库 vs. 自定义符号

可能你已经感觉到，**自定义符号** 和 **自定义词库** 二者在功能上似乎有些重叠，一些功能用两个方法都能实现。这个时候就要看哪种方法更优。

**例1**	小明经常使用微信聊天，想把 `[旺柴]` 这串字符添加至词库或符号，以实现在微信聊天中 “手打狗头” 的操作。

- 如果使用符号，合理的方法是将其添加至 `/wx` 符号列表，其他微信表情符号也可添加至此。（使用 `/wc` 或 `/wangchai` 似乎都不是好的方法，前者可能于其他符号冲突，后者太长）

- 如果使用词库，我只需添加一行代码即可，且拼音易于记忆

  ```yaml
  [旺柴]	wang chai	 1
  ```

对比发现，如果经常使用狗头表情的话，第一种方法更加方便.

**例2**	小红是麻将爱好者，有时需要输入 🀍 🀅 这样的麻将 emoji，这样的符号有很多，但并不是每个都经常使用.

- 如果使用自定义符号，可以定义 `/mj` 并添加所有麻将符号（默认已有，无需自行添加，此处仅作举例），这样不常用的符号（如七万 🀍）可以使用这种方法输入.

-  如果使用词库，可以为 🀅发财、🀄红中等常用的符号添加定义，并使用自己习惯的叫法，便于输入.

  ```yaml
  🀁	nan	 1
  🀅	fa	 1
  🀄	zhong	 1
  ```

**总结**

1. 常用emoji（`😂`）、无法直接用拼音输入的（`[旺柴]`）适合使用词库的方法.
2. 大量的不常用符号（麻将🀍 星座♌）适合使用自定义符号
3. 两种方法可以同时应用

> 关于词库文件 `dict.yaml`， [雪齋的文檔](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md#dictyaml-詳解) 有详细解释，需要高度自定义的读者可以阅读.

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

## 7 为什么我选择 Rime

下面几段话原本是开头来着，实在是 “赶动” 读者，就扔到最后了。搜狗还是比较好用的，如果没有广告的话。

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
7. [「鼠须管」的调教笔记](https://scomper.me/gtd/-shu-xu-guan-de-diao-jiao-bi-ji)
8. [〔新手推荐敎程〕关于导入词库及「深蓝词库转换」的正确操作方法【rime吧】](https://tieba.baidu.com/p/2757690418)
