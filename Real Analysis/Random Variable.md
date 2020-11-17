# Measurable function

## Mappings

Let $X : \Omega _{ 1 } \rightarrow \Omega_ { 2 }$ be a mapping, $\forall B\subset \Omega_2$ and $\mathcal{G} \subset \mathcal{P(\Omega_2)}$, the **inverse image** of 

- $B$ is $X ^ { - 1 } ( B ) = \left\{ \omega :\omega \in \Omega _ { 1 } , X ( \omega ) \in B\right\} : = \{ X \in B \}$

- $\mathcal{G}$ is $X ^ { - 1 } ( \mathcal { G } ) = \left\{ X ^ { - 1 } ( B ) : B \in \mathcal { G } \right\}$

There is some properties:

1. $X ^ { - 1 } \left( \Omega _ { 2 } \right) = \Omega _ { 1 } , X ^ { - 1 } ( \emptyset ) = \emptyset$
2. $X ^ { - 1 } \left( B ^ { c } \right) = \left[ X ^ { - 1 } ( B ) \right] ^ { c }$
3.
     $$ \begin{array} { l } X ^ { - 1 } \left( \cup _ { \gamma \in \Gamma } B _ { \gamma } \right) = \cup _ { \gamma \in \Gamma } X ^ { - 1 } \left( B _ { \gamma } \right) \text { for } B _ { \gamma } \subset \Omega _ { 2 } , \gamma \in \Gamma \\ X ^ { - 1 } \left( \cap _ { \gamma \in \Gamma } B _ { \gamma } \right) = \cap _ { \gamma \in \Gamma } X ^ { - 1 } \left( B _ { \gamma } \right) \text { for } B _ { \gamma } \subset \Omega _ { 2 } , \gamma \in \Gamma \end{array} $$
     
     where $\Gamma$ may not countable.
4. $X ^ { - 1 } \left( B _ { 1 } - B _ { 2 } \right) = X ^ { - 1 } \left( B _ { 1 } \right) - X ^ { - 1 } \left( B _ { 2 } \right) \forall B _ { 1 } , B _ { 2 } \subset \Omega _ { 2 }$
5. $B_1\sub B_2 \sub \Omega_2 \implies X^{-1}(B_1) \sub X^{-1}(B_2)$
6. If $\mathcal{B}$ is a $\sigma-$algebra, $X^{-1}(\mathcal{B})$ is also a $\sigma-$algebra.
It's easy to check $X^{-1}(\mathcal{B})$ is closed under complement and coutable union. (From properties 2 and 3)

7. If $\mathcal{C}$ is nonempty, $X ^ { - 1 } ( \sigma ( \mathcal { C } ) ) = \sigma \left( X ^ { - 1 } ( \mathcal { C } ) \right)$

**Remarks** $X^{-1}$ preserves all the set operations on $\Omega$.

## Measurable mappings

For two measurable spaces $(\Omega_1,\mathcal{A})$, $(\Omega_1,\mathcal{B})$, $X : \Omega _ { 1 } \rightarrow \Omega _ { 2 }$ is a **measurable mapping** if $X ^ { - 1 } ( \mathcal{B} ) \subset \mathcal { A }$

which is a **measurable function** if $\left( \Omega _ { 2 } , \mathcal { B } \right) = \left( \mathcal { R } ^ { n } , \mathcal { B } \left( \mathcal { R } ^ { n } \right) \right)$

Moreover, it's a **Borel function** if $\left( \Omega _ { 1 } , \mathcal { A } \right) = \left( \mathcal { R } ^ { m } , \mathcal { B } \left( \mathcal { R } ^ { m } \right) \right)$

If $\mathcal{B=\sigma(C)}$, the definition can be reduced to $X^{-1}(\mathcal{C})\subset \mathcal{A}$
since
$$ X ^ { - 1 } ( \mathcal { B } ) = X ^ { - 1 } ( \sigma ( \mathcal { C } ) ) = \sigma \left( X ^ { - 1 } ( \mathcal { C } ) \right) \subset \sigma ( \mathcal { A } ) = \mathcal { A } $$





## r.v

A r.v. $X$ is a measurable function from $(\Omega_1,\mathcal{A})$ to $(\mathcal{R},\mathcal{B})$. It denoted by $X$ is $\mathcal{A}$-measurable or $X \in \mathcal{A}$

**(Another definition)**: A r.v. $X$ is a measurable mapping from $(\Omega,\mathcal{A},P)$ to $(\mathcal{R},\mathcal{B})$ such that
$$ P ( | X | = \infty ) = P ( \{ \omega : | X ( \omega ) | = \infty \} ) = 0 $$

### Check a r.v.

