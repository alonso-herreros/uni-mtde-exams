## Teoría Moderna de la Detección y Estimación <!-- omit in toc -->

# Examen Final Ordinario

*Curso Académico 2023-2024*

---

### Tabla de contenidos <!-- omit in toc -->

* [Problema 1 ✓](#problema-1-)
    * [Pregunta 1.a) ✓](#pregunta-1a-)
    * [Pregunta 1.b) ✓](#pregunta-1b-)
    * [Pregunta 1.c) ✓](#pregunta-1c-)
    * [Pregunta 1.d) ✓](#pregunta-1d-)
    * [Pregunta 1.e) ✓](#pregunta-1e-)
    * [Pregunta 1.f) ✓](#pregunta-1f-)
* [Problema 2 ✓](#problema-2-)
* [Problema 3 ✓](#problema-3-)
    * [Pregunta 3.a) ✓](#pregunta-3a-)
    * [Pregunta 3.b) ✓](#pregunta-3b-)
    * [Pregunta 3.c) ✓](#pregunta-3c-)
* [Problema 4](#problema-4)
    * [Pregunta 4.a)](#pregunta-4a)
    * [Pregunta 4.b)](#pregunta-4b)
* [Problema 5](#problema-5)
* [Problema 6](#problema-6)
    * [Pregunta.1](#pregunta1)
    * [Pregunta.2](#pregunta2)

---

## Problema 1 ✓

Sean $X₁$ y $X₂$ dos variables aleatorias independientes. $X₁$ sigue una
distribución exponencial unilateral:

$$
p_{X₁}(x₁) = \frac{1}{θ} \exp\left( −\frac{x₁}{θ} \right) \quad 0 ≤ x₁ < ∞
$$

donde $θ > 0$ es un parámetro determinista de valor desconocido, mientras que
$X₂$ sigue una distribución uniforme en el intervalo $[0, θ]$, representando
$θ$ el mismo parámetro en ambas distribuciones.

Para estimar el valor de θ, se propone el siguiente estimador:

$$
\hat{θ} = aX₁ + bX₂
$$

donde $a$ y $b$ son dos constantes.

### Pregunta 1.a) ✓
Determine la esperanza matemática (valor medio) y varianza de la variable
aleatoria $X₁$.

> **Respuesta** (✓)
>
> $$
> \begin{aligned}
>     \mathbb{E} \{X₁\} &= ∫_{(X₁)} x p_{X₁}(x) dx \\
>     &= ∫_0^∞ x \frac{1}{θ} \exp\left(-\frac{x}{θ}\right) dx \\
>     &= \frac{1}{θ} ∫_0^∞ x \exp\left(-\frac{x}{θ}\right) dx \\
>     & \,\left\downarrow\; \left[\begin{aligned}
>         & u = x;   && dv = \exp\left(-\tfrac{x}{θ}\right) dx \\
>         & du = dx; && v = - θ \exp\left(-\tfrac{x}{θ}\right)
>     \end{aligned}\right] \right. \\
>     &= \frac{1}{θ} \left(- x θ \exp\left(-\tfrac{x}{θ}\right)\Big|_{x=0}^∞
>         - ∫_0^∞ - θ \exp\left(-\tfrac{x}{θ}\right) dx \right) \\
>     &= - x \exp\left(-\tfrac{x}{θ}\right)\Bigg|_{x=0}^∞
>         + ∫_0^∞ \exp\left(-\tfrac{x}{θ}\right) dx \\
>     &= - (\tfrac{∞}{e^∞} - 0⋅1)
>         - θ \exp\left(-\frac{x}{θ}\right)\Bigg|_{x=0}^∞ \\
>     &= 0 - θ ⋅ (0 - 1) \\
>     &\boxed{= θ}
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
>     \mathrm{Var} \{X₁\} &= \mathbb{E} \{X₁²\} - \mathbb{E}² \{X₁\} \\
>     &= ∫_0^∞ x² p_{X₁}(x) dx - θ² \\
>     &= ∫_0^∞ x² \frac{1}{θ} \exp\left(-\frac{x}{θ}\right) dx - θ² \\
>     &= \frac{1}{θ} ∫_0^∞ x² \exp\left(-\frac{x}{θ}\right) dx - θ² \\
>     & \,\left\downarrow\; \left[\begin{aligned}
>             & u = x²;       && dv = \exp\left(-\tfrac{x}{θ}\right) dx \\
>             & du = 2x dx; && v = - θ \exp\left(-\tfrac{x}{θ}\right)
>         \end{aligned}\right] \right. \\
>     &= \frac1θ \left(-x² θ \exp\left(-\tfrac{x}{θ}\right)\Big|_{x=0}^∞
>         - ∫_0^∞ - θ \exp\left(-\tfrac{x}{θ}\right) 2x dx \right) - θ² \\
>     &= - x² \exp\left(-\tfrac{x}{θ}\right)\Bigg|_{x=0}^∞
>         + 2∫_0^∞ x\exp\left(-\tfrac{x}{θ}\right) dx - θ² \\
>     & \,\left\downarrow\; \left[\begin{aligned}\textstyle
>             & \frac{1}{θ}∫_0^∞ x\exp\left(-\tfrac{x}{θ}\right) dx = θ \\
>             & ∫_0^∞ x\exp\left(-\tfrac{x}{θ}\right) dx = θ²
>         \end{aligned}\right] \right. \\
>     &= - (\tfrac{∞²}{e^∞} - 0⋅1) + 2θ² - θ² \\
>     & \boxed{= θ²}
> \end{aligned}
> $$
>
> En resumen: $\boxed{\mathbb{E}\{X₁\} = θ;\; \mathrm{Var} \{X₁\} = θ²}$

### Pregunta 1.b) ✓
Determine la esperanza matemática (valor medio) y varianza de la variable
aleatoria $X₂$.

> **Respuesta** (✓)
>
> $$
> X₂ ∼ U[0,θ] ⟹ \mathbb{E} \{X₂\} = \frac{θ-0}{2} = \boxed{\frac{θ}{2}}
> $$
>
> $$
> \begin{aligned}
>     \mathrm{Var} \{X₂\} &= \mathbb{E} \{X₂²\} - \mathbb{E}² \{X₂\} \\
>     &= ∫_{(X₂)} x² p_{X₂} (x) dx - \left(\frac{θ}{2}\right) \\
>     &= ∫_0^θ x² \frac{1}{θ} dx - \frac{θ²}{4} \\
>     &= \frac{1}{θ} \frac{x³}{3} \Bigg|_{x=0}^{θ} - \frac{θ²}{4} \\
>     &= \frac{θ²}{3} - \frac{θ²}{4} \\
>     & \boxed{= \frac{θ²}{12}}
> \end{aligned}
> $$
>
> En resumen: $\boxed{\mathbb{E}\{X₂\} = \frac{θ}{2};\; \mathrm{Var} \{X₂\} =
> \frac{θ²}{12}}$

### Pregunta 1.c) ✓
¿Es el estimador $\hat{θ}$ insesgado? Justifique su respuesta.

> **Respuesta** (✓)
>
> $$
> \def\E#1{\mathbb{E} \left\{#1\right\}}
> \begin{aligned}
>     \mathrm{Sesgo}(\hat{θ}) &= \E{θ - \hat{θ}} \\
>     &= \E{θ} - \E{\hat{θ}} \\
>     &= θ - \E{aX₁ + bX₂} \\
>     &= θ - a\E{X₁} + b\E{X₂} \\
>     &= θ - aθ - b\frac{θ}{2} \\
>     &= \left(1 - a - \frac{b}{2}\right) θ
> \end{aligned}
> $$
>
> El estimador $\hat{θ}$ está sesgado a menos que $a$ y $b$ cumplan la ecuación
> $a+\frac{b}{2} = 1$.

### Pregunta 1.d) ✓
Calcule la varianza del estimador $\hat{θ}$.

> **Respuesta** (✓)
>
> $$
> \def\E#1{\mathbb{E} \left\{#1\right\}}
> \def\Var#1{\mathrm{Var} \left\{#1\right\}}
> \def\Cov#1{\mathrm{Cov} \left\{#1\right\}}
>
> \begin{aligned}
>     \Var{\hat{θ}} &=&& \E{\hat{θ}²} - \E{\hat{θ}}² \\
>     &=&& \E{(aX₁ + bX₂)²} - \E{aX₁ + bX₂}² \\
>     &=&& \E{a²X₁² + 2abX₁X₂ + b²X₂²} - \left(a\E{X₁} + b\E{X₂}\right)² \\
>     &=&& a²\E{X₁²} + 2ab\E{X₁X₂} + b²\E{X₂²} - (aθ + b\tfrac{θ}{2})² \\
>     &=&& a²(2θ²) + 2ab(\E{X₁}\E{X₂} + \cancel{\Cov{X₁, X₂})} \\
>     &&& + b² ·\left(\frac{θ²}{3}\right)
>         - \left(a²θ² + abθ² + b²\frac{θ²}{4}\right) \\
>     &=&& 2a²θ² + \cancel{2ab θ ⋅ \frac{θ}{2}} + 0 + \frac{b²θ²}{3}
>         - a²θ² - \cancel{abθ²} - \frac{b²θ²}{4} \\
>     &=&& \boxed{\left(a² + \frac{b²}{12}\right) θ²}
> \end{aligned}
> $$

### Pregunta 1.e) ✓
Obtenga el valor de la constante $b$, en función de $a$, que hace que el
estimador $\hat{θ}$ sea insesgado. Reescriba la expresión del estimador
$\hat{θ}$ para que dependa sólo de la constante $a$.

> **Respuesta** (✓)
>
> Para que el estimador $\hat{θ}$ sea insesgado se debe cumplir la siguiente
> condicion:
>
> $$
> \begin{aligned}
>     \mathrm{Sesgo}(\hat{θ}) &= 0 \\
>     \left(1 - a - \frac{b}{2}\right) θ &= 0 \\
>     a + \frac{b}{2} &= 1 \\
>     \boxed{b = 2(1-a)}
> \end{aligned}
> $$
>
> Con esta expresion de $b$ podemos reescribir $\hat{θ}$:
>
> $$
> \boxed{\hat{θ} = aX₁ + 2(1-a) X₂}
> $$

### Pregunta 1.f) ✓
Determine el valor de $a$, tal que el estimador obtenido en el apartado anterior
tenga la menor varianza posible. ¿Cuál sería, por tanto, la expresión del
estimador $\hat{θ}$ insesgado de mínima varianza?

> **Respuesta** (✓)
>
> Sustituyendo $b$ en la varianza del estimador, tenemos la siguiente expresión:
>
> $$
> \begin{aligned}
>     \mathrm{Var} \{\hat{θ}\} &= \left(a² + \frac{(2(1-a))²}{12}\right) θ² \\
>     &= \left(\frac{3a² + \left(1-2a+a²\right)}{3}\right) θ² \\
>     &= \frac{θ²}{3} \left(4a² - 2a + 1\right) \\
> \end{aligned}
> $$
>
> Para minimizar, igualaremos la derivada con respecto a $a$ a $0$:
>
> $$
> \begin{aligned}
>     \frac{d}{da} \mathrm{Var} \{\hat{θ}\} &= 0 \\
>     \frac{d}{da} \frac{θ²}{3} \left(4a² - 2a + 1\right) &= 0 \\
>     \frac{d}{da} (4a² - 2a + 1) &= 0 \\
>     8a - 2 &= 0 \\
>     \boxed{a = \frac{1}{4}} \\
> \end{aligned}
> $$
>
> Sustituyendo en la expresión de $\hat{θ}$, obtenemos
>
> $$
> \begin{aligned}
>     \hat{θ}^* &= \frac{1}{4} X₁ + 2(1-\frac{1}{4}) X₂ \\
>     &= \boxed{\frac{1}{4}X₁ + \frac{3}{2}X₂}
> \end{aligned}
> $$

## Problema 2 ✓

Un sistema de vigilancia se encarga de detectar intrusos en un edificio. Se
considera el siguiente par de hipótesis:

* $H = 0$: no hay intruso
* $H = 1$: hay un intruso presente

El sistema envía un mensaje de alarma si se acepta la hipótesis $H = 1$. Suponga
que después de procesar los datos, se obtiene $P(1|x) = 0.05$. Asumiendo que el
coste de no detectar un intruso cuando sí lo hay es 10 veces el coste de decidir
que hay intruso cuando no es cierto, ¿debería el sistema enviar un mensaje de
alarma (es decir, aceptar la hipótesis $H = 1$)? Justifique su respuesta.

Nota: para la resolución del problema, considere que el coste de acierto
asociado a cada hipótesis es nulo.

> **Respuesta** (✓)
>
> $$
> P(1|x) = 0.05 ⟹ P(0|x) = 0.95 \\
> $$
>
> Coloquemos todos los valores en el detector bayesiano:
>
> $$
> \def\decgl#1#2{\enspace\overset{#1}{\underset{#2}{\gtrless}}\enspace}
>
> \begin{aligned}
>     \frac{P_{H|X}(1|x)}{P_{H|X}(0|x)} &\decgl{D₁}{D₀} \frac{c₁₀-c₀₀}{c₀₁-c₁₁} \\
>     \frac{0.05}{0.95} &\decgl{D₁}{D₀} \frac{c₁₀-0}{10c₁₀-0} \\
>     0.053 &\decgl{D₁}{D₀} 0.1 \\
> \end{aligned}
> $$
>
> El sistema debería aceptar la hipótesis $H=0$, según el detector bayesiano.
> Es decir, **no se deberia enviar un mensaje de alarma**

## Problema 3 ✓

Sabiendo que $N$ es una variable aleatoria cuya función de densidad de
probabilidad es una gaussiana de media 0 y varianza 1:

p_N(n) = G(n|0,1)

Considere el par de hipótesis:

$$
\begin{aligned}
    H = 0&: &&X = \sqrt{2}N \\
    H = 1&: &&X = 1 + N
\end{aligned}
$$

### Pregunta 3.a) ✓
Determine $p_{X|H}(x|0)$ y $p_{X|H}(x|1)$. Represente, en la misma gráfica,
ambas verosimilitudes.

> **Respuesta** (✓)
>
> Para $H=0$:
>
> $$
> X = \sqrt{2}N ⟹ \begin{cases}
>     m_X = \sqrt{2}m_N = 0\\
>     v_X = (\sqrt{2})²v_N = 2
> \end{cases}
> $$
>
> Para $H=1$:
>
> $$
> X = 1 + N ⟹ \begin{cases}
>     m_X = 1 + m_N = 1 \\
>     v_X = v_N = 1
> \end{cases}
> $$
>
> $$
> \boxed{p_{X|H}(x|0) = G(0,2)} \\
> \boxed{p_{X|H}(x|1) = G(1,1)}
> $$

### Pregunta 3.b) ✓
Obtenga el clasificador ML basado en $X$.

> **Respuesta** (✓)
>
> $$
> \def\decgl#1#2{\enspace\overset{#1}{\underset{#2}{\gtrless}}\enspace}
>
> \begin{aligned}
>     p_{X|H}(x|1) &\decgl{D₁}{D₀} p_{X|H}(x|0) \\
>     G(1,1) &\decgl{D₁}{D₀} G(0,2) \\
>     \frac{1}{\sqrt{2π⋅1}} \exp\left(-\frac{(x-1)²}{2⋅1}\right)
>         &\decgl{D₁}{D₀} \frac{1}{\sqrt{2π⋅2}} \exp\left(-\frac{x²}{2⋅2}\right) \\
>     \exp\left(-\frac{(x-1)²}{2} + \frac{x²}{4}\right)
>         &\decgl{D₁}{D₀} \frac{1}{\sqrt{2}} \\
>     \exp\left(\frac{2(x²-2x+1) - x²}{4}\right) &\decgl{D₀}{D₁} \sqrt{2} \\
>     x² - 4x + 2 &\decgl{D₀}{D₁} 4 \ln\sqrt{2} \\
>     x² - 4x + 2 - 4\ln\sqrt{2} &\decgl{D₀}{D₁} 0 \\
> \end{aligned}
> $$
>
> Podemos encontrar las fronteras de decisión resolviendo la ecuación de segundo
> grado:
>
> $$
> \begin{aligned}
>     x² - 4x + 2 - 4\ln\sqrt{2} &= 0 \\
>     x &= \frac{-4 \pm \sqrt{16 - 4(2 - 4\ln\sqrt{2})}}{2} \\
>     x &\in \{x_{b1}, x_{b2}\}, \text{ where } \begin{cases}
>             x_{b1} = 0.160 \\
>             x_{b2} = 3.840 \\
>         \end{cases}
> \end{aligned}
> $$
>
> Observando el valor en $x=0$ podemos deducir a qué decision corresponde cada
> región:
>
> $$
> 2 - 4\ln\sqrt{2} = 0.63 > 0 \text{, so } x = 0 ⟹ D=0
> $$
>
> $$
> \boxed{ϕ_{ML} = \begin{cases}
>     D=0 & \text{ if } x < 0.160 \text{ or } 3.840 < x \\
>     D=1 & \text{ if } 0.160 < x < 3.840
> \end{cases}}
> $$

### Pregunta 3.c) ✓
Calcule la probabilidad de falsa alarma del clasificador ML. Exprese esta
probabilidad utilizando la función:

$$
F(x) = ∫_{-∞}^x \frac{1}{\sqrt{2π}} \exp\left(-\frac{t²}{2}\right) dt
$$

> **Respuesta** (✓)
>
> $$
> \begin{aligned}
>     P_{FA} &= P_{D|H}(1|0) \\
>     &= ∫_{Ω₁} p_{X|H} (x|0) dx \\
>     &= ∫_{x_{b1}}^{x_{b2}} \frac{1}{\sqrt{4π}}
>         \exp\left(-\frac{x²}{4}\right) dx \\
>     &\left\downarrow\left[\begin{aligned}
>             t=\tfrac{x}{\sqrt{2}} &⟹ dt = \tfrac{1}{\sqrt{2}}dx;\; x=\sqrt{2}t \\
>             x=x_{b1} &⟹ t=\tfrac{x_{b1}}{\sqrt{2}} \\
>             x=x_{b2} &⟹ t=\tfrac{x_{b2}}{\sqrt{2}} \\
>         \end{aligned}\right]\right.\\
>     &= ∫_{\tfrac{x_{b1}}{\sqrt{2}}}^{\tfrac{x_{b2}}{\sqrt{2}}}
>         \frac{1}{\sqrt{2π}} \exp\left(-\frac{t²}{2}\right) dt \\
>     &= ∫_{-∞}^{\tfrac{x_{b2}}{\sqrt{2}}}
>         \frac{1}{\sqrt{2π}} \exp\left(-\frac{t²}{2}\right) dt
>         - ∫_{-∞}^{\tfrac{x_{b1}}{\sqrt{2}}}
>         \frac{1}{\sqrt{2π}} \exp\left(-\frac{t²}{2}\right) dt \\
>     &= F\left(\frac{x_{b2}}{\sqrt{2}}\right)
>         - F\left(\frac{x_{b1}}{\sqrt{2}}\right) \\
>     &\boxed{= F(2.715) - F(0.113)}
> \end{aligned}
> $$

## Problema 4

Suponga que se dispone del siguiente conjunto de datos de entramiento en el que
se incluyen muestras de la clase positiva ($+$) y muestras de la clase negativa
($−$), así como una muestra de test ($△$).

![alt](fig/F-2023_24-ES-4.1.png)

Todas las muestras se proyectan en un espacio vectorial de 2 características
($X₁$ y $X₂$). Suponiendo que se utiliza el algoritmo de clasificación $k$-NN
ponderado, responda a las siguientes preguntas:

### Pregunta 4.a) ✓
¿Cuál sería la clase asignada para la muestra de test si $k = 1$? Razone su
respuesta.

> **Respuesta** (✓)
>
> Visualmente podemos determinar que la muestra del conjunto de entrenamiento
> más cercana a la muestra de test es una muestra de la clase negativa, por lo
> que esta sería la clase asignada a la muestra de test.

### Pregunta 4.b)
Para este conjunto de datos de entrenamiento, ¿recomendaría utilizar $k = 11$?
Razone su respuesta.

## Problema 5

Razone si la siguiente afirmación es cierta o falsa:

> *“Para el regresor Lasso, si el parámetro de regularización es cero, la función
> de pérdida que se minimiza para obtener los coeficientes es la suma de los
> cuadrados de los errores entre los valores reales de las etiquetas y los
> valores predichos”*.

En caso de ser falsa, haga la(s) correccione(s) necesaria(s) para que la
afirmación sea cierta.

## Problema 6
Responda brevemente a las siguientes preguntas:

### Pregunta.1
¿Es el filtro de Wiener un filtro lineal? Justifique su respuesta.

### Pregunta.2
¿Qué es un filtro adaptativo? Indique un ejemplo de tipo de algoritmo que se usa
en filtros adaptativos para encontrar los coeficientes del mismo.
