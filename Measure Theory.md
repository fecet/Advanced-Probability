# Measure Theory

function $\mu : \mathcal { A } \rightarrow R = [ - \infty , \infty ]$ is a **set function**.

It's

- 1.  **finite** if $\forall A\in \mathcal{A},\quad |\mu(A)|<\infty$
  2. **$\sigma$-finite** if $\exists A_n \sub \mathcal{A},\quad s.t.\quad\cup_ { i = 1 } ^ { \infty } A _{ i } = \Omega\quad \forall n \quad |\mu(A_n)|<\infty$

      also iff $\Omega$ is countable

- 1.  **additive** $\iff \mu \left( \sum _{ i = 1 } ^ { n } A_ { i } \right) = \sum _{ i = 1 } ^ { n } \mu \left( A_ { i } \right)$
  2. **$\sigma-$additive**$\Longleftrightarrow \mu \left( \sum _{ i = 1 } ^ { \infty } A_ { i } \right) = \sum _{ i = 1 } ^ { \infty } \mu \left( A_ { i } \right)$

$\mu$ is a **measure** on $\mathcal{A}$ if

1. $\forall A \in \mathcal { A } : \mu ( A ) \geq 0$ 
2. It's $\sigma$ additive.

the triplet $(\Omega,\mathcal{A},\mu)$ is a **measure space** when $\mu$ is a measure and $(\Omega,\mathcal{A})$ is  a measurable space.  Whose sets are called **measurable sets** or **$\mathcal{A}$-measurable**
a measure space is a **probability space** if $P(\Omega)=1$.



Assume that $A_{1:n}\in\mathcal{A}$ and $A\in \mathcal{A}$ and $\mu$ is a measure.

1. $\mu$ is continues from above, if $A _{ n } \searrow A \implies \mu(A_n)\to\mu(A)$
2. $\mu$ is continues from below, if $A _{ n } \nearrow A \implies \mu(A_n)\to\mu(A)$
3. $\mu$ is continues at $A$, if $A _{ n } \to A \implies \mu(A_n)\to\mu(A)$

$\forall$ Measure $\mu$ is continues from below and may not continues from above. It will be continues from above if $\exist m<\infty,\mu(A_m)<\infty$.

Finte measure $\mu$ are always continues.

## Properties of measure

### Semialgebras

Let $\mu$ be a nonnegative additive set function on a semialgebra $\mathcal{A}$. $\forall A,B\in \mathcal{A}$ and $\{A_n,B_n,n\ge 1\} \in \mathcal{A}$

1. (**Monotonicity**): $A\sub B\implies \mu(A)\le\mu(B)$ 

2. (**$\sigma$-subadditivity**):

    1. $\sum _{ 1 } ^ { \infty } A_ { n } \subset A , \quad \Longrightarrow \quad \sum _{ 1 } ^ { \infty } \mu \left( A_ { n } \right) \leq \mu ( A )$
    2. Moreover, if $\mu$ is a measure, then

$$ B \subset \sum _{ n = 1 } ^ { \infty } B_ { n } \implies\mu ( B ) \leq \sum _{ n = 1 } ^ { \infty } \mu \left( B_ { n } \right) $$
From 2.2, we can implies a nonnegative set function $\mu$ is a measure by:

1. $\mu$ is additive
2. $\mu$ is $\sigma$ subadditive on $\mathcal{S}$

### Algebras

Let $\mu$ be a measure on an algebra $\mathcal{A}$ 
$$ A \subset \cup _{ 1 } ^ { \infty } A_ { n } \implies \mu ( A ) \leq \sum _{ 1 } ^ { \infty } \mu \left( A_ { n } \right) $$

clearly, all the properties for semialgebra also hold for algebras.

### $\sigma$ algebra

Let $\mu$ be a measure on an $\sigma$ algebra $\mathcal{A}$ 

1. Monotonicity
2. Boole's inequality(Countable Sub-Additivity)

$$ \mu \left( \cup _{ i = 1 } ^ { \infty } A_ { i } \right) \leq \sum _{ i = 1 } ^ { \infty } \mu \left( A_ { i } \right) $$

3. continuity from below
4. continuity from above(must meet some conditions metioned above)
5. continuity at A $\impliedby $ $\mu$ is a finite measure.

## Probability measure

If $\mu(\Omega)=1$, then $\mu$ is a probability measure, ususally written as $P$, the probability space is $(\Omega,\mathcal{A},P)$
For probability measure, which has following properties:

1. $\forall A\in \mathcal{A},\quad 0\le P(A) \le 1$
2. $P(\Omega)=1$
3. $P \left( \sum _ { 1 } ^ { \infty } A _ { n } \right) = \sum _ { 1 } ^ { \infty } P \left( A _ { n } \right)$
4. $A \sub B \implies P(B-A)=P(B)-P(A)$
5. $P(A) \le P(B) \impliedby A\sub B$
6. $P \left( \cup _{ k = 1 } ^ { n } A_ { k } \right) = \sum _ { k } P \left( A _ { k } \right) - \sum _ { i < j } P \left( A _ { i } \cap A _ { j } \right) + \ldots \ldots$
7. $P$ is continuous, as well as continuous from above and below.