$X$ is a r.v. from $(\Omega,\mathcal{A})$ to $(\reals,\mathcal{B})$ 
$$ \iff {X\le x}=X^{-1}([-\infty],x)\in \mathcal{A} \quad \forall x\in \Reals \\ \iff {X\le x}=X^{-1}([-\infty],x)\in \mathcal{A} \quad \forall x\in D$$
where $D$ is a dense subset of $\Reals$, e.g. $\mathbb{Q}$. $\{X \le x\}$ above can be replaced by
$$ \{ X \leq x \} , \quad \{ X \geq x \} , \quad \{ X < x \} , \quad \{ X > x \} , \quad \{ x < X < y \} $$


## Construction of random variables

> If $X : (\Omega _ { 1 },\mathcal{A_1}) \to (\Omega _ { 2 },\mathcal{A_2})$ and $f : (\Omega _ { 2 },\mathcal{A_2}) \to (\Omega _ { 3 },\mathcal{A_3})$ are measurable mappings. then $f ( X ) = f \cdot X : \left( \Omega _ { 1 } , \mathcal { A } _ { 1 } \right) \rightarrow \left( \Omega _ { 3 } , \mathcal { A } _ { 3 } \right)$ is also measurable mappings.


**Proof** $\forall A_3 \in \mathcal{A_3}$, $\{fX\in A_3\}=\{X \in f^{-1}(A_3)\}\in \mathcal{A_1}$ since $f^{-1}(A_3)\in \mathcal{A_2}$

> $\mathbf{X}=(X_1,\cdots,X_n)$ is a random vectors if $X_k$ is a r.v. $\forall k$ iff $\mathbf{X}$ is a measurable function from $(\Omega,\mathcal{A})$ to $(\mathcal{R^n},\mathcal{B(R^n)})$.

**Proof**

$$ \{\mathbf{X}\in \prod I_n\}=\bigcap\{X_n \in I_n\}\in \mathcal{A} $$

where $I_k=(a_k,b_k],-\infty\le a_k\le b_k\le \infty$ and follows from $\sigma(\{\prod I_n\})=\mathcal{B(R^n)}$. For the other direction, note

$$ \{X_k\le t\}=\{\mathbf{X}\in \prod_{i< k} \Reals  \times \{-\infty,t\}\times \prod_{i > k} \Reals\} \in \mathcal{A. \blacksquare}$$

By above results, we have


$\forall$ random $n$ vectors $X=(X_{1:n})$ and Borel function $f$ from $\mathcal{R^n\to R^m}$, then $f(X)$ is a random $m$ vectors.

**Remarks** Note that continuous function are borel measurable since continuity leads to inverse image of an open set is still open. So if $X_{1:n}$ are r.v.'s, so are $\sum X_n$, $\sin(x)$, $e^X$, $\text{Poly}(X),\cdots$. That implies:

$\forall X, Y\in \mathcal{A}$, so are $aX+bY,X \vee Y = \max \{ X , Y \} , X \wedge Y = \min \{ X , Y \},X^2,XY,X/Y,X^+=\max(x,0),X^-=-\min(x,0),|X|=X^++X^-$

where $X^+=\max\{X,0\}$, $X^-=\min\{X,0\}$ and $|X|=X^++X^-$

### Limiting opts

Let $X_{1:}$ are r.v. on $(\Omega,\mathcal{A})$.

1.  
     $\sup_{n\to \infty} X_n,\inf_{n\to \infty} X_n,\limsup_{n\to \infty} X_n,\liminf_{n\to \infty} X_n$ are r.v.'s.

     **Proof** First two follows from, $\forall t\in \Reals$:

     $$ \begin{aligned}
          \{\sup_{n\to \infty} X_n \le t\}&=\bigcap_{n=1}^\infty \{X_n \le t\} \in \mathcal{A}
          \\ \{\inf_{n\to \infty} X_n \ge t \}&=\bigcap_{n=1}^\infty \{X_n \ge t\} \in \mathcal{A}
     \end{aligned}$$

     and the last two follws from $\limsup_{n\to \inf}=\inf_{k\to \infty} \sup_{m\ge k} X_m$ and $\liminf_{n\to \inf}=\sup_{k\to \infty} \inf_{m\ge k} X_m$. $\blacksquare$

2.
     If $X=\lim_{n\to \infty} X_n$ everywhere, then $X$ is a r.v.

     **Proof** $X = \lim_{n\to \infty} X_n = \limsup_{n\to \infty} X_n=\liminf_{n\to \infty} X_n$ is a r.v. $\blacksquare$

3. 
     If $S=\sum_1^\infty X_n$ exists everywhere, then $S$ is a r.v.

     **Proof** Note $\sum_1^\infty X=\lim_{n\to \infty}\sum_n X_n$ is a r.v. $\blacksquare$


