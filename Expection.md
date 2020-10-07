### L-S integral and Lebesgue integral

Let $f$ be Borel measurable on $(\Omega,\mathcal{A},\mu)$.

- **(L-S integral)** In the case of $(\Omega,\mathcal{A},\mu)=(\Reals,\mathcal{B},\mu)$, we can write $x=\omega\in \Reals$ for easy understanding, then $$ \int f ( \omega ) \mu ( d \omega ) = \int f ( x ) \mu ( d x ) $$
- **(Lebesgue measure)** Moreover, if $\mu=\lambda$, where $\lambda$ is the Lebesgue measure, then $$ \int f(x)\lambda(dx)=\int f(x)dx $$

Recall that L-S measure is 

> **(L-S measure)** Suppose that $F$   is finite on $\Reals$ and 
>
> 1. $F$ is nondecreasing
> 2. $F$ is right continuous
Then there exist a unique measure $\mu$ on $(\Reals, \mathcal{B})$ with

$$ \mu((a,b])=F(b)-F(a) $$

Then we can define

$$ \int f d F : = \int f ( x ) d F ( x ) : = \int f ( x ) \mu ( d x ) = \int f d \mu $$

to be the **L-S integral of $f$ w.r.t. $F$**

Moreover if $\mu=\lambda$, which implies $F(x)=x$, hence

$$ \int f(x)dx=\int fd\lambda $$

which is the **Lebesgue integral of $f$**.

1. 
    Expectations are special case of integrals: 
    $$ EX=\int X(\omega)P(d\omega)=\int X(t)dF_X(t) $$

    where $F_X(t)=P(X\le t)$

#### Some special cases

Consider the $L-S$ integral of the form

$$ \int_B f dG $$

where $B$ is a borel set in $\Reals$.

When:

1. **$G$ is a discrete function** 
G will have jumps $\{x_1,x_2,\cdots\}$, where $\Delta G(x_n)=G(x_n)-G(x_n-)>0$, so $$ \int _ { B } f d G = \sum _ { n : x _ { n } \in B } f \left( x _ { n } \right) \Delta G \left( x _ { n } \right) $$

2. **$G$ is an absolutely continuous function**
When $G$ has derivative $g$, then
$$ \mu((s,t])=\int_{(s,t]}g(x)dx $$
Thus,

$$ \int_B fdG=\int_B f d\mu=\int_B f(x)g(x)dx $$

3. **$G$ is a mixture of discrete and absolute continuous functions**
In this case $G$ can be written as 
$$ G ( t ) = G ( a ) + \int _ { a } ^ { t } g ( x ) d x + \sum _ { n : x _ { n } \leq t } \Delta G \left( x _ { n } \right) $$
, then
 $$ \int _ { ( a , t ] } f ( x ) d G ( x ) = \int _ { ( a , t ] } f ( x ) g ( x ) d x + \sum _ { n : a < x _ { n } \leq t } f \left( x _ { n } \right) \Delta G \left( x _ { n } \right) $$

where $G$ is $G:[a,\infty)\to\Reals$

4. **$G$ is a right-continuous functions of bounded variation**
When $G$ is a right continuous function of bounded variation, then we have $G=G_1-G_2$, where both $G_1$ and $G_2$ are nondescreasing and right continuous.
then 
$$ \int _ { B } f d G = \int _ { B } f d G _ { 1 } - \int _ { B } f d G _ { 2 } $$



## Expectation

Let $X$ be a r.v. on $(\Omega,\mathcal{A},P)$

### Exceptation for simple r.v.

For simple r.v. $X=\sum_{1}^{n}a_iI_{A_i}$ with $\sum_1^n A_i=\Omega$ where $A_i$ are $\mathcal{A}$ measurable. Its expectation is 
$$ EX=\sum_1^n a_i P(A_i)$$

Some properties are list below:

1. $EC=C$
2. $E{I_A}=P(A)$
3. $E(aX+bY)=aEX+bEY$
4. $X\ge0 \implies EX \ge 0$
5. $X\ge Y \implies EX \ge EY$

Probability is continuous while expectation is not (but we still have expectations are continuous from below). To make sure its continuity, it should be

1. Monotone covergent
2. Dominated convergent

### Expection for nonnegative r.v.

Recall that any nonnegative r.v. can be approximated by a series of nonegative simple r.v.'s $X_n \nearrow X$

1. $E X=\lim_{n\to \infty} EX_n \le \infty$
2. $E_AX=E[X|A]=E(XI_A)$
3. If $Y\le0$, $-EY=E(-Y)$

$EX$ is well fefined, that is if $X_n \nearrow X$ and $Y_n \nearrow X$, then

$$ \lim EX_n = \lim E Y_n $$


#### Algebraic ops

Liinearity, nonegativity, monotonicity also holds.

If $X\ge 0$ Then $EX=0 \iff X =_{a.s.} 0$ which implies

