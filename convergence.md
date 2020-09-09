# Convergence

## Modes of convergence

**Definition:** Let $X,X_{1:}$ be r.v.'s on $(\Omega,\mathcal{A},P)$. We say that

- $X_n \to X\ a.s.$ if $$ P \left( \lim _ { n \rightarrow \infty } X _ { n } = X \right) = P \left( \left\{ \omega \in \Omega : \lim _ { n \rightarrow \infty } X _ { n } ( \omega ) = X ( \omega ) \right\} \right) = 1 $$

- $X_n\to X$ in $r$th mean, or in $L_r$ space, if $$ \lim _ { n \rightarrow \infty } E \left| X _ { n } - X \right| ^ { r } = 0 $$
- $X_n \to X$ in prob, i.e. $X_n \to_p X$, if $$ \forall \epsilon>0, \lim _ { n \rightarrow \infty } P \left( \left| X _ { n } - X \right| > \epsilon \right) = 0 $$
- $X_n \to X$ in distribution, i.e. $X_n\to_d X$ or $F_{X_n}\implies F_X$,if $$ \lim _ { n \rightarrow \infty } F _ { X _ { n } } ( x ) = F _ { X } ( x )  $$

$(X,\rho)$ is a **metric space**, when $\rho$ defined on $X\times X$ s.t. $\forall x,y,z \in X$:
1. $\rho(x,y)\ge 0$, the equality hold iff $x=y$.
2. $\rho(x,y)=\rho(y,x)$
3. $\rho(x,y)\le\rho(x,z)+\rho(z,y)$

$\rho$ is called a **metric**.

$\rho(Y,Z)=\| Y - Z \| _ { r }$ is a metric in $L_r=\{X:E|X|^r<\infty\}$

$$ \begin{aligned} \| X \| _ { r } = & E | X | ^ { r } , & & 0 < r < 1 \\ & \left( E | X | ^ { r } \right) ^ { 1 / r } , & & r \geq 1 \end{aligned} $$

>It's easy to check definition 1 and 2, for 3:
If $r\ge 1$. From Minkowski's inequality($\left[ E | X + Y | ^ { p } \right] ^ { 1 / p } \leq \left[ E | X | ^ { p } \right] ^ { 1 / p } + \left[ E | Y | ^ { p } \right] ^ { 1 / p }$): $$ \| X + Y \| _ { r } \leq \| X \| _ { r } + \| Y \| _ { r } $$take $X=x-z,Y=z-y$, we have definition 3 holds.
If $0<r<1$, note for $0<\lambda<1$:
$$ (\lambda^r+(1-\lambda)^r) \ge (r+1-r)^r=1$$ hence $E\lambda^r+E(1-\lambda)^r\ge 1\implies\|\lambda+(1-\lambda)\|_r\le \|\lambda\|_r+\|(1-\lambda)\|_r$. For any $X,Y$, take $\lambda=\frac{|X|}{|X|+|Y|}$. Then we have $$ \| X + Y \| _ { r } \leq \| X \| _ { r } + \| Y \| _ { r }  $$

So convergence in $r$th mean may be interpreted as convergence in the $L_r$ metric. That is, 

> - $X_n\to X$ in $r$th mean, or in $L_r$ space, if $$ \lim _ { n \rightarrow \infty } \|X_n-X\|_r=\lim \rho(X_n,X)= 0 $$

For convergence in prob. Define measure

$$\rho _ { \epsilon } ( X , Y ) = P ( | X - Y | > \epsilon ) = \int _ { E } d P $$

Where $E = \{ \omega \in \Omega : | X ( \omega ) - Y ( \omega ) | > \epsilon \}$. Then $X_n \to_p X$ if $\lim \rho_\epsilon(X_n,X)=0$

**Levy metric** For two d.f.'s $F,G$, let

$$ \rho ( F , G ) = \inf \{ \delta > 0 : F ( x - \delta ) - \delta \leq G ( x ) \leq F ( x + \delta ) + \delta , \text { for all } x \in R \} $$

We can show that convergence in dist. is equivalent to convergence in levy metric.

There still remains a.s. convergence case.

### Equivalent definition of a.s. convergence

The following are equivalent:

