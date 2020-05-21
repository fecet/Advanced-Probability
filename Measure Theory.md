# Measure Theory

function $\mu : \mathcal { A } \rightarrow R = [ - \infty , \infty ]$ is a **set function**.

It's

- 1.  **finite** if $\forall A\in \mathcal{A},\quad |\mu(A)|<\infty$
  2. **$\sigma$-finite** if $\exists A_n \sub \mathcal{A},\quad s.t.\quad\cup _ { i = 1 } ^ { \infty } A _ { i } = \Omega\quad \forall n \quad |\mu(A_n)|<\infty$

- 1.  **additive** $\iff \mu \left( \sum _ { i = 1 } ^ { n } A _ { i } \right) = \sum _ { i = 1 } ^ { n } \mu \left( A _ { i } \right)$
  2. **$\sigma-$additive**$\Longleftrightarrow \mu \left( \sum _ { i = 1 } ^ { \infty } A _ { i } \right) = \sum _ { i = 1 } ^ { \infty } \mu \left( A _ { i } \right)$

$\mu$ is a **measure** on $\mathcal{A}$ if

1.  $\forall A \in \mathcal { A } : \mu ( A ) \geq 0$ 
2. It's $\sigma$ additive.



the triplet $(\Omega,\mathcal{A},\mu)$ is a **measure space** when $\mu$ is a measure.  a measure space is a probability space if $P(\Omega)=1$.

For probability measure, which has following properties:

1. $\forall A\in \mathcal{A},\quad 0\le P(A) \le 1$
2. $P(A^c)=1-P(A)$
3. $P(A) \le P(B) \impliedby A\sub B$
4. $P \left( \cup _ { k = 1 } ^ { n } A _ { k } \right) = \sum _ { k } P \left( A _ { k } \right) - \sum _ { i < j } P \left( A _ { i } \cap A _ { j } \right) + \ldots \ldots$
5. $P$ is continuous, as well as continuous from above and below.

For $\mathcal{A}\sub\mathcal{B} \sub \mathcal{P}(\Omega)$, and $\mu:\mathcal{A}\to \reals,\nu:\mathcal{B}\to \reals$, if
$$
\mu(A) = \nu(A)\quad \forall A\in \mathcal{A}
$$
$\nu$ is an **extension** of $\mu$ from $\mathcal{A}$ to $\mathcal{B}$, and $\mu$ is an **restriction** from $\mathcal{B}$ to $\mathcal{A}$.

We can extent a non-negative and additive set function $\mu$ from a semialgebra $\mathcal{S}$ to $\bar{\mathcal{S}}$ as 
$$
\bar { \mu } ( A ) = \sum _ { 1 } ^ { m } \mu \left( A _ { i } \right)
$$
where $A\in \bar{\mathcal{S}}$ and $A = \sum _ { 1 } ^ { m } A _ { i }$ with $A_i \in \mathcal{S}$.



## Outer measure

Let $\mu$ be a measure on a semialgebra $\mathcal{S}$, for any $A \sub \Omega$
$$
\mu ^ { * } ( A ) : = \inf \left\{ \sum _ { n = 1 } ^ { \infty } \mu \left( A _ { n } \right) ; A \subset \cup _ { n = 1 } ^ { \infty } A _ { n } , A _ { n } \in \mathcal { S } \right\}
$$




