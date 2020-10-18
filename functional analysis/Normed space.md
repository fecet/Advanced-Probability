---
title: "Normed space"
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
## Existence of bias
Every non-zero vector space has a basis.

**Proof** Let $\mathcal{X}$ be the class of all independent subsets of space $V$. Then $(\mathcal{X},\subset)$ is a poset. Forall chain $\mathcal{Y}\subset \mathcal{X}$, note $\cup \mathcal{Y}\in \mathcal{X}$ is a upper bound of $\mathcal{Y}$. Apply Zorn's lemma we can find a maximal element $B\in \mathcal{X}$ and $\langle B \rangle=V$, so $B$ forms a basis of $V$.

## Inequality

### Young's inequality

Let $f$ be a continues and strictly increasing function with $f(0)=0$, then we have

$$ a b \leq \int _ { 0 } ^ { a } f ( x ) d x + \int _ { 0 } ^ { b } f ^ { - 1 } ( x ) d x $$

Take $f(x)=x^{p-1}$, then $f^{-1}(x)=x^{q-1}$ if $(p-1)(q-1)=1\iff \frac{1}{p}+\frac{1}{q}=1$. Hence we have

$$ ab\le\frac{a^p}{p}+\frac{b^q}{q} $$

### Holder's inequality

For $\mathbf{a,b}\in \mathbb{R^n}$, $\frac{1}{p}+\frac{1}{q}=1$,

$$ \sum |a_ib_i|=\mathbf{|a|'|b|}\le \|\mathbf{a}\|_p\|\mathbf{b}\|_q $$

### Minkowski's inequality

For $\mathbf{a,b}\in \mathbb{F}^n$, $\frac{1}{p}+\frac{1}{q}=1$,

$$ \|\mathbf{a+b}\|_p \le \|\mathbf{a}\|_p+\|\mathbf{b}\|_p $$

## Normed Vector spaces

Let $(X,+,\cdot)$ be a vector space over $\mathbb{F}$. A norm on $X$ is a function from $X\to \mathbb{R\ge0}$ satisfy:

1. $\|x\|\ge0$ and $=$ occurs iff $x=0$
2. $\|x+y\|\le \|x\|+\|y\|$
3. $\|cx\|=|c|\|x\|$

A vector space with a norm is **normed vector space**. 

Let $\mathbf{c}$ is $n\times 1$ and $\mathbf{X}=\begin{bmatrix}
  \mathbf{x_1}&\mathbf{x_2}&\cdots & \mathbf{x_n}
\end{bmatrix}$ is $n\times n$ where $x_i$ is $n$ vector. Then

$$ \begin{aligned}
  \|\mathbf{Xc}\|&=\|\sum c_i \mathbf{x_i}\|
  \\&\le \sum \|c_i \mathbf{x_i}\|
  \\&= \sum |c_i|\| \mathbf{x_i}\|
  \\&= \|\mathbf{X}\||\mathbf{c}|
\end{aligned} $$

where 

$$
\|\mathbf{X}\|=\begin{bmatrix}
  \|\mathbf{x_1}\|&\|\mathbf{x_2}\|&\cdots & \|\mathbf{x_n}\|
\end{bmatrix},|\mathbf{c}|=\begin{bmatrix}
  |c_1|\\
  |c_2|\\
  \vdots\\
  |c_n|
\end{bmatrix}
$$

Then we give some examples of normed space:

> Let $\ell^p,1\le p<\infty$, be collection of sequence satisfying
> $$ \sum_1^\infty |x_i|^p<\infty $$
> It's a vector space and 
> $$ \|x\|_p=(\sum_1^\infty |x_i|^p)^{\frac{1}{p}} $$
> defines a norm on $\ell^p$

> Let $\ell^\infty$ be the collection of all $\mathbb{F}$ valued bounded sequences, it's a vector space and 
> $$ \|x\|_\infty=\sup_i |x_i| $$ defines a proper norm.


Let $(X,\|\cdot\|)$ be a normed space, define $d(x,y)=\|x-y\|$, one can check $d$ is a metric and is called as induced metric of the form. Then we can talk about convergence in this space. Clearly, the norm is a continuous function and $+$ and $\cdot$ are also continuous.

If $x_n\to x$ in $\|\cdot\|_1\implies x_n\to x$ in $\|\cdot\|_2$, we say $\|\cdot\|_1$ is stronger than $\|\cdot\|_2$. If they are stonger than each other, we say they are equivalent.

> All norm on finite dimensional space are equivalent.

**Proof** It's sufficient to show that every norm is equivalet to $\|\cdot\|_2$:

$$ \|\mathbf{x}\|=\|\mathbf{Ex}\|\le\|\mathbf{E}\||\mathbf{x}|\le \|\mathbf{x}\|_2\|(\|\mathbf{E}\|')\|_2=c\|\mathbf{x}\|_2 $$

where 

$$ \mathbf{E}=\begin{bmatrix}
  \mathbf{e_1}&\mathbf{e_2}&\cdots & \mathbf{e_n}
\end{bmatrix}=\mathbf{I} $$

This state that $\|\cdot\|$ stronger than any norm. On the other hand, consider

$$ \alpha=\inf\{\|\mathbf{x}\|:\|\mathbf{x}\|_2=1\} $$

It's positive since $\{\|\mathbf{x}\|_2=1\}$ is compact. Then we have

$$ \alpha\le \|\frac{\mathbf{x}}{\|\mathbf{x}\|_2}\|=\frac{\|\mathbf{x}\|}{\|\mathbf{x}\|_2}\implies\|\mathbf{x}\|\ge \alpha \|\mathbf{x}\|_2 $$

For any abstract space $X$, $x\in X$ can be presented as linear combinations of bias, say $x=\sum a_i e_i$, then $x\mapsto (a_1,\cdots,a_n)$ is isomorph from $X$ to $\mathbb{R^n}$. And any norm iduced a norm on $\mathbb{R^n}$ by

$$ \|x\|=\|(a_1,\cdots,a_n)\widetilde{\|} $$

Hence all norm is equivalent.

### Separability

A subset $E$ of $(X,d)$ is a **dense set** if its closure is $X$: 

$$ \overline{E}=X $$

A metric space is called **separable** if it has a countable dense subset.

### Completeness

A metric space $(X,d)$ is **complete** if every Cauchy sequence converges.

> Every





<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>








