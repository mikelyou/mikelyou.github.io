---
layout: post
title: "Electrochemistry"
subtitle: 'E4260 Study Notes'
date: 2020-01-24 11:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/post-bg-2015.jpg"
mathjax: true
catalog: true
copyright-statement:
#excerpt: Some tips.
tags:
  - Notes
  - Electrochemistry
  - Thermodynamics
---

<!-- more -->

<!-- # 1
## 2
### 3
#### 4
##### 5
###### 6 -->

> This post is study note of E4260 course, all rights reserved. I do not own copyright of some contents, if the article unintentionally infringes your copyright, it will be deleted shortly after being informed.

## Lec 1 - Basic Structure of Electrochemical Cells

#### Trivia

$$ 1 𝑒𝑉 \sim 1.6 × 10^{−19} C/electron × 1𝑉 × 6.02 × 10^{23} electron/mole = 96.4 kJ/mole$$

this value is called Faraday's constant, $F$.

#### Cell notation

<!-- ![](\img\in-post\post-e4260-01-cell-notation.png)
*caption* -->

{% include image.html
            img="\img\in-post\post-e4260-01-cell-notation.png"
            title=""
            caption="Cell Notation"
            %}


$$
Z n(s)\left|Z n^{2+}(a q) \| C u^{2+}(a q)\right| C u(s)
$$

- Rules of writing cell notations:
  - Oxidation on the left, reduction on theright (in galvanic mode).
  - A line as phaseboundary.
  - Double line indicates a salt bridge: two interfaces.
  - Metal electrodes at two ends.

- Electrode: $Zn$, $Cu$
- Electrolyte: $ZnSO_4$ and $CuSO_4$ aqueous solutions
- Redox pair: $Cu^{2+} /Cu$, $Zn^{2+} /Zn$

- Anion: negatively charged ion  
  Cation: positively chargedion

- **Positive electrode**: **$Cu^{2+} /Cu$** is always at high electrical potential, tend to **lose** electrons.  
  **Negative electrode**: **$Zn^{2+} /Zn$** is always at low electrical potential, tend to **gain** electrons.  
  Positive and negative electrodes **do NOT change** during charge/discharge

- **Cathode**: where **reduction** (get electrons) occurs.  
  **Anode**: where **oxidation**(lose electrons) occurs

- Cathode and anode will change.  
  Positive and negtive will never change.

- **Galvanic cells (discharge)**: use the spontaneous redox chemical reaction to **generate electricity**.  
  **Electrolytic Cells (charge)**: use the electricity to force chemical reaction to take place.

$$
\begin{array}{c|c|c}{} & {\text { Positive }\left(\mathrm{Cu} / \mathrm{Cu}^{2+}\right)} & {\text { Negative }\left(\mathrm{Zn} / \mathrm{Zn}^{2+}\right)} \\ \hline \text { Galvanic } & {\text { Cathode }} & {\text { Anode }} \\ \hline \text { Electrolytic } & {\text { Anode }} & {\text { Cathode }}\end{array}
$$


#### Cell Reversibility

1.Chemical reversibily  

  In most cases, it is satisfied. For example:

  $$Pt | H_2 | H^+ , Cl^- | AgCl | Ag$$

  Reversing the current will reverse the cell reaction.  
  However, the following reaction

  $$Zn | ZnSO_4 \| H_2SO_4 | Pt$$

  Reversing the current will change the reaction instead.

2.Thermodynamic reversibily

3.Practical reversibily

If **change of driving force is slow enough** compared to the **kinetics** of the involved reaction so that equilibrium can be established very fast. Systems are called in **practical reversibility**.

#### Cell voltage (in more chemical way)

Take the $Zn-Cu$ cell as example.

$$
C u^{2+}(a q)+Z n(s) \rightarrow C u(s)+Z n^{2+}(a q)
$$

The voltage $E$ is defined as difference of electric potential of two half cells.

$$ V = E_+ - E_-$$

According to the energy conservation,

$$ -\Delta G = V \cdot Q = V \cdot n F $$

where $F = 96485 C/mol$ is Faraday's Constant.  
Derive $V$ from the above equation, we have

$$ V=-\left(G_{Z n^{2+}}+G_{C u}-G_{C u^{2+}}-G_{Z n}\right) / 2 F $$

Now consider the change of amount of substance during the reaction.  
Assume the amount of substance of component $i$ is $N_i$, the amount of substance change during a period of time is $m$.

$$
C u^{2+}(a q)+Z n(s)+C u(s)+Z n^{2+}(a q) \rightarrow C u^{2+}(a q)+Z n(s)+C u(s)+Z n^{2+}(a q)\\
1 mol + 1 mol + 1 mol + 1 mol \rightarrow (1-m)mol + (1-m)mol + (1+m)mol + (1+m)mol
$$

The change of $G$ is  

$$ \delta G_{C u^{2+}} = \frac{\partial G}{\partial N_{C u^{2+}}} \delta N =  \mu_{C u^{2+}} \cdot (-m) $$

and so for other components.  
Plugging in to get

$$ V=-\left(\mu_{Z n^{2+}}+\mu_{C u}-\mu_{C u^{2+}}-\mu_{Z n}\right) / 2 F $$

