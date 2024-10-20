## Modern Theory of Detection and Estimation

# Midterm 1: Analytic Estimation

*Academic year 2023-2024*

*Bachelor in Mobile and Space Communications Engineering*  
*Bachelor in Telematics Engineering*  
*Bachelor in Sound and Image Engineering*  
*Bachelor in Telecommunication Technologies Engineering*  

---

## Problem 1

The random variables X and S are related through the conditional distribution:

$$
p_{X|S}(x|s) = s x^{s-1}, \quad 0 ≤ x ≤ 1, \quad s ≥ 0
$$

### Question 1.a)
Find the ML estimate of $S$ given X, $\hat{S}_{\text{ML}}$

> **Answer** ($✓$)
>
> We'll use the definition of the ML estimator
>
> $$\\
> \begin{aligned}
>     \hat{S}_{\text{ML}} &= \arg\max_{s} p_{X|S}(x|s) \\
>     &= \arg\max_{s} s x^{s-1} \\
>     &= \arg\max_{s} \ln(s x^{s-1}) \\
>     &= \arg\max_{s} \ln(s) + (s-1) \ln(x) \\
> \end{aligned}
> $$
>
> We'll minimize that by taking the partial derivative
>
> $$\\
> \begin{aligned}
>     \frac{∂}{∂s} (\ln(s) + (s-1) \ln(x)) &= 0 \\
>     \frac{1}{s} + \ln(x) &= 0 \\
>     s &= -\frac{1}{\ln(x)} \\
> \end{aligned}
> $$
>
> Plugging that back into the original equation
>
> $$\\
> \boxed{\hat{S}_{\text{ML}} = -\frac{1}{\ln(x)}}
> $$

### Question 1.b)

Find the ML estimate of $S$ given a set $\left\{x^{(k)}, k=0, … , K−1\right\}$ of independent
observations of $X$.

> **Answer**  ($✓$)
>
> Since the observations are independent, we can find the joint *a priori* pdf for the set of
> observations $\{X^{(k)}\}$, instead of only $X$
>
> $$
> \begin{aligned}
>     p_{\{X^{(k)}\}|S}(\{x^{(k)}\}|s) &= ∏_{k=0}^{K-1} p_{X|S}\left(x^{(k)}|s\right) \\
>     &= ∏_{k=0}^{K-1} s \left(x^{(k)}\right)^{s-1} \\
> \end{aligned}
> $$
>
> And then find the ML estimator according to its definition
>
> $$
> \begin{aligned}
>     \hat{S}_{\text{ML}} (\{x^{(k)}\}) &= \arg\max_s p_{\{X^{(k)}\}|S}(\{x^{(k)}\}|s) \\
>     &= \arg\max_s \ln \left(p_{\{X^{(k)}\}|S}(\{x^{(k)}\}|s)\right) \\
>     &= \arg\max_s \ln ∏_{k=0}^{K-1} s \left(x^{(k)}\right)^{s-1} \\
>     &= \arg\max_s ∑_{k=0}^{K-1} \left(\ln s + (s-1) \ln x^{(k)}\right) \\
>     &= \arg\max_s \left(K \ln s + (s-1)∑_{k=0}^{K-1}  \ln x^{(k)}\right)
> \end{aligned}
> $$
>
> We'll take the partial derivative in order to maximize that
>
> $$
> \begin{aligned}
>     \frac{∂}{∂s} \left(K \ln s + (s - 1) ∑_{k=0}^{K-1} \ln x^{(k)}\right) &= 0 \\
>     \frac{K}{s} + ∑_{k=0}^{K-1} \ln x^{(k)} &= 0 \\
>     s &= -\frac{K}{∑_{k=0}^{K-1} \ln x^{(k)}}
> \end{aligned}
> $$
>
> And that's our ML estimator
>
> $$
> \boxed{s = -\frac{K}{∑_{k=0}^{K-1} \ln x^{(k)}}}
> $$

