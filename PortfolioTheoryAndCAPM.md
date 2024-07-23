# Portfolio Theory

$$
\text{Portfolio A} =
\begin{cases}
w_1A \\
\vdots \\
w_nA \\
\end{cases} \rightarrow B=
\begin{cases}
w_1A (1+r_1)\\
\vdots \\
w_nA (1+r_n) \\
\end{cases} 
$$

Consider the case of portfolio of n-asset where $\sum w_i = 1$, then

$$
\begin{aligned}
    \text{Portfolio B} &= \text{final wealth} = \sum w_i A(1+r_i) \\
    &= A \sum w_i (1+r_i) = A (\sum w_i + \sum w_ir_i) \\
    &= A (1 + \sum w_i r_i)
\end{aligned}
$$

Our portfolio return is then:

$$
\begin{aligned}
    r_p &= \frac{B}{A} - 1 = \frac{B-A}{A} = \frac{\text{final wealth - initial wealth}}{\text{final wealth}} \\
    &= \frac{A (1 + \sum w_i r_i)-A}{A} = \sum w_ir_i
\end{aligned}
$$

In matrix notation, we let $\utilde{w} = \begin{pmatrix} w_1\\ w_2\\ \vdots \\ w_n\end{pmatrix}$, then $1^Tw = 1$

and portfolo rate of return $= w^Tr$,  where $\utilde{r} = \begin{pmatrix} r_1\\r_2\\ \vdots \\ r_n\end{pmatrix}$

$$
\text{Portfolio mean} = E(r_p) = \sum w_i \mu_i = \mu_p  = w^T \mu
$$

$$
\begin{aligned}
    \text{Portfolio variance} &= Var(r_p) = Var(\sum_iw_ir_i) = Cov(\sum_iw_ir_i,\sum_iw_ir_i) \\
    &= \sum_i \sum_j w_iw_j\sigma_{ij} \\
    &= \sum_i w_i^2\sigma_i^2 + \sum_i \sum_{i\ne j}w_iw_j\sigma_{ij} \\
    &= \sum_i w_i^2\sigma_i^2 + 2\sum_i \sum_{i< j}w_iw_j\sigma_{ij} \\
    &=w^TCw
\end{aligned}
$$

where C is the variance-covariance matrix , C = $\begin{pmatrix}
\sigma_{11} & \sigma_{12} &\cdots & \sigma_{1n}\\
\sigma_{21} &\sigma_{22} &\cdots & \sigma_{2n}\\
\vdots & \vdots & &\vdots\\
\sigma_{n1} & \sigma_{n2} &\cdots & \sigma_{nn}
\end{pmatrix} \\$

----

We now consider the portfolio of 2 assets where $\utilde{w} = (\alpha,1-\alpha)^T$

$$
E(r_p) = \mu_p = \alpha \mu_1 + (1-\alpha)\mu_2
$$

$$
\begin{aligned}
Var(r_P) &= \sigma^2_p = \alpha^2 \sigma^2_1 + (1-\alpha)^2\sigma_2^2 + 2(\alpha)(1 - \alpha)\sigma_{1,2} \\
&=  \alpha^2 \sigma^2_1 + (1-\alpha)^2\sigma_2^2 + 2(\alpha)(1 - \alpha)\rho_{1,2} \sigma_1 \sigma_2
\end{aligned}
$$

We want to calculate the Global minimum Variance portfolio (GMVP): portfolio with smallest risk/variance. 

(proof not shown)

$$
\begin{aligned}
\alpha^* &= \frac{\sigma_2(\sigma_2 - \rho_{1,2}\sigma_1)}{\sigma_1^2 + \sigma_2^2 - 2\rho_{1,2}\sigma_1\sigma_2} \\
{\sigma^2_p}^* &= \frac{\sigma_1^2 \sigma_2^2(1 - \rho_{1,2}^2)}{\sigma_1^2 + \sigma_2^2 - 2\rho_{1,2}\sigma_1\sigma_2}
\end{aligned}\\
\mu_p^* = \alpha^*\mu_1 + (1-\alpha^*)\mu_2
$$

We want to find equation of portfolio curve ($\sigma_p$ as x-axis, $\mu_p$ as y-axis). we start from 

$$
\begin{align}
\mu_p &= \alpha \mu_1 + (1-\alpha)\mu_2 \\
\sigma^2_p &= \alpha^2 \sigma^2_1 + (1-\alpha)^2\sigma_2^2 + 2(\alpha)(1 - \alpha)\sigma_{1,2} >0
\end{align}
$$

from (1),

$$
\begin{aligned}
    \mu_p &= \alpha \mu_1 + \mu_2 -\alpha\mu_2 \\
    &\implies \alpha = \frac{\mu_p - \mu_2}{\mu_1 - \mu_2} \quad \text{and } (1-\alpha) = \frac{\mu_1 - \mu_p}{\mu_1 - \mu_2} \\
    \sigma^2_p &= (\frac{\mu_p - \mu_2}{\mu_1 - \mu_2} )^2 \sigma^2_1 + (\frac{\mu_1 - \mu_p}{\mu_1 - \mu_2})^2\sigma_2^2 + 2(\frac{\mu_p - \mu_2}{\mu_1 - \mu_2})(\frac{\mu_1 - \mu_p}{\mu_1 - \mu_2})\sigma_{1,2} \\
    &= A\mu_p^2 + B\mu_p + C \quad (\text{equation of curve}) \\
    &= A(\mu_p + \frac{B}{2A})^2 + C - \frac{B^2}{4A}
