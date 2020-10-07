---
title: "Set theory"
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

# Measure Theory

Let $\Omega$ be a space and $\mathcal{A}$ a class, then function $\mu : \mathcal { A } \rightarrow R = [ - \infty , \infty ]$ is a **set function**.

It's

- 1.  **finite** if $\forall A\in \mathcal{A},\quad |\mu(A)|<\infty$
  2. **$\sigma$-finite** if $\exists A_n \sub \mathcal{A},\quad s.t.\quad\cup_ { i = 1 } ^ { \infty } A _{ i } = \Omega\quad \forall n \quad |\mu(A_n)|<\infty$

- 1.  **additive** $\iff \mu \left( \sum _{ i = 1 } ^ { n } A_ { i } \right) = \sum _{ i = 1 } ^ { n } \mu \left( A_ { i } \right)$
  2. **$\sigma-$additive**$\Longleftrightarrow \mu \left( \sum _{ i = 1 } ^ { \infty } A_ { i } \right) = \sum _{ i = 1 } ^ { \infty } \mu \left( A_ { i } \right)$

$\mu$ is a **measure** on $\mathcal{A}$ if

1. $\forall A \in \mathcal { A } : \mu ( A ) \geq 0$ 
2. It's $\sigma$ additive.

the triplet $(\Omega,\mathcal{A},\mu)$ is a **measure space** when $\mu$ is a measure and $(\Omega,\mathcal{A})$ is  a measurable space.  Whose sets are called **measurable sets** or **$\mathcal{A}$-measurable**.A measure space is a **probability space** if $P(\Omega)=1$.

Assume that $A_{1:n}\in\mathcal{A}$ and $A\in \mathcal{A}$ and $\mu$ is a measure.

1. $\mu$ is continues from above, if $A _{ n } \searrow A \implies \mu(A_n)\to\mu(A)$
2. $\mu$ is continues from below, if $A _{ n } \nearrow A \implies \mu(A_n)\to\mu(A)$
3. $\mu$ is continues at $A$, if $A _{ n } \to A \implies \mu(A_n)\to\mu(A)$

$\forall$ Measure $\mu$ is continues from below and may not continues from above. It will be continues from above if $\exist m<\infty,\mu(A_m)<\infty$.So finite measure $\mu$ are always continues.

## Properties of measure

### Semialgebras

Let $\mu$ be a nonnegative additive set function on a semialgebra $\mathcal{A}$. $\forall A,B\in \mathcal{A}$ and $\{A_n,B_n,n\ge 1\} \in \mathcal{A}$

1. (**Monotonicity**): $A\sub B\implies \mu(A)\le\mu(B)$ 

2. (**$\sigma$-subadditivity**):

    1. $\sum _{ 1 } ^ { \infty } A_ { n } \subset A , \quad \Longrightarrow \quad \sum _{ 1 } ^ { \infty } \mu \left( A_ { n } \right) \leq \mu ( A )$
    2. Moreover, if $\mu$ is a measure, then

$$ B \subset \sum _{ n = 1 } ^ { \infty } B_ { n } \implies\mu ( B ) \leq \sum _{ n = 1 } ^ { \infty } \mu \left( B_ { n } \right) $$

We can assert a nonnegative set function $\mu$ is a measure by:

1. $\mu$ is additive
2. $\mu$ is $\sigma$ subadditive on $\mathcal{S}$

### Algebras

Let $\mu$ be a measure on an algebra $\mathcal{A}$ 
$$ A \subset \cup _{ 1 } ^ { \infty } A_ { n } \implies \mu ( A ) \leq \sum _{ 1 } ^ { \infty } \mu \left( A_ { n } \right) $$

**Proof** Note $A=A\cap(\cup A_n)=\cup(A\cap A_n)$, hence we can write $A$ as union in $\mathcal{A}$ by take $B_n=A\cap A_n \in \mathcal{A}$.

$$ A=\cup_1^\infty B_n $$