1. $X>_{a.s.}0\implies EX>0$
2. $EX\ge 0\implies P(X\ge 0)\gt 0$


#### Fatou's lamaa

1. Suppose that $X_n \ge Y$ a.s. for all $n$ and some $Y$ with $E|Y|\le \infty$

$$ E(\liminf_{n\to\infty}X_n)\le \liminf_{n\to\infty}EX_n $$

2. Suppose that $X_n \le Y$ a.s. for all $n$ and some $Y$ with $E|Y|\le \infty$

$$ E(\limsup_{n\to\infty}X_n)\ge \limsup_{n\to\infty}EX_n $$

#### MCT(Monotone convergence theorems)

Let $X_{1:n}$ be nonnegative r.v.'s, then

1. $X_n(\omega) \nearrow X(\omega) \implies EX_n \nearrow EX$
2. $X_n(\omega) \searrow X(\omega) \implies EX_n \searrow EX$

From above theorem we have:
> If $Y_k \ge 0$ and $\sum_1^{\infty}Y_k(\omega)<\infty$, then
> $$ E \left( \sum _ { k = 1 } ^ { \infty } Y _ { k } \right) = \sum _ { k = 1 } ^ { \infty } E Y _ { k } $$

Fatou's lamma and MCT are equivalent.

## Expectation for general r.v.'s

Recall that $X^+=\max\{X,0\}=XI_{\{X\ge0\}}$ and $X^-=\max\{-X,0\}=-XI_{\{X\le0\}}$

Then we have:

$$ X=X^+-X^-\\
|X|=X^++X^- $$

Hence we can define expectation for any r.v. $X$:
> Let $X$ be any r.v., if either $EX^+<\infty$ or $EX^-<\infty$
$$ EX=EX^+-EX^- $$ 

In this case, we say the expectation of $X$ is exist. Otherwise, $EX$ is not defined.
$X$ is integrable if $E|X|<\infty$

### Dominated Convergence Theorem

If $X_n\to X\ a.s.$, $|X_n|<Y \ \forall n$ and $EY<\infty$, then

$$ \lim_nEX_n=E\lim_nX_n=EX $$

**Proof**:

$$ EY-EX=E(Y-X)= E\liminf_n(Y-X_n)\\\le\liminf_nE(Y-X_n)=EY-\limsup_nEX_n\implies EX\ge\limsup EX_n$$

Similarly

$$ EY+EX\le EY+\liminf_n EX_n $$

hence 
$$ E\limsup X_n \le EX \le E\liminf_n X_n $$

## Summary

If $P(A)=1$, then $EX=E_AX$

If $E|X|<\infty$, then $|X|<\infty$ a.s., but not vise versa.

(**Absolute integrability**). $EX$ is finite iff $E|X|$ is finite.

**(Linearity)** $$ E(aX+bY)=aEX+bEY $$

**($\sigma$ additivity over sets)** If $A=\sum_{i=1}^\infty A_i$, then
$$ E _ { A } X = \sum _ { i = 1 } ^ { \infty } E _ { A _ { i } } X $$

**(Positivity)** If $X\ge 0$ a.s., then $EX\ge 0$

**(Monotonicity)** If $X_1\le X\le X_2$ a.s., then $EX_1\le EX \le EX_2$

**(Mean value theorem)** If $a\le X \le b$ a.s., then 

$$ aP(A)\le E_AX\le bP(A) $$

**(Modulus inequality)**: $|EX|\le E|X|$

