---
title: Ordenamiento
---
# Ordenamiento

Ordenar una colección de datos es otro de los problemas más frecuentes en programación: mostrar resultados de mayor a
menor, organizar una lista alfabéticamente, preparar datos para poder aplicar búsqueda binaria. En esta sección vemos
cuatro algoritmos clásicos, de los más simples a los más eficientes.

## Comparativa rápida

| Algoritmo | Idea central | Peor caso | ¿Estable? | ¿In-place? |
|---|---|---|---|---|
| **Burbuja** | Intercambiar pares adyacentes fuera de orden, repetidamente | O(n²) | Sí | Sí |
| **Selección** | Buscar el mínimo restante y colocarlo en su posición | O(n²) | No | Sí |
| **Inserción** | Insertar cada elemento en su lugar dentro de la parte ya ordenada | O(n²) | Sí | Sí |
| **Mezcla** | Dividir, ordenar recursivamente y mezclar (divide y vencerás) | O(n log n) | Sí | No |

Los primeros tres son intuitivos y fáciles de programar, pero todos comparten la misma limitación: en el peor caso
hacen del orden de n² comparaciones. **Mezcla** rompe esa barrera aplicando la misma idea de divide y vencerás que ya
viste con la potencia rápida (Unidad 2) y la búsqueda binaria (esta unidad): partir el problema en mitades más
pequeñas hasta que sea trivial, y luego combinar los resultados.

## Divide y vencerás: ordenamiento por mezcla

```{image} _static/unidad3/ordenamiento/merge_sort.png
:alt: Merge sort dividiendo la lista hasta listas de tamano 1 y luego mezclandolas de vuelta en orden
```

La parte que hace el trabajo pesado es **mezclar** (*merge*): combinar dos listas que ya están ordenadas en una sola
lista ordenada, recorriendo ambas una sola vez. Como dividir siempre parte el problema a la mitad, se necesitan solo
`log n` niveles de división — por eso la complejidad total es O(n log n) en vez de O(n²).

## ¿Cuándo usar cada uno?

| Úsalo si... | Evítalo si... |
|---|---|
| **Burbuja** — quieres el algoritmo más simple posible para explicar o depurar | Trabajas con listas grandes en producción |
| **Selección** — mover/escribir datos es costoso (hace pocos intercambios) | Necesitas que el orden sea estable entre elementos iguales |
| **Inserción** — la lista es pequeña o ya está casi ordenada | La lista es grande y desordenada |
| **Mezcla** — la lista es grande y necesitas garantías de rendimiento (O(n log n) siempre) | La memoria disponible es muy limitada (usa espacio extra O(n)) |

```{note}
En la práctica casi nunca implementas tu propio ordenamiento: `sorted()` y `list.sort()` de Python usan **Timsort**,
un algoritmo híbrido optimizado. Estos cuatro algoritmos se estudian porque enseñan ideas fundamentales
(comparar e intercambiar, insertar en su lugar, divide y vencerás) que reaparecen en muchos otros problemas.
```

## Manos a la obra! 🔃🐍

1. {doc}`Ordenamiento_Notebook` — implementación de burbuja, selección, inserción y mezcla, comparación de rendimiento,
   tabla comparativa (estabilidad, in-place) y ejercicios propuestos.