and then we can take $C_n=B_n-\cup_1^{n-1} B_i \in \mathcal{A}$ to write $A$ as disjoint union:

$$ A=\sum C_n $$

Then 

$$ \mu(\mathcal{A})=\mu(\sum C_n)=\sum \mu(C_n)\le \sum \mu(B_n)\le \sum\mu(A_n) $$

as $C_n \sub B_n \sub A_n$. $\blacksquare$

### $\sigma$ algebras

Let $\mu$ be a measure on an $\sigma$ algebra $\mathcal{A}$ 

1. Monotonicity
2. Boole's inequality(Countable Sub-Additivity) 
   $$ \mu \left( \cup _{ i = 1 } ^ { \infty } A_ { i } \right) \leq \sum _{ i = 1 } ^ { \infty } \mu \left( A_ { i } \right) $$
3. Continuity from below
4. Continuity from above if $\mu$ is finite in $A_i$.

The sense of **4** follows from suppose $A_i \searrow A$, then $A_1-A_i \nearrow A_1-A$, then

$$ \mu(A_1)-\mu(A)=\mu(A_1-A)=\lim \mu(A_1-A_i)=\mu(A_1)-\lim(A_i) $$

where $\mu(A_1)$ cannot be cancelled if $\mu(A_i)=\infty$.

Let $(\Omega,\mathcal{A},\mathcal{\mu})$ be a measure space, and $N\sub\Omega$

1. $N$ is a **$\mu$ null set** iff $\exist B\in \mathcal{A} \quad s.t. \quad \mu(B)=0, \quad N\sub B$
2. This measure space is a **complete measure** space if $\forall$ $\mu$ null space $N$, $N\in \mathcal{A}$

> Given any measure space $(\Omega,\mathcal{A},\mathcal{\mu})$ , there exist a complete measure space $(\Omega,\mathcal{\bar{A}},\mathcal{\bar{\mu}})$, such that $\mathcal{A}\sub \bar{\mathcal{A}}$ and $\bar{\mu}$ is an extension of $\mu$. This space is called completion of $(\Omega,\mathcal{A},\mathcal{\mu})$.

**Proof** Take 

$$ \begin{aligned}
  \bar{\mathcal{A}}&=\{A\cup N:A\in \mathcal{A}\}\\
  \bar{\mathcal{B}}&=\{A\Delta N:A\in \mathcal{A}\}
\end{aligned} $$

$\bar{\mathcal{A}}=\bar{\mathcal{B}}$ since $A\cup N=(A-B) \Delta (B\cap (A\cup N))$ and $A\Delta N=(A-B)\cup(B\cap(A\Delta N))$.

Then we can show that $\bar{\mathcal{A}}$ is a $\sigma$ algebra. Let $E_i=A_i \cup N_i\in \bar{\mathcal{A}}$, then

$$ \bigcup_1^\infty E_i=\bigcup_1^\infty A_i \cup \bigcup_1^\infty N_i $$ 

and note $\bigcup_1^\infty A_i\in \mathcal{A}$ and $\mu(\bigcup_1^\infty N_i)\le \mu(\cup_1^\infty B_i)\le \cup_1^\infty \mu(B_i)=0$. Thus $\bar{\mathcal{A}}$ is closed by countable union. As for complements, note $E^c=A^c \cap N^c=(A^c\cap N^c \cap B^c)\cup (A^c\cap N^c \cap B)=(A^c\cap B^c)\cup (A^c\cap N^c\cap B)\in \bar{\mathcal{A}}$.

Finally we define a measure $\bar{\mu}$ on $\bar{\mathcal{A}}$ by

$$ \bar{\mu}(A\cup N)=\mu(A) $$

We should prove it's well defined. Suppose $A_1\cup N_1=A_2 \cup N_2 \in \bar{\mathcal{A}}$, note $A\Delta B \Delta C=A\Delta (B\Delta C)$ and $A\Delta B=B\Delta A$.

