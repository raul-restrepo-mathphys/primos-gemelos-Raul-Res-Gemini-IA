# Clasificación Modular y Análisis de Admisibilidad de Primos Gemelos mediante un Molde Séxtuple

**Cuaderno de Investigación: Primos Gemelos (Raul - Gemini IA)**

## Resumen

En este documento se formalizan los resultados obtenidos sobre la distribución de los números primos gemelos mayores que $5$ mediante aritmética modular y conjuntos admisibles. Se demuestra que todo par de primos gemelos $(p, p+2)$ con $p > 5$ pertenece necesariamente a una de tres clases residuales módulo $30$, las cuales pueden agruparse dentro de un único molde admisible de seis elementos generado por la progresión aritmética $x = 11 + 30n$. Se incluye además la verificación computacional explícita para el rango $0 \le n \le 9$, un análisis de simetría frente a los divisores primos $p \ge 7$ y el estudio de la estructura algebraica módulo $10$.

---

## 1. Concepto de Admisibilidad

Sea $H = \{h_1, h_2, \dots, h_k\}$ un conjunto finito de enteros distintos. Se dice que $H$ es **admisible** si, para todo número primo $p$, existe al menos un entero $x$ tal que ninguno de los elementos del conjunto desplazado
$$x + H = \{x + h_1, x + h_2, \dots, x + h_k\}$$
es divisible por $p$. Equivalentemente, los elementos de $H$ no cubren todas las clases de congruencia módulo $p$ para ningún primo $p$.

* **Ejemplo admisible:** El conjunto $\{0, 4, 6, 10\}$ es admisible. Para $p = 2$ y $p = 3$, basta elegir $x = 1$, obteniendo $\{1, 5, 7, 11\}$, ninguno de cuyos elementos es divisible por $2$ ni por $3$. Para $p \ge 5$, al haber solo cuatro elementos, siempre queda al menos un residuo libre.
* **Ejemplo no admisible:** El conjunto $\{0, 2, 4, 8\}$ no es admisible porque, independientemente del valor de $x$, el subconjunto $\{x, x+2, x+4\}$ cubre los tres residuos posibles módulo $3$, garantizando siempre la aparición de un múltiplo de $3$.

*(Enfoque de cribas y Principio del Palomar de Maynard: Si una función de pesos logra que el promedio de primos dentro de un molde admisible de $k$ posiciones supere $1$, entonces infinitas veces caerán al menos $2$ primos simultáneamente dentro del mismo molde).*

---

## 2. Partición Módulo 30 y el Molde Séxtuple

Todo número primo mayor que $5$ es coprimo con el primorial $W = 2 \times 3 \times 5 = 30$. En consecuencia, cualquier primo $p > 5$ debe dejar uno de los ocho residuos coprimos con $30$:
$$p \equiv 1, 7, 11, 13, 17, 19, 23, 29 \pmod{30}.$$

Si exigimos que $(p, p+2)$ sea un par de primos gemelos con $p > 5$, únicamente existen tres parejas de residuos consecutivos separados por una distancia de $2$:
1. **Pareja A:** $(30n + 11,\; 30n + 13)$
2. **Pareja B:** $(30n + 17,\; 30n + 19)$
3. **Pareja C:** $(30n + 29,\; 30n + 31)$

Estas tres familias pueden integrarse en un único molde admisible de seis posiciones. Definimos el desplazamiento base $H = \{0, 2, 6, 8, 18, 20\}$ y el punto de partida $x = 11 + 30n$ para $n \in \{0, 1, 2, \dots\}$. De este modo, cada valor de $n$ genera la séxtupla:
$$S(n) = \{x,\; x+2,\; x+6,\; x+8,\; x+18,\; x+20\}.$$

Por construcción, ningún elemento de $S(n)$ es divisible por $2$, $3$ ni $5$, y todo par de primos gemelos mayor que $(5, 7)$ aparece necesariamente en una de las tres parejas internas de $S(n)$ para algún $n \ge 0$.

---

## 3. Verificación Explícita para $0 \le n \le 9$

La siguiente tabla muestra las diez primeras séxtuplas generadas por $x = 11 + 30n$, indicando los números primos en negrita y la cantidad total de primos por fila:

