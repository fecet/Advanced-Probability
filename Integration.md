---
title: "Integration"
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
# Expectation and integration

## Integration

Let $f$ be Borel measurable on $(\Omega,\mathcal{A},\mu)$. The **integral** of $f$ w.r.t $\mu$ is denoted by
$$ \int f ( \omega ) \mu ( d \omega ) = \int f d \mu = \int f $$

1. If $f=\sum_1^n a_iI_{A_i}$ with $a_i\ge 0$,
$$ \int f d \mu = \sum _ { 1 } ^ { n } a _ { i } \mu \left( A _ { i } \right) $$

2. 
    If $f\ge 0$,define

    $$ \int fd\mu=\lim_n \int f_nd\mu $$ 

    where $f_n$ are simple functions and $f_n \nearrow f$.

1. 
    For any $f$, we have $f=f^{+}-f^{-}$, define 
    
    $$ \int f d \mu : = \int f ^ { + } d \mu - \int f ^ { - } d \mu $$ 

2. 
    $f$ is said to be integrable w.r.t. $\mu$ if $\int|f|d\mu<\infty$. We denote all integrable functions by $L^1$.

**Proposition** 

1. 
    If $f$ is positive and $a\le f(x)\le b$ and $\mu(\Omega) > \infty$, then 

    $$ a\mu(\Omega)\le \int fd\mu \le b\mu(\Omega) $$

2.
    The integral of $f$ w.r.t $\mu$ over $A$ is defined by 
    
    $$ \int _ { A } f d \mu = \int f I _ { A } d \mu = \int f ( \omega ) I _ { A } ( \omega ) \mu ( d \omega ) $$

    If $\mu(A)=0$ and $f>0$, then

    $$ \int_A fd\mu=0 $$

### MCT

Suppose nonnegative $f_n\nearrow f$, then $\int f_n d\mu \nearrow \int f d\mu$.

**Proof** Note $\int f_n d\mu \le \int fd\mu$, $\int f_n d\mu$ must converges to some $L\le \int f$. Then we show $L\ge \int f$. 

Let $s=\sum a_i \chi_{E_i}$ be simple function and $s\le f$. Let $A_n=\{x:f_n(x)\ge cs(x)\}$ where $c\in(0,1)$, then $A_n \nearrow X$. For each $n$

$$ \begin{aligned}
    \int f_n\ge \int_{A_n} f_n &\ge c\int_{A_n} s
    \\&= c\int_{A_n} \sum a_i\chi_{E_i}
    \\&=c \sum a_i\mu(E_i\cap A_n)
    \\&\nearrow c\int s
\end{aligned} $$

hence $L\ge c\int s\implies L\ge \int s\implies L= \lim L\ge \lim \int s_n=\int f$. $\blacksquare$

If $f$ and $g$ are intergrable or $f,g\ge 0$, then

note where $f_n$ is integrable not enough since MCT not hold.

$$ \int f+g =\int f+\int g $$

Moreover, if $f_n>0$ then

$$ \int \sum_1^\infty f_n=\sum_1^\infty \int f $$

### Fatou's lemma

If  $f_n\ge 0$ then
$$ \int  \left( \liminf_ { n } f _{ n } \right) \leq \liminf_ { n } \int  f _ { n } $$

**Proof** Suppose $g_n=\inf_{i\ge n}f_i$ and recall that $\lim g_n=\liminf f_n$. Clearly $g_n\le f_i \forall i\ge n$  hence 

$$ \int g_n \le \inf_{i\ge n}\int f_i $$

Take limit both side and note $g_n$ is increasing:

$$ \lim \int g_n=\int \lim g_n=\int \liminf f_n\le \liminf \int f_n $$

### Dominated convergence theorem

Suppose $f_n(x)\to f(x) \forall x$, and there exists a nonnegative integrable $g$ s.t. $|f_n(x)|\le g(x)$(then we get $f_n\in L^1$ immediately), then

$$ \lim \int f_n d\mu=\int f d\mu $$

**Proof** Since $f_n+g\ge 0$

$$ \int f+\int g=\int f+g\le \liminf \int f_n+g=\liminf \int f_n+\int g $$

thus $\int f\le \liminf_{n\to \infty}\int f_n$. Similarly, we can get $\int f\le \liminf_{n\to \infty}\int f_n$ from $g-f_n\ge 0$. $\blacksquare$

## Properties of Lebesgue integrals

### Criteria for zero a.e.

Suppose $f$ is measurable and non-negative and $\int fd\mu=0$. Then $f=0$ a.e.

