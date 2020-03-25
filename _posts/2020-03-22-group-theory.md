---
layout: post
title: "Group Theory and Quantum Mechanics"
subtitle: 'A simple and uncomplete summary'
date: 2020-03-22 23:16:00
author: "Mike Lyou"
header-style: text
#header-img: "img/post-bg-2015.jpg"
mathjax: true
catalog: true
copyright-statement: CC BY-NC
hidden: true
excerpt: This is a study note of Group Theory and Quantum Mechanics.
tags:
  - Notes
  - Group Theory
---

<!-- more -->


> This is a study note of _Group Theory and Quantum Mechanics_.
>It is not complete and maybe never will be. I write this just because I have written it neatly on papers and it looks good. So I decided to turn it into a more convenient and explicit electronic version. It's converted from picture using OCR, so there may be some typo I didn't notice.
>Don't try to ask me questions. I don't know.


## 2 Abstract Group Theory

#### 2.1 Definition of Groups

A **group** is a set of elements that satisfy group multiplication, therefore must satisfy:

1. **Closed**. The product of two elements is in the set. ie $A B=C$
2. **Associative**. $A(B C)=(A B) C$
3. **Identity**. Unitary element must in set. $E A=A E=A$
4. **Inverse**. There is an inverse of each element. $A^{-1} A=A A^{-1}=E$

The number of elements $h$ is called **order**.

If group multiplication is **commutative**, i.e. $A B=B A$ the group is called  **Abelian Group**.

#### 2.2 Rearrangement Theorem

In the multiplication table, each element appears in each column or row **once and only once**.

#### 2.3 Subgroups ard Cosets

**A subgroup** is a subset of a larger group, and itself is a group.

Let $\mathscr{S}=E, S_2, S_3, \cdots, S_{g}$ be a subgroup of a larger group $\mathscr{G}$ of order $h$.

Then we call the set of $g$ elements $EX, S_2X, S_3X, \cdots, S_{g}X$ a **right coset** $\mathscr{S}X$, if $X$ not in $\mathscr{S}$. Similary, we can define left coset $X \mathscr{S}$

$\rightarrow$ cosets cannot be subgroups, since they cannot have identity element $E$.

$\rightarrow$ A coset $\mathscr{S}X$ contains no common elements with subgroup $\mathscr{S}$

$\rightarrow$ Two right (or left) cosets of subgroup $\mathscr{S}$ in $\mathscr{G}$ **either are identical or have no common elements**.

 The order $g$ of a subgroup $\mathscr{S}$ must be an integer divisor of the order $h$ of entire group $\mathscr{G}$, i.e. $h/g=l,$ where $l$ is called the index of the subgroup  $\mathscr{S}$ in $\mathscr{G}$

>Proof:
>
>Each of the $h$ elements of $\mathscr{G}$ must appear either in $\mathscr{S}$ or in  $\mathscr{S}X$, for some $X$. Thus each element must appear in one of the sets $\mathscr{S},\mathscr{S}X_2,\mathscr{S}X_3,\cdots, \mathscr{S}X_l$. And we know there are no common elements within these $l$ sets. Hense, the $l$ sets averagely divide $\mathscr{G}$, i.e. $h=l \times g$

>Ps. $\mathscr{S}$ is letter $S$, the LaTeX code is `$\mathscr{S}$`. Similary, $\mathscr{G},\mathscr{K},\mathscr{R}$ are $G,K,R$ respectively.

#### 2.4 Conjugate Elements and Class Structure

An element $B$ is said to **be conjugate to** $A$ if

$$B=XAX^{-1}$$

where $X$ is some mumber of the group.

$\rightarrow$ If $B$ is conjugate to $A$, then $A$ is conjugate to $B$. Since $A=X^{-1} B X$

$\rightarrow$ If $B$ and $C$ are both conjugates to $A$, then $B$ and $C$ are conjugate to each other.

The collection of all mutually conjugate elements is called **a class**.

$\rightarrow$ In Abelian groups, each element is in a class by itself. Since $X A X^{-1}=A X^{-1} X=A$, i.e. element $A$ can only be conjugated to itself.

#### 2.5 Normal Divisors and Factor Groups

If a subgroup $\mathscr{S}$ of a larger group $\mathscr{G}$ consists entirely of complete classes, it is called an **invariant subgroup** or **normal divisors**, ie if $A$ in $\mathscr{G}$, then all $X A X^{-1}$ in $\mathscr{G}$.

Now introduce the _notion of complex_.