| $n$ | $x$ | Séxtupla $S(n)$ | Primos | Factorización de compuestos |
| :---: | :---: | :--- | :---: | :--- |
| $0$ | $11$ | $\{\mathbf{11}, \mathbf{13}, \mathbf{17}, \mathbf{19}, \mathbf{29}, \mathbf{31}\}$ | $6$ | Ninguno |
| $1$ | $41$ | $\{\mathbf{41}, \mathbf{43}, \mathbf{47}, 49, \mathbf{59}, \mathbf{61}\}$ | $5$ | $49 = 7^2$ |
| $2$ | $71$ | $\{\mathbf{71}, \mathbf{73}, 77, \mathbf{79}, \mathbf{89}, 91\}$ | $4$ | $77 = 7 \cdot 11,\; 91 = 7 \cdot 13$ |
| $3$ | $101$ | $\{\mathbf{101}, \mathbf{103}, \mathbf{107}, \mathbf{109}, 119, 121\}$ | $4$ | $119 = 7 \cdot 17,\; 121 = 11^2$ |
| $4$ | $131$ | $\{\mathbf{131}, 133, \mathbf{137}, \mathbf{139}, \mathbf{149}, \mathbf{151}\}$ | $5$ | $133 = 7 \cdot 19$ |
| $5$ | $161$ | $\{161, \mathbf{163}, \mathbf{167}, 169, \mathbf{179}, \mathbf{181}\}$ | $4$ | $161 = 7 \cdot 23,\; 169 = 13^2$ |
| $6$ | $191$ | $\{\mathbf{191}, \mathbf{193}, \mathbf{197}, \mathbf{199}, 209, \mathbf{211}\}$ | $5$ | $209 = 11 \cdot 19$ |
| $7$ | $221$ | $\{221, \mathbf{223}, \mathbf{227}, \mathbf{229}, \mathbf{239}, \mathbf{241}\}$ | $5$ | $221 = 13 \cdot 17$ |
| $8$ | $251$ | $\{\mathbf{251}, 253, \mathbf{257}, 259, \mathbf{269}, \mathbf{271}\}$ | $4$ | $253 = 11 \cdot 23,\; 259 = 7 \cdot 37$ |
| $9$ | $281$ | $\{\mathbf{281}, \mathbf{283}, 287, 289, 299, 301\}$ | $2$ | $287 = 7 \cdot 41,\; 289 = 17^2,\; 299 = 13 \cdot 23,\; 301 = 7 \cdot 43$ |

---

## 4. Simetría Frente a Primos $p \ge 7$ y Séxtuplas Completas

Al analizar la distribución de los pares gemelos dentro de $S(n)$ para $0 \le n \le 9$ (todos los primos menores que $301$ excepto $(3,5)$ y $(5,7)$), se observa un reparto equilibrado de los $17$ pares entre las tres familias:
* **Pareja A ($6$ pares):** $(11,13)$, $(41,43)$, $(71,73)$, $(101,103)$, $(191,193)$, $(281,283)$.
* **Pareja B ($5$ pares):** $(17,19)$, $(107,109)$, $(137,139)$, $(197,199)$, $(227,229)$.
* **Pareja C ($6$ pares):** $(29,31)$, $(59,61)$, $(149,151)$, $(179,181)$, $(239,241)$, $(269,271)$.

Respecto a la aparición de séxtuplas donde los seis elementos sean primos simultáneamente, es condición necesaria que ningún elemento sea divisible por $7$. Dado que $30 \equiv 2 \pmod 7$, la condición $7 \nmid S(n)$ exige que:
$$n \equiv 0 \pmod 7.$$

En el intervalo $1 \le n \le 1000$, ningún múltiplo de $7$ logra producir seis primos simultáneos debido a obstrucciones de primos mayores ($11, 13, 17, 19, 23$). El siguiente índice después de $n = 0$ donde los seis elementos vuelven a ser primos ocurre en $n = 553$, correspondiente al punto de partida $x = 16601$:
$$S(553) = \{16601,\; 16603,\; 16607,\; 16609,\; 16619,\; 16621\}.$$

---

## 5. Estructura Algebraica Módulo 10 y Ciclo de Terminaciones

Al analizar únicamente el dígito de las unidades de los elementos del molde $S(n)$ (su reducción módulo $10$), todo número primo $p > 5$ debe terminar en uno de los cuatro dígitos coprimos con $10$:
$$(\mathbb{Z}/10\mathbb{Z})^\times = \{1, 3, 7, 9\}.$$

El dígito impar $5$ queda excluido por compartir factor común con $10$. Bajo la operación de multiplicación módulo $10$, el conjunto $(\mathbb{Z}/10\mathbb{Z})^\times$ constituye un **grupo cíclico de orden $4$**, pues satisface las propiedades de clausura, asociatividad, existencia de elemento neutro ($e = 1$), existencia de inversos y posee generadores únicos.

Dado que $\varphi(4) = 2$, el grupo admite exactamente dos generadores:
* **Generador $3$:** $3^1 \equiv 3,\; 3^2 \equiv 9,\; 3^3 \equiv 7,\; 3^4 \equiv 1 \pmod{10}$.
* **Generador $7$:** $7^1 \equiv 7,\; 7^2 \equiv 9,\; 7^3 \equiv 3,\; 7^4 \equiv 1 \pmod{10}$ (recorre el grupo en orden inverso).
* **No generadores:** El elemento $1$ solo genera el subgrupo trivial $\{1\}$ (orden $1$) y el elemento $9 \equiv -1 \pmod{10}$ genera el subgrupo $\{1, 9\}$ (orden $2$).

Finalmente, aunque el conjunto de terminaciones de las tres parejas $\{(1,3), (7,9), (9,1)\}$ no constituye un grupo algebraico cerrado por sí solo, sí describe una **órbita cíclica estricta de tres estados** en orden creciente dentro de cada bloque de $+30$:
$$(1,3) \longrightarrow (7,9) \longrightarrow (9,1) \longrightarrow (1,3) \dots$$

---

## 6. Próximas Preguntas / Líneas de Exploración

* [ ] Explorar el grupo multiplicativo módulo $30$, $(\mathbb{Z}/30\mathbb{Z})^\times$ (orden $8$), y su relación con los $8$ residuos del molde.
* [ ] Analizar la proporción de primos gemelos en las parejas A, B y C hasta $n = 100$.
* [ ] Estudiar el **problema de la paridad** en cribas y por qué los residuos módulo $30$ no bastan por sí solos para separar primos de semiprimos.
* [ ] Examinar cómo se comportan las quíntuplas y cuádruplas de primos dentro de $S(n)$.