1. $X_n \to X\ a.s.$
2. $\forall \epsilon>0, \lim _ { n \rightarrow \infty } P \left( \cap _ { m = n } ^ { \infty } \left\{ \left| X _ { m } - X \right| < \epsilon \right\} \right) = 1$
3. $\forall \epsilon > 0 , \lim _ { n \rightarrow \infty } P \left( \cup _ { m = n } ^ { \infty } \left\{ \left| X _ { m } - X \right| \geq \epsilon \right\} \right) = 0$
4. $\forall \epsilon > 0 , \lim _ { n \rightarrow \infty } P \left( \left\{ \sup _ { m = n } ^ { \infty } \left| X _ { m } - X \right| \right\} \geq \epsilon \right) = 0$ i.e. $$ \sup _ { m = n }^\infty \left| X _ { m } - X \right| \longrightarrow _ { p } 0 $$
5. $\forall \epsilon > 0 , P \left( \left| X _ { n } - X \right| \geq \epsilon , i . o . \right) = 0$

#### **Proof**
##### "$1 \iff 2$"
$\forall \epsilon>0,\exist n\ge 1,s.t.,|X_m(\omega)-X(\omega)|<\epsilon, \forall m\ge n$
$$ \left\{ \omega : \lim _ { n \rightarrow \infty } X _ { n } ( \omega ) = X ( \omega ) \right\}   = \bigcap _ { \epsilon > 0 } \bigcup _ { n = 1 } ^ { \infty } \bigcap _ { m = n } ^ { \infty } \left\{ \omega : \left| X _ { m } ( \omega ) - X ( \omega ) \right| < \epsilon \right\} $$

We can take $\epsilon$ as $\frac{1}{k},k=1,2,3,\cdots$:

$$ \begin{aligned}
 LHS&=\bigcap _ { k = 1 } ^ { \infty } \bigcup _ { n = 1 } ^ { \infty } \bigcap _ { m = n } ^ { \infty } \left\{ \omega : \left| X _ { m } ( \omega ) - X ( \omega ) \right| < \frac { 1 } { k } \right\}
\\&=
\bigcap _ { k = 1 } ^ { \infty } \lim _ { n \to \infty }  \bigcap _ { m = n } ^ { \infty } \left\{ \omega : \left| X _ { m } ( \omega ) - X ( \omega ) \right| < \frac { 1 } { k } \right\} 
\\&= 
\lim_{k\to\infty}\lim _ { n \to \infty }  \bigcap _ { m = n } ^ { \infty } \left\{ \omega : \left| X _ { m } ( \omega ) - X ( \omega ) \right| < \frac { 1 } { k } \right\}
\end{aligned}  $$

From 1 to 2:

$$ 1 = P \left( \left\{ \omega : \lim _ { n \rightarrow \infty } X _ { n } ( \omega ) = X ( \omega ) \right\} \right) \leq \lim _ { n \rightarrow \infty } P \left( \bigcap _ { m = n } ^ { \infty } \left\{ \omega : \left| X _ { m } ( \omega ) - X ( \omega ) \right| < \frac { 1 } { k } \right\} \right) \leq 1 $$

From 2 to 1:

$$ P \left( \left\{ \omega : \lim _ { n \rightarrow \infty } X _ { n } ( \omega ) \rightarrow X ( \omega ) \right\} \right) = \lim _ { k \rightarrow \infty } \lim _ { n \rightarrow \infty } P \left( \bigcap _ { m = n } ^ { \infty } \left\{ \omega : \left| X _ { m } ( \omega ) - X ( \omega ) \right| < \frac { 1 } { k } \right\} \right)= \lim_{k\to\infty}1=1$$

##### $2\iff 3$

##### $3\iff 4$
$\forall \epsilon>0$,let
$$ \begin{aligned}
A_{n,\epsilon}&=\left\{ \omega \in \Omega : \bigcup_ { m = n } ^\infty\left\{ \left| X _{ m } - X \right| \geq \epsilon \right\} \right\}\\
B_ { n , \epsilon }& = \left\{ \omega \in \Omega : \sup _{ m = n }^\infty \left| X_ { m } - X \right| \geq \epsilon \right\}
\end{aligned} $$

clearly we have $A_{n,\epsilon}\sub B_{n,\epsilon}\sub A_{n,\epsilon/2}$. Thus $\lim_n P(A_{n,\epsilon})=0\impliedby \lim_n P(B_{n,\epsilon})=0\impliedby \lim_n P(A_{n,\epsilon/2})=0$.

##### $3\iff 5$

Note

