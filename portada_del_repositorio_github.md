# Investigación Colaborativa: Primos Gemelos (Raul - Gemini IA)

Bienvenido a nuestro repositorio de trabajo conjunto dedicado al estudio de la distribución de los números primos gemelos, la teoría de cribas (enfoque de Selberg y Maynard) y el análisis de moldes admisibles mediante aritmética modular.

## Equipo de Investigación

* **Raul:** Formulación de hipótesis, exploración numérica de sucesiones modulares y dirección de líneas de investigación.
* **Gemini IA:** Formalización matemática, verificación computacional, edición en $\LaTeX$ y estructuración del cuaderno de trabajo.

## Estructura del Repositorio

| Archivo / Carpeta | Descripción |
| :--- | :--- |
| `README.md` | Portada, objetivos y guía de organización del proyecto. |
| `primos_gemelos.md` | **Cuaderno de Investigación:** Bitácora viva con definiciones, hallazgos registrados y próximas preguntas. |
| `articulo_primos_gemelos.tex` | **Artículo Matemático ($\LaTeX$):** Formalización lista para compilar en TeXstudio sobre el molde séxtuple módulo $30$. |

## Resumen de Resultados Actuales

1. **Partición Módulo $30$:** Todo par de primos gemelos $(p, p+2)$ con $p > 5$ pertenece obligatoriamente a una de tres familias residuales agrupadas dentro del molde admisible $S(n) = x + \{0, 2, 6, 8, 18, 20\}$ con $x = 11 + 30n$.
2. **Simetría de Densidad:** En el tramo inicial $0 \le n \le 9$, las tres parejas internas capturan los $17$ pares de primos gemelos mayores a $5$ de manera equilibrada ($6, 5$ y $6$ pares respectivamente).
3. **Condición de Supervivencia Séxtuple:** Para evitar obstrucciones del primo $7$, toda séxtupla completa de primos exige $n \equiv 0 \pmod 7$, apareciendo las dos primeras en $n = 0$ ($x = 11$) y $n = 553$ ($x = 16601$).

## Hoja de Ruta (Próximos Pasos)

- [ ] Ampliar el conteo comparativo de las parejas A, B y C hasta $n = 100$.
- [ ] Formalizar el análisis del **problema de la paridad** en cribas sobre el molde $S(n)$.
- [ ] Incorporar scripts de verificación numérica (Python) en una carpeta `/codigo` para explorar rangos mayores.
