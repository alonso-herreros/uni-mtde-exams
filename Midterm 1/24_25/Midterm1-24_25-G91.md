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