\end{aligned}
$$

We can deduce that the min $\sigma^2_p =  C - \frac{B^2}{4A}$ at $\mu_p = -\frac{B}{2A}$ and min $\sigma_p = \sqrt{C - \frac{B^2}{4A}}$

The GMVP = $(\sqrt{C - \frac{B^2}{4A}},-\frac{B}{2A})$ and the asymptote $\implies \sigma_p = \plusmn \sqrt{A}(\mu_p + \frac{B}{2A}) $

Typically to solve for GMVP and return, we 
1) first find $\sigma^2_p$ as a function of $\alpha \implies f(\alpha) = \sigma^2_p$
2) we set $f'(\alpha) =^{set} 0$ to get $\alpha^*$
3) Sub $\alpha^*$ into $\mu_p^*$ and ${\sigma^2_p}^2$
----

## Markowitz's portfolio theory

We shall now extend to n-assets and introduce the Modern Portfolio Theory

2 assumptions:
1) Assume that $\utilde{\mu} = {\begin{pmatrix}  \mu_1 \cdots \mu_n \end{pmatrix}}^T$ is not a scalar multiple of $\utilde{1}$
2) Assume that $\utilde{C}$ is positive definite $\iff \forall x>o, x^TCx >0 \quad \implies w^TCw>0$
   - if Variance = 0, not meaningful


We seek the min $\mu_p$ at a given $\mu$

Recall that $\sigma^2_p = \sum_i \sum_j w_iw_j\sigma_{ij} = \sum_i w_i^2\sigma_i^2 + 2\sum_i \sum_{i< j}w_iw_j\sigma_{ij} = w^TCw$

and lemma $\frac{\partial a^TB}{\partial B} = a$ and $\frac{\partial B^TAB}{\partial B} = 2AB$

Consider, $\frac{\partial}{\partial w_k} = 2w_k\sigma_k + 2 \sum_{j=1,j \ne k } w_j\sigma_{j,k} = 2\sum_k w_k\sigma_{j,k} = 2\begin{pmatrix} \sigma_{k1} \cdots \sigma_{kn} \end{pmatrix} \begin{pmatrix} w_{1} \\  \vdots \\ w_{k} \end{pmatrix}$

Then we have 
$$
\frac{\partial \sigma^2_p}{\partial w_k} =\frac{\partial w^TCw}{\partial w_k} =2\utilde{C}\utilde{w} = \begin{pmatrix} \frac{\partial}{\partial w_1} (\sum_i w_i^2\sigma_i^2 + 2\sum_i \sum_{i< j}w_iw_j\sigma_{ij})\\  \vdots \\ \frac{\partial}{\partial w_n} (\sum_i w_i^2\sigma_i^2 + 2\sum_i \sum_{i< j}w_iw_j\sigma_{ij}) \end{pmatrix}
$$

We use method of langragian multiplier subjected to 2 constants:
- $\sum w_i = 1 \iff 1^Tw = 1$
- $\sum \mu_i w_i = \mu_{fixed} \iff \mu^Tw = \mu_{fixed}$

Let $L = f - \lambda_1g_1 - \lambda_2g_2$ and set $\frac{\partial L}{\partial w_k} = 0$ and this will get give us w*

$$
\begin{aligned}
    L &= \frac{1}{2} \sigma^2_p - \lambda_1(\sum w_i -1) - \lambda_2(\sum\mu_i w_i - \mu_{fixed}) \\
    &= \frac{1}{2} w^TCw - \lambda_1(1^Tw -1) - \lambda_2(\mu^Tw - \mu_{fixed}) \\
    \frac{\partial L}{\partial w_k} &= \sum_j (w_k\sigma_{k,j}) - \lambda_1 - \lambda_2\mu_k \\
    \implies & \frac{\partial L}{\partial \utilde{w}} = \utilde{C}\utilde{w} - \lambda_1 \utilde{1} - \lambda_2 \utilde{\mu} \rightarrow_{\text{set to}} 0 
\end{aligned}
$$

We solve:

$$
\begin{cases}
    \utilde{C}\utilde{w} = \lambda_1 \utilde{1} + \lambda_2 \utilde{\mu} \implies \utilde{w} = \lambda_1 C^{-1}\utilde{1} + \lambda_2 C^{-1}\utilde{\mu} \\
    1^Tw =1\\
    \mu^Tw = \mu_{fixed}
\end{cases}
$$

Sub (1) into (2) and (3)

