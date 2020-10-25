---

layout: post
title: "Common LaTeX Mathematical Symbols"
subtitle: '常用 LaTeX 数学符号'
date: 2020-09-25 17:49:47
author: "Mike Lyou"
#header-style: text
header-img: "img/post-bg-table.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC-SA
hidden: false
#excerpt:
tags:
 - LaTeX

---

This article listed some common $\LaTeX$ mathematical symbols, especially those hard to remember ones. The list may not be as useful for you as for me, since people's majors varies, but hope it can help you.

<!-- more -->

**[Here](https://www.caam.rice.edu/~heinken/latex/symbols.pdf)** is the reference of this article, which concludes much more.

If there is any typo or incorrect thing, please tell me. Thank you.

## Common Symbols

###  Greek and Hebrew letters

| Symbol        | LaTeX code  |
| ------------- | ----------- |
| $\varphi$     | \varphi     |
| $\varepsilon$ | \varepsilon |
| $\vartheta$   | \vartheta   |
| $\eta$        | \eta        |
| $\lambda$     | \lambda     |
| $\rho$        | \rho        |
| $\xi$         | \xi         |
| $\chi$        | \chi        |
| $\Gamma$      | \Gamma      |
| $\Lambda$     | \Lambda     |
| $\Xi$         | \Xi         |

Too common letters like $\alpha$, $\beta$ are not listed here.

### $\LaTeX$ Math Constructs

| Symbol                 | LaTeX code           |
| ---------------------- | -------------------- |
| $\frac{abc}{xyz}$      | \frac{abc}{xyz}      |
| $\sqrt{abc}$           | \sqrt{abc}           |
| $\sqrt[n]{abc}$        | \sqrt[n]{abc}        |
| $\overline{abc}$       | \overline{abc}       |
| $\overrightarrow{abc}$ | \overrightarrow{abc} |
| $\overleftarrow{abc}$  | \overleftarrow{abc}  |

### Variable-sized symbols (大型运算符)

| Symbol  | LaTeX code | Comment                                      |
| ------- | ---------- | -------------------------------------------- |
| $\sum$  | \sum       | It's not $\Sigma$ (`\Sigma`)                 |
| $\prod$ | \prod      | It's not $\Pi$ (`\Pi`)                       |
| $\int$  | \int       |                                              |
| $\oint$ | \oint      |                                              |
| $\iint$ | \iint      | Can add up to 3 ($\iiint$) and 4 ($\iiiint$) |

###  Standard Function Names

Function names should appear in Roman, not Italic, e.g.,

- Correct: 	`\sin\theta` 	&rarr; 	$\sin\theta$
- Incorrect: 	`sin\theta` 	&rarr;	 $sin\theta$

| Symbol | LaTeX code |
| ------ | ---------- |
| $\sin$ | \sin       |
| $\exp$ | \exp       |
| $\ln$  | \ln        |

Many others are not listed here.

### Operation/Relation Symbols

| Symbol       | LaTeX code  |
| ------------ | ----------- |
| $\times$     | \times      |
| $\div$       | \div        |
| $\cdot $     | \cdot       |
| $\ast$       | \ast        |
| $\pm$        | \pm         |
| $\mp$        | \mp         |
| $\bot$       | \bot        |
| $\equiv$     | \equiv      |
| $\cong$      | \cong       |
| $\neq$       | \ne or \neq |
| $\sim$       | \sim        |
| $\simeq$     | \simeq      |
| $\approx$    | \approx     |
| $\propto$    | \propto     |
| $\leq$       | \leq        |
| $\leqslant$  | \\leqslant  |
| $\ll$        | \ll         |
| $\geq$       | \geq        |
| $\geqslant$  | \geqslant   |
| $\gg$        | \gg         |
| $\because$   | \because    |
| $\therefore$ | \therefore  |

### Arrow symbols

| Symbol            | LaTeX code      |
| ----------------- | --------------- |
| $\leftarrow$      | \leftarrow      |
| $\rightarrow$     | \rightarrow     |
| $\leftrightarrow$ | \leftrightarrow |
| $\Leftarrow$      | \Leftarrow      |
| $\longleftarrow$  | \longleftarrow  |
| $\Longleftarrow$  | \Longleftarrow  |

###  Miscellaneous symbols (杂项符号)

| Symbol         | LaTeX code              |
| -------------- | ----------------------- |
| $\infty$       | \infty                  |
| $\nabla$       | \nabla                  |
| $\partial$     | \partial                |
| $\hbar$        | \hbar                   |
| $\hslash$      | \hslash                 |
| $\prime$       | \prime                  |
| $\cdots$       | \cdots                  |
| $\vdots$       | \vdots                  |
| $\ddots$       | \ddots                  |
| $\AA$          | \AA  (See a note below) |
| $\mathring{A}$ | \mathring{A}            |
| $\LaTeX$       | \LaTeX                  |

> Note: `\AA` (as well as `\LaTeX`) belong to *text mode* rather than *symbols*, therefore maybe not work in some environment, e.g. [mathjax](https://github.com/mathjax/MathJax/issues/795). The simplest way is use `\mathring{A}` instead, which looks like $\mathring{A}$.

### Math mode accents

| Symbol      | LaTeX code |
| ----------- | ---------- |
| $\dot{a}$   | \dot{a}    |
| $\ddot{a}$  | \ddot{a}   |
| $\bar{a}$   | \bar{a}    |
| $\hat{a}$   | \hat{a}    |
| $\vec{a}$   | \vec{a}    |
| $\tilde{a}$ | \tilde{a}  |


## Several similar symbol pairs

| Symbol   | LaTeX code | Note                |
| -------- | ---------- | ------------------- |
| $\Sigma$ | \Sigma     | symbol              |
| $\sum$   | \sum       | e.g. $z=\sum_j z_j$ |

| Symbol        | LaTeX code  | Note                                |
| ------------- | ----------- | ----------------------------------- |
| $\epsilon$    | \epsilon    | Less common                         |
| $\varepsilon$ | \varepsilon | **Common used one in mathematics.** |

## Reference

https://www.caam.rice.edu/~heinken/latex/symbols.pdf