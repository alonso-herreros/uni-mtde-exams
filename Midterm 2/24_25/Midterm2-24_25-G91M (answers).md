## Teoría Moderna de la Detección y Estimación <!-- omit in toc -->

# Parcial 2: Decisión Analítica

*Curso Académico 2024-2025*  

*Grado en Ingeniería de Sonido e Imagen*  
*Grado en Ingeniería en Tecnologías de Telecomunicación*  

---

### Table of contents

---

## Problema 1

En un sistema de reconocimiento de voz, se utiliza un detector de palabras clave
para activar comandos específicos en dispositivos electrónicos. El sistema
necesita diferenciar entre dos situaciones:

* $H = 0$: solo hay ruido ambiental, sin presencia de la palabra clave.
* $H = 1$: la palabra clave está presente en el audio, junto con el ruido de fondo.

La amplitud de la señal procesada, $X$, se modela como una variable aleatoria
continua. Dependiendo de la presencia o ausencia de la palabra clave, la
amplitud sigue una función de densidad de probabilidad diferente:

Bajo la hipótesis $H = 0$ (solo hay ruido ambiental):

$$
p_{X|H}(x|0) = \frac{1}{2} \exp(−|x + 1|)
$$

Bajo la hipótesis $H = 1$ (presencia de la palabra clave):

$$
p_{X|H}(x|1) = 2 \exp(−2x) x ≥ 0
$$

### Pregunta 1.a
Obtenga el decisor de Neyman-Pearson dado por $P_{FA} ≤ 0.1$.

### Pregunta 1.b
Determine la probabilidad de detección del decisor de Neyman-Pearson.

## Problema 2

Considérese un examen tipo test donde cada pregunta tiene 3 posibles opciones y
solo una es correcta. En cada pregunta, cada alumno puede marcar tantas opciones
como desee. La política de puntuación de estas preguntas es la siguiente: Marcar
la respuesta correcta suma 1 punto. Cada respuesta incorrecta resta medio punto.
Para seguir una estrategia óptima de marcado de opciones vamos a traducir el
problema a un escenario de decisión analítica. Como cada pregunta tiene tres
opciones y solo una es correcta, consideramos 3 hipótesis: $H = 1$, $H = 2$ y $H
= 3$, donde $H = h$ quiere decir que $h$ es la opción correcta. Como se pueden
marcar tantas opciones como se quiera, existen 7 posibles decisiones (no marcar
ninguna opción equivale a marcarlas todas): $D = 1$, $D = 2$, $D = 3$, $D = 1,
2$, $D = 1, 3$, $D = 2, 3$ y $D = 1, 2, 3$ ($D = i, j$ quiere decir que se
marcan las opciones $i$ y $j$). En primer lugar adoptaremos una política de
costes tal que si $M$ es la nota que se obtiene en cada pregunta y $c_{d,h}$ es
el coste de decidir $D = d$ cuando la opción correcta es $H = h$, la nota de
cada pregunta del examen se calcule mediante:

$$
m_{d,h} = 1 − c_{d,h}
$$

Por ejemplo, si hacemos que el coste de acertar cuando únicamente se marca la
opción correcta sea 0, $c_{h,h} = 0$, la nota que se obtiene si la decisión
equivale a marcar únicamente la respuesta correcta $D = h$ sería 1 punto:

$$
m_{h,h} = 1 − c_{h,h} = 1 − 0 = 1
$$

Análogamente, el coste de marcar todas las opciones debería ser $c_{(1,2,3),h} =
1$. Esto es porque al marcar todas las opciones, se suma un punto por marcar la
opción correcta y se resta medio punto por cada una de las incorrectas,
resultando en una nota de cero puntos:

m_{(1,2,3),h} = 1 − c_{(1,2,3),h} = 1 − 1 = 0

### Pregunta 2.a
Complete la tabla que define la política de costes necesaria para calcular la nota de cada
pregunta en función de las opciones marcadas por el alumno.

|               | $H = 1$ | $H = 2$ | $H = 3$ |
| :-----------: | :-----: | :-----: | :-----: |
|    $D = 1$    |    0    |         |         |
|    $D = 2$    |         |    0    |         |
|    $D = 3$    |         |         |    0    |
|  $D = 1, 2$   |         |         |         |
|  $D = 1, 3$   |         |         |         |
|  $D = 2, 3$   |         |         |         |
| $D = 1, 2, 3$ |    1    |    1    |    1    |

### Pregunta 2.b

Un estudiante lee el enunciado de una pregunta y estima que las probabilidades a
posteriori de que cada una de las dos primeras opciones sea la correcta son:
$P_{H|X}(H = 1|x) = 0.5$ y $P_{H|X}(H = 2|x) = 0.3$. ¿Cuál será la opción que
marque el estudiante?

### Pregunta 2.c

En otra pregunta el estudiante tiene claro que la opción $H = 3$ no es correcta
y que la opción $H = 1$ es más probable que la opción $H = 2$, por lo que duda
entre marcar solo la primera opción (decidir $D = 1$) o marcar las opciones 1 y
2 (decidir $D = 1, 2$). ¿Para qué valores de p = P_{H|X}(H = 1|x) el estudiante
debería marcar las opciones 1 y 2 en lugar de solamente la opción 1?