$$
\begin{aligned}
    &\lambda_11^TC^{-1}1 + \lambda_21^TC^{-1}\mu = 1 \\
    &\lambda_1\mu^TC^{-1}1 + \lambda_2\mu^TC^{-1}\mu = \mu_{fixed} \\
    &\implies 
    \begin{pmatrix}
        1^TC^{-1}1 & 1^TC^{-1}\mu \\ 
        \mu^TC^{-1}1 & \mu^TC^{-1}\mu
    \end{pmatrix}
    \begin{pmatrix}
        \lambda_1 \\\lambda_2
    \end{pmatrix}
    =
    \begin{pmatrix}
        1 \\ \mu_{fixed}
    \end{pmatrix} \\
\end{aligned}
$$

Now, we generalise for $\mu$ instead of just $\mu_{fixed}$

We also denote $\begin{pmatrix}1^TC^{-1}1 & 1^TC^{-1}\mu \\ \mu^TC^{-1}1 & \mu^TC^{-1}\mu\end{pmatrix}$ as  $\begin{pmatrix}a & b \\ b & c\end{pmatrix}$. Given that  C is positive definite, then a>0 and c>0. In fact $ac - b^2 > 0$ (proof not shown)

$$
\begin{aligned}
    \begin{pmatrix}
        \lambda_1 \\\lambda_2
    \end{pmatrix} = \frac{1}{ac-b^2}
    \begin{pmatrix}
        c & -b \\ -b & a
    \end{pmatrix}
    \begin{pmatrix}
        1 \\ \mu
    \end{pmatrix} \\
    \implies \lambda_1 = \frac{c-b\mu}{ac-b^2} \quad \text{and } \lambda_2= \frac{a\mu-b}{ac-b^2}
\end{aligned}
$$

Sub back into (1), we have the weight with min var at any $\mu$, $w^*$

$$
w^* = \frac{c-b\mu}{ac-b^2} C^{-1}\utilde{1} + \frac{a\mu-b}{ac-b^2}C^{-1}\utilde{\mu}
$$

Then we can now get the equation of the min-var frontier

$$
\begin{aligned}
   w^TCw &= w^T(\frac{c-b\mu}{ac-b^2}\utilde{1} + \frac{a\mu-b}{ac-b^2}\utilde{\mu}) \\
   \sigma^2_p &= \frac{c-b\mu}{ac-b^2} + \frac{a\mu-b}{ac-b^2} \mu \because w^T\utilde{1} = 1 , w^T\utilde{\mu} = \mu \\
   &= \frac{a\mu^2 - 2b\mu+c}{ac-b^2} \\
   &= \frac{a(\mu-\frac{b}{a})^2 - \frac{b^2}{a} + c}{ac-b^2} \\
   &= \frac{a}{\Delta}(\mu-\frac{b}{a})^2 + \frac{1}{a}, \text{where } \Delta = ac-b^2
\end{aligned}
$$

From here, we can solve for $\mu_{gmvp} = \frac{b}{a}$ and $\sigma^2_{gmvp} = \frac{1}{a} \implies \sigma_{gmvp} =\sqrt{\frac{1}{a}}$

Then $w_{gmvp} = w^*_g = \frac{c-b(\frac{b}{a})}{ac-b^2} C^{-1}\utilde{1} + \frac{a(\frac{b}{a})-b}{ac-b^2}C^{-1}\utilde{\mu} = \frac{c-b(\frac{b}{a})}{ac-b^2} C^{-1}\utilde{1} + 0 = \frac{1}{a}C^{-1}\utilde{1} = \frac{C^{-1}\utilde{1}}{1^TC^{-1}\utilde{1}}$

and 

$$
\begin{aligned}
    \mu_g &= \frac{b}{a} = \frac{1^TC^{-1}\utilde{\mu}}{1^TC^{-1}\utilde{1}} = \frac{\mu^TC^{-1}\utilde{1}}{1^TC^{-1}\utilde{1}} \\
    \sigma^2_g &= \frac{1}{a} = \frac{1}{1^TC^{-1}\utilde{1}} \\
    w^*_g &= \frac{C^{-1}\utilde{1}}{1^TC^{-1}\utilde{1}} \quad (\text{normalised }C^{-1}\utilde{1})
\end{aligned}
$$

Corollary (proof not shown):

$$
\begin{aligned}
    Cov(r_p,r_q) &= \sum_i \sum_j w_i w_j \sigma_{ij} \\
    &= w_p^T Cw_q = w_q^T Cw_p
\end{aligned}
$$

and 

$$
Cov(r_g,r_q) = \frac{1}{1^TC^{-1}\utilde{1}} = \sigma^2_g 
$$
---

### Two-fund Theorem

States that any 2 distinct portfolio form a spanning set ie $\{\alpha w_1 + (1-\alpha) w_{fund2}: \alpha \in \real \}$

Recall that $w_{\mu}^* = \frac{c-b\mu}{ac-b^2} C^{-1}\utilde{1} + \frac{a\mu-b}{ac-b^2}C^{-1}\utilde{\mu}$ , we now normalise:

