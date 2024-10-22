## Teoría Moderna de la Detección y Estimación

# Parcial 1: Estimación Analítica

*Curso Académico 2023-2024*  

*Grado en Ingeniería en Tecnologías de Telecomunicación*  
*Grado en Ingeniería de Sonido e Imagen*  

---

## Problema 1

Se desea estimar la variable aleatoria $S$ a partir de la variable aleatoria $X$, conociendo la
función de densidad de probabilidad conjunta de ambas, dada por:

$$
p_{X,S}(x, s) = \begin{cases}
    2 \exp[-(s + x)] & 0 < s < x, 0 < x < ∞ \\
    0 & \text{en otro caso}
\end{cases}
$$

### Pregunta 1.a) Determínese el estimador $\hat{S}_{\text{MAD}}$

> **Respuesta**
>
> El estimador MAD debe coincidir con la mediana de la distribución de $S$ condicionada a $X$:
>
> $$
> \begin{aligned}
>     ∫_{-∞}^{\hat{S}_{\text{MAD}}} p_{S|X}(s|x) ds &= \frac{1}{2} \\
> \end{aligned}
> $$
>
> Para resolver esta expresión debemos obtener la probabilidad marginal a partir de la conjunta:
>
> $$
> \begin{aligned}
>     p_{S|X}(s|x) &= ∫_{(X)} p_{X,S}(x, s) dx \\
>     &= ∫_0^∞ 2 \exp(-s - x) dx \\
>     &= 2 ∫_0^∞ \exp(-s) \exp(-x) dx \\
>     &= 2 \exp(-s) ∫_0^∞ \exp(-x) dx \\
>     &= 2 \exp(-s) ⋅\left(-\exp(-x)\Big|_{x=0}^{x=∞}\right) \\
>     &= 2 \exp(-s)
> \end{aligned}
> $$
>
> Con esto, podemos reemplazar en la expresión original.
>
> $$
> \begin{aligned}
>     ∫_{-∞}^{\hat{S}_{\text{MAD}}} p_{S|X}(s|x) ds &= \frac{1}{2} \\
>     ∫_0^{\hat{S}_{\text{MAD}}} 2 \exp(-s) ds &= \frac{1}{2} \\
>     - \exp(-s) \Big|_{s=0}^{\hat{S}_{\text{MAD}}} &= \frac{1}{4} \\
>     \exp (-\hat{S}_{\text{MAD}}) - \exp(0) &= -\frac{1}{4} \\
>     -\hat{S}_{\text{MAD}} &= \ln \left(-\frac{1}{4} + 1\right) \\
> \end{aligned}
> $$
>
> Menuda pérdida de tiempo. Probemos con la otra mitad de la integral
>
> $$
> \begin{aligned}
>     ∫_{\hat{S}_{\text{MAD}}}^∞ 2 \exp(-s) ds &= \frac{1}{2} \\
>     ∫_{\hat{S}_{\text{MAD}}}^x \exp(-s) ds &= \frac{1}{4} \\
>     -\exp(-s) \Big|_{s=\hat{S}_{\text{MAD}}}^{x} &= \frac{1}{4} \\
>     \exp(-\hat{S}_{\text{MAD}}) - \exp(-x) &= \frac{1}{4} \\
>     -\hat{S}_{\text{MAD}} &= \ln \left(\frac{1}{4} + \exp(-x)\right)
> \end{aligned}
> $$
>
> Esta podría ser la respuesta, de no ser por el hecho de que no lo es. Probemos otra vez
>
> $$
> \begin{aligned}
>
>     ∫_{-∞}^{\hat{S}_{\text{MAD}}} p_{S|X}(s|x) ds &= ∫_{\hat{S}_{\text{MAD}}}^∞ p_{S|X}(s|x) ds \\
>     ∫_0^{\hat{S}_{\text{MAD}}} 2 \exp(-s) ds &= ∫_{\hat{S}_{\text{MAD}}}^x 2 \exp(-s) ds \\
>     -\exp(-s) \Big|_{s=0}^{\hat{S}_{\text{MAD}}} &= -\exp(-s) \Big|_{s=\hat{S}_{\text{MAD}}}^x \\
>     \exp(-\hat{S}_{\text{MAD}}) - \exp(0) &= \exp(-x) - \exp(-\hat{S}_{\text{MAD}}) \\
>     2 \exp(-\hat{S}_{\text{MAD}}) &= \exp(-x) + 1 \\
>     \hat{S}_{\text{MAD}} &= \ln \left(\frac{\exp(-x) + 1}{2}\right)
> \end{aligned}
> $$
>
> Por fin, hemos llegado a la respuesta correcta:
>
> $$
> \boxed{\hat{S}_{\text{MAD}} = \ln \left(\frac{1 + \exp(-x)}{2}\right)}
> $$

