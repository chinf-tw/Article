---
title: '如何證明兩個集合相等'
date: 2022-06-28
tags:
  - prove
  - math
  - null space
math: true
---

## 證明題目
Let $\forall \mathbf{A} \in \mathbb{R}^{m\times n}$, $\text{N}(\mathbf{A})$ be the null space of $\mathbf{A}$, $\text{N}(\mathbf{A}^{\mathrm{T}} \mathbf{A})$ = $\text{N}(\mathbf{A})$.  

本文章將以直接證明法證明 $\mathbf{A}^{\mathrm{T}} \mathbf{A}$ 的零空間集合與 $\mathbf{A}$ 的零空間集合是相等的，屆時即教學如何證明兩集合相等。

### 集合相等的充分且必要條件

$$
\text{Let }\mathbf{A} \text{ and } \mathbf{B} \text{ are set. } \mathbf{A} = \mathbf{B}  \iff  \mathbf{A} \subseteq \mathbf{B} \text{ and } \mathbf{B} \subseteq \mathbf{A}
$$

如果 $\mathbf{A}$ 為 $\mathbf{B}$ 的子集，代表著 $\forall a \in \mathbf{A}$ 且 $a \in \mathbf{B}$，知道要證明兩集合相等需要的子證明後，回到原本要證明的題目，該題目要證明的是兩個零空間集合相等，在證明之前先介紹零空間的定義：

$$
\text{N}(\mathbf{A})=\left\{ \vec{x}\  \middle| \ \mathbf{A}\vec{x}=\vec{0} \right\}
$$

### 補充

$$
\vec{y}^\mathrm{T}\vec{y}=\lVert \vec{y} \rVert^2=0 \iff\vec{y}=\vec{0}
$$

## 開始證明
透過上述**集合相等的充分且必要條件**的描述可知，只需證明 $\text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A}) \subseteq \text{N}(\mathbf{A})$ 與 $\text{N}(\mathbf{A}) \subseteq \text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A})$ 成立，即可證明 $\text{N}(\mathbf{A}^{\mathrm{T}} \mathbf{A}) = \text{N}(\mathbf{A})$。 

首先，先證明 $\text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A}) \subseteq \text{N}(\mathbf{A})$：

$$
\begin{aligned}
  \forall \vec{u} \in \text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A})&,\ \mathbf{A}^{\mathrm{T}}\mathbf{A}\vec{u}=\vec{0} \\
  \vec{u}^{\mathrm{T}}\mathbf{A}^\mathrm{T}\mathbf{A}\vec{u}&=\vec{u}^{\mathrm{T}}\vec{0}=0 \\
  (\mathbf{A}\vec{u})^\mathrm{T}\mathbf{A}\vec{u}&=0 \\
  \mathbf{A}\vec{u}&=\vec{0} \\
  \therefore \text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A}) &\subseteq \text{N}(\mathbf{A})
\end{aligned}
$$

接著證明 $\text{N}(\mathbf{A}) \subseteq \text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A})$：

$$
\begin{aligned}
  \forall \vec{u} \in \text{N}(\mathbf{A})&,\ \mathbf{A}\vec{u}=\vec{0} \\
  \mathbf{A}^\mathrm{T}\mathbf{A}\vec{u}&=\mathbf{A}^\mathrm{T}\vec{0}=\vec{0} \\
  \mathbf{A}^\mathrm{T}\mathbf{A}\vec{u}&=\vec{0} \\
  \therefore \text{N}(\mathbf{A}) &\subseteq \text{N}(\mathbf{A}^{\mathrm{T}}\mathbf{A})
\end{aligned}
$$

Q.E.D.