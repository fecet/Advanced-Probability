# Independence

## Definition

Let $(\Omega,\mathcal{A},P)$ be a probability space

1. **Events** $A_{1:n}\in \mathcal{A}$ are said to be independent iff $$ P \left( \bigcap _ { i \in J } A _ { i } \right) = \prod _ { i \in J } P \left( A _ { i } \right) \quad\forall J$$ where $J\in \mathcal{P}(\{1,2,\cdots,n\})$


2. **Classes** $\mathcal{A_{1:n}}$ are said to be independent iff $$ P \left( \bigcap _ { i \in J } A _ { i } \right) = \prod _ { i \in J } P \left( A _{ i } \right)\quad \forall J,A_i\in \mathcal{A_i} $$Moreover, if classes mentioned above are $\sigma$ algebras, they are independent iff $$ P \left( \bigcap_ { i = 1 } ^ { n } A _ { i } \right) = \prod _ { i = 1 } ^ { n } P \left( A _ { i } \right)\quad \forall A_i\in \mathcal{A_i} $$

3. The **r.v.'s** $X_{1:n}$ are said to be independent iff the events $\{X_i\in B_i\}$ are independent. $$ P \left( \bigcap _ { i \in J } \left\{ X _ { i } \in B _ { i } \right\} \right) = \prod _ { i \in J } P \left( \left\{ X _ { i } \in B _ { i } \right\} \right) $$ Recall that $\{X\in \mathcal{B}\}$ is $\sigma$ algebra. Hence which is equivalent to $$ P \left( \bigcap _ { i = 1 } ^ { n } \left\{ X _ { i } \in B _ { i } \right\} \right) = \prod _ { i = 1 } ^ { n } P \left( \left\{ X _ { i } \in B _ { i } \right\} \right) \quad \forall B_i\in \mathcal{B}$$

4. The r.v.'s that are independent and have same d.f. are called **i.i.d**

## Check independence

In order to check if $X_{1:n}$ are independent. We only need to check:

$$ F _ { X _ { 1 } , \ldots , X _ { n } } \left( t _ { 1 } , \ldots , t _ { n } \right) = F _ { X _ { 1 } } \left( t _ { 1 } \right) \ldots \ldots F _ { X _ { n } } \left( t _ { n } \right)\quad \forall t_{1:n}\in \Reals $$

If $\mathcal{G}$ and $\mathcal{D}$ are independent classes, and $\mathcal{D}$ is a $\pi$ class, then $\mathcal{G}$ and $\sigma(\mathcal{D})$ are independent.

Hence we have,

Let $\mathcal{A_{1:n}}$ are independent and each is a $\pi$ class, then $\sigma(\mathcal{A_1}),\cdots,\sigma(\mathcal{A_n})$ are independent.

### Discrete case

Discrete r.v.'s $X_{1:n}$ taking values in $C_i$, are independent iff

$$ P \left( X _ { 1 } = a _ { 1 } , \ldots , X _ { n } = a _ { n } \right) = \prod _ { i = 1 } ^ { n } P \left( X _ { i } = a _ { i } \right) $$

where $a_i\in C_i$

### Absolutely continuous case

Let $X=(X_{1:n})$ be an absolutely continuous random vector. Then $X_{1:n}$ are independent iff $\forall y_i\in\Reals$
$$ f _ { X } \left( y _ { 1 } , \ldots , y _ { n } \right) = \prod _ { i = 1 } ^ { n } f _ { X _ { i } } \left( y _ { i } \right) $$

## Functions of independent r.v.'s

If $X_{1:n}$ are independent and $g_{1:n}$ are borel, then $g_i(X_{i})$ are independent.
Moreover Let $\{n_{j-1:j}\}$ be a partition of ${1:n}$ and $g_j$ be borel of $n_j-n_{j-1}$ variables, then

$$ g_j(X_{n_{j-1}+1:n_j}) $$

are dependent

### Convolutions

Let $X,Y$ be independent and absolutely continuous. Then $X+Y$ is absolutely continuous and

$$ f _ { X + Y } ( t ) = \int _ { - \infty } ^ { \infty } f _ { X } ( t - s ) f _ { Y } ( s ) d s , \quad t \in \mathcal { R } $$

### Correction

The covariance of two r.v.'s $X$ and $Y$ is 

$$ \operatorname { Cov } ( X , Y ) : = E ( X - E X ) ( Y - E Y ) = E ( X Y ) - E X E Y $$

If $X,Y$ are independent, then

$$ Cov(X,Y)=0 $$

Moreover, if $X_{1:n}$ are independent, then

$$ E\prod X_i=\prod EX_i $$

Let $u,v$ be both monotone with the same directions, then

$$ E u ( X ) E v ( X ) \leq E [ u ( X ) v ( X ) ] $$

which is equivalent to 

$$ Cov(u(X),v(Y))\ge0 $$

Take $u(x)=x^r$ and $v(x)=x^s$, then we have

$$ \left( E | X | ^ { r } \right) \left( E | X | ^ { s } \right) \leq E | X | ^ { r + s } , \quad r , s \geq 0 $$

## Borel-Cantelli Lemma

Let $A_{1:n}$ be a sequence of events on $(\Omega,\mathcal{A},P)$,Recall

$$ \{A_n,\ i.o.\}=\limsup_n A_n=\bigcap_{n=1}^\infty \bigcup_{m=n}^\infty A_m=\lim_{n\to\infty}\sup\{ A_{n:\infty}\}=\lim_{n\to\infty}\bigcup_{m=n}^\infty A_m$$

