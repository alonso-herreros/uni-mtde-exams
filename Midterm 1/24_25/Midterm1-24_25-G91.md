## Teoría Moderna de la Detección y Estimación

# Parcial 1: Estimación Analítica

*Curso Académico 2024-2025*  

*Grado en Ingeniería en Tecnologías de Telecomunicación*  
*Grado en Ingeniería de Sonido e Imagen*  

---

## Problema 1

Sea $S$ una variable aleatoria continua con la siguiente distribución:

$$
p_S(s) = \begin{cases}
    2s & 0 ≤ s ≤ 1 \\
    0 & \text{en otro caso}
\end{cases}
$$

Y sabiendo que:

$$
p_{X|S}(x|s) = \begin{cases}
    2sx − s + 1 & 0 ≤ x ≤ 1 \\
    0 & \text{en otro caso}
\end{cases}
$$

### Pregunta 1.a) Obtenga $\hat{S}_{\text{MMSE}}$
Obtenga el estimador de mínimo error cuadrático medio de $S$ a la vista de $X$,
$\hat{S}_{\text{MMSE}}$.

> **Respuesta**
>
> La siguiente fórmula nos ayudará con esta pregunta:
>
> $$
> \begin{aligned}
>     \hat{S}_{\text{MMSE}} &= \mathbb{E}[S|X] \\
>     &= ∫_{(S)} s ⋅ p_{S|X}(s|x) \, ds \\
> \end{aligned}
> $$
>
> Esa distribución no la tenemos, pero la podemos averiguar:
>
> $$
> \begin{aligned}
>     p_{S|X}(s|x) &= \frac{p_{X,S}(x,s)}{p_X(x)} \\
>     &= \frac{p_{X|S}(x|s) \cdot p_S(s)}{∫_{(S)}p_{X|S}(x|s)⋅p_S(s)ds} \\
>     &= \frac{2s(2sx-s+1)}{∫_0^1 2s(2sx-s+1) ds} \\
>     &= \frac{4s^2x - 2s^2 +2s}{∫_0^1 4s^2x - 2s^2 +2s ds} \\
>     &= \frac{2s^2 (2x-1) +2s}{2⋅\frac{1^3}{3} (2x-1) + 2⋅\frac{1^2}{2}} \\
>     &= \frac{2s^2 (2x-1) +2s}{\frac{4}{3}x + \frac{1}{3}}, \quad s, x ∈ [0, 1] \\
> \end{aligned}
> $$
>
> Asumamos que ese resultado es correcto.
>
> $$
> \begin{aligned}
>     \hat{S}_{\text{MMSE}} &= \mathbb{E}[S|X] \\
>     &= ∫_{(S)} s ⋅ \frac{2s^2(2x-1) + 2s}{\frac{4}{3}x + \frac{1}{3}} \, ds \\
>     &= \frac{3}{4x+1} ∫_0^1 2s^3(2x-1) + 2s^2 \, ds \\
>     &= \frac{3}{4x+1} \left(\frac{2}{4} (2x-1) ⋅1^4 + \frac{2}{3} ⋅1^3\right) \\
>     &= \frac{3x - \frac{3}{2} + 2}{4x + 1} \\
>     &= \boxed{\frac{3x + \frac{1}{2}}{4x + 1}, \quad 0 ≤ x ≤ 1} \\
> \end{aligned}
> $$

### Pregunta 1.b)
Obtenga el estimador lineal de menor error cuadrático medio de $S$ a la vista de
$X$ ($\hat{S}_{LMSE}$):