$$
\begin{aligned}
    w_{\mu}^* &= \alpha \frac{C^{-1}\utilde{1}}{1^TC^{-1}\utilde{1}} + (1-\alpha) \frac{C^{-1}\utilde{\mu}}{1^TC^{-1}\utilde{\mu}} \quad \text{ where } \alpha = a \frac{c-b\mu}{ac-b^2} \quad \text{and } (1-\alpha) = b\frac{a\mu-b}{ac-b^2}\\
    &= \alpha w_{fund1} + (1-\alpha) w_{fund2} \\
    &= \alpha w_{g} + (1-\alpha) w_{fund2}
\end{aligned}
$$

Verify that $w_{fund2}$ lies on min -variance frontier: 

$$
\begin{aligned}
    \mu_{fund2} &= \mu^T w_{fund2} = \mu^T\frac{C^{-1}\utilde{\mu}}{1^TC^{-1}\utilde{\mu}} = \frac{c}{b}\\
    w_{\mu} \bigg|_{\mu = \frac{c}{b}}& = \frac{a\frac{c}{b}-b}{ac-b^2}C^{-1}\utilde{\mu} = \frac{1}{b}C^{-1}\utilde{\mu} = w_{fund2}
\end{aligned}
$$

The set of min-var portfolio is spanned by 2 min variance portfolio. In fact, any pair of distinct min variance portfolio forms a spanning set.

Corollary: 

1) let $w_1$ and $w_2$ be 2 distinct **efficient** portfolio then any convex sum of $\alpha w_1 + (1-\alpha) w_{2}$ is an **efficient** portfolio. Recall that efficient $\iff \mu_{w_k} \gt \mu_g$ 

- pf: $\mu_{w1}>\mu_{g} \wedge \mu_{w2}>\mu_{g} \implies \alpha w_1 + (1-\alpha) w_{2} \ge \alpha w_g + (1-\alpha) w_{g} = w_g$
  
1) If $b = 1^TC^{-1}\mu \gt 0$ then fund 2 is efficient. ie $\mu_{fund2} - \mu_g = \frac{c}{b} - \frac{b}{a} = \frac{ac-b^2}{ab} \gt 0$. ($a\gt0,c\gt0,ac-b^2\gt0$ - property of semi positive definite matrix) This also implies that $\forall$ portfolio $\alpha w_g + (1-\alpha) w_{fund2}$ is an efficient portfolio
---

### Portfolio with risk free asset

Now we consider the portfolio with a risk free asset ( n risky + 1 risk free) ie hold cash as well.

Rate of return = $r_p = (1 - 1^Tw)r_f + w^Tr$

$\mu_p = (1 - 1^Tw)r_f + w^T\mu$

$\sigma^2_p = Var((1 - 1^Tw)r_f + w^Tr) = w^TCw = \sum_i \sum_j w_iw_j\sigma_{ij}$

Similary we minimise $\sigma^2_p$ with the constraint: $(1 - 1^Tw)r_f + w^T\mu = \mu_{fixed}$. Note that we no longer need the constraint that the sum of the weights in n risky asset = 1 

The target function is set at: $w^TCw/2 = \sigma^2_p/2$

Set $L = \sigma^2_p/2 - \lambda(\mu^Tw + (1 - 1^Tw)r_f - \mu)$. here we already set for a general $\mu_{fixed}$

$$
\begin{aligned}
    \frac{\partial L}{\partial \utilde{w}} &= \utilde{C}\utilde{w} - \lambda \utilde{\mu} + \lambda r_f\utilde{1} = \utilde{C}\utilde{w} - \lambda(\utilde{\mu} - r_f\utilde{1})\rightarrow_{\text{set to}} 0  \\
    \utilde{w} &= \lambda C^{-1}(\mu - r_f1) \rightarrow_{\text{sub into constraint}}
\end{aligned}
$$

$$
\begin{aligned}
    \mu^T(\lambda C^{-1}(\mu - r_f1)) + (1 - 1^T( \lambda C^{-1}(\mu - r_f1)))r_f - \mu &=0 (\text{ the last mu is a scalar} ) \\
    \lambda\mu^TC^{-1}(\mu-r_f1) + (1 - \lambda 1^TC^{-1}\mu + \lambda r_f 1^TC^{-1}1)r_f - \mu &=0\\
    \lambda(\mu^TC^{-1}(\mu-r_f1) - r_f1^TC^{-1}\mu + r_f^2 1^TC^{-1}1)  &= \mu-r_f \\
    \lambda(\mu^TC^{-1}(\mu-r_f1) - r_f1^TC^{-1}(\mu-r_f1)) &= \mu-r_f \\
    \lambda((\mu^TC^{-1} - r_f1^TC^{-1})(\mu-r_f1)) &= \mu-r_f \\
    \lambda((\mu^T - r_f1^T)C^{-1}(\mu-r_f1))&= \mu-r_f \\
    \lambda((\mu - r_f1)^TC^{-1}(\mu-r_f1))&= \mu-r_f \\
    \implies \lambda = \frac{\mu-r_f}{(\mu - r_f1)^TC^{-1}(\mu-r_f1)}\\
    \implies \utilde{w} = \lambda C^{-1}(\mu - r_f1)  = \frac{(\mu-r_f) C^{-1}(\utilde{\mu} - r_f\utilde{1})}{(\mu - r_f1)^TC^{-1}(\mu-r_f1)}
