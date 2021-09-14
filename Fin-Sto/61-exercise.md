## Exercise


::: {.exercise  name=""}

:::


::: {.solution}

$W_{u_2}-W_{u_1}$ is independent of $\mathcal{F}_{u_1} \supset \mathcal{F}_{t}$, thus independent of $\mathcal{F}_{t}$.

:::


::: {.exercise  name=""}

Show that $W^2_{t}-t$ is a martingale.

:::

::: {.solution}

$$
\begin{aligned}
    \mathop{{}\mathbb{E}}_{s}W_t^2-t&=\mathop{{}\mathbb{E}}_{s}\left[ (W_{t}-W_{s})^2+2W_{t}W_{s}-W_{s}^2 \right]-t
    \\ &= \mathop{{}\mathbb{E}}_{} \left( W_{t}-W_{s} \right)^2+2W_{s}\mathop{{}\mathbb{E}}_{s}W_{t}-W_{s}^2-t
    \\ &=  W_{s}^2-s
\end{aligned}
$$

:::


::: {.exercise  name=""}


:::


::: {.solution}

MGF of $X-\mu$ is $\varphi(t)=\exp \left\{ \frac{1}{2} t^2\sigma^2 \right\}$. The kurtosis is given by $\varphi^{(4)}(0)$:
$$
\varphi^{(4)}(t)=\left( 6 \sigma^{6}t^2+\sigma^{8}t^{4}+3\sigma^{4} \right)\exp \left\{ \frac{1}{2} \sigma^2 t^2 \right\} 
$$
thus $\mathop{{}\mathbb{E}}_{}\left( X-\mu \right)^{4}=3 \sigma^{4}$.


:::



::: {.exercise  name=""}

Show that:

1. $dW_t=\infty$
2. $\left( dW_{t} \right)^{3}=0$

:::


::: {.solution}

1.  Note that
    $$
    \sum_{}^{} \left( W_{t_{i+1}}-W_{t_i} \right)^2\le \max \left| W_{t_{i+1}}-W_{t_i} \right| \sum_{}^{} \left| W_{t_i+1}-W_{t_i} \right|
    $$
    As $\Pi \to 0$, $T\le 0\cdot \sum_{}^{}\left| W_{t_i+1}-W_{t_i} \right|$, that force $dW_{t}=\infty$.


2.  Similarly, note
    $$
    \sum_{}^{} \left| W_{t_{i+1}}-W_{t_i} \right|^3\le \max \left| W_{t_{i+1}}-W_{t_i} \right| \sum_{}^{} \left( W_{t_i+1}-W_{t_i} \right)^2 \to  0
    $$

:::


::: {.exercise  name="BSM formula"}

Suppose a call option with $\sigma$ volatility, $S_0$ price underlying have strike $K$, the risk-free rate is $r$. Then the value of such option can be determined by $e^{-rT}\mathop{{}\mathbb{E}}_{}(S_T-K)^{+}$ if we assume
$$
S_{t}=S_0 \exp \left\{ \left( r-\frac{1}{2}\sigma^2 \right)t+\sigma W_{t} \right\}
$$

:::


::: {.solution}

Let $S_{T}=K$, note
$$
W_{T}=\frac{1}{\sigma} \left[ \ln \frac{K}{S_0}-\left( r-\frac{1}{2}\sigma^2 \right)T \right]= \frac{-d_{-}}{\sqrt{T}}
$$
thus
$$
\begin{aligned}
    \mathop{{}\mathbb{E}}_{} (S_{T}-K)^{+} &=
    \int_{\frac{-d_{-}}{\sqrt{T}}}^{\infty}  \left( S_0 \exp \left\{ \left( r-\frac{1}{2}\sigma^2 \right)T+\sigma x \right\}-K \right) \frac{e^{-\frac{x^2}{2T}}}{\sqrt{2\pi T}}dx
    \\ &\xlongequal{dy=\frac{dx}{\sqrt{T}}}
    \int_{-d_{-}}^{\infty}  \left( S_0 \exp \left\{ \left( r-\frac{1}{2}\sigma^2 \right)T+\sigma \sqrt{T}y \right\}-K \right) \frac{e^{-\frac{y^2}{2}}}{\sqrt{2\pi }}dy
    \\ &= 
    S_0 \exp \left\{ \left( r-\frac{1}{2}\sigma^2 \right)T \right\}
    \int_{-d_{-}}^{\infty}   \frac{e^{-\frac{y^2}{2}+\sigma \sqrt{T}y}}{\sqrt{2\pi }}dy-\int_{-d_{-}}^{\infty} K f(y)dy 
    \\ &= 
    S_0 \exp \left\{ rT \right\}
    \int_{-d_{-}}^{\infty}   \frac{e^{-\frac{y^2}{2}+\sigma \sqrt{T}y-\frac{1}{2}\sigma^2T}}{\sqrt{2\pi }}dy-\int_{-d_{-}}^{\infty} K f(y)dy 
    \\ & \xlongequal{z=y-\sigma\sqrt{T}} S_0 e^{rT} \int_{-d_{+}} f(z)dz-\int_{-d_{-}}^{\infty} K f(y)dy 
    \\ &= 
    S_0 e^{rT} N(d_{+})-KN(d_{-})