Suppose $f$ is integrable and $\int_A f=0$ for all measurable $A$. Then $f=0$ a.e.

Suppose $f:\mathbb{R} \to \mathbb{R}$ is integrable and $\int_a^x f=0$ for all $x$, then $f=0$ a.e.

**Proof** For any interval $I=[c,d]$,

$$ \int_i f=\int_a^d f-\int_a^c f=0 $$

Then the integral is $0$ for finite disjoint union of intervals from additivity. Note open sets $G$ can be written as countable union of disjoint open intervals $G=\sum_1^\infty I_i=\lim \sum I_n\implies$

$$\int_G f=\int f\chi_G=\int f\sum_1^\infty \chi_{I_i}=\int \lim f\sum \chi_{I_i}=\lim \int f\sum \chi_{I_i}=0 $$

If $G_n\searrow H$, then

$$ \int_H f = \int f\chi_H=\int \lim f\chi_{G_n}=\lim\int f\chi_{G_n}=\lim \int_{G_n} f=0 $$

where we apply DMT twice and take domiated function $g=|f|$.

Finally, for any borel measurable set $E$, there is $G_\delta\supset E$ and $m(G_\delta-E)=0$, then

$$ \int_E f=\int f\chi_E=\int f\chi_{G_\delta}=\int_{G_\delta} f=0 $$

Recall proposition **2**, we are done. $\blacksquare$

(**Absolute integrability**). $\int f$ is finite iff $\int|f|$ is finite.

**(Linearity)** If $f,g,a,b\ge 0$ or $f,g\in L^1$
$$ \int(af+bg)=a\int f+b\int g $$

**($\sigma$ additivity over sets)** If $A=\sum_{i=1}^\infty A_i$, then
$$ \int _ { A } f = \sum _ { i = 1 } ^ { \infty } \int _ { A _ { i } } f $$

**(Positivity)** If $f\ge 0$ a.s., then $\int f\ge 0$

**(Monotonicity)** If $f_1\le f\le f_2$ a.s., then $\int f_1\le \int f 
\le \int f_2$

**(Mean value theorem)** If $a\le f \le b$ a.s., then 

$$ a\mu(A)\le \int _Af\le b\mu(A) $$

**(Modulus inequality)**: $|\int f|\le \int |f|$