\end{aligned}
$$

Note that $(\mu - r_f1)^TC^{-1}(\mu-r_f1) >0$ and $C^{-1}(\utilde{\mu} - r_f\utilde{1})$ consist of $C^{-1}: n\times n$ and $(\utilde{\mu} - r_f\utilde{1}): n \times 1$

From here, we can get

$$
\begin{aligned}
    \sigma^2_p &= w^TCw = W^TC(\lambda C^{-1}(\mu - r_f1)) \\
    &= \lambda(W^T(\mu - r_f1)) = \lambda((\lambda C^{-1}(\mu - r_f1))^T(\mu - r_f1)) \\
    &= \lambda^2 (\mu^T - r_f1^T)C^{-1}(\mu - r_f1) \\
    & = \frac{(\mu-r_f)^2}{[(\mu - r_f1)^TC^{-1}(\mu-r_f1)]^2}(\mu - r_f1)^TC^{-1}(\mu - r_f1) \\
    &= \frac{(\mu-r_f)^2}{(\mu - r_f1)^TC^{-1}(\mu-r_f1)}  \\
    &\implies \sigma_p = \frac{|\mu-r_f|}{\sqrt{(\mu - r_f1)^TC^{-1}(\mu-r_f1)}} \sim \mu_p \\
    &= \frac{|\mu-r_f|}{\sqrt{\mu^TC^{-1}\mu - 2r_f1^TC^{-1}\mu + r_f^2 1^TC^{-1}1}} \\
    &= \frac{|\mu-r_f|}{\sqrt{c - 2r_fb + r_f^2 a}} 
\end{aligned}
$$

This shows that all min variance portfolio lies on 2 straight rays from the point $(0,r_f)$ We call these lines the min-variance frontier for the n + 1 assets. The upper part of the min-variance forntier is the efficient frontier, it is also known as the **capital market line (CML)**

Any feasible portfolio of the (n+1) lies to the right of the 2 rays. The feasible set lie within the open triangular region enclosed by the 2 frontier lines. 

The feasible of portfolios invested only in the n risky assets will lie within the triangular region. the portfolio here means $\sum_i w_i =1$

---
#### Tangency Portfolio

Consider when $\mu_{gmvp} = \frac{b}{a} \gt r_f$

We can see that the efficient fronteir line is tangential to the min-variance frontier for risky assets.  this point of tangency is called the tangency portfolio. This unique portfolio satisfies the following conditions:
1) Lies on the efficient frontier line
2) Lies on the min-variance efficient frontier for risky assets
3) it invest only in the n risky assets i.e. $\sum_i w_i =1$

We know that any portfolio on efficient frontier line has:

$$
\utilde{w} = \lambda C^{-1}(\mu - r_f1)  = \frac{(\mu-r_f) C^{-1}(\utilde{\mu} - r_f\utilde{1})}{(\mu - r_f1)^TC^{-1}(\mu-r_f1)}
$$

we now set $w_{tan}$ such that $1^TW_{tan} = 1$

$$
1^Tw_{tan} = 1 = \lambda 1^TC^{-1}(\mu - r_f1) \implies \lambda = \frac{1}{1^TC^{-1}(\mu - r_f1)}
$$

the following implies 

$$
\begin{aligned}
    w_{tan} &= \frac{C^{-1}(\mu - r_f1)}{1^TC^{-1}(\mu - r_f1)} \\
    \mu_{tan} &= \mu^Tw_{tan} = \frac{\mu^TC^{-1}(\mu - r_f1)}{1^TC^{-1}(\mu - r_f1)} = \frac{c - r_f b}{b - r_f a} \\
    \sigma^2_{tan} = w_{tan}^T C w_{tan} &= \frac{(\mu - r_f1)^TC^{-1}(\mu - r_f1)}{[1^TC^{-1}(\mu - r_f1)]^2}  = \frac{c - 2r_f b + r_f^2a}{(b - r_f a)^2}
\end{aligned}
$$

From here, we determine the equation of the CML, we have 2 points on the line $(0,r_f)$ and $(\sigma_{tan},\mu_{tan})$.

for any point $(\sigma_p,\mu_p)$,

$$
\text{gradient} = \frac{\mu_{tan} - r_f}{\sigma_{tan}}  = \frac{\mu_p - r_f}{\sigma_p - 0} \implies \mu_p = r_f + \sigma_p (\frac{\mu_{tan} - r_f}{\sigma_{tan}})
$$

rearranging, we have that $\mu_p - r_f =  \frac{\sigma_p}{\sigma_{tan}}(\mu_{tan} - r_f)$ Which we will use later.

#### Sharpe ratio

The sharpe ratio of a portfolio in (n+1) assets is denoted by $SR_P$ :

$$
SR_P = \frac{\mu_p - r_f}{\sigma_p}
$$

The sharpe ratio is a risk-adjusted return in the sense it measures the expected excess return per unit risk. Obvioulsy the portfolios that lie on the CML attain the highest Sharpe ratio.

biggest sharpe ratio $\iff$ biggest $tan(\theta$) $\iff$ biggest $\tan \iff$ lie on CML