\end{aligned}
$$

:::



::: {.exercise  name="Transition probability of Geometry Brownian Motion"}



:::


::: {.solution}

1.  Apply independence lemma again.
    $$
    \begin{aligned}
        \mathop{{}\mathbb{E}}_{s}f(X_{t})&=\mathop{{}\mathbb{E}}_{s}f(X_{t}-X_{s}+X_{s})
        \\ &= 
        \mathop{{}\mathbb{E}}_{s}f(W_{t}-W_{s}+\mu(t-s)+W_{s}+\mu s)
        \\ &= 
        \mathop{{}\mathbb{E}}_{}f(W_{t}-W_{s}+\mu(t-s)+x)|_{x=X_{s}}
        \\ &= 
        \int_{\mathbb{R}}f(y)p(\tau,X_{s},y)dy
    \end{aligned}
    $$
    where $p$ is pdf of $\mathcal{N}(X_{s}+\mu(t-s),t-s)$.

2.  Note that $S_{t}=S_0\exp \sigma X_{t}$ where $X_{t}=W_{t}+\frac{\mu}{\sigma}$, then
    $$
    \begin{aligned}
        \mathop{{}\mathbb{E}}_{s}f(S_{t}) &= \int_{\mathbb{R}} f(S_0 \exp \sigma y)p(\tau,X_{s},y)dy
        \\ & \xlongequal{S_0 \exp \sigma y=z}
        \int_{0}^{\infty} f(z)p(t-s,S_{s},z)dz
    \end{aligned}
    $$

:::


::: {.exercise  name="First passage distribution for drift Brownian motion"}



:::



::: {.solution}

1.  Clearly as $Z_{t}=\exp \left\{ \sigma W_{t}-\frac{1}{2}\sigma^2t \right\}$
2.  $Z_{t \land \tau_{m}}$ is also martingale and thus
    $$
    1=\mathop{{}\mathbb{E}}_{}Z_0=\mathop{{}\mathbb{E}}_{}Z_{t \land \tau_m}=\mathop{{}\mathbb{E}}_{}\exp \left\{ \sigma X_{t \land \tau_{m}}-\left( \sigma\mu+\frac{1}{2}\sigma^2 \right)(t \land \tau_{m}) \right\}
    $$
3.  Taking limit inside expectations:
    $$
    \lim_{t \to \infty}\exp \left\{ \sigma X_{t \land \tau_{m}}-\left( \sigma\mu+\frac{1}{2}\sigma^2 \right)(t \land \tau_{m}) \right\}=\bm{1}_{\tau_{m}<\infty}\exp \left\{\sigma m -\left( \frac{1}{2} \sigma^2+\sigma \mu \right) \tau_{m}    \right\}
    $$
    that implies
    $$
    \mathop{{}\mathbb{E}}_{}\bm{1}_{\tau_{m}<\infty} \exp \left\{ -\left( \frac{1}{2} \sigma^2 +\sigma \mu\right) \tau_{m} \right\}= \exp \left\{ -\sigma m \right\}
    $$
    take $\sigma \searrow 0$, we have $\tau_{m}$ is finite $a.s.$. Then take $t=\frac{1}{2}\sigma^2+\sigma\mu$,
    $$
    \mathop{{}\mathbb{E}}_{}\exp \left\{ -t \tau_{m} \right\}=\exp \left\{m \mu -  m \sqrt{2 t+\mu^2} \right\}
    $$

4.  $\mathop{{}\mathbb{E}}_{}\tau_{m}=\varphi'(0)=\frac{m}{\mu}<0$.

:::


::: {.exercise  name="Binomial model with nonzero interest rate"}


:::


::: {.solution}

1.	Directly algebra yields: 
    $$
    \begin{aligned}
        \varphi_{n}(u)&=\mathop{{}\mathbb{E}}_{}\exp \left\{ u \frac{M_{nt,n}}{\sqrt{n}} \right\}= \prod_{i=1}^{nt} \mathop{{}\mathbb{E}}_{}\exp \left\{ u \frac{X_{i,n}}{\sqrt{n}} \right\}
        \\ &=
        \prod_{i=1} ^{nt} \left[ \exp \left\{ \frac{u}{\sqrt{n}} \right\} \widetilde{p}_{n}+\exp \left\{ -\frac{u}{\sqrt{n}} \right\}\widetilde{q}_{n} \right]
        \\ &= 
         \left[ \exp \left\{ \frac{u}{\sqrt{n}} \right\} \widetilde{p}_{n}+\exp \left\{ -\frac{u}{\sqrt{n}} \right\}\widetilde{q}_{n} \right] ^{nt}
    \end{aligned}
    $$
    

2.	As $n\to \infty$:
    $$
    \lim_{n \to \infty} \varphi_{n}(u)=\exp \left\{ \frac{1}{2} t u \left(\frac{2 r}{\sigma }-\sigma +u\right) \right\}
    $$
    which is MGF of $\mathcal{N}\left( t(\frac{r}{\sigma}+\frac{\sigma}{2}),t \right)$. Thus $\frac{\sigma}{\sqrt{n}}M_{nt,n}$ converge to $\mathcal{N}\left( t(r-\frac{\sigma^2}{2}),\sigma^2t \right)$


:::







<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>