$$\begin{aligned}
  (A_1\Delta A_2)\Delta(N_1\Delta N_2)&=(A_1\Delta A_2 \Delta N_1)\Delta N_2
  \\&=(A_1\Delta N_1)\Delta(A_2\Delta N_2)
  \\&=\emptyset
\end{aligned}$$

Hence $A_1 \Delta A_2=N_1\Delta N_2$, note $N_1\Delta N_2 \subset N_1\cup N_2 \subset B_1 \cup B_2$, hence $\mu(A_1\Delta A_2)=0$ and thus $\mu(A_1 - A_2)=\mu(A_2-A_1)=0$. Therefore

$$ \begin{aligned}
  \mu(A_1)&=\mu(A_1-A_2)+\mu(A_1\cap A_2)=\mu(A_1\cap A_2)
  \\
  \mu(A_2)&=\mu(A_2-A_1)+\mu(A_1\cap A_2)=\mu(A_1\cap A_2)
\end{aligned} $$

$\bar{\mu}$ is do well defined. $\mu^*$ is auto $\sigma$ additive since so is $\mu$ and is easy to check that all $\mu^*$ null set is $\mu$ null set. $\blacksquare$

## Extension of set functions from semialgebra to algebra.

For $\mathcal{A}\sub\mathcal{B} \sub \mathcal{P}(\Omega)$, and $\mu:\mathcal{A}\to \reals,\nu:\mathcal{B}\to \reals$, if
$$
\mu(A) = \nu(A)\quad \forall A\in \mathcal{A}
$$
$\nu$ is an **extension** of $\mu$ from $\mathcal{A}$ to $\mathcal{B}$, and $\mu$ is an **restriction** from $\mathcal{B}$ to $\mathcal{A}$.

We can extent a non-negative and additive set function $\mu$ from a semialgebra $\mathcal{S}$ to $\bar{\mathcal{S}}$ as
$$
\bar { \mu } ( A ) = \sum _{ 1 } ^ { m } \mu \left( A_ { i } \right)
$$
where $A\in \bar{\mathcal{S}}$ and $A = \sum _{ 1 } ^ { m } A_ { i }$ with $A_i \in \mathcal{S}$. Note such extension is unique and such extenstion keep the $\sigma$ or normal additivity property.

## Outer measure

Let $\mu$ be a measure on a semialgebra $\mathcal{S}$, for any $A \sub \Omega$, now suppose the extension from $\mathcal{S}$ to $\mathcal{P}(\Omega)$
$$
\mu ^ { * } ( A ) : = \inf \left\{ \sum _ { n = 1 } ^ { \infty } \mu \left( A _ { n } \right) ; A \subset \cup _ { n = 1 } ^ { \infty } A _ { n } , A _ { n } \in \mathcal { S } \right\}
$$

to be the **outer measure** of $A$, $\mu^*$ is called the outer measure.

**Remarks:**

1. $\mu^*$ is defined on $\mathcal{P(\Omega)}$
2. $\mu^*$ may not be a measure
3. $\cup_1^\infty A_n$ is a countable covering of A

There is some properties as follows:

1. $\forall A\in \mathcal{S} \quad \mu^*(A)=\mu(A)$
2. Monotonicity
3. $\sigma$ subadditivity 
   $$ \mu ^ { *} \left( \cup _ { 1 } ^ { \infty } A _ { n } \right) \leq \sum _ { 1 } ^ { \infty } \mu ^ {* } \left( A _ { n } \right) $$

**Proof** 

1. 
    By definition, $\mu^*(A)\le \mu(A)$. Then we prove $\mu^*(A)\ge \mu(A)$. For any $\cup_1^\infty A_n\supset A$, ${\mu}(A)\le \sum_1^\infty {\mu}(A_n)$, then taking inf both side.

