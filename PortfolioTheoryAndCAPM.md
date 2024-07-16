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

### Two-fund Theorem

### Portfolio with risk free asset

### One-fund Theorem