$$ \begin{aligned}
P \left( \left| X _ { n } - X \right| \geq \epsilon , \text {i.o.} \right) & = P \left( \bigcap _ { n = 1 } ^ { \infty } \bigcup _ { m = n } ^ { \infty } \left\{ \left| X _ { m } - X \right| \geq \epsilon \right\} \right) 
\\ & = 
P \left( \lim _ { n \rightarrow \infty } \bigcup _ { m = n } ^ { \infty } \left\{ \left| X _ { m } - X \right| \geq \epsilon \right\} \right) 
\\ & = \lim _ { n \rightarrow \infty } P \left( \bigcup _ { m = n } ^ { \infty } \left\{ \left| X _ { m } - X \right| \geq \epsilon \right\} \right)
\end{aligned} $$


## Cauchy Criterion

Following statements are equivalent:

1. $X_n$ converges a.s.
2. $\forall \epsilon>0,\lim _ { n \rightarrow \infty } P \left( \left| X _ { m } - X _ { m ^ { \prime } } \right| \leq \epsilon , \forall m > m ^ { \prime } \geq n \right) = 1$
3. $\forall \epsilon>0,\lim _ { n \rightarrow \infty } P \left( \left| X _ { m } - X _ { m ^ { \prime } } \right| > \epsilon , \forall m > m ^ { \prime } \geq n \right) = 0$
4. $\forall \epsilon > 0,\lim _ { M \rightarrow \infty } P \left( \sup _ { m , n \geq M } \left| X _ { m } - X _ { n } \right| > \epsilon \right) = 0$
5. $\sup _ { m , n \geq M } \left| X _ { m } - X _ { n } \right| \longrightarrow _ { p } 0$

**Proof**:
Take $S_m^i=X_{m+i}-X_m$, hence
$$ \lim_n P(|S_m^i|\le \epsilon)=1 $$Note $ \bigcap_{m=n}^N \{|S_m^1|\le \epsilon\} \supset \{|S_m^N|\le N\epsilon\} $ , which implies

$$ \lim_n P(\lim_N  \bigcap_{m=n}^N \{|S_m^1|\le \epsilon\})=\lim_n P(\bigcap_{m=n}^\infty\{|S_m^1-0|\le \epsilon\})=1$$ i.e. $S_m^1$ converges to 0 a.s.,hence $X_n$ converges a.s.

## Relationships between models of convergence

1. $\forall r\ge 1 $,$$ \text{Either of }\begin{array} { c } X _ { n } \rightarrow X \text { a.s.} \\ X _ { n } \rightarrow X \text { in } L _ { r } \end{array} \implies X_n\to_p X \implies X_n\to_d X $$
2. If $r>s>0$, then $$ X _ { n } \rightarrow X \text { in } L _ { r } \Longrightarrow X _ { n } \rightarrow X \text { in } L _ { s } $$

**Proof**

1. $X_n\to X a.s.\implies X_n\to_p X$
It's trivial since: $$ \{|X_n-X|\ge \epsilon\}\subset \bigcup_{m=n}^\infty\{|X_m-X|\ge \epsilon\} $$
2. $X_n\to X$ in $ L_r$ $\implies X_n\to_p X$ $$ P(|X_n-X|\ge \epsilon)\le \frac{E|X_n-X|^r}{\epsilon^r}\to 0 $$
3. $X_n\to_p X\implies X_n \to_d X$
Show that $$ F ( x - \epsilon ) - P \left( \left| X _{ n } - X \right| > \epsilon \right) \leq F_ { n } ( x ) \leq F ( x + \epsilon ) + P \left( \left| X _{ n } - X \right| > \epsilon \right) $$ then we have $$ F ( x - \epsilon ) \leq \liminf_ { n } F _{ n } ( x ) \leq \limsup_ { n } F _ { n } ( x ) \leq F ( x + \epsilon ) $$
4. Trivial since Lyapunov's inequality

## Partial converses

If $C$ is a degenerate r.v., i.e. a constant, then

$$ X_n \to_d C\iff X_n \to_p C $$

### Dominated convergence

The following are two useful lemmas:
>If $X_n \to_p X,|X_n|\le Y a.s.$, then $|X|\le Y\ a.s.$

> If $E|Y|<\infty$ and $P(A_n)\to 0$, then $E_{A_n}|Y|\to 0$

Then we have **Lebesgue dominated convergence theorem:
If $X_n\to_p X$, $|X_n|<Y$ a.s. and $EY^r<\infty$ for $r>0$ then $X_r\to X$ in $L_r$, hence $EX_n^r \to EX^r$

**Proof**: $|X_n-X|\le 2Y$ a.s. since lemma 1, then $\forall \epsilon$

