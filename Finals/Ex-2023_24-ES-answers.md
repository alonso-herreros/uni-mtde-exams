## Teoría Moderna de la Detección y Estimación <!-- omit in toc -->

# Examen Final Ordinario

*Curso Académico 2023-2024*

---

### Tabla de contenidos <!-- omit in toc -->

* [Problema 1](#problema-1)
    * [Pregunta 1.a)](#pregunta-1a)
    * [Pregunta 1.b)](#pregunta-1b)
    * [Pregunta 1.c)](#pregunta-1c)
    * [Pregunta 1.d)](#pregunta-1d)
    * [Pregunta 1.e)](#pregunta-1e)
* [Problema 2](#problema-2)
    * [Pregunta 2.a)](#pregunta-2a)
    * [Pregunta 2.b)](#pregunta-2b)
    * [Pregunta 2.c)](#pregunta-2c)
* [Problema 3](#problema-3)
    * [Pregunta 3.a)](#pregunta-3a)
    * [Pregunta 3.b)](#pregunta-3b)
* [Problema 4](#problema-4)
* [Problema 5](#problema-5)
    * [Pregunta 5.a)](#pregunta-5a)
    * [Pregunta 5.b)](#pregunta-5b)
* [Problema 6](#problema-6)

---

## Problema 1

Se realiza un test de habilidades matemáticas entre los estudiantes
universitarios de España matriculados en un Grado de Ingeniería. Suponga que la
puntuación $X$ que obtiene un estudiante en la prueba de “estadística y
probabilidad” es un número en el intervalo $[0, 1]$, mientras que la puntuación
$Y$ que obtiene en la prueba de “funciones y gráficas” también es un número en el
intervalo $[0, 1]$.

Asuma que las puntuaciones $X$ e $Y$ se distribuyen conforme a la siguiente
función de densidad probabilidad conjunta:

$$
p_{X,Y} (x, y) = \begin{cases}
    12(1 − x) y(1 − y) & 0 ≤ x ≤ 1,\; 0 ≤ y ≤ 1 \\
    0                    & \text{ en otro caso}
\end{cases}
$$

### Pregunta 1.a)
Establezca las expresiones de las funciones de densidad de probabilidad
marginales: $p_X(x)$ y $p_Y(y)$.

### Pregunta 1.b)
Obtenga el estimador MMSE de $X$ dado $Y$, $\hat{X}_{MMSE}(Y)$.

### Pregunta 1.c)
Determine el estimador MAD de $X$ dado $Y$, $\hat{X}_{MAD}(Y)$.

### Pregunta 1.d)
Calcule el MSE de los estimadores obtenidos en los apartados (b) y (c). ¿Cuál
de los dos estimadores tiene menor MSE? Justifique su respuesta.

### Pregunta 1.e)
Si se seleccionase un estudiante universitario al azar, ¿cuál sería el valor
predicho de su puntuación en la prueba de “estadística y probabilidad” que
tiene menor MSE? Razone su respuesta.

## Problema 2

Las variables aleatorias $X$ y $S$ están relacionadas a través de la siguiente
función de verosimilitud:

$$
p_{X|S}(x|s) = ln(s)s^{−x},\; x ≥ 0, s > 1
$$

y la distribución a priori:

$$
p_S(s) = \frac{1}{s²},\; s > 1
$$

### Pregunta 2.a)
Determine el estimador ML de $S$ a la vista de $X$, $\hat{S}_{ML}(X)$.

### Pregunta 2.b)
Determine el estimador ML de S a la vista de un conjunto $\mathcal{C} =
\{x^{(k)}\}_{k=0}^{K−1}$ de K realizaciones independientes de X.

### Pregunta 2.c)
Determine el estimador MAP de $S$ a la vista de $X$, $\hat{S}_{MAP}(X)$.

## Problema 3

Considere un problema de decisión binaria con hipótesis equiprobables definido
mediante las siguientes funciones de verosimilitud:

$$
p_{X₁,X₂|H}(x₁, x₂|H = 0) = \begin{cases}
    18, & 0 < x₁ < \frac{1}{3} , 0 < x₂ < \frac{1}{3} − x₁ \\
    0, & \text{ resto}
\end{cases}
$$

$$
p_{X₁,X₂|H}(x₁, x₂|H = 1) = \begin{cases}
    6(1 − x₁ − x₂), & 0 < x₁ < 1, 0 < x₂ < 1 − x₁ \\
    0, & \text{ resto}
\end{cases}
$$

y política de costes donde acertar no conlleva penalización alguna y $c₀₁ =
4c₁₀$.

### Pregunta 3.a)
Determine el decisor de mínimo coste medio dada la observación.

### Pregunta 3.b)
¿Cuánto deberían valer las probabilidades *a priori* de cada hipótesis para que
el decisor de coste medio mínimo, dada la observación, no incurra en falsas
alarmas?

## Problema 4

Describa brevemente en qué consiste la validación cruzada e indique para qué se puede emplear.

## Problema 5

Considere el problema de clasificación definido por el conjunto de
entrenamiento que se muestra en la tabla a continuación.

| x     | Clase |
| ----- | ----- |
| -0,45 | -1    |
| -0,03 | -1    |
| -0,09 | 1     |
| 0,23  | 1     |
| 0,38  | -1    |
| 0,92  | 1     |
| 1,19  | 1     |
| 1,28  | 1     |
| 1,33  | 1     |

### Pregunta 5.a)

Dibuje la frontera de clasificación que se obtendría con un árbol de decisión
de 3 nodos hoja.

### Pregunta 5.b)

Calcule la probabilidad de falsa alarma del clasificador del apartado anterior
para el conjunto de test de la tabla siguiente.

| x     | Clase |
| ----- | ----- |
| -0,15 | -1    |
| 0,31  | -1    |
| 1,22  | 1     |

## Problema 6

Describa cómo puede resolverse un problema de predicción de valores de una
señal utilizando un filtro lineal. Dibuje un esquema del filtro indicando
claramente las señales involucradas.