$$ \{A_n,\ ult.\}=\liminf_n A_n=\bigcup_{n=1}^\infty \bigcap_{m=n}^\infty A_m=\lim_{n\to\infty}\inf\{ A_{n:\infty}\}=\lim_{n\to\infty}\bigcap_{m=n}^\infty A_m$$

Note that:

$$ \liminf_n A_n = (\limsup_n A_n^c)^c $$

1. $P(A_n,i.o.)=0\impliedby \sum_{n}^\infty P(A_n)<\infty$
2. $P(A_n,i.o.)=1\impliedby \sum_{n}^\infty P(A_n)=\infty$ and $A_{1:n}$ are independent.

**Proof**:

1. $$P(A_n,i.o.)=P(\lim_{n\to\infty}\cup_{m=n}^\infty A_m)=\lim_{n\to\infty}P(\cup_{m=n}^\infty A_m)\le \lim_{n\to\infty}\sum_{m=n}^\infty P (A_m)=\lim_n P(A_n)=0$$
2. 

Actually, the condition "$A_{1:n}$ are independent." can be reduced to $A_{1:n}$ are pairwise independent.

If $A_{1:n}$ are independent and $A_n\to A$, then $P(A)$ can only be $0$ or $1$.

$$X_n\to 0\ a.s.\iff P({\{|X_n|\ge \epsilon\}},i.o.)\iff\sum_{n=1}^\infty P\{|X_n|\ge \epsilon\} <\infty$$

then we have

Let $X_{1:n}$ and $X$ be i.i.d., then

$E|X|<\infty \iff\sum_n P(|X|>\epsilon n)<\infty\quad \forall \epsilon>0\iff |X_n|/n\to 0\iff X_n = o(n)\ a.s.$


## Kolmogorov 0-1 laws

The **tail $\sigma$ algebra** or **remote future** of a sequence $X_{1:n}$ of r.v.'s on $(\Omega,\mathcal{A},P)$ is

$$ \bigcap _ { n = 1 } ^ { \infty } \sigma \left( X _ { j } , j \geq n \right) \equiv \bigcap _ { n = 1 } ^ { \infty } \sigma \left( X _ { n } , X _ { n + 1 } , \ldots \ldots \right) $$

The sets of which are called **tail events**, and functions on which are **tail functions**

**Kolmogorov 0-1 Law**
> Tail events of independent $X_{1:n}$ have probability $0$ or $1$

Proof:
$\forall n\ge 1$, $\sigma(X_{1:n})$ and $\sigma({X_{n+1:})}$ are independent

Denoted $\cap_{n=1}^\infty\sigma({X_{n+1:}})=\mathcal{D}$, then we clearly have $\mathcal{D}\sub \sigma(X_{n+1:})\quad\forall n\ge 1$
$\implies \forall n\ge 1$, $\sigma(X_{1:n})$ and $\mathcal{D}$ are independent

Denoted $\cup_{n=1}^\infty \sigma(X_{1:n})=\mathcal{A}$

$\implies \mathcal{A}$ and $\mathcal{D}$ are independent.

For finite $A_i\in \mathcal{A}$, there exist $N$ s.t.

$$ A_i \in \sigma(X_{1:N})\implies \cup A_i \in \sigma(X_{1:N})\sub \mathcal{A} \\
A_i \in \sigma(X_{1:N})\implies  A_i^c \in \sigma(X_{1:N})\sub \mathcal{A} 
$$

hence $\mathcal{A}$ is an algebra, hence a $\pi$ class.

$ \implies \sigma(\mathcal{A})$ and $\mathcal{D}$ are independent.

$$ \sigma(X_{1:})= \sigma(\cup_{i=1}^\infty\sigma(X_i))$$

$$ \sigma(\mathcal{A})=\sigma(\cup_{n=1}^\infty \sigma(X_{1:n})) $$

Note that $$\sigma(X_{1:n})\sub \sigma(X_{1:n+1})\sub \cdots\sub \sigma(X_{1:})$$

hence $\sigma(\mathcal{A})=\sigma(X_{1:})$
Then we have

$$ \mathcal{D}\sub \sigma(X_{n+1:})\sub \sigma(X_{1:})=\sigma(\mathcal{A}) $$

that is $\mathcal{D}$ are independent of itself. Thus

$$ \forall B\in \mathcal{D} \quad s.t.\quad P(B)=P(B\cap B)=P^2(B)\implies P(B)=1\ or\ 0 $$


>Tail function of independent r.v.'s are degenerate a.s.


Note that $Y\le c$ is tail events.


>$\limsup_n X_n$ and $\liminf_n X_n$ are degenerate a.s.

Foreach $n\ge k \ge 1$, since
$$ \sigma(X_n) \sub \sigma(X_{k:}) $$
thus $X_n$ is $\sigma(X_{k:})$ measurable, then we have

$$ Y_k=: \sup_{n\ge k}X_n\text{ is $\sigma(X_{k:})$ measurable }  $$

Hence, $Y_n$ is $\sigma(X_{n:})$ measurable and hence $\sigma(X_{k:})$ since $\sigma(X_{n:})\sub \sigma(X_{k:})$. Thus

$$ \lim_{n\to \infty}Y_n=\limsup_n X_n $$ is $\sigma(X_{k:})$ measurable forall $k\ge 1$. Hence $\limsup X_n$ is $\cap_{k=1}^\infty \sigma(X_{k:})$ measurable, i.e., a tail function.

<br><br><br><br><br><br>
<br><br><br><br><br><br>