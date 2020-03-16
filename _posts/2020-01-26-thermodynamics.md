---
layout: post
title: "Thermodynamics"
subtitle: 'E4201 Study Notes'
date: 2020-01-26 11:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/post-bg-2015.jpg"
mathjax: true
catalog: true
copyright-statement:
#excerpt: Some tips.
tags:
  - Notes
  - Thermodynamics
---

<!-- more -->



<!--
**注意：这是一个临时笔记，编辑过后应及时保存到本地。**
**注意：本文的最新版本在印象笔记，由马克飞象编辑，请不要编辑这个文件，请前往马克飞象进行编辑。**
**注意：本文在博客的版本可能是过时的，且只能单方向的由印象笔记更新至此。**
-->

> This post is Mike Lyou's study notes of Materials course E4201 and E4202. I do not own the copyright of some contents, if the article unintentionally infringes your copyright, it will be deleted shortly after being informed. All rights reserved.

> This note is still being editing, so you may see some poorly written parts. Let me know if you notice any errors or typos, thanks so much.


## 1 - Macroscopic Thermodynamics

### 1.1 Three level of thermodynamics
There are threed levels of thermodynamics.

- The **macroscopic（宏观） or phenomenological** description.

  - It treat matter as structureless.
  - Macroscopic (equilibrium) thermodynamics describes and only describes equilibrium states.

- The **statistical（统计）** description.
- The **quantum** description.

### 1.2 Systems, Barriers and Surrounding

- System
- Barriers
  - Diathermal（透热） or adiabatic（绝热）
  - Permeable or impermeable
  - Movable or fixed
- Surrounding

### 1.3 Thermodynamic Variables

#### State variables and process Variables

- **State variables(or state functions)**: depends only on condition(or state) of the system. Eg. $V$, $S$, $T$, $U$, $H$, $G$.
- **Process variables**: quantities than only have meaning for changing systems. They are variable depending on the choice of path. Eg. $W$, $Q$.

#### Extensive and Intensive State Variables

The state variables can be classified into finer classes.

- **Extensive** state variables: depend on system size. Which means double the system will change the variable value. Eg. $V$, $S$, $n$, $U$, $H$, $G$.

- **Intensive** state variables: not depend on system size. Eg. $T$, $P$, $\mu$(chemical potemtial).

- **Normalized extensive variables\***: extensive variables per mole or unit volume. These are in effect **intensive**. Eg. $v$, $s$.

#### Conjugate Variables

Many extensive variable has a conjugate intensive variable. $(S,T),(-P,V),(\mu,N)$

$\color{blue}{\text{(needs extention)}}$

***

## 2 - Laws of Thermodynamics

> ~~众所周知，热力学三大定律一共有四条（还有第零定律）。~~

### 2.1 Zeroth Law
**If two systems are each in equilibrium with a third system, they
are also in equilibrium with each other**.

It seacribes the equilibrium.

### 2.2 First law
**Energy is conserved, it cannot be created or destoryed**.

$$ dU=\delta Q + \delta W + \delta W^\prime $$

$$（能增 = 吸热 + 得工）$$

Where,

$dU$ means **increase** of internal energy,  
$\delta Q$ means heat transferred **into** system,  
$\delta W = -P dV$ is mechanical work,  
$\delta W^\prime$ is sum of other works.

The first law is law of energy.

### 2.3 Second law
Entropy never decreases.

$$ \mathrm{d} S \geqslant \frac{\delta Q}{T} $$

where equal sign holds only for **reversible process**.

### 2.4 Third law
**The entropy of a thermodynamic system in internal equilibrium
approaches a universal constant (usually taken as zero) as the absolute temperature goes to zero.**

Which means entropy of any system at $T=0K$ is zero, no matter what values other system parameters are. It can be expressed as:

$$
\left( \frac { \partial U } { \partial S } \right)_ { V, N_{1}, \ldots , N_{r} } = 0
$$

In the above equation, partial value is zero because $S \equiv 0$.

####  Calculation of entropy
According to the Third Law, absolute value of entropy can be calculated.