## Extension of set functions from semialgebra to algerba.

For $\mathcal{A}\sub\mathcal{B} \sub \mathcal{P}(\Omega)$, and $\mu:\mathcal{A}\to \reals,\nu:\mathcal{B}\to \reals$, if
$$
\mu(A) = \nu(A)\quad \forall A\in \mathcal{A}
$$
$\nu$ is an **extension** of $\mu$ from $\mathcal{A}$ to $\mathcal{B}$, and $\mu$ is an **restriction** from $\mathcal{B}$ to $\mathcal{A}$.

We can extent a non-negative and additive set function $\mu$ from a semialgebra $\mathcal{S}$ to $\bar{\mathcal{S}}$ as
$$
\bar { \mu } ( A ) = \sum _{ 1 } ^ { m } \mu \left( A_ { i } \right)
$$
where $A\in \bar{\mathcal{S}}$ and $A = \sum _{ 1 } ^ { m } A_ { i }$ with $A_i \in \mathcal{S}$. Note such extension is unique.

Moreover, $\mu$ is a measure $\implies$ $\bar{\mu}$ is also a measure.



## Outer measure

Let $\mu$ be a measure on a semialgebra $\mathcal{S}$, for any $A \sub \Omega$
$$
\mu ^ { * } ( A ) : = \inf \left\{ \sum _ { n = 1 } ^ { \infty } \mu \left( A _ { n } \right) ; A \subset \cup _ { n = 1 } ^ { \infty } A _ { n } , A _ { n } \in \mathcal { S } \right\}
$$

to be the **outer measure** of $A$, $\mu^*$ is called the outer measure.

**Remarks:**

1. $\mu^*$ is defined on $\mathcal{P(\Omega)}$
2. $\mu^*$ may not be a measure
3. $\cup_1^\infty A_n$ is a coutable covering of A

There is some properties as follows:

1. $\forall A\in \mathcal{S} \quad \mu^*(A)=\mu(A)$
2. Monotonicity
3. $\sigma$ subadditivity $$ \mu ^ { *} \left( \cup _ { 1 } ^ { \infty } A _ { n } \right) \leq \sum _ { 1 } ^ { \infty } \mu ^ {* } \left( A _ { n } \right) $$

A set $A\sub \Omega$ is said to be measurable w.r.t. an outer measure $\mu^*$ if for any $D\sub\Omega$:
$$ \mu ^ {* } ( D ) = \mu ^ { *} ( A \cap D ) + \mu ^ {* } \left( A ^ { c } \cap D \right) $$

Note $\mu^*(D)=\mu ^ {* } ( D ) = \mu ^ { *} ( (A \cap D ) \cup (A ^ { c } \cap D)) \le \mu ^ {* } ( A \cap D ) + \mu ^ { * } \left( A ^ { c } \cap D \right)$
hence we have

> A set $A\sub \Omega$ is said to be measurable w.r.t. an outer measure $\mu^*$ iff for any $D\sub\Omega$:
$$ \mu ^ { * } ( D ) \ge \mu ^ { *} ( A \cap D ) + \mu ^ {* } \left( A ^ { c } \cap D \right) $$

Let $A^*$ be the class of all $\mu^*$ measurable sets

1. the class is a $\sigma$ algebra
(Note $A^{c^c}=A$)

2. if $A=\sum_1^\infty A_i$ with $A_i\in A^*$, then for any $D\sub \Omega$

$$ \mu^*(A\cap D)=\sum_1^\infty\mu^*(A_n \cap D) $$

3. $\left( \Omega , \mathcal { A } ^ { *} , \left. \mu ^ {* } \right| _{ \mathcal { A } ^ { * } } \right)$ is a measure spcae. $\mu^*|_{\mathcal{A^*}}$ is an extension of $\mu$

## Extension of measures from semialgebra to $\sigma$ algerba

$$ \begin{array} { l l l l l l l l l } \mathcal { S } & \subset & \overline { \mathcal { S } } & \subset & \sigma ( \mathcal { S } ) & \subset & \mathcal { A } ^ { * } & \subset & \mathcal { P } ( \Omega ) \end{array} $$
**(Caratheodory Extension Theorem)**
Let $\mu$ be a measure on a semialgebra $\mathcal{S}$, then

1. $\mu$ has an extension to $\sigma(\mathcal{S})$, denoted by $\mu|_{\sigma(\mathcal{S})}$, further more, acctually it can be taken by the restriction of $\mu^*$

$$ \left. \mu \right| _{ \sigma ( \mathcal { S } ) } = \left. \mu ^ { * } \right|_ { \sigma ( \mathcal { S } ) } $$

2. If $\mu$ is $\sigma$ finite, the the extension is unique.