A set $A\sub \Omega$ is said to be measurable w.r.t. an outer measure $\mu^*$ if for any $D\sub\Omega$:
$$ \mu ^ {* } ( D ) = \mu ^ { *} ( A \cap D ) + \mu ^ {* } \left( A ^ { c } \cap D \right) $$

Note $\mu^*(D)= \mu ^ {*} ( (A \cap D ) \cup (A ^ { c } \cap D)) \le \mu ^ {*} ( A \cap D ) + \mu ^ {* } \left( A ^ { c } \cap D \right)$
hence we have

> A set $A\in \mathcal{P}(\Omega)$ is said to be measurable w.r.t. an outer measure $\mu^*$ iff for any $D\sub\Omega$:
$$ \mu ^ {* } ( D ) \ge \mu ^ { *} ( A \cap D ) + \mu ^ {* } \left( A ^ { c } \cap D \right) $$

To make $\mu^*$ be a measure, we should restric $\mathcal{P}(\Omega)$ to some $\mathcal{A^*}$ again. Let $A^*$ be the class of all $\mu^*$ measurable sets

- the class is a $\sigma$ algebra

**Proof** 
$A^*$ is clearly closed under complement. Then it remains to show $A^*$ is closed under countable union.

> **Lemma 1** Let $A_{1:n}\in \mathcal{A}$ be disjoint, then $\mu^*(D)=\sum \mu^*(A_i \cap D)+\mu^*((\sum A_i)^c\cap D)$
> 
> **Proof** Note $\mu^*(D)=\mu^*(A_1\cap D)+ \mu^*(A_1^c\cap D)$ and $A_1=A_2\cap A_1+A_2^c \cap A_1$, hence we have
> 
> $$ \mu^*(D)=\mu^*(A_1\cap D)+\mu^*(A_1^c\cap A_2\cap D)+\mu^*(A_1^c\cap A_2^c \cap D) $$ 
> 
> repeat such progresses, then we finialy have
> 
> $$ \mu^*(D)=\sum_{k=1}^n \mu^*(A_k \cap \bigcap_{i=1}^{k-1} A_i^c\cap D)+\mu^*(\bigcap_{k=1}^n A_k^c\cap D)$$ 
> 
> since $A_{1:n}$ are disjoint, we have
> 
> $$ \begin{aligned}
  A_k \cap \bigcap_{i=1}^{k-1} A_i^c&=A_k\\
  \bigcap_{k=1}^n A_k^c&=(\sum A_k)^c
\end{aligned} $$ 
>
> Then we finished. $\blacksquare$
> 
> **Lemma 2**
> Let $\mathcal{F}$ be an algerba, then it's a $\sigma$ algebra iff it's closed under countable disjoint union.
> 
> **Proof** Sufficency is trival. For the necessity, suppose $B_{1:n} \in \mathcal{F}$ and note 
> 
> $$ C_n=B_n-\cup_1^{n-1} B_i $$ 
> 
> lies in $\mathcal{F}$ are disjoint since $\mathcal{F}$ is an algebra and $\bigcup B_n=\bigcup C_n \in \mathcal{F}$. $\blacksquare$


We have 

$$\begin{aligned}
  \mu^*(D) &= \sum \mu^*(A_i \cap D)+\mu^*((\sum A_i)^c\cap D)
  \\&\geq \mu^*(D\cap\sum A_n)+\mu^*(D\cap (\sum A_n)^c)
  \\&\geq \mu^*(D\cap\sum_1^\infty A_n)+\mu^*(D\cap (\sum A_n)^c)
\end{aligned} $$ 

since lemma 1.

Then is remains to show that $\mathcal{F}$ is an algebra since lemma 2. Note the proof of lemma 1, we already have:
For $A_1,A_2\in \mathcal{F}$(may or may not disjoint): 