If $X=\lim_{n\to \infty} X_n$ holds **almost** everywhere, i.e., define $\Omega_0$ is the set of all $\omega$, such that $\lim_n X_n(\omega)$ exists, then $P(\Omega_0)=1$, we say that $X_n$ converges a.s. and write:

$$ X_n \to X \quad a.s. $$

For a measurable function $f$, we may modify it at a null set into $f'$ and it remain mesurable since for any open set $G$, $f'^{-1}(G)$ differ $f^{-1}(G)$ a at most null set, by the completion of lebesgue measure space, $f'{-1}(G)$ is measurable and thus $f^{-1}$ measurable. Hence, for $f_n \to f$ a.s., we may ignore a null set and then $f_n\to f$ everywhere and thus $f$ measurable.



## Approximations of r.v. by simple r.v.s

### Indicator r.v.
If $A\in \mathcal{A}$, the indicator function $I_A$ is a r.v.

### Simple r.v.
If $\Omega=\sum_1^n{A_i}$, where $A_i \in \mathcal{A}$, then $X=\sum_1^n a_i I_{A_i}$ is a r.v.

**Proof** Note $\{X\in B\}=\bigcup_{a_i\in B}A_i \in \mathcal{A}$. $\blacksquare$

Any r.v. can be approximated by simple ones:

> $\forall X \in \mathcal{A}$, $\exists 0\le X_1\le X_2 \cdots X_n$ s.t. $X _ { n } ( \omega ) \nearrow X ( \omega )$ everywhere.

**Proof** Suppose

$$ X_n(\omega)=\sup\{\frac{j}{2^n}:j\in \mathbb{Z},\frac{j}{2^n}\le \min(X(\omega),2^n)\}  $$

One can check $X_n$ is simple r.v. and $X_n(\omega) \nearrow X(\omega)$ for all $\omega \in \Omega$.

##  $\sigma$ algebra generated by r.v.

Let $\left\{ X _ { \lambda } , \lambda \in \Lambda \right\}$ is r.v.s on $(\Omega,\mathcal{A})$. Define
$$ \sigma \left( X _ { \lambda } , \lambda \in \Lambda \right) : = \sigma \left( X _ { \lambda } \in B , B \in \mathcal { B } , \lambda \in \Lambda \right) = \sigma \left( X _ { \lambda } ^ { - 1 } ( \mathcal { B } ) , \lambda \in \Lambda \right) = \sigma \left( \cup _ { \lambda \in \Lambda } X _ { \lambda } ^ { - 1 } ( \mathcal { B } ) \right) $$
which is called  $\sigma$ algebra generated by $\left\{ X _ { \lambda } , \lambda \in \Lambda \right\}$, where $\Lambda$ is a index set which can be uncountable. 

For $\Lambda=\mathbb{N^+}$:

1. 
   $$ \begin{aligned} \sigma \left( X _ { i } \right) & = \sigma \left( X _ { i } ^ { - 1 } ( \mathcal { B } ) \right) = X _ { i } ^ { - 1 } ( \mathcal { B } ) = \left\{ X _ { i } \in \mathcal { B } \right\} \\ \sigma \left( X _ { 1 } , \ldots , X _ { n } \right) & = \sigma \left( \cup _ { i = 1 } ^ { n } X _ { i } ^ { - 1 } ( \mathcal { B } ) \right) = \sigma \left( \cup _ { i = 1 } ^ { n } \sigma \left( X _ { i } \right) \right) \end{aligned} $$
2. 
   $$ \begin{array} { c } \sigma \left( X _ { 1 } \right) \subset \sigma \left( X _ { 1 } , X _ { 2 } \right) \subset \ldots \ldots \subset \sigma \left( X _ { 1 } , \ldots , X _ { n } \right) \\ \sigma \left( X _ { 1 } , X _ { 2 } , \ldots . . \right) \supset \sigma \left( X _ { 2 } , X _ { 3 } , \ldots . . \right) \supset \ldots \ldots \supset \sigma \left( X _ { n } , X _ { n + 1 } , \ldots . . \right) \end{array} $$

3. $\bigcap_1^\infty \sigma(X_n,X_{n+1},\cdots)$ is the tail $\sigma$ algebra of $X_{1:}$

If $A_{1:n}$ are not mutually exclusive to each other, then we have

$$ |\sigma(A_{1:n})|=2^{2^n} $$

Which follows from for a partition $A_{1:n}$,

$$ \sigma(A_1,\cdots,A_n)=\{\bigcup_{i\in J} A_i\} $$ 

where $J$ is any subset of $\mathbb{N}\le n$ and $A_0=\emptyset$. Hence for discrete r.v. $Y$, $\sigma(Y)$ can be generated from $A_i=\{Y=y_i\}$ forall $y_i$'s. For continuous case, it's generated by all intervals.