The proportion of investors total wealth invested in the tangency portfolio of risky assets increases as one moves towards the point of tangency. 

Investors need only decide how much to invest in a singee fund - the tangency portfolio

---
### One-fund Theorem

In a financial market, with risky asset and risk free asset, an investor will choose to hold only the risk-free asset and tangency portfolio. Investors differ only in the proportion of total wealth allocated to the tangency portfolio. 

CML portfolio  = $\alpha w_{tan} + (1-\alpha) \text{ risk free}$

$\mu_p = \alpha \mu_{tan} + (1-\alpha) r_f$

Investors hold risky assets in same relative proportion as given by the tangency portfolio

# Capital Asset Pricing Model (CAPM)

Market portfilio:  portfolio comprising of all outstanding units of risky aasets. i.e. supplies all risky assets in the market. Suppose there are $u_i$ units of asset i, at price $p_i$ The total market value or Market Capitalization of asset i is given by $u_ip_i$. the market portfilio is thus given by:

$$
w_i = \frac{u_i p_i}{\sum u_i p_i}
$$

We denote $\mu_m$ and $\sigma^2_m$ as the mean and variance of the market portfolio. 

From one fund theorem, we know that all market participants invest only in the tangency portfolio and risk free asset. They hold risky assets in the same relative proportion given by the tangency portfolio. As such, at market equilibrium(demand = supply), the tangency portfolio is the market portfolio.

Recall that from the CML, we have $\mu_p - r_f =  \frac{\sigma_p}{\sigma_{tan}}(\mu_{tan} - r_f) = \frac{\sigma_p}{\sigma_{m}}(\mu_{m} - r_f)$ 
 
The term $(\mu_{p} - r_f)$ is called the risk premium / expected return in excess of risk. 

excess return of portfolio p $\propto$ excess return of market portfolio.\

### Theorem : CAPM for single asset  

let $\mu_i$ be mean of asset i and $\sigma_{im}$ be covariance of asset i with the market. then

$$
\mu_i - r_f = \frac{\sigma_{im}}{\sigma_{m}^2}(\mu_{m} - r_f)
$$

here 

$$
\frac{\sigma_{im}}{\sigma_{m}^2} = \frac{Cov(r_i.r_m)}{Var(r_m)} = \beta_i
$$ 

refer to this as  the **beta** of asset i denoted by $\beta_i$ 

<details>

<summary>Proof</summary>

suppose we have $\alpha$ invested in asset i and $(1-\alpha)$ invested in market portfolio

As $\alpha \in \R$ we we have the points $(\sigma(\alpha),\mu(\alpha))$ where $\mu(\alpha) = \alpha\mu_i + (1-\alpha)\mu_m$ and $\sigma(\alpha) = \sqrt{\alpha^2\sigma_i^2 + (1-\alpha)^2\sigma^2_m + 2\alpha(1-\alpha)\sigma_{im}}$

When we have $\alpha =0$, this is just the market portfolio or the curve tangential to the CML. so the slope of CML follows :

$$
\frac{d\mu}{d\sigma}\bigg|_{\alpha = 0} = \frac{\mu_m - r_f}{\sigma_m}
$$

But

$$
\begin{aligned}
    \frac{d\mu}{d\sigma}&= \frac{d\mu}{d\alpha} \div \frac{d\sigma}{d\alpha} \\
    &= (\mu_i - \mu_m) \times \frac{1}{\alpha \sigma_i^2 - (1-\alpha)\sigma^2_m + (1-2\alpha)\sigma_{im}} \sqrt{\alpha^2\sigma_i^2 + (1-\alpha)^2\sigma^2_m + 2\alpha(1-\alpha)\sigma_{im}}
\end{aligned}
$$

we then sub in for $\alpha = 0$, whcih we then get

$$
\frac{d\mu}{d\sigma} = \frac{\mu_i - \mu_m}{-\sigma^2_m + \sigma_{im}}\sigma_m
$$

Hence, 

$$
\begin{aligned}
    \frac{\mu_i - \mu_m}{-\sigma^2_m + \sigma_{im}}\sigma_m &= \frac{\mu_m - r_f}{\sigma_m} \\
    (\mu_i - \mu_m)\sigma_m &= \frac{\mu_m - r_f}{\sigma_m}(-\sigma^2_m + \sigma_{im})\\
    &= (\mu_m - r_f)(-\sigma_m) + (\mu_m - r_f)\frac{\sigma_{im}}{\sigma_m} \\
    [(\mu_i - \mu_m) &+ (\mu_m - r_f)]\sigma_m = (\mu_m - r_f)\frac{\sigma_{im}}{\sigma_m} \\
    \implies \mu_i - r_f &= \frac{\sigma_{im}}{\sigma_m^2}(\mu_m - r_f) \quad \square
\end{aligned}
$$

Alt:

$$
\begin{aligned}
    \sigma_{im} &= Cov(r_i,r_m) = e_i^TCW_m \quad \text{where }
    e_i^T = 
    \begin{pmatrix}
        0 \\ \vdots 0 \\ 1\\ \vdots \\ 0
    \end{pmatrix}
    \\
    &= e_i^T C \frac{C^{-1}(\mu - r_f1)}{1^TC^{-1}(\mu - r_f1)} = \frac{e_i^T(\mu - r_f1)}{1^TC^{-1}(\mu - r_f1)}\\
    &= \frac{\mu_i - r_f}{1^TC^{-1}(\mu - r_f1)} = \frac{\mu_i - r_f}{b-r_fa} \\
    \implies (RHS) \frac{\sigma_{im}}{\sigma_m^2}(\mu_m - r_f) &= \frac{\mu_i - r_f}{b-r_fa} \times \frac{(b - r_f a)^2}{c - 2r_f b + r_f^2a}\times (\frac{c - r_f b}{b - r_f a} - rf) \\
    &= \mu_i - r_f (LHS) \quad \square
\end{aligned}
$$

</details>

### Theorem: CAPM for n-risky asset portfolio

$$
(\mu_p - r_f) = \beta_p (\mu_m - r_f), \quad \beta_p = \frac{\sigma_{pm}}{\sigma^2_m} \\
$$

<details>

<summary>Proof</summary>

We start from $\mu_i - r_f = \frac{\sigma_{im}}{\sigma_m^2}(\mu_m - r_f)$, and the fact that $\sum_i w_i = 1$ for n risky asset. Hence, $\mu_p - r_f = \sum w_i \mu_i - 1 \times r_f = \sum \mu_i - \sum w_i r_f  = \sum w_i (\mu_i - r_f)$

then, 

$$
\begin{aligned}
    \mu_p - r_f &= \sum w_i  \frac{\sigma_{im}}{\sigma_m^2}(\mu_m - r_f) = \frac{(\mu_m - r_f)}{\sigma_m^2}\sum w_i \sigma_{im} \\
    &\because \sum w_i \sigma_{im} =\sum w_i Cov(r_i,r_m)  = Cov(\sum w_ir_i,r_m) = Cov(r_p,r_m) = \sigma_{pm}\\
    \implies \mu_p - r_f &=\frac{(\mu_m - r_f)}{\sigma_m^2}\sigma_{pm}\\
    &= \frac{\sigma_{pm}}{\sigma_m^2}(\mu_m - r_f) \quad \square
\end{aligned} 
$$

</details>

#### Corollary: if $p \in CML, \beta_p = \frac{\sigma_{pm}}{\sigma^2_m} = \frac{\sigma_p}{\sigma_m}$

Proof: $p\in CML\iff \alpha \ge 0$ thus, 

$$
\sigma_{pm} = Cov(r_p,r_m) = Cov(\alpha r_m + (1-\alpha)r_f,r_m) = \alpha Cov(r_m,r_m) = \alpha \sigma^2_m \implies \frac{\sigma_{pm}}{\sigma^2_m} = \alpha
$$

then we have

$$
\begin{aligned}
    \sigma^2_p = Var(r_p) &= Var(\alpha r_m + (1-\alpha)r_f) = \alpha^2 Var(r_m) = \alpha^2 \sigma^2_m\\
    &\implies \sigma_p = \sqrt{\alpha^2 \sigma^2_m} = \alpha \sigma_m \\
    &\implies \frac{\sigma_p}{\sigma_m} = \alpha
\end{aligned}
$$

Equating the above 2 equations together we get, $\alpha = \frac{\sigma_{pm}}{\sigma^2_m} = \frac{\sigma_p}{\sigma_m} = \beta_p$

Note that:
- $w_m : \beta_m =1$
- $w_g : \beta_g = \frac{\sigma^2_g}{\sigma^2_m}$
- $w_{r_f} = 0 : \beta_{r_f} = 0$

## Portfolio Beta

We define the beta of a security as $\beta_i = \frac{\sigma_{im}}{\sigma_{m}^2}$ and the portfolio beta as $\beta_p =\frac{\sigma_{pm}}{\sigma^2_m}$

$$
\beta_p = \frac{Cov(r_p,r_m)}{\sigma^2_m} = \frac{\sum w_i \sigma_{im}}{\sigma^2_m} = \sum w_i \beta_i = w^T\beta
$$

Above result follow that CAPM holds for any portfolio of risky asset. 

In fact, from the above Corollary, for any efficient portfolio p lying on the CML i.e. $p\in CML\iff \alpha \ge 0$ then 

$$
(\mu_p - r_f) = \frac{\sigma_{pm}}{\sigma^2_m}(\mu_m - r_f)
$$

is equivalent to 

$$
(\mu_p - r_f) = \frac{\sigma_{p}}{\sigma_m}(\mu_m - r_f)
$$

### Security Market Line (SML)

from the CAPM, we have that $\mu_i - r_f = \frac{\sigma_{im}}{\sigma_m^2}(\mu_m - r_f) = \beta_i (\mu_m - r_f) $

By rearranging terms, we have the SML equation:

$$
\mu_i = r_f + (\mu_m - r_f)\beta_i 
$$

Here we obtained a relationship between mean return and the beta for any asset. This is portrayed graphically with a straight line and a slope: $(\mu_m - r_f)$

