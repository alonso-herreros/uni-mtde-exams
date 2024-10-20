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

### Pregunta 1.b) Determínese el estimador $\hat{S}_{\text{MAP}}$

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

### Pregunta 2.b) Establezca la expresión de $\hat{A}_{\text{ML}}$

Establezca la expresión del estimador de máxima verosimilitud del parámetro \hat{A}_{\text{ML}}, en
función de los valores de $K$ muestras de $Y$ tomadas independientemente, $\{Y^{(k)}\}_{k=1}^K$

NOTA: Si no ha logrado resolver el apartado (a), utilice como distribución de la variable aleatoria
$Y$, la siguiente expresión:

$$
p_Y(y) = \frac{a}{2} \exp\left(-\frac{ay}{2}\right), y ≥ 0
$$