For a reversible process

$$ \mathrm{d} S = \frac{\delta Q}{T} $$

and

$$ \delta Q=C_{p} d T $$

Therefore

$$S_T = S_0 + \int_{0}^T \frac{C_p}{T} dT = \int_0^T \frac{C_p}{T} dT $$

or more practically

$$ S_T = S_{298.15} + \int_{298.15}^{T} \frac{C_{p}}{T} d T $$

***

## 3 - Conditions of Equilibrium

### Equilibrium States

Equilibrium states of simple macroscopic systems are characterized by system parameters including

$$\left( U, V, N_1, N_2, \cdots , N_r \right) $$

If systems are more complex, parameters will be more.

The **equilibrium states** are states in which **entropy is maximized** for the given constraints.

$\color{blue}{\text{(needs extention)}}$



##  5 - Second Derivatives of Fundamental Equation, Maxwell Relations, Stability

### 5.1 Useful Second Derivatives

These ~~four~~ five useful second derivatives should be remembered. They can sometimes serve as known values.

1. Cofficient of thermal expansion
$$ \alpha \equiv \frac{1}{v}\left(\frac{\partial v}{\partial T}\right)_ {P} = \frac{1}{V}\left(\frac{\partial V}{\partial T}\right)_ {P, N} ~ K^{-1}$$

2. Isothermal compressibility
$$ \kappa_T~\text{or}~\beta  \equiv -\frac{1}{v}\left(\frac{\partial v}{\partial P}\right)_ {T} = -\frac{1}{V}\left(\frac{\partial V}{\partial P}\right)_ {T, N} ~atm^{-1} $$

3. Adiabatic compressibility
$$ \kappa_S \equiv -\frac{1}{v}\left(\frac{\partial v}{\partial P}\right)_ {S} = -\frac{1}{V}\left(\frac{\partial V}{\partial P}\right)_ {S, N} ~atm^{-1} $$

4. Molar heat capacity at constant pressure
$$ c_P \equiv T \left(\frac{\partial s}{\partial T}\right)_ {P} = \frac{T}{N} \left(\frac{\partial S}{\partial T}\right)_ {P, N} ~J\cdot mol^{-1} \cdot K^{-1}$$

5. Molar heat capacity at constant volume
$$ c_V \equiv T \left(\frac{\partial s}{\partial T}\right)_ {V} = \frac{T}{N} \left(\frac{\partial S}{\partial T}\right)_ {V, N} ~J\cdot mol^{-1} \cdot K^{-1}$$

Ps. We can notice that they are partial derivatives of $V$ and $S$ with respect to $T$ and $V$ multiplied by other functions.

