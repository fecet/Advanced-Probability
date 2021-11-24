# Brownian Motion

Brownian motion at time $t$$t$ is limit of infinite fast random walk $W^{n}_t$, it can be equivalently characterized by

1. Any increment $W_{t_1}-W_{t_2}$$0$ is normal distributed with mean $0$$t_1-t_2$ and variance $t_1-t_2$$t_1,t_2,\dots,t_{m}$. Disjoint increment are independency.
2. For any time $t_1,t_2,\dots,t_{m}$$\bm{W}=(W_{t_1},W_{t_2},\dots,W_{t_{m}})$, $\bm{W}=(W_{t_1},W_{t_2},\dots,W_{t_{m}})$$\bm{W}$ is normal distributed with zero mean and covariance
$$
\bm{\Sigma}=\begin{bmatrix}
                t_1	& t_1	& \dots	& t_1	\\
                t_1	& t_2	& \dots	& t_2	\\
                \vdots	& \vdots	& 	& \vdots	\\
                t_1	& t_2	& \dots	& t_{m}	\\
            \end{bmatrix}
$$
3.  $\bm{W}$$t_0=0$ has MGF
    $$
    \varphi(\bm{t})=\exp \left\{ \sum_{i=1}^{m}\frac{1}{2}\left( \sum_{j=i}^{m} t_{j} \right)^2 (t_i-t_{i-1}) \right\}
    $$
    where $t_0=0$$dW_{t}=\infty$.

Brownian motion is a Markov martingale with variation:

1.  $dW_{t}=\infty$$dW_t dW_{t}=dt$
2.  $dW_t dW_{t}=dt$$dW_{t}dt=dt^2=0$
3. $dW_{t}dt=dt^2=0$$X\in  \mathcal{A}$


## Markov Property


::: {.lemma  name="Independence Lemma"}

Suppose $X\in  \mathcal{A}$$Y \perp \mathcal{A}$, $Y \perp \mathcal{A}$$f=g\times h$, then
$$
\mathop{{}\mathbb{E}}_{\mathcal{A}}f(X,Y)=\mathop{{}\mathbb{E}}_{}f(x,Y)|_{x=X}
$$

:::


:::: {.proof}

When $f=g\times h$$g,h$ for some $g,h$$\sigma$, then
$$
\mathop{{}\mathbb{E}}_{\mathcal{A}}f(X,Y)=\int K(X,dy)f(X,y)=\int \mu(dy)f(X,y)=\mathop{{}\mathbb{E}}_{}f(x,Y)|_{x=X}
$$
since product $\sigma$$p(\tau,W_{s},y)$ algebra is generated by measurable rectangles, monotone class theorem completes the proof.

::::

Preceding lemma implies
$$
\begin{aligned}
    \mathop{{}\mathbb{E}}_{s}f(W_{t})&=\mathop{{}\mathbb{E}}_{s}f(W_{t}-W_{s}+W_{s})
    \\ &= 
    \mathop{{}\mathbb{E}}_{}f(W_{t}-W_{s}+x)|_{x=W_{s}}
    \\ &= 
    \frac{1}{\sqrt{2\pi(t-s)}}\int_{\mathbb{R}} f(w+x)\exp \left\{ - \frac{w^2}{2(t-s)} \right\}dw|_{x=W_{s}}
    \\ &\xlongequal{\tau=t-s,y=w+x}
    \frac{1}{\sqrt{2\pi \tau}}\int_{\mathbb{R}} f(y)\exp \left\{ - \frac{w^2}{2\tau} \right\}dw|_{x=W_{s}}
    \\ & \xlongequal{}
    \int_{\mathbb{R}}f(y)p(\tau,W_{s},y)dy
\end{aligned}
$$
where $p(\tau,W_{s},y)$$\mathcal{N}(W_{s},\tau)$ is pdf of $\mathcal{N}(W_{s},\tau)$$W_t$.



## Exponential Martingale

::: {.proposition  name=""}

Suppose $W_t$$\mathbb{F}$ is a Brownian Motion with filtration $\mathbb{F}$$m$, then process
$$
Z_t=\exp \left\{ \sigma W_t - \frac{1}{2} \sigma^2t\right\}
$$
is a martingale.

:::

Define the first passage time to $m$$\sigma \searrow 0$ as
$$
\tau_m=\min \left\{ t\ge 0,W_t=m \right\}
$$
recall the stopped martingale, we have
$$
1=\mathop{{}\mathbb{E}}_{}Z_0=\mathop{{}\mathbb{E}}_{}Z_{t \land \tau_m}=\mathop{{}\mathbb{E}}_{}\exp \left\{ \sigma W_{t \land \tau_m} - \frac{1}{2} \sigma^2(t \land m) \right\}
$$
Taking limit inside expectations:
$$
\lim_{t \to \infty} \exp \left\{ \sigma W_{t \land \tau_m} - \frac{1}{2} \sigma^2(t \land m) \right\}=\bm{1}_{\tau_{m}<\infty}\exp \left\{\sigma m -\frac{1}{2} \sigma^2 \tau_{m}    \right\}
$$
that implies
$$
\mathop{{}\mathbb{E}}_{}\bm{1}_{\tau_{m}<\infty} \exp \left\{ -\frac{1}{2} \sigma^2 \tau_{m} \right\}= \exp \left\{ -\sigma m \right\}
$$
take $\sigma \searrow 0$$\tau_{m}$, we have $\tau_{m}$$a.s.$ is finite $a.s.$$\tau_{m}$.

And the characteristic function of $\tau_{m}$$t=\frac{1}{2}\sigma^2$ is given by taking $t=\frac{1}{2}\sigma^2$$0<m\ge w$:
$$
\mathop{{}\mathbb{E}}_{}\exp \left\{ -t \tau_{m} \right\}=\exp \left\{ - \left| m \right|\sqrt{2 t} \right\}
$$

## Reflection

By the symmetry of Brownian motion, we have
$$
\mathop{{}\mathbb{P}}\left\{ \tau_{m}\le t,W_t\le w \right\}=\mathop{{}\mathbb{P}}\left\{ W_t\ge 2m-w \right\}
$$
when $0<m\ge w$$m=w$. On the other hand:
$$
\mathop{{}\mathbb{P}}\left\{ \tau_{m}\le t,W_t\ge w \right\}=\mathop{{}\mathbb{P}}\left\{ W_t\ge w \right\}
$$
take $m=w$$M_{t}\ge m$ and adding these two:
$$
\mathop{{}\mathbb{P}}\left\{ \tau_{m}\le t \right\}=2\mathop{{}\mathbb{P}}\left\{ W_{t} \ge m \right\}
$$

### Joint Distribution of Brownian Motion and its maximum

Define maximum process:
$$
M_{t}=\max_{0\le s\le t}W_{s}
$$
clearly, $M_{t}\ge m$$\tau_{m}\le t$ iff $\tau_{m}\le t$$\tau_{m}\le t$, thus
$$
\mathop{{}\mathbb{P}}\left\{ M_{t}\ge m,W_{t}\le w \right\}=\mathop{{}\mathbb{P}}\left\{ W_{t}\ge 2m-w \right\}     
$$
from which we have:
$$
f_{M,W}(m,w)=\frac{2(2m-w)}{t \sqrt{2\pi t}}e^{- \frac{(2m-\omega)^2}{2t}}
$$