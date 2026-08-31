---
title: Recursividad
---
# Recursividad

La **recursividad** es una técnica en la que una función se llama a sí misma (o a otra función, que la llama de vuelta) para resolver un problema descomponiéndolo en subproblemas más pequeños de la **misma forma**, hasta llegar a un **caso base** que se resuelve directamente. Piénsalo como muñecas rusas: vas abriendo versiones cada vez más pequeñas hasta llegar a la más simple.

En esta sección vemos las **tres formas** de recursión — de pila, de cola y cruzada — y los **patrones** que te ayudan a diseñar cualquier función recursiva desde cero.

## Comparativa rápida

| Tipo | Idea central | Ejemplo típico |
|---|---|---|
| **De pila** | Cada llamada espera el resultado de la siguiente; queda una operación **pendiente** hasta que la llamada regresa | `factorial(n) = n * factorial(n-1)` |
| **De cola** | La llamada recursiva es lo **último** que hace la función; su resultado **es** el resultado final, sin nada pendiente | `factorial_cola(n, acumulador)` |
| **Cruzada** | Dos (o más) funciones se llaman **entre sí** (auto-invocación indirecta) hasta llegar a un caso base | `es_par(n)` ↔ `es_impar(n)` |

```{note}
Python **no** hace *tail-call optimization*: una recursión de cola sigue creando un marco de pila por llamada, igual que una de pila. La única forma real de ahorrar memoria es convertirla en un bucle `while`.
```

## Los tres patrones para diseñar una recursión

Casi cualquier función recursiva sigue uno de estos tres moldes:

| Patrón | Idea | Ejemplo |
|---|---|---|
| **Índice** | Avanza un puntero (o recorta la entrada) hasta un caso base | `suma_lista(xs, i)` |
| **Divide y vencerás** | Parte el problema en subproblemas independientes, resuelve y combina | Búsqueda binaria |
| **Incluir/Excluir** | En cada posición decides si tomas o no el elemento (backtracking) | Generar subconjuntos |

```{image} _static/unidad2/recursion_pila.png
:alt: Traza de la recursion de pila en factorial(4): se apilan las llamadas y luego se resuelven multiplicando
```

::::{grid} 1
:gutter: 3

:::{grid-item}
```{image} _static/unidad2/recursividad/recursion_cola.png
:alt: Traza de recursion de cola de factorial_cola(4, acumulador=1), el acumulador ya viaja resuelto
```
:::

:::{grid-item}
```{image} _static/unidad2/recursividad/recursion_cruzada.png
:alt: es_par(4) y es_impar se llaman mutuamente hasta llegar al caso base es_par(0) = True
```
:::

::::

## Material de apoyo

```{note}
Teoría, ejemplos y plantillas en blanco 📎 [Introducción a la recursividad (PDF)](_static/unidad2/recursividad/RecursividadenPython.pdf) · [Patrones esenciales (PDF)](_static/unidad2/recursividad/RecursividadPatronesEsenciales.pdf) · [Recursión de cola en profundidad (PDF)](_static/unidad2/recursividad/RecursionDeCola.pdf) · [Plantillas de aula (PDF)](_static/unidad2/recursividad/PlantillasRecursividad_handout.pdf) · [Diagramas de árbol y trazas recursivas (PDF)](_static/unidad2/recursividad/DiagramasArbolTrazaRecursiva.pdf)
```

## Manos a la obra! 💪🐍

El notebook de esta sección desarrolla en código todo lo anterior: factorial y suma de lista (pila vs. cola), la transformación paso a paso de pila a cola, `es_par`/`es_impar` (cruzada), búsqueda binaria, backtracking (Hanoi y subconjuntos), recorridos de árboles, memoización vs. programación dinámica Bottom-Up, y un decorador para visualizar tú mismo el árbol de llamadas de cualquier función recursiva.

1. {doc}`Recursividad_Notebook` — recursión de pila, de cola y cruzada, con ejemplos ejecutables y ejercicios propuestos.