### Pregunta 1.b) Determínese el estimador $\hat{S}_{\text{MAP}}$

> **Respuesta**
>
> Lo haremos usando la definición
>
> $$
> \hat{S}_{\text{MAP}} = \arg \max_s p_{S|X}(s|x)
> $$
>
> Por suerte, ya obtuvimos la expresión de $p_{S|X}(s|x)$ en el apartado anterior. Solo debemos
> maximizarla.
>
> $$
> \begin{aligned}
>     \frac{∂}{∂s} p_{S|X}(s|x) &= 0 \\
>     \frac{∂}{∂s} 2 \exp(-s) &= 0 \\
>     -2 \exp(-s) &= 0 \\
>     \exp(-s) &= 0
> \end{aligned}
> $$
>
> Lo cual no significa que no exista respuesta, sino que no existen máximos ni mínimos. En este
> caso, analizaremos el crecimiento de la función: ya que es decreciente en todo su dominio, el
> máximo se encuentra en el valor más pequeño de $s$. Como $s$ está acotado a $0<s<x$, el valor que
> buscamos es $s=0$.
>
> $$
> \boxed{\hat{S}_{\text{MAP}} = 0}
> $$

## Problema 2

Se conoce la función de densidad de probabilidad de la variable aleatoria $X$ dada por:

$$
p_X(x) = \exp(-x), x ≥ 0
$$

Dicha variable aleatoria sufre una transformación dada por:

$$
Y = aX
$$

Siendo a un valor constante, donde a > 0.

### Pregunta 2.a) Obtenga $p_Y(y)$

Obtenga la función de densidad de probabilidad de la variable aleatoria $Y$, $p_Y (y)$

> **Respuesta**
>
> Primero, obtengamos la expresión de $X$ en función de $Y$
>
> $$
> Y = aX ⟹ X = \frac{Y}{a}
> $$
>
> Ahora podemos usar la siguiente fórmula para la probabilidad bajo un cambio de variable:
>
> $$
> \begin{aligned}
>     p_Y(y) &= p_X(x(y)) \left| \frac{d}{dy} x(y) \right| \\
>     &= p_X\left(\frac{y}{a}\right) \left| \frac{d}{dy} \frac{y}{a} \right| \\
>     &= \exp\left(-\frac{x}{a}\right) \left| \frac{1}{a} \right|, \quad \frac{y}{a} ≥ 0 \\
>     &= \boxed{\frac{\exp\left(-\frac{1}{a}\right)}{a} , \quad y≥0}
> \end{aligned}
> $$

### Pregunta 2.b) Establezca la expresión de $\hat{A}_{\text{ML}}$

Establezca la expresión del estimador de máxima verosimilitud del parámetro \hat{A}_{\text{ML}}, en
función de los valores de $K$ muestras de $Y$ tomadas independientemente, $\{Y^{(k)}\}_{k=1}^K$

NOTA: Si no ha logrado resolver el apartado (a), utilice como distribución de la variable aleatoria
$Y$, la siguiente expresión:

$$
p_Y(y) = \frac{a}{2} \exp\left(-\frac{ay}{2}\right), y ≥ 0
$$