**(Fatou's) inequality** If  $f_n\ge 0$ a.s., then
$$ \int  \left( \liminf_ { n } f _{ n } \right) \leq \liminf_ { n } \int  f _ { n } $$

**(Dominated Convergence Theorem)** If $f_n \to f$ a.s., $|f_n|\le g$ a.s. for all n and $\int g <\infty$, then

$$ \lim_n \int f_n=\int f=\int \lim_n f_n $$

**(Monotone Convergence Theorem)** If $0\le f_n\nearrow f$, then
$$ \lim_n \int f_n=\int f=\int \lim_n f_n $$

**(Integration term by term)** If $\sum_{i=1}^\infty \int |f_n|<\infty$, then
$$ \sum_{i=1}^\infty |f_n|<\infty,\ a.s. $$

and
$$ \int  \left( \sum _{ i = 1 } ^ { \infty } f_ { n } \right) = \sum _{ i = 1 } ^ { \infty } \int  f_ { n } $$


### An approximation result

Suppose $f:\mathbb{R}\to \mathbb{R}$ is integrable, then $\forall \epsilon> 0$, there exists a continuous $g$ with compact support and

$$ \int|f-g|< \epsilon $$

**Proof** Note $\int f\chi_{[-n,n]}\nearrow \int f$, hence we may assume $f$ is bounded.

If $f=\chi_A$, there exist $F\subset A\subset G$ and $m(G-F)< \epsilon$, take $\delta=d(K,G^c)$, let

$$ g(x)=(1-\frac{d(x,F)}{\delta}) $$

Then $g$ has compact support $\overline{G}$ and $\int|g-\chi_A|\le \int \chi_{G}-\chi_F=m(G-F)< \epsilon$.

If $f=\sum a_i\chi_{A_i}$ is simple with bounded $A_i$. Then we may take $g=\sum a_i g_i$ with compact support is $\overline{\cup G_i}$.

If $f$ is non-negaive, there exist $\int s_n\nearrow \int f$, then we can pick $s$ s.t.

$$ \int |f-s|< \epsilon/2 $$

and we can pick

$$ \int |s-g|< \epsilon/2 $$

hence we find $\int |f-g|< \epsilon$. $\blacksquare$

## Riemann Integration

Suppose an interval $I$ and $f:I\to \mathbb{R}$ is riemann integrable, then it's also Lebesgue measurable.

$$ \int_I f=\mathscr{R}\int_I f $$

**Proof** One can take a series of partition $D_n^\alpha$ and $D_n^\beta$ s.t. 

$$ 
\lim L(D_n^\alpha,f)= \mathscr{R}\underline{\int_I} f,\lim L(D_n^\beta,f)= \mathscr{R}\overline{\int_I} f, 
$$

Let $D_n=D_n^\alpha \cup D_n^\beta$, then it's a finer partition than $D_n^\alpha$ and $D_n^\beta$, then 

$$  \begin{aligned}
    L(D_n,f)&\ge L(D_n^\alpha,f)
    \\U(D_n,f)&\le U(D_n^\beta,f)
\end{aligned}$$

hence

$$ 
\lim L(D_n,f)= \mathscr{R}\underline{\int_I} f,\lim L(D_n,f)= \mathscr{R}\overline{\int_I} f, 
$$

Moreover, refine $D_n$ into $P_n=\bigcup_{1}^n D_i$, recall

$$ L(P_n,f)=I(\alpha_{P_m})=\sum \alpha_{P_n}(x)(x_i-x_{i-1}) $$

where 

$$ \alpha_P(x)=\begin{cases}
    \inf\{f(x):x\in(x_{i-1},x_i]\} & x\in (x_{i-1},x_i]
    \\ \inf\{f(x):x\in[a,x_1]\} & x=a
\end{cases} $$

$\alpha_{P_n}(x)$ is increasing $\forall x$ since $P_n\subset P_{n+1}$, thus $\alpha_{P_n}\to g\le f$
and similarly $\beta_{P_n}\to h\ge f$.

Note lebesgue integrate is identical to riemann integrable

$$ \int_I \alpha_P=I(\alpha_P)=\mathscr{R}\int_I \alpha_P $$

hence

$$ \begin{aligned}
    \int_I g=\int_I \lim  \alpha_{P_n}=\lim \int_I \alpha_{P_n}=\lim I(\alpha_{P_n})=\mathscr{R}\underline{\int_I} f
\end{aligned} $$

Similarly $\int_I h=\mathscr{R}\overline{\int_I} f$, therefore

$$ \int_I h=\int_I g \implies \int_I h-g=0\implies h=_{a.s.}g\implies f=_{a.s.}g  $$

Thus we finally have

$$ \int_I f=\int_I g=\mathscr{R}\int_I f.\blacksquare $$

Continue the discussion above. Let $\Delta(D)=\max\{x_i-x_{i-1}\}$, then

> If $\lim_{n\to \infty} \Delta(P_n)=0$, then $\forall x_0\notin \cup P_n$, $f$ continous at $x_0$ iff $g(x_0)=f(x_0)=h(x_0)$.

**Proof** $\implies$: There exists $N$ s.t. $\forall n\ge N$, $\Delta(P_n)\le \delta$. Suppose $x_0\in I$, then $m(I)\le\delta$, hence $|f(y)-f(x_0)|\le \epsilon$ holds for all $y\in I$ hence

$$ |\inf_{I} f(y)-f(x_0)|\le \epsilon\implies |\alpha_{P_n}(x_0)-f(x_0)|\le\epsilon $$

together with $|\beta_{P_n}(x_0)-f(x_0)|\le\epsilon$, we have

$$ |h(x_0)-g(x_0)|\le |\beta_{P_n}(x_0)-\alpha_{P_n}(x_0)|\le 2\epsilon $$

hence $g=f=h$ at $x_0$.

$\impliedby$: If $f$ isn't continous at $x_0$, there exist $y\in I\ni |f(y)-f(x_0)|\ge \epsilon$, however

$$ \sup_I f-\inf_I f\ge |f(y)-f(x_0)|\ge \epsilon $$

hence $\beta_{P_n}-\alpha_{P_n}\ge \epsilon$ hold for all $n$, take $\lim$ both side

$$ h(x_0)-g(x_0)\ge \epsilon $$

contradition. $\blacksquare$

Then we are ready to the main theorem this chapter.

> Let $f:I\to \mathbb{R}$ is bounded, then $f$ is riemann integrable iff $f$ is continuous a.e.

**Proof** Suppose $P_n$ we taking before. We have:
$f$ continous a.e. in $I$ iff $f$ continous a.e. in $I-\cup P_n$ iff $g=h$ holds a.e. iff $\int_I g=\int_I h$ iff $f$ is integrable.




















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
<br>
<br>
<br>
