---
layout: post
title: "Thermodynamics"
subtitle: 'E4201 and E4202 Study Notes'
date: 2020-01-26 11:00:00
author: "Mike Lyou"
header-style: text
#header-img: "img/post-bg-2015.jpg"
mathjax: true
catalog: true
copyright-statement:
hidden: true
#excerpt: Some tips.
tags:
  - Notes
  - Thermodynamics
---

<!-- more -->

@(b0-学习)[Temporary]

<!--
**注意：这是一个临时笔记，编辑过后应及时保存到本地。**
**注意：本文的最新版本在印象笔记，由马克飞象编辑，请不要编辑这个文件，请前往马克飞象进行编辑。**
**注意：本文在博客的版本可能是过时的，且只能单方向的由印象笔记更新至此。**
-->

> This post is Mike Lyou's study notes of Materials course E4201 and E4202. I do not own the copyright of some contents, if the article unintentionally infringes your copyright, it will be deleted shortly after being informed. All rights reserved.

> This note is still being editing, so you may see some poorly written parts. Let me know if you notice any errors or typos, thanks so much.

# Thermodynamics


## 1 - Macroscopic Thermodynamics

### 1.1 Three levels of thermodynamics
There are three levels of thermodynamics.

- The **macroscopic（宏观） or phenomenological** description.

  - It treats the matter as structureless.
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

#### State variables and Process Variables

- **State variables(or state functions)**: depends only on condition(or state) of the system. Eg. $V$, $S$, $T$, $U$, $H$, $G$.
- **Process variables**: quantities than only have meaning for changing systems. They are variable depending on the choice of path. Eg. $W$, $Q$.

#### Extensive and Intensive State Variables

The state variables can be classified into finer classes.

- **Extensive** state variables: depend on system size. Which means double the system will change the variable value. Eg. $V$, $S$, $n$, $U$, $H$, $G$.

- **Intensive** state variables: not depend on system size. Eg. $T$, $P$, $\mu$(chemical potemtial).

- **Normalized extensive variables** *: extensive variables per mole or unit volume. These are in effect **intensive**. Eg. $v$, $s$.

$\rightarrow$ We're more interested in intensive variables

