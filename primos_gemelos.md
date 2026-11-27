# Cuaderno de Investigación: Primos Gemelos

## 1. Definiciones Base

* **Admisibilidad:** Un conjunto $H = \{h_1, \dots, h_k\}$ es admisible si para cada primo $p$ existe al menos un entero $x$ tal que ningún elemento de $x + H$ es divisible por $p$.

* **Primorial ($W$):** Producto de los primeros primos pequeños ($2 \times 3 \times 5 = 30$). Permite filtrar múltiplos pequeños mediante clases residuales.

* **Principio del Palomar (enfoque de Maynard):** Si una función de pesos logra que el promedio de primos dentro de un molde admisible de $k$ posiciones supere $1$, entonces infinitas veces caerán al menos $2$ primos simultáneamente dentro del mismo molde.

## 2. El Molde Séxtuple Módulo 30

* **Molde:** $H = \{0, 2, 6, 8, 18, 20\}$

* **Progresión generadora:** $x = 11 + 30n$ con $n = 0, 1, 2, 3, \dots$

* **Propiedad fundamental:** Todo par de primos gemelos mayor a $(5, 7)$ cae obligatoriamente en una de las tres parejas internas de esta séxtupla:

  * **Pareja A:** $(30n + 11,\; 30n + 13)$

  * **Pareja B:** $(30n + 17,\; 30n + 19)$

  * **Pareja C:** $(30n + 29,\; 30n + 31)$

## 3. Estructura Algebraica Módulo 10 y Ciclo de Terminaciones

* **Grupo Multiplicativo $(\mathbb{Z}/10\mathbb{Z})^\times$:** Al excluir los múltiplos de $2$ y $5$, los residuos coprimos con $10$ forman el conjunto $\{1, 3, 7, 9\}$. Bajo la multiplicación módulo $10$, este conjunto constituye un **grupo cíclico de orden $4$** (cumple clausura, asociatividad, neutro $1$, inversos y generador único).

* **Generadores del grupo ($\varphi(4) = 2$):**
  * **Generador $3$:** $3^1 \equiv 3$, $3^2 \equiv 9$, $3^3 \equiv 7$, $3^4 \equiv 1 \pmod{10}$.
  * **Generador $7$:** $7^1 \equiv 7$, $7^2 \equiv 9$, $7^3 \equiv 3$, $7^4 \equiv 1 \pmod{10}$ (recorre el grupo en sentido inverso).
  * **No generadores:** El $1$ genera solo el subgrupo trivial $\{1\}$ (orden $1$) y el $9 \equiv -1 \pmod{10}$ genera $\{1, 9\}$ (orden $2$).

* **Órbita cíclica de las parejas:** Aunque el conjunto de parejas $\{(1,3), (7,9), (9,1)\}$ no forma un grupo algebraico por sí mismo, sí describe un **ciclo periódico estricto de $3$ estados** en orden creciente dentro de cada bloque de $+30$:
  $$(1,3) \longrightarrow (7,9) \longrightarrow (9,1) \longrightarrow (1,3) \dots$$

## 4. Hallazgos Registrados

* **Tramo $0 \le n \le 9$ ($x \le 281$):** Aparecen $17$ pares de primos gemelos repartidos de forma simétrica: $6$ en la Pareja A, $5$ en la Pareja B y $6$ en la Pareja C.

* **Obstrucción del primo $7$:** Para que una séxtupla completa de $6$ primos sobreviva sin múltiplos de $7$, es obligatorio que $n \equiv 0 \pmod 7$.

* **Séxtuplas completas de primos:** La primera ocurre en $n = 0$ ($x = 11$) y la segunda recién en $n = 553$ ($x = 16601$).

## 5. Próximas Preguntas / Líneas de Exploración

* [ ] Explorar el grupo multiplicativo módulo $30$, $(\mathbb{Z}/30\mathbb{Z})^\times$ (orden $8$), y su relación con los $8$ residuos del molde.

* [ ] Analizar la proporción de primos gemelos en las parejas A, B y C hasta $n = 100$.

* [ ] Estudiar el **problema de la paridad** en cribas y por qué los residuos módulo $30$ no bastan por sí solos para separar primos de semiprimos.

* [ ] Examinar cómo se comportan las quintuplas y cuádruplas de primos dentro de $S(n)$.
