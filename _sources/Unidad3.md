---
title: Unidad 3
---
# Unidad 3

## De organizar a encontrar 🌀🔎

En la Unidad 2 aprendiste a *pensar* un problema desde cero (fuerza bruta, recursión, backtracking). Ahora damos un
paso más práctico: ¿cómo encontramos un dato rápido dentro de una colección, y cómo la dejamos **ordenada** para que
esa búsqueda sea aún más rápida?

Vamos a recorrer dos familias de algoritmos: primero **búsqueda** (lineal y binaria), y luego **ordenamiento**
(burbuja, selección, inserción y mezcla) — con un hilo conductor claro: una lista ordenada permite búsquedas mucho
más rápidas, y ordenar bien vale la pena cuando vas a buscar muchas veces.

## Comparativa rápida

| Técnica | Idea central | Complejidad (peor caso) |
|---|---|---|
| Búsqueda lineal | Revisar los elementos uno por uno | O(n) |
| Búsqueda binaria | Descartar la mitad de los candidatos en cada paso (requiere lista ordenada) | O(log n) |
| Ordenamiento burbuja | Intercambiar pares adyacentes fuera de orden, repetidamente | O(n²) |
| Ordenamiento por selección | Buscar el mínimo restante y colocarlo en su posición | O(n²) |
| Ordenamiento por inserción | Insertar cada elemento en su lugar dentro de la parte ya ordenada | O(n²) |
| Ordenamiento por mezcla | Dividir, ordenar recursivamente y mezclar (divide y vencerás) | O(n log n) |

## Cómo se ve esto en código 🔍

::::{grid} 1
:gutter: 3

:::{grid-item}
```{image} _static/unidad3/busqueda/busqueda_binaria.png
:alt: Busqueda binaria descartando la mitad del rango en cada ronda hasta encontrar el objetivo
```
:::

:::{grid-item}
```{image} _static/unidad3/ordenamiento/merge_sort.png
:alt: Merge sort dividiendo la lista hasta listas de tamano 1 y luego mezclandolas de vuelta en orden
```
:::

::::

## Manos a la obra! 💪🐍

En esta unidad vamos a practicar con:

* **Búsqueda**
  * Lineal
  * Binaria
* **Ordenamiento**
  * Burbuja
  * Selección
  * Inserción
  * Mezcla
* **Resolución de problemas** aplicados con estas técnicas
