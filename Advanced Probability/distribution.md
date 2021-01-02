## Probability measure

If $\mu(\Omega)=1$, then $\mu$ is a probability measure, usually written as $P$, the probability space is $(\Omega,\mathcal{A},P)$
For probability measure, which has following properties:

1. $\forall A\in \mathcal{A},\quad 0\le P(A) \le 1$
2. $P(\Omega)=1$
3. $P \left( \sum _ { 1 } ^ { \infty } A _ { n } \right) = \sum _ { 1 } ^ { \infty } P \left( A _ { n } \right)$
4. $A \sub B \implies P(B-A)=P(B)-P(A)$
5. $P(A) \le P(B) \impliedby A\sub B$
6. $P \left( \cup _{ k = 1 } ^ { n } A_ { k } \right) = \sum _ { k } P \left( A _ { k } \right) - \sum _ { i < j } P \left( A _ { i } \cap A _ { j } \right) + \ldots \ldots$
7. $P$ is continuous, as well as continuous from above and below.

**Boole's inequality**
$$
P \left( \bigcup _ { i = 1 } ^ { \infty } A _ { i } \right) \leq \sum _ { i = 1 } ^ { \infty } P \left( A _ { i } \right)
$$
**Bonferroni's inequality**
$$
P \left( \bigcap _ { i = 1 } ^ { n } A _ { i } \right) \geq \sum _ { i = 1 } ^ { n } P \left( A _ { i } \right) - ( n - 1 )
$$

### Probability measures and d.f.

A real-valued function $F$ to $\mathcal{R}$ is d.f. if

1. $F(-\infty)=0,F(\infty)=1$
2. $F$ is nondecreasing and right continues.


**(Correspondence theorem)**

$$ F(x)=P((-\infty,x]) $$

establish a 1-1 correspondence between all d.f. and probability measure on $(\mathcal{R},\mathcal{B})$.

**Proof** Measure $\implies$ d.f:

Suppose $x_{1:n} \searrow -\infty$, then $(-\infty,x_n]\searrow \empty$, thus

$$ F(x_n)=P((-\infty,x_n])\searrow P(\emptyset)=0 $$

hence $F(-\infty)=0$, we can show that $F(\infty)=1$ and $F$ is right continuous in similar way. The monotoncity of $F$ follows from monotonicity of $P$.

d.f. $\implies$ measure:

A d.f. is a L-S measure function, hence there exist a measure $P$ satisfying

$$ P((y,x])=F(x)-F(y) $$

Let $y \searrow -\infty$, we have

$$ P((-\infty,x])=F(x)-F(-\infty)=F(x).\quad \blacksquare $$

**Remark** For a d.f. $F$, the set
$$ S ( F ) = \{ x : F ( x + \epsilon ) - F ( x - \epsilon ) > 0 , \text { for all } \epsilon > 0 \} $$
is called the **support** of $F$. Further more, any point of which is called a **point of increase**. Then we have:

1. Each jump point of $F$ belongs to the support.
2. $S(F)$ is a closed set
3. a d.f. can have support $(-\infty,\infty)$

**Proof** 

1. 
   $x$ is F jump point suggests $F(x)-F(x-)>0$, clearly $\forall \epsilon$

   $$ F(x+\epsilon)-F(x-\epsilon)\ge F(x)-F(x-)>0 $$
   
   Thus $x\in S(F)$.

2. 
   Let $x_{1:}\in S(F)$ and $x_n \to x$, take $n_0$ s.t. $|x_{n_0}-x|<\epsilon/2$.  We have

   $$ F(x+\epsilon)-F(x-\epsilon)\ge F(x_{n_0}-\epsilon/2+\epsilon)-F(x_0+\epsilon/2-\epsilon)\ge 0$$
3. Suppose jump only at rational number case. $\blacksquare$






### Different types of distributions

1. 
   A d.f. $\delta_t$ is called **degenerate** at $t$ if
    $$ \begin{array} { r l r l } \delta _ { t } ( x ) & =  0 & x < t \\ & = 1 & x \geq t \end{array} $$

2.
   A d.f. $F$ is called **discrete** if it can be represented in the form 

   $$ F(x)=\sum_1^\infty p_n \delta_{a_n}(x) $$



    where $\sum p_j=1$ and $\{a_n\}$ is countable.

3. A d.f. $F$ is continuous if it's continuous everywhere.

**Remarks** The measure of discrete d.f. 

$$ P((a,b])=\sum_{\{n:a<a_n\le b\}} p_n $$



### Decomposition of d.f.