$$ E \left| X _{ n } - X \right| ^ { r } = E \left| X_ { n } - X \right| ^ { r } I _{ \left\{ \left| X_ { n } - X \right| > \epsilon \right\} } + E \left| X _{ n } - X \right| ^ { r } I_ { \left\{ \left| X _ { n } - X \right| \leq \epsilon \right\} } $$

Note the first part of RHS less than $E(2Y)^rI_{A}$ where $A=\{|X_n-X|> \epsilon\}$, it's converges to $0$ from lemma 2. And the last part of RHS is less than $\epsilon^r$ clearly. Recall the metric in $L^r$ and so the remaining is proved. $\blacksquare$

The r.v. $Y$ can be replaced as some constant $C$. Ans so we have

> $|X_n|\le C\ a.s.$ Then $\forall r>0$,$$ X_ { n } \rightarrow X \text { in } L _{ r } \quad \Longleftrightarrow \quad X_ { n } \rightarrow _ { p } X $$

### Convergence in probability sufficiently fast implies a.s. convergence

$$ \sum _{ n = 1 } ^ { \infty } P \left( \left| X_ { n } - X \right| > \epsilon \right) < \infty \implies X_n \to X\ a.s. $$ 
**Proof**: Note $$ P \left( \bigcup_ { m = n } ^ { \infty } \left\{ \left| X _{ m } - X \right| > \epsilon \right\} \right) \leq \sum_ { m = n } ^ { \infty } P \left( \left| X _{ m } - X \right| > \epsilon \right) $$
 Such $X_{1:}$ is also called converge completely(since such convergence implies a.s. convergence)

### Convergence in mean sufficiently fast implies a.s. convergence

$$ \sum _{ n = 1 } ^ { \infty } E \left| X_ { n } - X \right| ^ { r } < \infty \implies X_n \to X\ a.s. $$ Trivial since markov's inequality implies converge in prob sufficiently fast.

### Convergence sequences in probability contains a.s. subsequences

If $X_n\to_p X$, then there exists a series $n_{1:}$ s.t. $X_{n_i}\to X$ a.s.

### Convergence in distribution implies a.s. convergence in another probability space.

Let $\mathcal{B}_{[0,1]}$ denote the Borel set in $[0,1]$ and $\lambda_{[0,1]}$ the Lebesgue measure restricted to $[0,1]$. Then we have

**Skoroshod's representation theorem** Suppose $X_n \to_d X$, then there exist r.v.'s $Y$ and $\{Y_n\}$ on $\left( ( 0,1 ) , \mathcal { B }_ { ( 0,1 ) } , P _{ \lambda } = \lambda_ { ( 0,1 ) } \right)$ s.t.

1. $X_n =_d Y_n, X=_d Y$
2. $Y_n \to Y\ a.s.$

**Proof** 
1. For $t\in (0,1)$ define $$ Y _ { n } ( t ) = F _ { n } ^ { - 1 } ( t ) = \inf \left\{ x : F _{ n } ( x ) \geq t \right\},
Y _ { } ( t ) = F _ { } ^ { - 1 } ( t ) = \inf \left\{ x : F _ {} ( x ) \geq t \right\} $$ i.e. $Y(t)$ is the $t$ quantile w.r.t. $X$. $$ P_\lambda(Y\le x)=P_\lambda(\{ t : Y ( t ) \leq x \})=P_\lambda(\{ t : t \leq F (x) \})=P_\lambda(0,F(x)]=F(x) $$ Similarly $P_\lambda(Y_n\le x)=F_n(x)$

2. Pick continuity $x$ s.t. $$ Y ( t ) - \epsilon < x < Y ( t ) $$ Then we have for sufficiently large $n$, $$ Y ( t ) - \epsilon < x < Y _ { n } ( t ) $$ Letting $n\to \infty$: $$ \liminf _ { n } Y _{ n } ( t ) \geq Y ( t ) $$ Similarly, we can show that: $$ \limsup_ { n } Y _{ n } ( t ) \leq Y \left( t ^ {  } \right) $$ Thus $$ Y ( t ) \leq \liminf_ { n } Y _{ n } ( t ) \leq \limsup_ { n } Y _{ n } ( t ) \leq Y \left( t ^ { } \right) $$ i.e. $\lim_ { n } Y _{ n } ( t ) = Y ( t )$. Note $t$ is continuous, so such $t$ is rich enough hence $Y_n\to Y$ a.s. $\blacksquare$

## Convergence of moments

### Definition of uniform integrability
Note that $X\in L^1$ implies $\forall \epsilon>0,\exists K>0,s.t.$ as $K\to \infty$
$$  E | X | I \{ | X | > K \} \leq \epsilon $$