>**Attention:** Not confuse $c_V$ with $C_V$ (which we nearly won't see).
>$c_V$ is *molar heat capacity*: $\Delta Q = n c_V \Delta T$ (where $n$ is mole number);
>$C_V$ is *specific heat*: $\Delta Q = m c_V \Delta T$ (where $m$ is mass)
>They are related by  Avogadro number $N_A$
>$$c_V =  C_V / N_A$$

Additional relations (should be able to [derive them](http://showard.sdsmt.edu/MET320/Cp-Cv.pdf)):
$$c_{P}=c_{V}+\frac{T V \alpha^{2}}{N \kappa_{T}}$$
$$\kappa_{T}=\kappa_{S}+\frac{T V \alpha^{2}}{N c_{P}}$$

#### Derive $\boxed{c_{P}=c_{V}+\frac{T V \alpha^{2}}{N \kappa_{T}}}$
By defination, we have

$$ c_P - c_V = \frac{T}{N} \cdot \left[\left(\frac{\partial S}{\partial T}\right)_ {P, N} -\left(\frac{\partial S}{\partial T}\right)_ {V, N} \right] $$

Pluging in the total differential of $S=S(V,T)$

$$ dS = \left(\frac{\partial S}{\partial T}\right)_ {V,N} dT + \left(\frac{\partial S}{\partial V}\right)_ {T,N} dV$$

We have

$$ \left(\frac{\partial S}{\partial T}\right)_ {P,N} = \left(\frac{\partial S}{\partial T}\right)_ {V,N} \cdot 1  + \left(\frac{\partial S}{\partial V}\right)_ {T,N} \left(\frac{\partial V}{\partial T}\right)_ {P,N} $$

$$ \left(\frac{\partial S}{\partial T}\right)_ {V,N} = \left(\frac{\partial S}{\partial T}\right)_ {V,N} \cdot 1  + 0 $$

And therefore

$$ c_P - c_V = \frac{T}{N} \cdot \left[\left(\frac{\partial S}{\partial V}\right)_ {T,N} \left(\frac{\partial V}{\partial T}\right)_ {P,N} \right]$$

Simplify two derivatives inside

$$ \left(\frac{\partial S}{\partial V}\right)_ {T,N} = \color{red}{+}\left(\frac{\partial P}{\partial T}\right)_ {V,N} = - \frac{\left(\frac{\partial V}{\partial T}\right)_ {P,N}}{\left(\frac{\partial V}{\partial P}\right)_ {T,N}} = -\frac{\alpha V}{-\kappa_T V} = \frac{\alpha}{\kappa_T}$$

$$ \left(\frac{\partial V}{\partial T}\right)_ {P,N} = \alpha V$$

Pluging in to have

$$ c_P - c_V = \frac{T}{N}  \cdot \frac{\alpha}{\kappa_T} \cdot \alpha V = \frac{\alpha^2 TV}{\kappa_T N}$$

Q.E.D	(What is [Q.E.D](https://en.wikipedia.org/wiki/Q.E.D.)?)

### 5.2 Maxwell Relations
#### How to derive them
Derivation of Maxwell relations is simple. As an example, we have
$$ dU=T dS - PdV + \mu dN $$

And

$$ \frac{\partial^{2} U}{\partial S \partial V}=\frac{\partial^{2} U}{\partial V \partial S} $$

Therefore, we have

$$ -\left(\frac{\partial P}{\partial S}\right)_ {V, N_{1}, N_{2}, \ldots}=\left(\frac{\partial T}{\partial V}\right)_ {S, N_{1}, N_{2}, \ldots} $$

#### How to remember:
1. Each pair of conjugate functions, e.g. $(S,T)$, sits at diagonal position.
$$ -\left(\frac{\partial  \color{green}{P}}{\partial \color{red}{S}}\right)_ {V, N}=\left(\frac{\partial  \color{red}{T}}{\partial \color{green}{V}}\right)_ {S, N} $$

2. If $P$ involved, add a negative sign.  
Because the conjugate $(-P,V)$ has a negative sign.
$$ \color{red}- \left(\frac{\partial P}{\partial {S}}\right)_ { {V}, N}=\left(\frac{\partial T}{\partial {V}}\right)_ { {S}, N} $$

3. If not all denominator are intensive (or all molecule are extensive) (e.g.$\partial T/ \partial V$), each exception gives one negative sign.
$$\color{red}{-}\left(\frac{\partial \color{red}{S}}{\partial N}\right)_ {T, V}=\left(\frac{\partial \mu}{\partial \color{red}{T}}\right)_ {V, N}$$

4. Each molecule is the constant of the derivitiave across the equal sign.
$$ -\left(\frac{\partial P}{\partial \color{red}{S}}\right)_ {\color{red}{V}, N}=\left(\frac{\partial T}{\partial \color{red}{V}}\right)_ {\color{red}{S}, N} $$

You can find your own way to remember this, which is easiest to remember for you is the best.

### 5.3 Jacobian

See the supplymentary document on Jacobians to help understand, which is more mathematical. Here we just list the results, which is enough for solving problems.

$$
\boxed{\begin{aligned}
\left(\frac{\partial X}{\partial Y}\right)_ {Z} &=1 /\left(\frac{\partial Y}{\partial X}\right)_ {Z} \\
\left(\frac{\partial X}{\partial Y}\right)_ {Z} &=\left(\frac{\partial X}{\partial W}\right)_ {Z} /\left(\frac{\partial Y}{\partial W}\right)_ {z} \\
\left(\frac{\partial X}{\partial Y}\right)_ {Z} &= \color{red}{-}\left(\frac{\partial Z}{\partial Y}\right)_ {X} /\left(\frac{\partial Z}{\partial X}\right)_ {Y}	\end{aligned}
}$$

Jacobians is very useful when we have e.g. $G,S$ as constant, and we want to bring it to demoninators, so that we can either expand them or get the useful second derivatives.

### 5.4 Reduce the Derivatives (EP4)

**General rules:**

1. Try to put extensive variables at molecule, and intensive variables at denominator. For example:
$$ \left( \frac{\partial P}{\partial U} \right) _ {G,N} 	\rightarrow \left[ \left( \frac{\partial U}{\partial P} \right) _ {G,N} \right] ^ {-1}$$

2. Try to put expandable functions $(U,F,H,G)$ at molecule and expand them.
$$ \because dU=T dS-P dV +\mu dN $$
$$ \therefore \left[\left(\frac{\partial U}{\partial P}\right)_ {G,N}\right]^{-1} = \left[T\left(\frac{\partial S}{\partial P}\right)_ {G, N}-P\left(\frac{\partial V}{\partial P}\right)_ {G, N}\right]^{-1} $$  

3. Make use of the **jacobians** and **Maxwell relationships** when you need.  

$$ \left(\frac{\partial S}{\partial P}\right)_ {G, N} = \frac{\left(\frac{\partial G}{\partial P}\right)_ {S, N}}{\left(\frac{\partial G}{\partial S}\right)_ {P, N}} $$

$$ \left(\frac{\partial S}{\partial P}\right)_ {T, N}=\left(\frac{\partial V}{\partial T}\right)_ {P, N}=-\alpha V $$

4. Be sure to remember all ~~four~~  five second derivatives clearly.
$$\alpha, \kappa_T ~(\text{or}~ \beta),\kappa_S, c_V, c_P $$

5. Plug in all results back and simplify it.

>Ps. Not to confuse with this two:

>$$
\left(\frac{\partial \color{red}{T}}{\partial X}\right)_ {\color{red}{T}, N} \equiv 0, \quad
\left(\frac{\partial \color{red}{T}}{\partial \color{red}{T}}\right)_ {X, N} \equiv 1
$$

### Stability
...

## 9 - Multicomponent Homogeneous Nonreacting Systems: _Solution_

### 9.1 Partial Molar Properties (PMP)

Consider a multcomponent homogeneous system, with $c$ different components, each has mole number of $n_k ~ (k=1,2,...,c)$.
> **Attention:**$~ ~ ~$ $n_k$ is mole number, not confuse with $N_k$ which is partical number. $$N_k= n_k \cdot N_A(\text{Avogadro number}).$$

For an extensive thermodynamic property $\left(\mathrm{B}^{\prime}=\mathrm{U}^{\prime}, \mathrm{S}^{\prime}, \mathrm{V}^{\prime}, \mathrm{H}^{\prime}, \mathrm{G}^{\prime}, . .\right)$,

$$d B^{\prime}=\left(\frac{\partial B^{\prime}}{\partial T}\right)_ {P, n_{k}} d T+\left(\frac{\partial B^{\prime}}{\partial P}\right)_ {T, n_{k}} d P+\sum_{k=1}^{c} \color{red}{ \left(\frac{\partial B^{\prime}}{\partial n_{k}}\right)_ {T, P, n_{j}   \neq n_{k}} } d n_{k}$$

The partial molar property $B$ for component $k$ is then

$$\overline{B_{k}} \equiv\left(\frac{\partial B^{\prime}}{\partial n_{k}}\right)_ {T, P, n_{j} \neq n_{k}} \quad(k=1,2, \ldots,c)$$

***

At constant temperature and pressure, we have

$$d B_{T, P}^{\prime}=\sum_{n_{k}=1}^{c} \overline{B_{k}} d n_{k}$$

From full differential of $dB^\prime$ we know

$$d B^{\prime}=\sum_{k=1}^{c}\left[\overline{B_{k}} d n_{k}+n_{k} d \overline{B_{k}}\right]$$

Combining above two equations, we get the **Gibbs-Duhem Equation(Relation)**:

$$\boxed{\sum_{n_{k}=1}^{c} n_{k} d\overline{B_{k}} =0}$$

### 9.2 Solution (Im's Class)

Consider a solution made of two components:

$$\boxed{n_A \text{pure}A} + \boxed{n_B \text{ pure}B} \rightarrow \boxed{(n_A+n_B) ~(A+B\text{ solution})}$$

The Gibbs free energy before and after mixing are:

$$G_{~seperate\\(or~before)}=n_A G_A^o+n_B G_B^o$$

$$G_{~solution\\(or~after)}=n_A \overline{G_A}+n_B \overline{G_B}$$

In which $G^o$ is Gibbs free energy of pure matter $\color{red}{(needs~ varify)}$, $\overline{G_A}$ is partial molar Gibbs free energy. They are both chemical potential, but little different.

$$G^o=\mu_A^o $$
$$\overline{G_A}=\frac{\partial G_{solution}}{\partial n_A}=\mu_A $$

>**Attention:**
>Only in unary system $\mu \equiv g \equiv G$ (here $g=G/N$) .
>In multicomponent system $\mu_i = \partial G / \partial n_i $ for component $i$.

We can write the Gibbs-Duhem Equation

$$n_A d\overline{G_A}+n_B d\overline{G_B}=0$$

For 1 mole solution, substituting in

$$x_A=\frac{n_A}{n_A+n_B} \quad x_B=\frac{n_B}{n_A+n_B}$$

We have:

$$\boxed{ x_A d\overline{G_A}+x_B d\overline{G_B}=0 }$$

And

$$\boxed{ G_{~seperate(or~before)}=x_A G_A^o+x_B G_B^o}$$

$$\boxed{ G_{~solution(or~after)}=x_A \overline{G_A}+x_B \overline{G_B}}$$

***

Now consider the Gibbs free energy change $\Delta G_{mix}$ before and after mixing, which should be:

$$\Delta G_{mix} =  G_{solution} - G_{seperate}$$

And then we can derive the following relations:

$$\Delta G_{mix} =  \Delta H_{mix} - T \Delta S_{mix}$$

or

$$\Delta G_{mix} =  x_A  \Delta \overline G_{mix, A}+x_B  \Delta \overline G_{mix, B} = x_A (\overline{G_A}-G_A^o) + x_B (\overline{G_B}-G_B^o)$$

Likewise

$$G_{sol} = H_{sol} - T \cdot S_{sol}$$

$$G_{sol} = x_A \overline G_A + x_B \overline G_B \tag{*}$$

$$G_{sol} = \Delta G_{mix} + G_{seperate}$$

Now we can construct the curve of $G_{sol}$ for the first step.

![Alt text|center](./free_energy_solution_01.jpg)

***

From $(*)$ we can derive

$$\frac{dG_{sol}}{dx_B} = - \overline G_A + \overline G_B$$

And the tangent line at point $\left( x_B^\prime, G_{sol}\right)$ is then $G^\prime = G_{sol} +  (x_B-x_B^\prime) \frac{dG_{sol}}{dx_B} $. Therefore we have the partial molar Gibbs free energy of $A$ and $B$:

$$\overline G_B = G_{sol} + (1-x_B)\frac{dG_{sol}}{dx_B} $$

$$\overline G_A = G_{sol} + ~ ~ ~ ~ ~ x_B   \cdot \color{red}{-}\frac{dG_{sol}}{dx_B} $$

![Alt text|center](./free_energy_solution_02.jpg)

***
Plugging in activity $a$

$$ \overline G_A = G_A^o +RT \ln a_A  = \mu_A$$

where
$$a_A = \gamma _A \cdot x_A = \frac{f_A}{f_A^o} \approx \frac{P_A}{P_A^o}$$

In which, $\gamma_A$ is activity coefficient, $x_A$ is mole fraction of $A$.

>This part seems to have collision with Prof. Barmak's lecture, see [Lec 9 Page 9]().

Then we can expand $(*)$ to

$$\begin{aligned}G_{sol} ~&= x_A \overline G_A + x_B \overline G_B \\
&=x_A G_A^o +x_A RT \ln a_A + x_B G_B^o +x_B RT \ln a_B\\
&=\color{red}{\left(x_A G_A^o +x_B G_B^o \right) }+ \color{green}{RT \left(x_A \ln a_A + x_B  \ln a_B \right)}\\
&=\color{red}{G_{sep}}\text{(known)}+ \color{green}{\Delta G_{mix}}\text{(conclusion)}
\end{aligned}$$

<!--
As we already know $G_{sep}=\left(x_A G_A^o +x_B G_B^o \right)$
Then we can conclude $\Delta G_{mix} = RT \left(x_A \ln a_A + x_B  \ln a_B \right)$
-->
Then

$$\Delta \overline G_{mix, A} \equiv \frac{\partial \Delta G_{mix}}{\partial x_A} = RT \ln a_A = \overline G_A -G_A^o\\
\Delta \overline G_{mix, B} \equiv \frac{\partial \Delta G_{mix}}{\partial x_B} = RT \ln a_B = \overline G_B -G_B^o$$

![Alt text|center](./free_energy_solution_03.jpg)


### 9.3 Binary Dilute solution
The solvent obeys Raoult's Law

$$\lim_{X_A \rightarrow 1} a_A = X_A$$

The solute boeys Henry's Law

$$\lim_{X_B \rightarrow 0} a_B = \gamma^o X_B \\(\gamma^o:\text{Henry's Law constant})$$

Here is illustration from Prof. Barmak's Lecture.


![][binary_dilute_solution]

[binary_dilute_solution]: ./binary_dilute_solution.jpg
<!--E:\GitHub\mikelyou.github.io\img\in-post\post-thermodynamics\binary_dilute_solution.jpg-->

### 9.4 Ideal Solution
Assumption of ideal solution:
$$\boxed{ a_A = x_A, a_B = x_B} \quad (\text{i.e. } \gamma_A =\gamma_B =1)$$

>This assumption is derivated from ideal gas mixture, see [Barmak's Lec 9 Page 10]().

Upon this very simple assumption, we can derive

$$\Delta G_{mix}^{ideal} = RT \left[ x_A \ln x_A + x_B  \ln x_B \right] \propto T\\
\Delta V_{mix}^{ideal} =\left(\frac{\partial \Delta G_{mix}^{ideal}}{\partial P}\right)_{T, x_B}=0\\
\Delta U_{mix}^{ideal} =\Delta H_{mix}^{ideal} = \left[\frac{\partial (\Delta G_{mix}^{ideal}/T)}{\partial (1/T)}\right]_{P, x_B} =0$$

Noticing that $\Delta H_{mix}^{ideal}=0$, we can conclude that $\Delta G_{mix}^{ideal} = -T \Delta S_{mix}^{ideal}$, i.e.

$$\Delta S_{mix}^{ideal} = -R \left[ x_A \ln x_A + x_B  \ln x_B \right] $$

Here are two fine graphs:

![Alt text|500x0|center](./ideal_solution.jpg)
![Alt text|500x0|center](./ideal_solution_2.jpg)


### 9.5 Regular Solution

The difference of regular solution to ideal solution is, the ehthalpy of regular solution is nonzero. $\color{red}{\text{needs varification}}$

Here we directly give the results:

$$\begin{aligned}
\Delta G_{mix}^{reg} &= \Omega x_A x_B + RT \left[ x_A \ln x_A + x_B  \ln x_B \right] \\
\Delta S_{mix}^{reg} &= \color{white}{zzzzzzzzzz}RT \left[ x_A \ln x_A + x_B  \ln x_B \right] =\Delta S_{mix}^{ideal}\\
\Delta H_{mix}^{reg} &= \Omega x_A x_B  \color{white}{zzzzzzzzzzzzzzzzzzzzzzzzzzzzz} \left(\Delta H_{mix}^{ideal} = 0 \right)
\end{aligned}$$

Regular solution will simplify to ideal solution when $\Omega = 0$

> **Attention: Nomenclature **
> In Im's class, $\Omega$  is *regular solution parameter*, $\Omega = N_a \cdot z \left[ \epsilon_{AB} - \frac{1}{2} (\epsilon_{AA}+\epsilon_{BB})\right]$, $\omega$ is *configurational entropy*, $\omega = \frac{(N_A+N_A)!}{N_A! N_B!}$ .
> While in Barmak's class, the regular solution parameter is $a_0$, and configurational entropy is $\Omega$. Pay attention to this.

***
Using the "excess terms", which means the difference with ideal solution

$$
\Delta G_{mix}^{xs} = \Delta G_{mix} - \Delta G_{mix}^{ideal}	\\
\Delta H_{mix}^{xs} = \Delta H_{mix} - \Delta H_{mix}^{ideal}	\\
\Delta S_{mix}^{xs} = \Delta S_{mix} - \Delta S_{mix}^{ideal}
$$

For regular solution, we can prove that

$$
\Delta G_{mix}^{xs,~reg} = \Omega ~ x_A x_B	\\
\Delta H_{mix}^{xs,~reg} = \Omega ~ x_A x_B	\\
\Delta S_{mix}^{xs,~reg} = 0 	\color{white}{zzzzzz}
$$

![Alt text](./regular_solution.jpg)


### 9.6 Nonregular(Subregular or Real) Solution

For component $A$, we have

$$
\Delta \overline G_{mix,~A}^{xs,~real} = \Delta \overline G_{mix,~A}^{real} - \Delta G_{mix,~A}^{ideal} = RT \ln \gamma_A
$$

Therefore for the whole solution, we have

$$
\begin{aligned}
\Delta G_{mix}^{xs,~real} &= \Delta G_{mix}^{~real} - \Delta G_{mix}^{ideal} = RT \left[ x_A \ln \gamma_A + x_B \ln \gamma_B\right]	\\
\Delta G_{mix}^{xs}&= \Delta H_{mix}^{xs} - T \Delta S_{mix}^{xs}
\end{aligned}
$$

Since we already know $\Delta H_{mix}^{ideal} = 0$,  $\Delta V_{mix}^{ideal} = 0$, then we know

$$
\Delta H_{mix}^{xs,~real} = \Delta H_{mix}\\
\Delta V_{mix}^{xs,~real} = \Delta V_{mix}
$$

![Alt text](./nonregular_solution.jpg)

## X - Unclassfied Notes from Im's class

### $G$ as a dunction of temperature

$$\because C_{P}=\left(\frac{\partial Q}{\partial T}\right)_ {P}=\left(\frac{\partial H}{\partial T}\right)_ {P}$$

$$\therefore H=H_0 +\int C_ P dT$$

$$S=\int_0^T d S=\int_0^T \frac{d Q}{T}=\int_0^T \frac{C_P}{T} d T$$

$$G=H-TS$$

$$\left(\frac{\partial G}{\partial T}\right)_ P =-S < 0$$
$$\left(\frac{\partial^{2} G}{\partial T^{2}}\right)_ {P}=-\left(\frac{\partial S}{\partial T}\right)_ {P}=-\frac{C_{P}}{T} < 0$$

We should be able to draw sketches about $H$, $S$, $G$.

Need to add picture later.

### Order of Phase Transitions(Trasnformations)

Ehrenfest's defination:

For s $n$-th order transformation, $\large \frac{\partial^{n-1} G}{\partial T^{n-1}}$ is continious, and $\large \frac{\partial^{n} G}{\partial T^{n}}$ is discontinious.

### Thermodynamic Driving Force of Transformation
$$\large \color{red} {\text{Need to do}}$$