> The set of discontinuities of a non-decreasing function is countable.
> 
> **Proof** Every discontinuous point contains a rational number and thus the cardinal of such set is no greater than $\mathcal{Q}$.

Let $\{a_n\}$ be the countable set of jump of a d.f. $F$ and $p_j=F(a_j)-F(a_j-)>0$ the size at jump $a_j$, consider: 

$$ F _ { d } ( x ) = \sum _ { j = 1 } ^ { \infty } p _ { j } \delta _ { a _ { j } } ( x )=\sum_{\{a_j\le x\}} p_j
$$ 

clearly it's nondecreasing and right continuous with

$$ F_d(-\infty)=0 \quad F_d(\infty)=\sum_j p_j $$

Then we can show that there exist a decomposition such that $F=F_c+F_d$ and such decomposition is unique. 

**Proof** Begin with its existence,let $F_c(x)=F(x)-F_d(x)$, then we show that $F_c$ is nonnegative, nondecreasing, and continuous.

$$ F_d(y)-F_d(x)=\sum_{x<a_j<y} p_j= \sum_{x<a_j<y} F(a_j)-F(a_j-)\le F(y)-F(x)$$

hence $F_c$ is nodecreasing. Take $x\searrow -\infty$, we can see $F_c(y)=F(y)-F_d(y)\ge 0$ is nonegative. It's remains to show that it's continous. Note

$$ F_c(x)-F_c(x-)=[F(x)-F(x-)]+[F_d(x)-F_d(x-)]=0 $$

thus it's left continous and it's right continous since $F$ and $F_d$ do. $\blacksquare$

The uniqueness follows from $F_d$ is unique, otherwise there exist some jump $a$ and another discrete $G_d$ s.t.

$$ \begin{aligned}
  0&=F_c(a)-F_c(a-)
  \\&=[F(a)-F_d(a)]-[F(a-)-F_d(a-)]
  \\&=[F(a)-F(a-)]-[F_d(a)-F_d(a-)]
  \\&\neq[F(a)-F(a-)]-[G_d(a)-G_d(a-)]
  \\&=[F(a)-G_d(a)]-[F(a-)-G_d(a-)]
  \\&=G_c(a)-G_c(a-)=0
\end{aligned} $$

A contradiction. $\blacksquare$

Note that both $F_c$ and $F_d$ are almost d.f. excpet they are not equal to $1$ when $x\to \infty$. Therefore, we can take $\frac{F_c(x)}{F_c(\infty)}$ and $\frac{F_d}{F_d(\infty)}$ to get two proper d.f. which suggests

> Every d.f. $F$ can be uniquely written as the convex combination of $a$ discrete and a continuous one:
>
> $$ F ( x ) = F _{ d } ( x ) + F_ { c } ( x ) = \alpha \frac { F _ { d } ( x ) } { F _ { d } ( \infty ) } + ( 1 - \alpha ) \frac { F _ { c } ( x ) } { F _ { c } ( \infty ) } =a F_1(x)+(1-a)F_2(x)$$ 


### Further decomposition of a continuous d.f

#### Absolutely continuous

A function $F$ is called **absolutely continuous** iff there exists a function $f$ in $L^1$, s.t.
$$\forall x<y<\infty, F(y)-F(x)=\int_x^y f(t)dt $$
$f(t)$ is called the **density** of $F$. It can be shown that $ F'(t)=f(t) $ a.e.

Another defintion is 
$$ \text{$F$ is absolutely continuous} \iff \exist f \quad s.t. \quad F ( x ) = \int _ { - \infty } ^ { x } f ( t ) d t $$
here $f(t)$ is called p.d.f

#### Singular
A funtion $F$ is **singular** iff it's continuoues, not identically zero, $F'$ exsits a.e., and $F'(t)=0$ a.e.
<br><br>
We can further decompose a continuous d.f. as:

$$\text {A continuous d.f.
} = \text { an absolutely continuous d.f. } + \text { a  singular d.f.} $$

## Randon-Nickodym theorem

Let $\mu$ and $\nu$ be two measures on the measurable space $(\Omega,\mathcal{F})$, we say that $v$ is absolutely continuous w.r.t. $\mu$, written as $\nu << \mu$ if

$$ \mu(A)=0 \implies \nu(A)=0 $$

**(Randon-Nikodym theorem)**
Given a measurable space $(X,\Sigma)$. if $\nu << \mu$, where $\nu$ is a measure and $\mu$ is a $\sigma$ finite measure $\mu$ on $(X,\Sigma)$, then there is a measurable function $f$ on $X$, and taking values in $[0,\infty]$,s.t.

$$ \nu(A)=\int_A fd\mu $$

for any measurable set $A$.

