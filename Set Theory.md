# Set Theory

Semi-algebra:

1. $$
   A , B \in \mathcal { S } \Rightarrow A\cap B \in S
   $$

2. $$
   A\in S \Rightarrow \exist A _ { i } \in \mathcal { S } , \quad A _ { i } \cap A _ { j } = \emptyset , i \neq j,\quad s.t.  \quad A^c=\sum_{i=1}^{n}A_i
   $$

algebra:

1. $$
   A^c \in \mathcal{A} \iff A\in \mathcal{A}
   $$

2. $$
   \cup_i A_i \in \mathcal{A} \impliedby \forall i,  A_i\in\mathcal{A}
   $$

   Note that algebra is closed by finite union and we can prove that is Equivalent   to it is closed by finite intersection

$\sigma$ algebra:

1.  is an algebra

2. $$
   \cup_i^\infty A_i\in \mathcal{A} \impliedby \forall i,\ A_i\in \mathcal{A}
   $$



a semi-algebra $\mathcal{S}$ can generate algebras by take all finite  disjoint unions of sets, i.e
$$
\overline { \mathcal { S } } = \{ \text {finite disjoint unions of sets in } \mathcal { S } \} = \mathcal{A} (\mathcal{S})
$$
is an algebra



Let $\left\{ \mathcal { A } _ { \gamma } : \gamma \in \Gamma \right\}$ is a collection of  $\sigma$ algebra, then we have 
$$
\mathcal { A } = \cap _ { \gamma \in \Gamma } \mathcal { A } _ { \gamma }
$$
is also  a $\sigma$ algebra.



$\forall \mathcal{A} \sub \mathcal{P}(\Omega), \quad \exist \sigma(\mathcal{A}) \quad s.t. $ 

1. $$
   \quad \mathcal{A} \sub \sigma(\mathcal{A})
   $$

2. $$
   \forall \mathcal{A} \sub\mathcal{B} \in \sigma \text{-algebras} \quad \sigma(\mathcal{A}) \sub \mathcal{B}
   $$

3.  $\sigma(\mathcal{A})$ is unique.



We have 
$$
\sigma ( \mathcal { S } ) = \sigma ( \overline { \mathcal { S } } )
$$
Which can be proved by show that
$$
\mathcal{S} \sub \sigma(\bar{\mathcal{S}}) \implies \sigma(\mathcal{\bar{S}}) \sub \sigma({\mathcal{S}})\\
\mathcal{\bar{S}} \sub \sigma({\mathcal{S}})\implies \sigma(\mathcal{{S}}) \sub \sigma({\bar{\mathcal{S}}})
$$

## $m-,\pi-,\lambda-$class 

**m-class:**

If $A_n\in\mathcal{A}$ and $A_n\uparrow or \downarrow$
$$
\lim_{n\to\infty}A_n\in \mathcal{A}
$$
**$\pi-$class** 
$$
A,B\in \mathcal{A} \implies A\cap B\in \mathcal{A}
$$
**$\lambda-$ class**

1. $$
   \Omega \in \mathcal{A}
   $$

2.  closed under proper difference:
   $$
   A-B \in \mathcal{A} \impliedby B\sub A\in \mathcal{A}
   $$

3.  is an m-class (cause $\Omega-A_i \downarrow$ whenever $A_i \uparrow$ )



m-class is equivalent to $\sigma-$ algebra when it is already an algebra.
$$
\mathcal{A} \text{ is a $\sigma-$ algebra} \iff \mathcal{A} \text{ is a $\pi-$ class} \and \mathcal{A} \text{ is a $\lambda-$ class}
$$