> **Respuesta**
>
> Ahora tenemos la restricción de linearidad
>
> $$
> \hat{S}_{\text{LMSE}} = w_0 + w_1 X \\
> $$
>
> Por suerte, este problema tiene una solución dada por la siguiente fórmula
>
> $$
> \hat{S}_{\text{LMSE}} = \mathbb E\{S\}
>     + \frac{\mathrm{Cov}(S,X)}{\mathrm{Var}\{X\}} (X - \mathbb E\{X\}) \\
> $$
>
> Por lo que tendremos que hallar esos valores
>
> $$
> \begin{aligned}
>     \mathbb E\{S\} &= ∫_{(S)} s p_S(s) ds \\
>     &= ∫_0^1 s ⋅ 2s \,ds \\
>     &= 2 ⋅ \frac{1^3}{3} \\
>     &= \frac{2}{3} \\[2em]
>
>     \mathbb E\{X\} &= ∫_{(X)} x p_X(x) dx \\
>     &= ∫_0^1 x ⋅ \left(\frac{4}{3}x + \frac{1}{3}\right) dx \\
>     &= \frac{4}{9} + \frac{1}{6} \\
>     &= \frac{11}{18} \\[2em]
>
>     \mathrm{Var} \{X\} &= \mathbb E\{X^2\} - \mathbb E^2\{X\} \\
>     &= ∫_{(X)} x^2 p_X(x) dx - \left(\frac{11}{18}\right)^2 \\
>     &= ∫_0^1 x^2⋅\left(\frac{4}{3}x + \frac13\right) dx - \frac{11^2}{18^2} \\
>     &= \frac{4}{3⋅4} + \frac{1}{3⋅3} - \frac{11^2}{18^2} \\
>     &= 0.0710 \\[2em]
>
>     \mathrm{Cov} (X,S) &= \mathbb E\{X⋅S\} - \mathbb E\{X\} \mathbb E\{S\} \\
>     &= ∫_{(X)} ∫_{(S)} xs ⋅ p_{X,S}(x,s)\,ds\,dx - \frac{11⋅2}{18⋅3} \\
>     &= ∫_0^1 ∫_0^1 xs ⋅ 2s(2sx-s+1) \,ds\,dx - \frac{11}{27} \\
>     &= ∫_0^1 ∫_0^1 (4s^3x^2 - 2s^3x +2s^2x) \,ds\,dx - \frac{11}{27} \\
>     &= ∫_0^1 \left(\frac{4}{4}x^2 - \frac{2}{4}x + \frac{2}{3}x\right) dx
>         - \frac{11}{27} \\
>     &= \frac{1}{3} - \frac{2}{8} + \frac{2}{6} - \frac{11}{27} \\
>     &= 9.260 ⋅10^{-3}
> \end{aligned}
> $$
>
> Finally, let's put all of those values into our formula for the estimator
>
> $$
> \begin{aligned}
>     \hat{S}_{\text{LMSE}} &= \mathbb E\{S\}
>         + \frac{\mathrm{Cov}(S,X)}{\mathrm{Var}\{X\}} (X - \mathbb E\{X\}) \\
>     &= \frac23 + \frac{9.260⋅10^{-3}}{0.0710} ⋅\left(X-\frac{11}{18}\right) \\
>     &= \boxed{\frac{3}{23} ⋅X - \frac{27}{46}} \\
>     &= \boxed{0.1304 ⋅X - 0.5870}
> \end{aligned}
> $$

## Problema 2

Una variable aleatoria $X$ sigue una distribución de gamma inversa con
paramétros deterministas $α > 0$ y $β > 0$:

$$
p_X(x) = \frac{β^α}{(α − 1)!}x^{−α−1} \exp\left(−\frac{β}{x}\right), \quad x > 0
$$

### Pregunta 2.a) Obtenga $\hat{β}_{\text{ML}}$
Suponiendo conocido el valor de α, determine el estimador de máxima
verosimilitud de $β$, $\hat{β}_{ML}$, basado en un conjunto de $K$ observaciones
independientes de la variable aleatoria $X$,

$$
\{X^{(k)}\}_{k=1}^K
$$

### Pregunta 2.b) Calcule $\hat{β}_{ML}$ y la verosimilitud dado un conjunto

Si se dispone del siguiente conjunto de observaciones:

$$
\{x^{(k)}\}_{k=1}^4 = \{4, 1, \frac{2}{3}, \frac{4}{5}\}
$$

y asumiendo que $α = 1$, calcule el valor de $\hat{β}_{ML}$. Para ese valor de
$\hat{β}_{ML}$, obtenga el valor de la (máxima) verosimilitud que se obtendría
con el conjunto de observaciones dado. Si lo desea, puede dejar el resultado en
función del número $e$ o $\exp()$.
