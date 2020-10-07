# TAO-IMT

An **interval** is in the form of **([)(a,b)(])** and we define a measure on it as $m(I)=|I|=b-a$. A box in $R^d$ is $B:=\prod_1^d I_i$, and its measure is $m(B)=|B|=\prod_1^d |I_i|$. Take

$$ \mathcal{S}=\{\text{all the boxes}\} $$

One can check such class of sets is semialgebra. Then form **elementary sets** as all finite union of boxes in $\mathcal{S}$, it's contains $\overline{\mathcal{S}}$ clearly. We can show that any elementary set can be expressed as finite disjoint union and thus it's actually $\overline{\mathcal{S}}$. Finally we can extend measure space $(\Reals,\mathcal{S},m)$ to $(\Reals,\overline{\mathcal{S}},\overline{m})$.

Before discussing outer measure, we can restrict countable to finite to define jordan outer measure as

$$ m^{*,J}(E)=\inf \left\{ \sum _ { n = 1 } ^ { N } \mu \left( B _ { n } \right) ; E \subset \cup _ { n = 1 } ^ { N } B _ { n } , B _ { n } \in \mathcal { S } \right\} $$

that is 

$$ m^{*,J}(E)=\inf \left\{ \overline{m}(B) ; E \subset B , B \in \overline{S} \right\} $$

and jordan inner measure

$$ m_{*,J}(E)=\sup \left\{ \sum _ { n = 1 } ^ { N } \mu \left( B _ { n } \right) ; B \supset \cup _ { n = 1 } ^ { N } B _ { n } , B _ { n } \in \mathcal { S } \right\} $$

similarly

$$ m_{*,J}(E)=\sup \left\{ \overline{m}(B) ; E \supset B , B \in \overline{S} \right\} $$

One set is jordan measurable iff such two measurable agree.

### Lebesgue measurability

Then consider its outer measure as usual and define a lebesgue measurability differently:

> $E$ is lebesgue measurable iff there exists an open set $U\subset R^d$ s.t. $m^*(U-E)\le \epsilon$ for any $\epsilon\gt 0$.

Which is equivalent to the before definition. $\implies$ follows from we can show that $m^*(A\cap U)-\mu^*(A\cap E)\le \epsilon$ and $m^*(A-E)-m^*(A-U)\le \epsilon$. And $\impliedby$ follows from

$$m^*(E) \le m^*(U) = m^*(E)+m^*(U-E)\le m^*(E)+\epsilon$$

by picking $m^*(U)\le m^*(E)+\epsilon$ and noting $U$ and $E$ both in $\mathcal{A^*}$ and thus $m^*$ is additive. Where we used the truth that open sets are countable disjoint union of boxes and thus $U\in \mathcal{A}^*$ and we can enlarge the cover of $E$ slightly to pick $U$ such that $m^*(U)\le m^*(E)+\epsilon$.

### Recover additivity

Note the addictive can be recover if the two disjoint sets are **separated**, that is

$$ \text{dist}(E,F):=\inf\{|x-y|:(x,y)\in E\times F\}>0 $$

since so that we can divide the cover of $E\cup F$ into two pieces which cover $E$ and $F$ separately.

### Inequity with jordan measure

Employed monotonicty in $(\Reals,\mathcal{A^*},m^*)$, $m^*(P)\ge {m}^*(B)$ for any $B\subset E \subset P$. Where $B\in \overline{\mathcal{S}}$ and $P=\cup_1^\infty P_i \in \mathcal{S}$ and thus $P,B\in \mathcal{A^*}$. Thus

$$ \sum_1^\infty m^*(P_i)= \sum_1^\infty m(P_i) \ge m^*(P) \ge m^*(B)=\overline{m}(B) $$

Note $m^*(B)=\overline{m}(B)$ follows from $m^*$ in $\mathcal{A^*}$ is additive.

Thus $m^*(E)=\inf\{\sum_1^\infty m(P_i): P=\cup_1^\infty P_i \supset E\}\ge \sup\{\overline{m}(B),B\subset E\}=m_{*,J}(E)$. Therefore

$$ m_{*,J}(E)\le m^*(E)\le m^{*,J}(E) $$
















