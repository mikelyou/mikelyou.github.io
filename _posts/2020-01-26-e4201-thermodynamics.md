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

> This post is study note of E4201 course, all rights reserved. I do not own copyright of some contents, if the article unintentionally infringes your copyright, it will be deleted shortly after being informed.

## Lec 1 - Macroscopic Thermodynamics

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
  - Diathermal/adiabatic（绝热） or not
  - Permeable or impermeable
  - Movable or fixed
- Surrounding

### 1.3 Thermodynamic Variables

#### Defination and innerrelation of thermodynamic Variables

$$ G \equiv U + PV - TS $$

$$ H = U + PV $$

$$ F = U - TS $$

$$ \mu_i = \frac{\partial G}{\partial n_i} $$

#### State variables and process Variables

- **State variables(or state functions)**: depends only on condition(or state) of the system. Eg. $V$, $S$, $T$, $U$, $H$, $G$.
- **Process variables**: quantities than only have meaning for changing systems. They are variable depending on the choice of path. Eg. $W$, $Q$.

#### Extensive and Intensive State Variables

The state variables can be classified into finer classes.

- **Extensive** state variables: depend on system size. Which means double the system will change the variable value. Eg. $V$, $S$, $n$, $U$, $H$, $G$.

- **Intensive** state variables: not depend on system size. Eg. $T$, $P$, $\mu$(chemical potemtial).

- **Normalized extensive variables\***: extensive variables per mole or unit volume. These are in effect **intensive**.

#### Conjugate Variables

Each extensive variable has a conjugate intensive variable.

## Lec 2 - Laws of Thermodynamics

> 众所周知，热力学三大定律一共有四条（还有第零定律）。

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

## Lec 3 - Conditions of Equilibrium

### Equilibrium States

Equilibrium states of simple macroscopic systems are characterized by system parameters including

$$\left( U, V, N_1, N_2, \cdots , N_r \right) $$

If systems are more complex, parameters will be more.

The **equilibrium states** are states in which **entropy is maximized** for the given constraints.
