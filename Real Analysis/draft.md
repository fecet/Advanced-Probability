---
title: "Random-Nikodym Theorem"
author: Xie Zejian
# date: Sep 27, 2020
output:
  pdf_document:
    toc: true
    toc_depth: 2
    # number_sections: true  
    highlight: tango
    latex_engine: pdflatex

export_on_save:
  pandoc: true
---

## Signed measures

A finite set function $\mu:\mathcal{A}\to \mathbb{R}$ is called as a **signed measure** if it's $\sigma$ additive.

Given a signed measure, its **total variance** is given by

$$ |\mu|(E)=\sup_P\{\sum_j |\mu(E_j)|\} $$

for all partitions $P$  of $E$. One can check total variance is also a finite measure.

Following proposition yield lots of signed measure:

> Let $(X,\mathcal{A},\mu)$ be a measure space and $\omega\in L^1(\mu)$. Then define
> $$ \nu(A)=\int_A \omega d\mu $$
> Such $\nu$ is a signed measure and $\mu \ll \nu$. For all measurable function $f:X\to [0,\infty]$, we have
> $$ \int_A fd\nu=\int_A f\omega d\mu $$
> And its total variance is given by
> $$ |\nu|(E)=\int_E |\omega| d\mu $$

**Proof**

$\nu$ is $\sigma$ additive since lebesgue integral is $\sigma$ additive over sets and absolute continuous follows from integral on an null sets is zero. 

Suppose $f$ is simple and $f=\sum a_i \chi_{E_i}$, then

$$ \begin{aligned}
    \int_A f dv&=\sum a_i \int_A \chi_{E_i} d\nu
    \\&=\sum a_i \int_{A\cap E_i} d\nu
    \\&=\sum a_i \nu(A\cap E_i)
    \\&=\sum a_i \int_{A\cap E_i} \omega d\nu
    \\&=\sum a_i \int_{A} \omega \chi_{E_i}d\nu
    \\&=\int_A f\omega d\mu
\end{aligned} $$

If is measurable, then we can find $f_n \nearrow f$ and by MCT

$$\int_A f d\nu=\lim \int_A f_n d\nu=\lim \int_A f_n \omega d\mu=\int_A f\omega d\mu $$

For the total invariance, note $A=\{x\in E:\omega(x)\ge 0\}$ and $A=\{x\in E:\omega(x)< 0\}$ are a measurable partition of $E$, and

$$ |\nu|(E)\ge |\nu(A)|+|\nu(B)|=\int_E|\omega| d\mu $$

On the other hand:

$$ \begin{aligned}
    \sum |\lambda(E_i)|&=\sum|\int_{E_i} \omega d\mu|
    \\&\le \sum \int_{E_i} |\omega| d\mu
    \\&=\int_E |\omega| d\mu
\end{aligned} $$

Taking sup both sides, we get what we desired. $\blacksquare$


Let $\mu$ and $\nu$ be two measure, then $\nu$ is absolutely continuous w.r.t. $\mu$ if $\mu(A)=0\implies \nu(A)=0$ and denoted as $v\ll \mu$.

Let $\mu$ and $\nu$ be two signed measure, then $\nu$ is absolutely continuous w.r.t. $\mu$ if $|\mu|(A)=(\mu^++\mu^-)(A)=0\implies \nu(A)=0$ and denoted as $v\ll \mu$.

Let $\mu$ be a measure and $\nu$ be any kind measure, then $\nu$ is absolutely continuous w.r.t. $\mu$ if $\mu(A)=0\implies \nu(A)=0$ and denoted as $v\ll \mu$.

Let $\mu$ be any kind of measure then $\mu$ is **concentrated** if $\forall E\in \mathcal{A}$, $\nu(A)=\nu(E\cap A)$. 