## Problem 2

Consider the estimation of a random variable $S$ from a random variable $X$, where their joint
probability density function is given by

$$
p_{X,S}(x, s) = \begin{cases}
    6s & 0 ≤ s ≤ x, 0 ≤ x ≤ 1 \\
    0 & \text{otherwise}
\end{cases}
$$

### Question 2.a)
Determine the estimator $\hat{S}_{\text{MMSE}}$.

> **Answer**  ($✓$)
>
> That's a question of applying the standard formula for the MMSE estimator
>
> $$
> \begin{aligned}
>     \hat{S}_{\text{MMSE}} &= \arg\min_{\hat{S}} \mathbb E \{(S - \hat{S})^2\} \\
>     &= \arg\min_{\hat{S}} ∫_{(S)} (s-\hat{S})^2 p_{S|X}(s|x) ds \\
> \end{aligned}
> $$
>
> We don't have the expression for the marginal required, but we do have the joint pdf, so we can
> find this marginal by integrating over $X$
>
> $$
> \begin{aligned}
>     p_{S|X}(s|x) &= ∫_{(X)} p_{X,S}(x,s) dx \\
>     &= ∫_0^1 6s dx \\
>     &= 6s, \quad 0 ≤ s ≤ x, 0 ≤ x ≤ 1 \\
> \end{aligned}
> $$
>
> We'll jump straight into the partial differential in order to minimize the MSE
>
> $$
> \begin{aligned}
>     \frac{∂}{∂\hat{S}} ∫_{(S)} (s-\hat{S})^2 p_{S|X}(s|x) ds &= 0 \\
>     ∫_0^x 2(s-\hat{S}) ⋅ (-1) ⋅ 6s ds &= 0 \\
>     ∫_0^x (s^2 - s\hat{S}) ds &= 0 \\
>     \left.\frac{s^3}{3} - \frac{s^2}{2} \hat{S}\right|_{s=0}^x &= 0 \\
>     \frac{x^3}{3} - \frac{x^2}{2} \hat{S} &= 0 \\
>     \hat{S} &= \frac{2}{3}x
> \end{aligned}
> $$
>
> And from here, we get that our MSE estimator is
>
> $$
> \boxed{\hat{S}_{\text{MMSE}} = \frac{2}{3}X}
> $$

### Question 2.b)
Consider the estimation of $S$ based on the observation of $X$, with the objective to minimize the
following cost function:

$$
c(S, \hat{S}) = a^2 (S - \hat{S})^2
$$

Determine the optimal estimator of $S$, $\hat{S}$, which minimizes the expected cost of the
estimator.

> **Answer**  ($✓$)
>
> A Bayesian estimator minimizes the expected cost. Let's do that.
>
> $$
> \begin{aligned}
>     \hat{S} &= \arg\min_{\hat{s}} \mathbb E \{c(S, \hat{S})\} \\
>     \hat{S} &= \arg\min_{\hat{s}} \mathbb E \{a^2 (S - \hat{S})^2\} \\
>     \hat{S} &= \arg\min_{\hat{s}} ∫_{(S)} a^2 (s - \hat{S})^2 p_{S|X}(s|x) ds \\
> \end{aligned}
> $$
>
> Then we take the partial derivative with respect to $\hat{S}$
>
> $$
> \begin{aligned}
>     \frac{∂}{∂\hat{S}} ∫_{(S)} a^2 (s - \hat{S})^2 p_{S|X}(s|x) ds &= 0 \\
>     a^2 ∫_0^x 2(s - \hat{S}) ⋅6s \, ds &= 0 \\
>     ∫_0^x (s^2 - s\hat{S}) ds &= 0 \\
> \end{aligned}
> $$
>
> This has converged with the previous question, so we can reuse the result
>
> $$
> \boxed{\hat{S} = \frac{2}{3}X}
> $$