## Distributions and induced distribution functions
### Random variables
A r.v. $X$ on $(\Omega,\mathcal{A},P)$ induces another probability space $(\mathcal{R,B},P_X)$ through:

$$ \forall B \in \mathcal { B } : \quad P _ { X } ( B ) = P \left( X ^ { - 1 } ( B ) \right) = P ( X \in B ) $$

One can check such $P_X$ is nonegative and $\sigma$ additive.

Then we define:

1. The distribution of $X$ is:

$$ P _ { X } ( B ) = P \left( X ^ { - 1 } ( B ) \right) = P ( X \in B ) , \quad B \in \mathcal { B } $$

2. The distribution function of $X$ is:

$$ F _ { X } ( x ) = P _ { X } ( ( - \infty , x ] ) = P ( X \leq x ) $$

Given two r.v.'s $X$ and $Y$, they are **identically distributed** if $F_X=F_Y$, denoted by $X=_d Y$, they are **equal almost sure** if $P(X=Y)=1$, denoted by $X=_{a.s.}Y$.

**Remarks**:

1. $X=_d Y$ does not have to be in the same probability space while equal a.s. must be.
2. $X=_{a.s.} Y \implies X=_d Y$  but not vice versa.  

A r.v. is **discrete** if $\exist$ a countable set $C\sub\Reals$, s.t., $P(X\in C)=1$. Note that $X$ is discrete iff $F_X$ is discrete. Where

$$ F_X(x)=\sum_1^\infty p_i\delta_{a_i}(x) $$

$p_i=P_X(\{a_i\})$ and $C=\{a_i\}$.

### Random vectors

$\mathbf{X}=(X_1,\cdots,X_n)$ is a random vector.


1. The distribution of $\mathbf{X}$ is:

$$ P _ { \mathbf{X} } ( B ) = P \left( \mathbf{X} ^ { - 1 } ( B ) \right) = P ( \mathbf{X}\in B ) , \quad B \in \mathcal { B^n } $$

1. The distribution function of $\mathbf{X}$ is:

$$ F _ {\mathbf{X} } ( x ) = P (X_i\le x_i) $$

Marginal d.f. can be generated from joint d.f. by taking some $x_i\to \infty$.

$\mathbf{X}$ is discrete iff all $X_i$ is discrete.


## Generating r.v. with prescribed distributions

The inverse of a d.f. $F$ is defined as quantile function associated by

$$ F ^ { - 1 } ( u ) = \inf \{ t : F ( t ) \geq u \} , \quad \forall u \in ( 0,1 ) $$

There are some of the properties of $F^{-1}$

1. 
   $F^{-1}$ is nondecreasing and left continuous

   Note $\{F(t)\ge u_1\}\supset \{F(t)\ge u_2\}$ and if $u_1\lt u_2$ thus $F^{-1}(u_1)\le F^{-1}(u_2)$. 

   Let $u_n \nearrow u$. Then $F^{-1}(u_n)$ must converge to some $b$ and $b\le F^{-1}(u)$. However $F(b)\ge \lim_n u_n=u\implies F^{-1}(u)\le b$ thus $F^{-1}(u)=b$.

2. 
     $F^{-1}\cdot F(x)\le x$

     since $F^{-1}(F(x))=\inf\{F(t)\ge F(x)\}\le x$.

3. 
     $F\cdot F^{-1}(x)\ge x$

     Note $\{F(t)\ge u\}$ in the form of $[a,\infty)$ since $F$ is monotone and right continuous. Moreover, $a=F^{-1}(u)$, i.e.

     $$ F^{-1}(u)=\inf\{F(t)\ge u\} = \min \{F(t)\ge u\} $$
4.
     $F^{-1}(u)\le t \iff u\le F(t)$

     $\implies$ follows from $F^{-1}(u)\le t\implies F.F^{-1}(u)\le F(t)$ and note $F.F^{-1}(u)\ge u$.

     $\impliedby$ follows from $u\le F(t)\implies F^{-1}(u)\le  F^{-1}.F(t)\le t$.

5. 
     If $F$ is continuous, then it me strictly monotone and hence $F \cdot F^{-1}(u)=u$ and $F^{-1}\cdot F(x)=x$

>**Quantile transformation**  $F$ is a d.f. and $U$ is a uniform random variable on $(0,1)$

$$ X : = F ^ { - 1 } ( U ) \sim F $$

**Proof** 

$$ P(X\le x)=P(F^{-1}(U)\le x)=P(U\le F(x))=F(x).\blacksquare$$

> If a r.v. $X$ has a continuous d.f. $F$, then $F(X)\sim U(0,1)$. 




<br><br><br><br><br><br><br><br><br><br>