>$\mathscr{K}=\left(K_{1}, K_{2}, \cdots, K_{n}\right)$ is a colllection of group elements disregarding order.
>
>$\mathscr{K} X=\left(K_1 X, K_2 X, \cdots, K_{n} X\right)$
>
>$\mathscr{K}\mathscr{R}=\left(K_1 R_{1}, K_{1} R_{2},\cdots, K_{n} R_{m}\right)$
>
>Elements are considered to be included only once, regardless of how often they are generated.

Then we can state our argument using complexes.

- $\mathscr{S}\mathscr{S}=\mathscr{S}$ closure of groups.

- $X^{-1}\mathscr{S}X=\mathscr{S}$  for invariant subgroup $\mathscr{S}$ and all $X$ in $\mathscr{G}$

- $\mathscr{S}X=X\mathscr{S}$ left and right cosets of an invariant subgroup are identical.

In `Sec.02-3` we prove that there are a finite number $(l-1)$ of distinct cosets for any subgroup $\mathscr{S}$. The collection of $\mathscr{S}$ ard the $(l-1)$ distinct cosets can themselves be regarded as elements of a new group.

This group $\mathscr{S},\mathscr{S}X_2,\mathscr{S}X_3,\cdots, \mathscr{S}X_l$ is called **the factor group** of $\mathscr{G}$ with respect to the **normal divisor** $\mathscr{S}$. In this factor group, $\mathscr{S}$ forms the unit element, since

$$\mathscr{S}\mathscr{K}_i = \mathscr{S} (\mathscr{S} {K}_i) = (\mathscr{S}\mathscr{S}) {K}_i = \mathscr{S} K_i =\mathscr{K}_i$$

#### 2.6 Isomorphy and homomorphy

Two groups are said to be i**somorphy** if there exist a one-to-one correspondence between the elements $A, B,\cdots$ of one group and elements $A^{\prime}, B^{\prime},\cdots$ of the other group, such that $A B=C$ implies $A^{\prime} B^{\prime}=C^{\prime},$ and vice versa.

$\rightarrow$ Tuo groups are isomorphy when they have the same multiplication table.

Two groups are said to be **homomorphy** if there exist a correspondence between two groups that $A \leftrightarrow A_{1}^{\prime} A_{2}^{\prime}, \cdots, \quad B \leftrightarrow B_{1}^{\prime}, B_{2}^{\prime}, \ldots, \quad C \leftrightarrow C_{1}^{\prime}, C_{2}^{\prime}, \ldots \quad$ such that $A B=C$ implies $A_i^\prime B_j^\prime $will be a number of the set $C_{k}^{\prime}$

In general, a **homomorphism** is a many-to-one correspondence.
It specializes to **isomorphism** if the correspondence is one-to-one.

#### 2.7 Class Multiplication

! In this section, $\mathscr{R} = \mathscr{K} $ implies that each element appear as often in $\mathscr{R}$ as in $\mathscr{K}$.

>?

## 3 Theory of Group Representation

#### 3.1 Representation of an abstract group

A _rep_ of an abstract group is in general any group composed of concrete mathematical entities which is **homomorphic** to the abstract group. However, we are interested in **square matrices**, i.e we associate each group element $A \leftrightarrow \hat{\Gamma}(A)$ with a matrix such that

$$
\hat{\Gamma}(A) \hat{\Gamma}(B)=\hat{\Gamma}(A B)
$$

$\rightarrow$ Clearly, $\hat{\Gamma}(E)=\hat{E}$ or $\hat{1}$

$\rightarrow$ number of rows or columns of the matrix is called the **dimensionality** of the representation.

If each matrix is different, then the two groups are isomorphic (rather then only homomorphic), and the representation is said to be **true or faithful**.

If several elements correspond to a single matrix, then all elements corresponding to the unit matrix $\hat{E}$ form an **invariant subgroup** of the full group. And elements corresponding to other matrices rather than $\hat{E}$ form the **distinct cosets** of that invariant group. And these matrices form a true representation of the **factor group** of this invariant subgroup.

If a similarity transformation leaves matrix equations unchanged, i.e.

$$\begin{aligned}
\hat{\Gamma}(A) &=\hat{S}^{-1} \Gamma(A) \hat{S}\\
\downarrow \\
\hat{\Gamma} (A) \hat{\Gamma} (B) &= \left[\hat{S}^{-1}\Gamma (A) \hat{S} \right] \left[\hat{S}^{-1}\Gamma (B) \hat{S} \right] =\hat{S}^{-1} \hat{\Gamma} (A)\hat{\Gamma} (B)\hat{S} = \hat{\Gamma} (AB)
\end{aligned}$$

then the transformed matrics $\hat{\Gamma}^{\prime}$ form a representation, as long as $\Gamma$ do, ie they are **equivalent**.

> Reference: Tinkham, M. _Group Theory and Quantum Mechanics_.