$$\begin{aligned}
    \mu^*(D)&=\mu^*(A_1\cap D)+\mu^*(A_1^c\cap A_2\cap D)+\mu^*(A_1^c\cap A_2^c \cap D)
    \\&=\mu^*(A_1\cap A_2 \cap D)+\mu^*(A_1\cap A_2^c\cap D)+\mu^*(A_1^c\cap A_2\cap D)+\mu^*(A_1^c\cap A_2^c \cap D)
    \\&\ge \mu^*((A_1\cap A_2 \cap D)\cup (A_1\cap A_2^c\cap D)\cup(A_1^c\cap A_2 \cap D))+\mu^*((A_1\cup A_2)^c\cap D)
    \\&=\mu^*((A_1\cup A_2)\cap D)+\mu^*((A_1\cup A_2)^c\cap D)
\end{aligned} $$ 

which suggests $A_1\cup A_2 \in \mathcal{F}$ and thus $\mathcal{F}$ is a algebra. $\blacksquare$

- If $A=\sum_1^\infty A_i$ with $A_i\in A^*$, then for any $D\sub \Omega$

$$ \mu^*(A\cap D)=\sum_1^\infty\mu^*(A_n \cap D) $$

**Proof** From the above proof, we have

$$\mu^*(D)=\sum \mu^*(A_i \cap D)+\mu^*((\sum A_i)^c\cap D)$$ 

holds for any $D\subset \Omega$, assign $D=A\cap D$, then

$$ \mu^*(A\cap D)= \sum \mu^*(A_i\cap D)+\mu^*(\emptyset)$$

note $\mu^*(\emptyset)=0$, we are done. $\blacksquare$

- $\left( \Omega , \mathcal { A } ^ { *} , \left. \mu ^ {* } \right| _{ \mathcal { A } ^ { * } } \right)$ is a measure spcae. $\mu^*|_{\mathcal{A^*}}$ is an extension of $\mu$.

$\mu^*$ is a measure since it's nonegative and $\sigma$ additive from above.

Where we didn't use any property of semialgebra hence above results is general for any class set which $\cup \mathcal{S}=\Omega$

## Extension of measures from semialgebra to $\sigma$ algerba

**Theorem** $\mathcal{S}\subset \mathcal{A^*}$ and hence $\sigma(\mathcal{S})\subset \mathcal{A}^*$

<!-- **Proof** We have  -->

$$ \begin{array} { l l l l l l l l l } \mathcal { S } & \subset & \overline { \mathcal { S } } & \subset & \sigma ( \mathcal { S } ) & \subset & \mathcal { A } ^ { * } & \subset & \mathcal { P } ( \Omega ) \end{array} $$

**(Caratheodory Extension Theorem)**
Let $\mu$ be a measure on a semialgebra $\mathcal{S}$, then

1. $\mu$ has an extension to $\sigma(\mathcal{S})$, denoted by $\mu|_{\sigma(\mathcal{S})}$, further more, acctually it can be taken by the restriction of $\mu^*$

$$ \left. \mu \right| _{ \sigma ( \mathcal { S } ) } = \left. \mu ^ { * } \right|_ { \sigma ( \mathcal { S } ) } $$

2. If $\mu$ is $\sigma$ finite, the the extension is unique.

> If $P$ is a probability defined on a semialgebra $\mathcal{S}$ on $\Omega$, then there exist a unique probability space $(\Omega,\sigma(\mathcal{S}),P^*)$, s.t.
> $$ P^*(A)=P(A)\quad \forall A \in \mathcal{S} $$

## Completion of a measure



Following lemma is useful.

> Let $\mu$ be a measure on a semialgrbra $\mathcal{S}$, and $\mu^*$ the outer measure induced by $\mu$. If $A\sub\Omega$, and $\mu^*(A)<\infty$ , then $\exist B \in \sigma(\mathcal{S})$, s.t:
>
> 1. $A \sub B$
> 2. $\mu^*(A)=\mu^*(B)$
> 3. $\forall C \sub B-A$ and $C\in \sigma(\mathcal{S})$, we have $\mu^*(C)=0$
>
> Such $B$ is called as a **meaurable cover** of $A$.