**(Fatou's) inequality** If  $X_n\ge 0$ a.s., then
$$ E \left( \liminf _ { n } X _ { n } \right) \leq \liminf _ { n } E X _ { n } $$

**(Dominated Convergence Theorem)** If $X_n \to X$ a.s., $|X_n|\le Y$ a.s. for all n and $EY<\infty$, then

$$ \lim_n EX_n=EX=E\lim_n X_n $$

**(Monotone Convergence Theorem)** If $0\le X_n\nearrow X$, then
$$ \lim_n EX_n=EX=E\lim_n X_n $$

**(Integration term by term)** If $\sum_{i=1}^\infty E|X_n|<\infty$, then
$$ \sum_{i=1}^\infty |X_n|<\infty,\ a.s. $$ 

and 
$$ E \left( \sum _{ i = 1 } ^ { \infty } X_ { n } \right) = \sum _{ i = 1 } ^ { \infty } E X_ { n } $$


## Measur-theoretic and probabilistic languages

|    Measure     |   Probability   |
| :------------: | :-------------: |
|    Integral    |   Expectation   |
| Measurable set |      Event      |
| Measurable set | Random Variable |
|      a.e.      |      a.s.       |

## Compute expectation

Let $X$ be measurable from $(\Omega,\mathcal{A},P)$ to $(\Omega_0,\mathcal{A_0},P_X)$, Whre $P_X=P\cdot X^{-1}$, $g$ be borel on $(\Omega_0,\mathcal{A_0})$ and either $g\ge 0$ or $E|g(X)|<\infty$

Then

$$ E g ( X ) =\int_\Omega g(X(\omega))dP= \int_ { \Omega _ { 0 } } g ( y ) P _ { X } ( d y ) $$

In most cases, we just choose

$$ (\Omega_0,\mathcal{A_0},P_X)=(\Reals^n,\mathcal{B^n},P_X) $$

### Expected values of absolutely continuous r.v.'s 

Let $X$ be an absolutely continuous r.v. with density function $f$, i.e., $F_X(x)=\int_{-\infty,x}f(x)dt$. Let $P_X$ be the measure w.r.t. $F_X$, then

$$ P _ { X } ( B )=EI_B=\int I_B dP_X=\int_B dP_X=\int_B dF_X = \int _ { B } f d \lambda = \int _ { B } f ( x ) d x , \quad \forall B \in \mathcal { B } $$

Moreover, let $g$ is borel, then

$$ E g ( X ) = \int _ { \mathcal { R } } g ( x ) f ( x ) d x $$

In short,

$$ E g ( X ) = \int _ { \mathcal { R } } g ( x ) P _ { X } ( d x ) = \int _ { \mathcal { R } } g ( x ) d F _ { X } ( x ) = \int _ { \mathcal { R } } g ( x ) f ( x ) d x $$

### Expected values of absolutely discrete r.v.'s

Let $X$ be discrete with $P(X=x_k)=p_k$ and $g$ is borel, then

$$ E g ( X ) = \sum _ { k = 1 } ^ { \infty } g \left( x _ { k } \right) P \left( X = x _ { k } \right) = \sum _ { k = 1 } ^ { \infty } p _ { k } g \left( x _ { k } \right) $$

## Expectation and tail probability

$$ \sum _ { n = 1 } ^ { \infty } P ( | X | \geq n ) \leq E | X | \leq 1 + \sum _ { n = 1 } ^ { \infty } P ( | X | \geq n ) $$

It's easy to check by taking $EX=\int P(X\ge x)dx= \int (1-F(x))dx$. The left equality holds when $X$ only takes integer values.

Moreover, we have:
If $X\ge0$ and $r>0$,then

$$ E Y ^ { r } = r \int _ { 0 } ^ { \infty } x ^ { r - 1 } P ( Y \geq x ) d x = r \int _ { 0 } ^ { \infty } x ^ { r - 1 } P ( Y > x ) d x $$

## Moments and Moment inequalities

Let $X$ be a r.v. and $r>0$,
Define:
1. rth Moment: $EX^r$
2. rth Absolute Moment: $E|X|^r$
3. rth Central Moment: $E(X-EX)^r$
4. rth Absolute Central Moment: $E|X-EX|^r$
5. $L^r$ space: $\{X:E|X|^r<\infty\}$

### Young's inequality

Let $f$ be a continues and strictly increasing function with $f(0)=0$, then we have

$$ a b \leq \int _ { 0 } ^ { a } f ( x ) d x + \int _ { 0 } ^ { b } f ^ { - 1 } ( x ) d x $$

### Holder's inequality

Suppose that $p,q>1$ satisfy $\frac{1}{p}+\frac{1}{q}=1$, then

$$ E | X Y | \leq \left[ E | X | ^ { p } \right] ^ { 1 / p } \left[ E | Y | ^ { q } \right] ^ { 1 / q } $$


### Cauchy-Schwarz inequality

$$ E | X Y | \leq \sqrt { \left[ E | X | ^ { 2 } \right] \left[ E | Y | ^ { 2 } \right] } $$

### Lyapunov's inequality
1. $\forall p\ge 1, E|X|\le E(|X|^p)^{\frac{1}{p}}$
2. $\forall 0<r\le s<\infty,\left[ E | Z | ^ { r } \right] ^ { 1 / r } \leq \left[ E | Z | ^ { s } \right] ^ { 1 / s }$

### Minkowski's inequality
$\forall p\ge 1, $
$$ (E|\sum X_i|^p)^{\frac{1}{p}}\le \sum (E|X_i|^p)^{\frac{1}{p}} $$

### Jensen's inequality

Let $\psi$ be convex, that is, $\forall \lambda\in (0,1), x,y\in \Reals$:

$$ \lambda \psi ( x ) + ( 1 - \lambda ) \psi ( y ) \geq \psi ( \lambda x + ( 1 - \lambda ) y ) $$

Then
$$ \psi ( E X ) \leq E [ \psi ( X ) ] $$

### Chebyshev(Markov) inequality

If $g$ is strictly increasing and positive on $\Reals^+$, $g(x)=g(-x)$, and $X$ is a r.v. s.t. $E(g(X))<\infty$, then $\forall a>0$ 
$$ P ( | X | \geq a ) \leq \frac { E g ( X ) } { g ( a ) } $$

<br><br><br><br><br><br><br><br><br><br><br><br>