Within framework of CAPM, the risk premium/excess return of any asset should lie on SML. There is a mispricing if it does not.

We can use SML as a benchmark for evaluating performance and fair value:
- Portfolio is undervalued $\iff$ estimated return > CAPM benchmark
- Portfolio is overvalued $\iff$ estimated return < CAPM benchmark
 

Differenece between estimated return and benchmark return (SML) is also known as alpha

$$
\text{alpha} = (\beta_{SML},\mu_{i}) - (\beta_{SML},\mu_{SML})
$$

Underpriced assets have positive alpha, overpriced alpha has negative alpha. 

### Other important Beta Results

1) $\beta = \frac{1}{\sigma^2} C w_m$

$$
\beta = \frac{1}{\sigma^2} \begin{pmatrix}
    \sigma_{1m} \\ \vdots \\ \sigma_{nm}
\end{pmatrix} =  \frac{1}{\sigma^2}
\begin{pmatrix}
    e_1^T Cw_m \\ \vdots \\ e_n^TCw_m
\end{pmatrix} = \frac{1}{\sigma^2}
\begin{pmatrix}
    e_1^T \\ \vdots \\ e_n^T
\end{pmatrix} C w_m = \frac{1}{\sigma^2}IC w_m
$$

2) $w_m = \frac{C^{-1}\beta}{1^TC^{-1}\beta} = $ normalised $C^{-1}\beta$

from equation 1, we have $w_m = \sigma^2 C^{-1} \beta$ and

$$
1^TC^-1\beta = 1^TC^{-1}\frac{1}{\sigma^2} C w_m = \frac{1}{\sigma^2} \implies w_m = \frac{1}{1^TC^-1\beta}C^{-1}\beta
$$

3) $\beta^Tw_m = \frac{\beta^TC^-1\beta}{1^TC^-1\beta} =1 \iff \beta^TC^-1\beta =  1^TC^-1\beta$

this is because  $\beta^Tw_m = \beta_m = \frac{Cov(r_m,r_m)}{\sigma^2_m} = 1$

## Systematic and Non-systematic risk

From CAPM, $\mu_p  = r_f + \beta_p (\mu_m - r_f)$

then this suggest that 

$$
r_p = r_f + \beta_p(r_m - r_f) + \epsilon_p
$$

for some random variable $\epsilon_p$ which we take as the error term

In fact, $E(\epsilon_p) = 0$ and $Cov(\epsilon_p,r_m) = 0$

<details>

<summary>Proof</summary>

$$
E(\epsilon_p) = E(r_p -r_f - \beta_p(r_m - r_f)) = \mu_p - r_f - \beta_p(\mu_m - r_f) =0 \because \text{CAPM definition}
$$

$$
\begin{aligned}
    Cov(\epsilon_p,r_m) &= Cov(r_p -r_f - \beta_p(r_m - r_f),r_m) \\
    &= Cov(r_p  - \beta_p r_m -r_f + \beta_p r_f,r_m) \\
    &= Cov(r_p  - \beta_p r_m,r_m) \\
    &= Cov(r_p,r_m) - \beta_p Cov(r_m,r_m) \\
    &= \sigma_{pm} - \frac{\sigma_{pm}}{\sigma^2_m} \sigma^2_m = 0
\end{aligned}
$$

</details>

It then follows that $Var(r_p) = \beta^2\sigma^2_m + Var(\epsilon_p)$

$$
\begin{aligned}
    Var(r_p) &= Var(r_f + \beta_p(r_m - r_f) + \epsilon_p) \\
    &=  Var( \beta_p r_m + r_f- \beta_p r_f+ \epsilon_p) \\
    &= Cov(\beta_p r_m + \epsilon_p, \beta_p r_m + \epsilon_p) \\
    &= \beta^2_p Cov(r_m.r_m) + 2\beta_p Cov(r_m,\epsilon_p) + Cov(\epsilon_p,\epsilon_p) \\
    &= \beta^2_p Var(r_m) + Var(\epsilon_p) \\
    &= \beta^2_p \sigma^2_m + Var(\epsilon_p)
\end{aligned}
$$

Hence the total risk of any portfolio is the sum of 2 components : the systematic risk - $\beta^2_p \sigma^2_m$ and the non-systematic/specific risk - $Var(\epsilon_p)$

The systematic risk is the market risk that cannot be diversified away since every asset with a non-zero beta contains this risk
- i.e. given a fixed $\beta_p$, we cannot do other combination of assets to reduce systematic risk

The non-systematic risk is uncorellated with the market, and can be reduced through diversification. 

Portfolios that lie on CML:
- let rate of return on this portfolio p be : $r_p = \alpha r_m + (1-\alpha)r_f$
- then its portfolio varianceis given by $\sigma^2_p = \beta^2_p \sigma^2_m$ - where there is only systematic risk. 
  - recall that if p $\in CML$ then $\beta_p = \frac{\sigma_{pm}}{\sigma^2_m} = \frac{\sigma_p}{\sigma_m} \implies \sigma^2_p = \beta^2_p \sigma^2_m $


Efficient portfolios contain only systematic risk