Then we are ready to show that $\mathcal{A^*}$ is actually $\overline{\sigma(\mathcal{S})}$.

> Let $\mu$ be a $\sigma$ finite measure on a semialgrbra $\mathcal{S}$, and $\mu^*$ the outer measure induced by $\mu$, and $\mathcal{A^*}$ the $\sigma$ algebra consists of all the $\mu^*$ measurable sets. Then $(\Omega,\mathcal{A^*},\mathcal{\mu^*|_{\mathcal{A^*}}})$ is the completion of $\left(\Omega , \sigma ( \mathcal { S } ) , \left. \mu ^ { * } \right|_ { \sigma ( \mathcal { S } ) } \right)$.

It's sufficient to show that $\overline{\sigma(\mathcal{S})}=\mathcal{A}^*$ since

$$\mu^*(A)\le \mu^*(A\cup N)\le \mu^*(A)+0 \implies \mu^*(A\cup N)=\mu^*(A) $$

i.e. $\mu^*=\bar{\mu}$. We first show that $\overline{\sigma(\mathcal{S})}\subset\mathcal{A^*}$. Let $E=A\cup N\in \overline{\sigma(\mathcal{S})}$, it's sufficient to show that $N\in \mathcal{A^*}$ since $A\in \sigma(\mathcal{S}) \subset \mathcal{A^*}$.


$$ \begin{aligned}
  \mu^*(D\cap N^c)+\mu^*(D\cap N) &\le \mu^*(D\cap N^c)+\mu^*(N)
  \\&\le \mu^*(D\cap N^c)+\mu^*(B)
  \\&\le \mu^*(D\cap N^c)
  \\&\le \mu^*(D).
\end{aligned}  $$

Then we show that $\mathcal{A^*}\subset \overline{\sigma(\mathcal{S})}$. Suppose $A\in \mathcal{A} \ni \mu^*(A)<\infty$,consider its measurable cover $B$ and the measurable cover of $B-A$, $C$. Note that

$$ A=(B-C)+(A\cap C) $$

and $B-C\in \sigma(\mathcal{S})$ and $A\cap C$ is a $\mu^*$ null set since

$$ \mu^*(A\cap C)\le \mu^*(C)=\mu^*(B-A)=0 $$

, we have $A\in \overline{\sigma(\mathcal{S})}$. If $\mu^*(A)=\infty$, we can write it as countable union of finite $A_i$ and back to the case before. $\blacksquare$

As a matter of fact, $A^*$ is  $\overline { \sigma ( \mathcal { S } ) }$, i.e.
$$ A^*= { \sigma ( \mathcal { S } ) }+\{all \ \mu|_{\sigma}\ null\ sets\} $$

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
1. Such function $F$ is called a **L-S measure function**
2. The completed measure $\mu$ is called the **L-S measure**. The (uncompleted) measure is called the **B(roel)-L-S measure**
3. If $F(x)=x$, then $\mu$ is called the **L measure**, if $\mu$ is uncompleted is called **B measure**. L measure is not finite but $\sigma$ finite.
4. $F$ uniquely determines $\mu$, but not visa versa.
5. If restrict $\mu$ to $([0,1],\mathcal{B}\cap[0,1])$, then $\mu$ is a probability measure.

**Proof** Follow the general procedures, suppose $\mathcal{S}=\{(a,b]\}\cup \{\Reals,\empty,\{-\infty\}\}$, one can chenck such $\mathcal{S}$ is a semi algebra and $\mathcal{B=\sigma(S)}$. Define

$$ \begin{aligned}
  \mu((a,b])&=F(b)-F(a)\\
  \mu(\{-\infty\})&=0\\
  \mu(\Reals)&=F(\infty)-F(-\infty)
\end{aligned} $$

Check it's well defined, $\sigma$ finite, additive and $\sigma$ subadditive and apply Caratheodory's extension theorem we can get the desired result.
