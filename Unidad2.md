---
title: Unidad 2
---
# Unidad 2 

## De la fuerza bruta a la elegancia 🧠⚙️

En la Unidad 1 aprendiste a **guardar y organizar** información (listas, pilas, colas). Ahora el foco cambia: ¿cómo *pensamos* para resolver un problema cuando no es obvio por dónde empezar?

Vamos a recorrer ese camino en orden: primero la **fuerza bruta** — probar todo lo posible, sin atajos — y de ahí subimos a formas más inteligentes de explorar un problema: la **recursión** (una función que se llama a sí misma) y el **backtracking**, que construye una solución paso a paso y sabe *retroceder* cuando un camino no sirve.

## Comparativa rápida

| Técnica | Idea central | Ejemplo típico |
|---|---|---|
| Fuerza bruta | Probar **todas** las combinaciones posibles hasta dar con la solución | Adivinar una clave probando cada contraseña |
| Recursión de pila | Cada llamada espera el resultado de la siguiente; se van **apilando** llamadas pendientes | `factorial(n) = n * factorial(n-1)` |
| Recursión de cola | La llamada recursiva **es** el resultado final, sin cuentas pendientes (optimizable) | `factorial_cola(n, acumulador)` |
| Recursión cruzada | Dos o más funciones se llaman **entre sí** de forma recursiva | `es_par(n)` ↔ `es_impar(n)` |
| Backtracking | Construye la solución paso a paso y **poda** las ramas que ya no pueden funcionar | N-Reinas, Sudoku, permutaciones |

## Cómo se ve esto en código 🔍

::::{grid} 1
:gutter: 3

:::{grid-item}
```{image} _static/unidad2/recursion_pila.png
:alt: Traza de la recursion de pila en factorial(4): se apilan las llamadas y luego se resuelven multiplicando
```
:::

:::{grid-item}
```{image} _static/unidad2/backtracking.png
:alt: Arbol de backtracking buscando un subconjunto que sume 5, con ramas podadas
```
:::

::::

## Manos a la obra! 💪🐍

En esta unidad vamos a practicar con:

* **Fuerza bruta**
* **Recursión**
  * De pila
  * De cola
  * Cruzada
* **Backtracking**
* **Resolución de problemas** aplicados con estas técnicas