$\rightarrow$ Many **(Every?)** extensive variable has a **conjugate** intensive variable.  Common pairs are $(S,T)$, $(-P,V)$ and $(\mu,N)$. $\rightarrow$ See [First Derivatives of Fundamental Equation](#first-derivatives-of-fundamental-equation) for why they are conjugate.


***
## 2 - Laws of Thermodynamics

> ~~众所周知，热力学三大定律一共有四条（还有第零定律）。~~

### 2.1 Zeroth Law
**If two systems are each in equilibrium with a third system, they
are also in equilibrium with each other**.

It describes the equilibrium.

### 2.2 First law
**Energy is conserved, it cannot be created or destroyed**.

$$ dU=\delta Q + \delta W + \delta W^\prime $$

$$（能增 = 吸热 + 得工）$$

Where,

$dU$ means **increase** of internal energy,  
$\delta Q$ means heat transferred **into** system,  
$\delta W = -P dV$ is mechanical work,  
$\delta W^\prime$ is sum of other works.

The first law is the law of energy.

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
According to the Third Law, the absolute value of entropy can be calculated.

For a reversible process

$$ \mathrm{d} S = \frac{\delta Q}{T} $$

and

$$ \delta Q=C_{p} d T $$

Therefore

$$S_T = S_0 + \int_{0}^T \frac{C_p}{T} dT = \int_0^T \frac{C_p}{T} dT $$

or more practically

$$ S_T = S_{298.15} + \int_{298.15}^{T} \frac{C_{p}}{T} d T $$


## 3 - Conditions of Equilibrium

### 3.1 Equilibrium States

Equilibrium states of simple macroscopic systems are characterized by system parameters including$\left( U, V, N_1, N_2, \cdots , N_r \right) $. If systems are more complex, parameters will be more.

The **equilibrium states** are states in which **entropy is maximized** for the given constraints.

###  3.2 The Fundamental Relation

The relation that gives the entropy as a function of the extensive parameters is known as **the fundamental relation (in the entropic representation)**, which is

$$\boxed{S=S \left( U,V,N_1,N_2,\cdots N_r \right)}$$

This relation is very useful.

- If the fundamental relation of a system is known, **all conceivable thermodynamic information** about the system is ascertainable from it.

- In other words, the information contained in the fundamental relation is **thermodynamically all-inclusive**.

### 3.3 Entropy of a Composite System

The entropy of a composite system has three important properties:

**1. Additive over constituent subsystems**

The entropy of a composite system is additive over the constituent subsystems, where the entropy of each subsystem is a function of the extensive parameters of that subsystem alone:

$$S=\sum_{\alpha} S^{(\alpha)} = \sum_{\alpha} S^{(\alpha)}\left(U^{(\alpha)}, V^{(\alpha)}, N_{1}^{(\alpha)}, \ldots, N_{r}^{(\alpha)}\right)$$

The additive propertiey requires, that the entropy of a simple system is a homogeneous first-order function of the extensive parameters, or equavalent denoted as:

$$S\left(\lambda U, \lambda V, \lambda N_{1}, \dots, \lambda N_{r}\right)=\lambda S\left(U, V, N_{1}, \dots, N_{r}\right)$$

**2.  Monotonically increase with respect to the energy**

The monotonic property inplies that the partial derivative is positive.
$$\left(\frac{\partial S}{\partial U}\right)_{V, N_{1}, \cdots, N_{r}}>0$$

We can know additionally, from this relation, that temperature is non-negative.

 $$T \equiv \left(\frac{\partial U}{\partial S}\right)_{V, N_{1}, \cdots, N_{r}} = \left(\frac{\partial S}{\partial U}\right)_{V, N_{1}, \cdots, N_{r}} ^{-1}>0$$

**3.  Continuous and differentiable**
The continuity, differentiability and monotonic properties together, imply that the entropy function can be inverted with respect to the energy. And the internal energy is single-valued, continuous and differentiable.

<!--
$$S=S\left(U, V, N_{1}, \cdots, N_{r}\right) \rightarrow U=U\left(S, V, N_{1}, \cdots ,N_{r}\right)$$
-->

$$\boxed{U=U\left(S, V, N_{1}, \cdots ,N_{r}\right)}$$

Above is called **the fundamental relation (in the energy representation)**.

Both of the two is the fundamental relation while in different forms, and each contains **all** thermodynamic information about the system.

$$S=S\left(U, V, N_{1}, \cdots, N_{r}\right) \leftrightarrow U=U\left(S, V, N_{1}, \cdots ,N_{r}\right)$$

Because we are more interested in progress and changes in extensive parameters, we are more concerned with **the energy representaton**.

$\color{blue}{\text{(needs extention)}}$

### 3.4 First Derivatives of Fundamental Equation

Computing the first differential

$$
d U=\left(\frac{\partial U}{\partial S}\right)_{V, N_{1}, \cdots, N_{r}} d S+\left(\frac{\partial U}{\partial V}\right)_{S, N_{1}, \cdots, N_{r}} d V+\sum_{j=1}^{r}\left(\frac{\partial U}{\partial N_{j}}\right)_{S, V_{N}, N_{r \neq j}} d N_{j}
$$

From the first differential we can obtain the first derivatives, which are defined as temperature $T$, pressure $P$, and chemical potential $\mu_j$.

$$
\left(\frac{\partial U}{\partial S}\right)_{V, N_{1}, \cdots, N_{r}} \equiv T	\\
\color{red}-\left(\frac{\partial U}{\partial V}\right)_{S, N_{1}, \cdots, N_{r}} \equiv P \\
\left(\frac{\partial U}{\partial N_j}\right)_{S, N_{1}, \cdots, N_{r\neq j}} \equiv \mu_j
$$

>Notice that these partial derivatives are just the conjugate intensive functions of the corresponding extensive functions in the energetic representation.

Plugging them back, we have

$$d U=\color{blue}{T d S}-\color{green}{P d V}+\sum_{j=1}^{r}\mu_{j} d N_{j}$$

Compare with the statement of the first law

$$dU=\color{blue}{\delta Q }+ \color{green}{\delta W_{mechanical}}+ \delta W_{chemical}$$

$\color{blue}{\text{(result of the first law, or not?)}}$

### 3.5 Equation of State

Temperature, pressure and electrochemical potentials are partial derivatives of a function of $(\mathrm{S}, \mathrm{V}, \mathrm{N}_{1}, \cdots \mathrm{N}_{\mathrm{r}})$ and consequently are also functions of of $(\mathrm{S}, \mathrm{V}, \mathrm{N}_{1}, \cdots \mathrm{N}_{\mathrm{r}})$.

Thus, we have

$$\begin{aligned}
&T=T\left(S, V, N_{1}, \dots, N_{r}\right)\\
&P=P\left(S, V, N_{1}, \dots, N_{r}\right)\\
&\mu_{j}=\mu_{j}\left(S, V, N_{1}, \dots, N_{r}\right)
\end{aligned}$$

These relations are called **the equations of state**. They express the intensive parameters in terms of extensive parameters.

Knowledge of a single equation of state does not constitute complete knowledge of the thermodynamic properties of the system, but **knowledge of all the equations of state does**.

Since the fundamental equation is homogeneous first order, it must be true that the
equations of state are homogeneous zero order. We can represent this as

$$T\left(\lambda S, \lambda V, \lambda N_{1}, \ldots, \lambda N_{r}\right)=T\left(S, V, N_{1}, \ldots, N_{r}\right)$$

The temperature of all systems is equal to the temperature of all subsystems (at equilibrium), this is the property an intensive function should have.

### 3.6 Conditions of Equilibrium

From the single fact that **entropy is maximized for the given constraints**, we can get several important implications.

![Alt text](./1584381231912.png)

#### 3.6.1 Equilibrium of Temperature

Now we have an isolated, composite system consisting of two simple systems. Two subsystems are separated by a wall that is **rigid, impermeable, but allow the flow of heat.**

Given the condition, we know that the volumes and mole numbers of each system are fixed. The only variables are **energies of two subsystems**, with the constrain of energy conservation

$$U^{(1)}+U^{(2)}=\text { constant } \quad \text{or} \quad dU^{(1)}+dU^{(2)}=0$$

**When the system has reached equilibrium**, according to the definition of equilibrium, **the entropy should reach its maximum**. That is, a virtual transfer of energy from system 1 to system 2 will produce no change of entropy, i.e.

$$dS=0$$

The entropy of the system is

$$S=S^{(1)}\left(U^{(1)}, V^{(1)} , N_{j}^{(1)}\right)+S^{(2)}\left(U^{(2)}, V^{(2)} , N_{j}^{(2)} \right) $$

>For better readability, here we use $N_j$ to represent $ N_{1},N_2,\cdots ,N_{r}$.

Since volumes and mole numbers are fixed, we can reresent the difference of entropy as

$$\begin{aligned}
d S&=\left(\frac{\partial S^{(1)}}{\partial U^{(1)}}\right)_{V^{(1)},N_{j}^{(1)}} d U^{(1)}+\left(\frac{\partial S^{(2)}}{\partial U^{(2)}}\right)_{V^{(2)},  N_{j}^{(2)}} d U^{(2)}\\
&=\frac{1}{T^{(1)}} d U^{(1)}+\frac{1}{T^{(2)}} d U^{(2)}\\
&=\left(\frac{1}{T^{(1)}}-\frac{1}{T^{(2)}}\right) d U^{(1)}
\end{aligned}$$

Therefore

<!--$$\because dS=0 \quad \therefore T^{(1)}=T^{(2)}$$-->

$$dS=0 \quad \Longrightarrow \quad T^{(1)}=T^{(2)}$$

Q.E.D.

#### 3.6.2 Equilibrium of Pressure

Similarly, if we have an isolated, composite system consisting of two simple systems. Two subsystems are separated by a wall that is **impermeable, but moveable, and  allow the flow of heat.**

Upon this condition, the variables become **energies and volumes** of two subsystems. The only constants are mole numbers. And we can write

$$U^{(1)}+U^{(2)}=\text { constant } \quad \text{or} \quad dU^{(1)}+dU^{(2)}=0$$

$$V^{(1)}+V^{(2)}=\text { constant } \quad \text{or} \quad dV^{(1)}+dV^{(2)}=0$$

When the whole system has reached equilibrium, we have $dS=0$, and it can be expanded as

$$\begin{aligned}
d S&=\left(\frac{\partial S^{(1)}}{\partial U^{(1)}}\right)_{V^{(1)},N_{j}^{(1)}} d U^{(1)} + \left(\frac{\partial S^{(1)}}{\partial V^{(1)}}\right)_{U^{(1)},N_{j}^{(1)}} d V^{(1)} \\
& +\left(\frac{\partial S^{(2)}}{\partial U^{(2)}}\right)_{V^{(2)},  N_{j}^{(2)}} d U^{(2)} + \left(\frac{\partial S^{(2)}}{\partial V^{(2)}}\right)_{U^{(2)},  N_{j}^{(2)}} d V^{(2)}\\
&=\frac{1}{T^{(1)}} d U^{(1)} + \frac{P^{(1)}}{T^{(1)}} d V^{(1)} + \frac{1}{T^{(2)}} d U^{(2)} + \frac{P^{(2)}}{T^{(2)}} d V^{(2)}\\
&=\left(\frac{1}{T^{(1)}}-\frac{1}{T^{(2)}}\right) d U^{(1)} + \left(\frac{P^{(1)}}{T^{(1)}}-\frac{P^{(2)}}{T^{(2)}}\right) d V^{(1)}
\end{aligned}$$

Now we know $dS=0$, then it must be true that

$$\left(\frac{1}{T^{(1)}}-\frac{1}{T^{(2)}}\right) = 0, \quad \left(\frac{P^{(1)}}{T^{(1)}}-\frac{P^{(2)}}{T^{(2)}}\right) = 0$$

Therefore

$$dS=0 \quad \Longrightarrow \quad T^{(1)}=T^{(2)}  \quad \Longrightarrow \quad P^{(1)}=P^{(2)}$$

Q.E.D.

>Ps1. Here we can prove wrong a possible mistake, which I have made before, that **$dV^{(1)}+dV^{(2)}$ alone cannot derive the conclusion $P^{(1)}=P^{(2)}$**.
>
>Ps2. We can prove $(\partial S / \partial V)_ {U,N_j} \equiv P/T$ using [jacobian](#53-jacobian).

#### 3.6.3 Equilibrium of Chemical Potential
~~I dont wanna prove it since its similar to previous two.~~

### 3.7 Entropy Maximum Principle and Energy Minimum Principle

>...

### 3.8 The Euler Equation
>Ps. The pronunciation of Euler should be /ˈɔɪlər/. See [wikipedia](https://en.wikipedia.org/wiki/Leonhard_Euler) for more.

>...

### 3.9 The Gibbs-Duhem Relation

>...


## 4 - Legendre Transformations, Thermodynamic Potentials and the Extremum Principle

Experimentally, we do not have an “entropymeter" to measure entropy, but instead we have the very useful and simple “thermometer” to measure temperature.

Also, experimentally it is often easier to do experiments at constant pressure rather than constant volume.

In other words, **we would like the intensive**, rather than the extensive, parameter(s) to be the independent variable(s).

### 4.1 Legendre Transform

For function $Y$ with a single independent variable $X$

$$\boxed{\begin{array}{c}
Y=Y(X) \\
P={d Y}/{d X} \\
\psi=-P X+Y \\
\psi=\psi(P)
\end{array}}$$

And $\psi=\psi(P)$ is the Legendre transformed function of $Y=Y(X) $

$$Y=Y(X) \quad \rightarrow \quad \psi=\psi(P)$$

Using the energy representation, the Legendre transformed functions are the thermodynamic potentials:

$$F=U-TS$$

$$H=U+PV$$

$$G=U-TS+PV$$

$$\Xi\quad?$$

### 4.2 The Extremum Principle

Here we will show, that **the extremum principle for the thermodynamic potentials is one wherein the potential is minimized** (for the given constraints).

Consider a composite system in **diathermal contact** with a heat reservoir (reversible heat source).

In the equilibrium state, the total internal energy of the composite system + the reservoir will reach its minimum:

$$\begin{aligned}
&d\left(U+U^{r}\right)=0\\
&d^{2}\left(U+U^{r}\right)=d^{2} U>0
\end{aligned}$$

Also, the total entropy will reach its maximum:

$$\begin{aligned}
&d\left(S+S^{r}\right)=0\\
&d^{2}\left(S+S^{r}\right)=d^{2} U<0
\end{aligned}$$

If the composite system is simple and comprises two subsystems 1 and 2, then we have

$$\begin{aligned}
d\left(U+U^{r}\right) &=T^{(1)} d S^{(1)}+T^{(2)} d S^{(2)}+T^{r} d S^{r} \\
&=T^{(1)} d S^{(1)}+T^{(2)} d S^{(2)}-T^{r} d\left(S^{(1)}+S^{(2)}\right)=0\\
\therefore T^{(1)}=T^{(2)}&=T^{r}
\end{aligned}$$

Therefore, we can write

$$d\left(U+U^{r}\right)=d U+T^{r} d S^{r}=d U-T^{r} d S=0$$

$$ d \left(U-T^{r}  S\right)=0 \tag{1}$$

In addition, we can get this methematically:

$$ d^2 \left(U-T^{r}  S\right) = d^2U>0 \tag{2}$$

Combining $(1)(2)$ we see, the minimum of inner energy or maximum of entropy also indicate the minimum of Helmholtz potential at equilibrium

$$F= U - T^r  S$$

Since the temperature of each subsystem is qual to temperature of reservoir, we can write it as

$$dF= d\left(U - T  S\right)=0 \quad \text{(at equilibrium)}$$

Known as **Helmholtz Potential Minimum Principle**.

Similarly, we can derive other principles:

<details>
<summary>Enthalpy minimum principle</summary>
...
</details>

<details>
<summary>Gibbs free energy minimum principle</summary>
...
</details>

### 4.3 Thermodynamics Potentials, Process and Work

Take Helmholtz free energy as our example again. We showed that $dF=0$ at equilibrium.

However, for any process that takes a system from an initial state to a final state, we can write for a small change in the state of the system

$$d F=d U-T d S-S d T$$

Using the combination of first and second law

$$d U=T d S+\delta W_{\text{mechanical}}+\delta W_{\text{other}}$$

We can write

$$d F=-S d T+\delta W_{\text{mechanical}}+\delta W_{\text{other}}$$

Therefore we can arrive at the conclusion:

For **isothermal(等热) processes**, the **Helmholtz free energy** reports the **total (reversible) work** done on the system.

Similar for enthalpy $H$ and Gibbs free energy $G$ (E4201-hw8-2).

##  5 - Second Derivatives of Fundamental Equation, Maxwell Relations, Stability

### 5.1 Useful Second Derivatives

These ~~four~~ five useful second derivatives should be remembered. They can sometimes serve as known values.

1. Coefficient of thermal expansion

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
>
>$c_V$ is *molar heat capacity*: $\Delta Q = n c_V \Delta T$ (where $n$ is mole number);
>
>$C_V$ is *specific heat*: $\Delta Q = m c_V \Delta T$ (where $m$ is mass)
>
>They are related by  Avogadro number $N_{avo}$
>
>$$c_V =  C_V / N_{avo}$$

Additional relations (should be able to [derive them](http://showard.sdsmt.edu/MET320/Cp-Cv.pdf)):

$$c_{P}=c_{V}+\frac{T V \alpha^{2}}{N \kappa_{T}}$$

$$\kappa_{T}=\kappa_{S}+\frac{T V \alpha^{2}}{N c_{P}}$$

#### Derive $c_{P}=c_{V}+\frac{T V \alpha^{2}}{N \kappa_{T}}$

<details>
<summary>Click to expand</summary>

By definition, we have

$$ c_P - c_V = \frac{T}{N} \cdot \left[\left(\frac{\partial S}{\partial T}\right)_ {P, N} -\left(\frac{\partial S}{\partial T}\right)_ {V, N} \right] $$

Plugging in the total differential of $S=S(V,T)$

$$ dS = \left(\frac{\partial S}{\partial T}\right)_ {V,N} dT + \left(\frac{\partial S}{\partial V}\right)_ {T,N} dV$$

We have

$$ \left(\frac{\partial S}{\partial T}\right)_ {P,N} = \left(\frac{\partial S}{\partial T}\right)_ {V,N} \cdot 1  + \left(\frac{\partial S}{\partial V}\right)_ {T,N} \left(\frac{\partial V}{\partial T}\right)_ {P,N} $$

$$ \left(\frac{\partial S}{\partial T}\right)_ {V,N} = \left(\frac{\partial S}{\partial T}\right)_ {V,N} \cdot 1  + 0 $$

And therefore

$$ c_P - c_V = \frac{T}{N} \cdot \left[\left(\frac{\partial S}{\partial V}\right)_ {T,N} \left(\frac{\partial V}{\partial T}\right)_ {P,N} \right]$$

Simplify two derivatives inside

$$ \left(\frac{\partial S}{\partial V}\right)_ {T,N} = \color{red}{+}\left(\frac{\partial P}{\partial T}\right)_ {V,N} = - \frac{\left(\frac{\partial V}{\partial T}\right)_ {P,N}}{\left(\frac{\partial V}{\partial P}\right)_ {T,N}} = -\frac{\alpha V}{-\kappa_T V} = \frac{\alpha}{\kappa_T}$$

$$ \left(\frac{\partial V}{\partial T}\right)_ {P,N} = \alpha V$$

Plugging in to have

$$ c_P - c_V = \frac{T}{N}  \cdot \frac{\alpha}{\kappa_T} \cdot \alpha V = \frac{\alpha^2 TV}{\kappa_T N}$$

Q.E.D	(What is [Q.E.D](https://en.wikipedia.org/wiki/Q.E.D.)?)

</details>

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

3. If not all denominators are intensive (or all molecule are extensive) (e.g.$\partial T/ \partial V$), each exception gives one negative sign.

$$\color{red}{-}\left(\frac{\partial \color{red}{S}}{\partial N}\right)_ {T, V}=\left(\frac{\partial \mu}{\partial \color{red}{T}}\right)_ {V, N}$$

4. Each molecule is the constant of the derivative across the equal sign.

$$ -\left(\frac{\partial P}{\partial \color{red}{S}}\right)_ {\color{red}{V}, N}=\left(\frac{\partial T}{\partial \color{red}{V}}\right)_ {\color{red}{S}, N} $$

You can find your own way to remember this, which is easiest to remember for you is the best.

### 5.3 Jacobian

See the supplementary document on Jacobians to help understand, which is more mathematical. Here we just list the results, which is enough for solving problems.

$$
\boxed{\begin{aligned}
\left(\frac{\partial X}{\partial Y}\right)_ {Z} &=1 /\left(\frac{\partial Y}{\partial X}\right)_ {Z} \\
\left(\frac{\partial X}{\partial Y}\right)_ {Z} &=\left(\frac{\partial X}{\partial W}\right)_ {Z} /\left(\frac{\partial Y}{\partial W}\right)_ {z} \\
\left(\frac{\partial X}{\partial Y}\right)_ {Z} &= \color{red}{-}\left(\frac{\partial Z}{\partial Y}\right)_ {X} /\left(\frac{\partial Z}{\partial X}\right)_ {Y}	\end{aligned}
}$$

Jacobians is very useful when we have e.g. $G,S$ as constant, and we want to bring it to denominators, so that we can either expand them or get the useful second derivatives.

### 5.4 Reduce the Derivatives (EP4)

**General rules:**

1. Try to put extensive variables at molecule, and intensive variables at denominator. For example:

$$ \left( \frac{\partial P}{\partial U} \right) _ {G,N} 	\rightarrow \left[ \left( \frac{\partial U}{\partial P} \right) _ {G,N} \right] ^ {-1}$$

2. Try to put expandable functions $(U,F,H,G)$ at molecule and expand them.

$$ \because dU=T dS-P dV +\mu dN $$

$$ \therefore \left[\left(\frac{\partial U}{\partial P}\right)_ {G,N}\right]^{-1} = \left[T\left(\frac{\partial S}{\partial P}\right)_ {G, N}-P\left(\frac{\partial V}{\partial P}\right)_ {G, N}\right]^{-1} $$  

3. Make use of the **jacobians** and **Maxwell relationships** when you need it.  

$$ \left(\frac{\partial S}{\partial P}\right)_ {G, N} = \frac{\left(\frac{\partial G}{\partial P}\right)_ {S, N}}{\left(\frac{\partial G}{\partial S}\right)_ {P, N}} $$

$$ \left(\frac{\partial S}{\partial P}\right)_ {T, N}=\left(\frac{\partial V}{\partial T}\right)_ {P, N}=-\alpha V $$

4. Be sure to remember all ~~four~~  five second derivatives clearly.

$$\alpha, \kappa_T ~(\text{or}~ \beta),\kappa_S, c_V, c_P $$

5. Plug in all results back and simplify it.

>Ps. Not to confuse with this two:
>
>$$
\left(\frac{\partial \color{red}{T}}{\partial X}\right)_ {\color{red}{T}, N} \equiv 0, \quad
\left(\frac{\partial \color{red}{T}}{\partial \color{red}{T}}\right)_ {X, N} \equiv 1
$$

### 5.5 Stability
...

## 6 - Unary Heterogeneous Systems

Unary: single component

Heterogeneous: more than one phase.

### Phase

A **phase** is a physically distinct region of a system.

Different crystal structure means different phase, including _allotropes_ (single component) and _polymorphs_ (multicomponents).

### Phase Diagrams

**Phase diagrams** can tell us which phase id stable for a system under certain condition. Sometimes write for short as $\mathrm{PD}$ or $\mathrm{\Phi D}$.

![@PD of SiO2|center|300x0](./1585260821906.png)

> 2nd order phase cannot co-exist, but 1st order phase can.

### The Clausius-Clapeyron Equation

A equilibrium line, where $\alpha$ and $\beta$ phases are in equilibrium, the $G, \mu, P,T$ must be equal, and therefore their viaration too $dG,d \mu, dP,dT$.

Then we have

$$\because d \mu^{\alpha}=d \mu^{\beta}$$

$$\therefore  -S^{\alpha} d T+V^{\alpha} d P=-S^{\beta} d T+V^{\beta} d P$$

$$\therefore \frac{d P}{d T}=\frac{\Delta S^{\alpha \rightarrow \beta}}{\Delta V^{\alpha \rightarrow \beta}}$$

Because

$$\Delta S^{\alpha \rightarrow \beta}=\frac{\Delta H^{\alpha \rightarrow \beta}}{T}$$

If one of $\alpha$ and $\beta$ phases is gas phase, the volume of gas is much larger then condensed phase, using the ideal gas model

$$\Delta V^{\alpha \rightarrow {g}}=V^{g}-V^{\alpha} \approx V^{g}=\frac{R T}{P}$$

Plugging in

$$ \frac{d P}{d T}=\frac{\Delta H^{\alpha \rightarrow \beta}}{RT^2/P}$$


Simplify it, we finally arrive at a very usefulrelation

$$ \frac{d \ln P}{d T}=\frac{\Delta H^{\alpha \rightarrow \beta}}{RT^2}$$

[EP5.2]()

## 9 - Multicomponent Homogeneous Nonreacting Systems: _Solution_

### 9.1 Partial Molar Properties (PMP)

Consider a multcomponent homogeneous system, with $c$ different components, each has mole number of $n_k ~ (k=1,2,...,c)$.

> **Attention:**$~ ~ ~$ $n_k$ is mole number, not confuse with $N_k$ which is partical number. $$N_k= n_k \cdot N_{avo}(\text{Avogadro number}).$$

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

$$G_{sol} = x_A \overline G_A + x_B \overline G_B \tag{* }$$

$$G_{sol} = \Delta G_{mix} + G_ {seperate}$$

Now we can construct the curve of $G_ {sol}$ for the first step.

![Alt text |center](./free_energy_solution_01.jpg)

***

From $(* )$ we can derive

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

The solute obeys Henry's Law

$$\lim_{X_B \rightarrow 0} a_B = \gamma^o X_B \\(\gamma^o:\text{Henry's Law constant})$$

Here is an illustration from Prof. Barmak's Lecture.


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

The difference of regular solution to ideal solution is, the enthalpy of regular solution is nonzero. $\color{red}{\text{needs varification}}$

Here we directly give the results:

$$\begin{aligned}
\Delta G_{mix}^{reg} &= \Omega x_A x_B + RT \left[ x_A \ln x_A + x_B  \ln x_B \right] \\
\Delta S_{mix}^{reg} &= \color{white}{zzzzzzzzzz}RT \left[ x_A \ln x_A + x_B  \ln x_B \right] =\Delta S_{mix}^{ideal}\\
\Delta H_{mix}^{reg} &= \Omega x_A x_B  \color{white}{zzzzzzzzzzzzzzzzzzzzzzzzzzzzz} \left(\Delta H_{mix}^{ideal} = 0 \right)
\end{aligned}$$

Regular solution will simplify to ideal solution when $\Omega = 0$

> **Attention: Nomenclature**
>
> In Im's class, $\Omega$  is **[regular solution parameter](#regular-solution-parameter)**, $\Omega = N_a \cdot z \left[ \epsilon_{AB} - \frac{1}{2} (\epsilon_{AA}+\epsilon_{BB})\right]$, $\omega$ is **configurational entropy**, $\omega = \frac{(N_A+N_A)!}{N_A! N_B!}$ .
>
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

#### Regular Solution Parameter

<!--[Regular Solution Parameter](#regular-solution-parameter) -->

<details>
<summary>Click to expand</summary>

Consider **1 mole** solid solution made of atoms A and B, with mole fraction of $x_A$ and $x_B$. And we want to investigate the enthalpy change during the mixing process $\Delta H_{mix}$

$$\Delta H_{mix} = H_{\text{solution}} - H_{\text{initial}}$$

Because solid solution is a condensed system, the enthalpy is approximately equal to energy, which can be expressed in terms of bound energies:

$$\Delta H_{mix}  \approx E_{\text{solution}} - E_{\text{initial}} \tag{1}$$

For intial state,

$$E_{\text{initial}} = x_A E_A^o + x_B E_B^o$$

where $E_A^o$ is energy of 1 mole pure A, and $E_B^o$ is energy of 1 mole pure B:

$$E_A^o = \frac{ N_{avo}Z}{2} \epsilon_{AA} \quad E_B^o = \frac{ N_{avo}Z}{2} \epsilon_{BB}$$

in which, $N_{avo}$ is Avogadro's number, $Z$ is coordination number(number of nearest neighbors), and **we assume the coordination number is same for A, B and AB solution.** $\epsilon_{AA}$ and $\epsilon_{BB}$ are bound energies of A-A bound and B-B bound.

Therefore the total energy before mixing is

$$E_{\text{initial}} =   \left[ x_A \epsilon_{AA} +x_B \epsilon_{BB} \right] \frac{ N_{avo}Z}{2} \tag{2}$$

For solid solution

$$E_{\text{solution}} = P_{AA}\epsilon_{AA} + P_{BB}\epsilon_{BB} + P_{AB}\epsilon_{AB} $$

where $P_{AA}, P_{BB},P_{AB}$ are numbers of A-A, B-B and A-B bounds.

Because of  an important assumption of regular solution, that **atoms are mixed randomly**, we have

$$ P_{AA} =  \frac{ N_{avo}Z}{2}$$

$$ P_{BB} = x_B x_B \frac{ N_{avo}Z}{2}$$

<!--$$ P_{AB} = x_A x_B \frac{ N_{avo}Z}{2} + x_B x_A \frac{ N_{avo}Z}{2} = 2 x_A x_B \frac{ N_{avo}Z}{2}$$-->

$$ P_{AB} = 2 \cdot x_A x_B \frac{ N_{avo}Z}{2}$$

Then substitute to get total energy after mixing

$$E_{\text{solution}} = \left[ x_A^2 \epsilon_{AA} +x_B^2 \epsilon_{BB}  + 2 x_A x_B \epsilon_{AB}\right] \frac{ N_{avo}Z}{2} \tag{ 3}$$

Plugging $(2)(3)$ into $(1)$

$$\begin{aligned}
\Delta H_{mix}  &\approx \frac{ N_{avo}Z}{2} \left[	 (x_A \epsilon_{AA} +x_B \epsilon_{BB} ) -(x_A^2 \epsilon_{AA} +x_B^2 \epsilon_{BB}  + 2 x_A x_B \epsilon_{AB}) \right]\\
&= \frac{ N_{avo}Z}{2} x_A x_B\left[	2 \epsilon_{AB} - \epsilon_{AA} - \epsilon_{BB}\right]	\\
&= \Omega x_A x_B
\end{aligned}$$

where

$$\Omega =  N_{avo}Z\left[ \epsilon_{AB} - \frac{1}{2}(\epsilon_{AA} - \epsilon_{BB})\right]$$

</details>


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

### $G$ as a function of temperature

$$\because C_{P}=\left(\frac{\partial Q}{\partial T}\right)_ {P}=\left(\frac{\partial H}{\partial T}\right)_ {P}$$

$$\therefore H=H_0 +\int C_ P dT$$

$$S=\int_0^T d S=\int_0^T \frac{d Q}{T}=\int_0^T \frac{C_P}{T} d T$$

$$G=H-TS$$

$$\left(\frac{\partial G}{\partial T}\right)_ P =-S < 0$$

$$\left(\frac{\partial^{2} G}{\partial T^{2}}\right)_ {P}=-\left(\frac{\partial S}{\partial T}\right)_ {P}=-\frac{C_{P}}{T} < 0$$

We should be able to draw sketches about $H$, $S$, $G$.

Need to add picture later.

### Order of Phase Transitions(Transformations)

Ehrenfest's defination:

For s $n$-th order transformation, $\large \frac{\partial^{n-1} G}{\partial T^{n-1}}$ is continious, and $\large \frac{\partial^{n} G}{\partial T^{n}}$ is discontinious.

### Thermodynamic Driving Force of Transformation
$$\large \color{red} {\text{Need to do}}$$

### Gibbs Phase Rule

Generally, **the freedom of a system $F$**, equals the numbers of variables minus numbers of independent relations. We can write it informally as

$$ F = N_{\text{variables}} - N_{\text{relations}} \tag{1 }$$

Consider a system composed of **$C$ components** and has **$P$ phases**.

In order to describe the composition of particular phase $\phi$,  we need $(C-1)$ variables

$$x_i^\phi \quad (i=1,2,\cdots,C-1;\phi=\alpha,\beta,\delta,\cdots)$$

>Here we don't need the $C$-th variables, since it's independent and can be determined via $\sum x_i^\phi = 1$.

Then for all $P$ phases we have $P(C-1)$ variables.

In addition, we treat **temperature and pressure** as variable for common thermodynamics systems, therefore there are two more variables. And in sum, we have

$$N_{\text{variables}} = P (C-1) + 2 \tag{2}$$

As for the numbers of relations, we know that chemical potential of every component in each phase is equal in equilibrium, i.e.

$$\mu_i^\alpha = \mu_i^\beta = \mu_i^\delta = \cdots \quad (i=1,2,\cdots,C)$$

In sum

$$N_{\text{relations}}  = C (P-1) \tag{3}$$

Plugging $(2)(3)$ back to $(1)$, we have

$$\begin{aligned}
F &=  P (C-1) + 2 -  C (P-1)\\
&= C-P+2
\end{aligned}$$

**The Gibbs Phase Rule**

$$\boxed{F=C-P+2}$$

If we are investigating **condensed systems**, the pressure can be considered fixed, therefore we have another representation

$$F=C-P+1$$

$\rightarrow$ &rarr; [Application of chemical reaction](http://www.che.uc.edu/jensen/w.%20b.%20jensen/reprints/079.%20Phase%20Rule.pdf)