Knowing that

$$ \mu = \mu_0 + RT \ln a , \quad a = \gamma c$$

where  

$\mu$ is chemical potentisl,  
$\mu_0$ is chemical  potential at standered condition $[298 K, 1 atm, a = 1 (~1M)]$  
$a$ is activity coefficient,  
$c$ is concentration,  
$\gamma$ is activity factor.

Plugging in to get

$$
V=V^{0}-\frac{R T}{2 F} \ln \frac{a_{Z n 2+} a_{C u}}{a_{C u 2+} a_{Z n}}
\quad V^{0}=-\frac{\mu_{C u}^{0}+\mu_{Z n^{2+}}^{0}-\mu_{C u^{2+}}^{0}-\mu_{Z n}^{0}}{2 F}
$$

For a general cell reaction

$$ O x 1+R e d 2 \leftrightarrow \operatorname{Re} d 1+O x 2 $$

$$ V=V^{0}-\frac{R T}{n F} \ln \frac{a_{R e d 1} a_{O x 2}}{a_{O x 1} a_{R e d 2}}=V^{0}-\frac{R T}{n F} \ln Q $$

This is what known as **Nernst Equation**.  
In which $Q$ is called reaction quotient.

$$ Q = \frac{a_{R e d 1} a_{O x 2}}{a_{O x 1} a_{R e d 2}}$$

$$ V^{0}=-\frac{\mu_{R e d 1}^{0}+\mu_{O x 2}^{0}-\mu_{O x 1}^{0}-\mu_{R e d 2}^{0}}{n F}
$$

Further more, we can break Nernst Equation into two **Half Cell Nernst Equations**:

$$
V=\left(-\frac{\mu_{R e d 1}^{0}-\mu_{O x 1}^{0}}{n F}-\frac{R T}{n F} \ln \frac{a_{R e d 1}}{a_{O x 1}}\right)-\left(-\frac{\mu_{R e d 2}^{0}-\mu_{O x 2}^{0}}{n F}-\frac{R T}{n F} \ln \frac{a_{R e d 2}}{a_{O x 2}}\right)\\
=E_+^{(O x 1+n e^{-} \leftrightarrow \operatorname{Red} 1)}  - E_-^{(O x 2+n e^{-} \leftrightarrow \operatorname{Red} 2)}
$$

#### Cell voltage (in more physicial way)

**Voltage** is the difference in **electrochemical potential of electrons ($\bar{\mu}_{e}$)** in two electrodes. Where

$$\bar{\mu}_{e}=\mu_{e}-F \phi$$

In above equation,  
$\mu_{e}$ is chemical potential (in J/mol),  
$\phi$ is electrostatic potential (in V)

From above equation, voltage($V$) can be derived as

$$ V=-\left(\bar{\mu}_{e, M 1}-\bar{\mu}_{e, M 2}\right) / F $$

Therefore we know, that voltage includes two parts:  
- Difference in chemical potential ($\mu_{e}$)
- Difference in electrostatic potential ($\phi$)

If two metal plates with different **chemical potential** contacts with each other, metal plate with higher chemical potential (called A) has higher electrochemical potential than another (called B), therefore the electrons will flow from A to B. When equilibrium state is reached, the B will have more electrons, thus has higher **electrostatic potential**. As sum of chemical potential and electrostatic potential, A and B have the **same electrochemical potential**, i.e. $V=0$.

Now let us re-consider this reaction:

$$C u^{2+}(a q)+Z n(s)+2 e^{-}(Z n) \leftrightarrow C u(s)+Z n^{2+}(a q)+2 e^{-}(C u)$$

When Electrochemical equilibrium established, we have

$$ \bar{\mu}_{C u 2+}+\bar{\mu}_{Z n}+2 \bar{\mu}_{e, z n}=\bar{\mu}_{C u}+\bar{\mu}_{Z n 2+}+2 \bar{\mu}_{e, C u} $$

Therefore

$$ V=-\frac{\bar{\mu}_{e, C u}-\bar{\mu}_{e, Z n}}{2 F}=-\frac{\bar{\mu}_{C u 2+}+\bar{\mu}_{Z n}-\bar{\mu}_{C u}-\bar{\mu}_{Z n 2+}}{2 F} $$

Since for ions, $\bar{\mu}_{M^{z+}}=\mu_{M^{z+}}+z F \phi$  
And for neutral metal, $\bar{\mu}_M=\mu_M$

$$ V=-\frac{\mu_{C u 2+}+2 F \phi_{s o l}+\mu_{Z n}-\mu_{C u}-\mu_{Z n 2+}-2 F \phi_{s o l}}{2 F}=-\frac{\mu_{C u 2+}+\mu_{Z n}-\mu_{C u}-\mu_{Z n 2+}}{2 F} $$

Finally, we derived the Nernst Equation

$$ V=V^{0}-\frac{R T}{n F} \ln \frac{a_{Z n 2+} a_{C u}}{a_{C u 2+} a_{Z n}} \quad V^{0}=-\frac{\mu_{C u 2+}^{0}+\mu_{Z n}^{0}-\mu_{C u}^{0}-\mu_{Z n 2+}^{0}}{n F} $$