> If $P$ is a probability defined on a semialgebra $\mathcal{S}$ on $\Omega$, then there exist a unique probability space $(\Omega,\sigma(\mathcal{S}),P^*)$, s.t.
> $$ P^*(A)=P(A)\quad \forall A \in \mathcal{S} $$

## Completion of a measure

Let $(\Omega,\mathcal{A},\mathcal{\mu})$ be a measure space, and $N\sub\Omega$

1. $N$ is a **$\mu$-null set** iff $\exist B\in \mathcal{A} \quad s.t. \quad \mu(B)=0, \quad N\sub B$
2. This measure space is a complete measure space if $\forall$ $\mu$ null space $N$, $N\in \mathcal{A}$

> Given any measure space $(\Omega,\mathcal{A},\mathcal{\mu})$ , there exist a complete measure space $(\Omega,\mathcal{\bar{A}},\mathcal{\bar{\mu}})$, such that $\mathcal{A}\sub \bar{\mathcal{A}}$ and $\bar{\mu}$ is an extension of $\mu$. This space is called completion of $(\Omega,\mathcal{A},\mathcal{\mu})$.

Let $\mu$ be a measure on a semialgrbra $\mathcal{S}$, and $\mu^*$ the outer measure induced by $\mu$. If $A\sub\Omega$, and $\mu(A)<\infty$ , then $\exist B \in \sigma(\mathcal{S})$, s.t:

1. $A \sub B$
2. $\mu^*(A)=\mu^*(B)$
3. $\forall C \sub B-A$ and $C\in \sigma(\mathcal{S})$, we have $\mu^*(C)=0$

Such $B$ is called as a **meaurable cover** of $A$.

> Let $\mu$ be a $\sigma$ finite measure on a semialgrbra $\mathcal{S}$, and $\mu^*$ the outer measure induced by $\mu$, and $\mathcal{A^*}$ the $\sigma$ algebra consists of all the $\mu^*$ measurable sets. Then $(\Omega,\mathcal{A^*},\mathcal{\mu^*|_{\mathcal{A^*}}})$ is the completion of $\left(\Omega , \sigma ( \mathcal { S } ) , \left. \mu ^ { * } \right| _ { \sigma ( \mathcal { S } ) } \right)$


As a matter of fact, $A^*$ is  $\overline { \sigma ( \mathcal { S } ) }$, i.e.
$$ A^*=\overline { \sigma ( \mathcal { S } ) }+\{all \ \mu|_{\sigma}\ null\ sets\} $$

## Construction of measures on a $\sigma$ algebra $\mathcal{S}$

We can constructing measures on $\mathcal{A}$ as follows:

1. Identify a semialgebra so that $\mathcal{A}=\sigma(\mathcal{S})$
2. Define a measure $\mu:\mathcal{S}\to \Reals$
3. Extend the measure to $\mathcal{A}$:

$$ \begin{array} { l } \mathcal { S } \Longrightarrow \overline { \mathcal { S } } \Longrightarrow \mathcal { A } ^ { *} \Longrightarrow \sigma ( \mathcal { S } ) = \mathcal { A } \\ \left. \left. \mu \Longrightarrow \bar { \mu } _ { \sigma } \Longrightarrow \mu ^ {* } \right| _{ \mathcal { A } ^ { * } } \Longrightarrow \mu ^ { * } \right|_ { \sigma ( \mathcal { S } ) } = \left. \mu \right| _ { \sigma ( \mathcal { S } ) } \end{array} $$

### Lebesgue and Lebesgue-StiItjes measures

**(L-S measure)** Suppose that $F$ is finite on $\Reals$ and

1. $F$ is nondecreasing
2. $F$ is right continuous

Then there exist a unique measure $\mu$ on $(\Reals, \mathcal{B})$ with
$$ \mu((a,b])=F(b)-F(a) $$

> **Lebegue measure**
> $$ \lambda((a,b])=b-a $$

**Remarks:**

1. The completed measure $\mu$ is called the **L-S measure**. The (incompleted) measure is called the **B-L-S measure**
2. If $F(x)=x$, then $\mu$ is called the **L measure**, if $\mu$ is incompleted is called **B measure**. L measure is not finite but $\sigma$ finite.
3. $F$ uniquely determines $\mu$, but not visa versa.
4. If restrict $\mu$ to $([0,1],\mathcal{B}\cap[0,1])$, then $\mu$ is a probability measure.

### Probability measures and d.f.

A real-valued function $F$ to $\mathcal{R}$ is d.f. if

1. $F(-\infty)=0,F(\infty)=1$
2. $F$ is nondecreasing and right continues.

Hence, we have
$$ F(x)=P((-\infty,x)) $$
which implies:
**(Correspondence theorem)**
there is a 1-1 correspondence between all d.f. and probability measure on $(\mathcal{R},\mathcal{B})$

For a d.f. $F$, the set
$$ S ( F ) = \{ x : F ( x + \epsilon ) - F ( x - \epsilon ) > 0 , \text { for all } \epsilon > 0 \} $$
is called the **support** of $F$. Further more, any point of which is called a **point of increase**.





<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>