A sequence of r.v.'s $Y_{1:}$ is u.i. iff $$ \lim _ { C \rightarrow \infty } \sup _ { n } E \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } \right\} = 0 $$

To give an alternative definition of u.i., introduce following lemmas firstly:
>If $X\in L^1$, then $Q(A):=E_A|X|$ is absolutely continuous,i.e.$\forall \epsilon >0, \exist \delta>0, s.t. \forall P(A)<\delta$ $$ Q(A)<\epsilon$$

> $Y_{1:}$ are integrable together if $$ \sup _ { n } E \left| Y _ { n } \right|  < \infty $$

Then we have another definition of u.i.:
A sequence of r.v.'s $Y_{1:}$ is u.i. iff 

1. $Y_{1:}$ are integrable together
2. $Q(A)=E_A|Y_n|$ is absolutely continuous forall $n$

**Proof**:
Suppose $Y_{1:}$ is u.i., then we have
$$ \begin{aligned}
 \sup _ { n } E \left| Y _ { n } \right| & \leq \sup _ { n } E \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| \leq C \right\} } \right\} + \sup _ { n } E \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } \right\} \\ & \leq C + \sup _ { n } E \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } \right\}\\
  \sup _ { n } E_A \left| Y _ { n } \right| & \leq \sup _ { n } E_A \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| \leq C \right\} } \right\} + \sup _ { n } E_A \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } \right\} \\ & \leq CP(A) + \sup _ { n } E \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } \right\}
\end{aligned} $$ For any $\epsilon>0$, there exist $C$ such that $\sup _ { n } E \left\{ \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } \right\}\le \epsilon$, then choose $\delta\le \frac{\epsilon}{C}$, hence we have: $\sup _ { n } E \left| Y _ { n } \right| \le C+\epsilon<\infty $, $\sup _ { n } E _ { A } | Y _ { n }\le2\epsilon$. So we finish the sufficiency.


For the necessity, denote $M$ as $M:=\sup_n E|Y_n|$, from Chebyshev's inqueality:
$\forall \epsilon>0,\exist \delta>0$,s.t., $\forall n\ge 1$
$$ P \left( \left| Y _ { n } \right| > C \right) \leq \frac { E \left| Y _ { n } \right| } { C } \leq \frac { \sup _ { n } E \left| Y _ { n } \right| } { C } \leq \frac { M } { C } $$ Let $\delta>\frac{M}{C}$, take $A=\left\{ \left| Y _ { n } \right| > C \right\}$ then we have $$ \sup _ { n } E _ { A } \left| Y _ { n } \right| = \sup _ { n } E \left| Y _ { n } \right| I _ { \left\{ \left| Y _ { n } \right| > C \right\} } < \epsilon\quad \blacksquare$$ 

It's easy to check the following result:
1. $\{X_n\}$ is u.i. iff $\{|X_n|\}$ is so
2. If $Y_{1:}$ is u.i., then $$ |X_n|\le |Y_n|\implies X_{1:}\text{ is u.i.} $$
3. $X_{1:}$ is u.i. iff $X_{1:}^+$ and $X_{1:}^-$ are both u.i.
4. If $X_{1:}$ and $Y_{1:}$ are each u.i., so is $X_{1:}+Y_{1:}$
5. If $X_{1:}$ is u.i., so is any subsequence of it.
6. If $|X_n|\le Y\in L^1$, then $X_{1:}$ is u.i. (since $\sup _ { n \geq 1 } E \left\{ \left| X _ { n } \right| I _ { \left\{ \left| X _ { n } \right| > C \right\} } \right\} \leq E \left\{ | Y | I _ { \{ | Y | > C \} } \right\} \rightarrow 0$)
7. If $E \sup_n |X_n|<\infty$ then $X_{1:}$ is u.i.(since $|X_n|\le \sup_n |X_n|\in L_1$)
8. Let $\psi(x)=\omega(x)$. Then $$ \sup _ { n } E \psi \left( \left| X _ { n } \right| \right) < \infty\implies X_{1:}\text{ is u.i.} $$

### Convergence in prob + u.i. $\implies$ convergence in mean

**Vitali's theorem** Suppose $X_n\to X$ and $X_n \in L_r$ then the following statements are equivalent.

1. $\{X_n^r\}$ is u.i.
2. $X_n\to X$ in $L_r$
3. $E|X_n|^r\to E|X|^r$

a. Let vita










<br><br><br>
<br><br><br>
<br><br><br>


