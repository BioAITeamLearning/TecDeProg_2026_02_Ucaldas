---
title: Pilas y Colas
---
# Pilas y Colas

Las **pilas** y las **colas** son estructuras de datos lineales que restringen *cómo* se accede a la información. Una pila solo permite trabajar desde un extremo (**LIFO**: el último en entrar es el primero en salir). Una cola permite insertar por un extremo y retirar por el otro (**FIFO**: el primero en entrar es el primero en salir).

## Comparativa rápida

| Característica | Pila (Stack) | Cola (Queue) | Deque |
|---|---|---|---|
| Principio | LIFO | FIFO | Ambos extremos |
| Inserción | Solo en la cima (`push`) | Solo al final (`enqueue`) | Ambos extremos |
| Eliminación | Solo desde la cima (`pop`) | Solo desde el frente (`dequeue`) | Ambos extremos |
| Aplicaciones típicas | Deshacer, recursión, expresiones | Procesos, turnos, BFS | Historial, buffers |
| En Python | `list.append()` / `list.pop()` | `deque.append()` / `deque.popleft()` | `deque` nativo |

::::{grid} 1
:gutter: 3

:::{grid-item}
```{image} _static/pilas_colas/pila_diagrama.png
:alt: Operaciones de una pila - push, pop y estado LIFO
```
:::

:::{grid-item}
```{image} _static/pilas_colas/cola_diagrama.png
:alt: Operaciones de una cola - enqueue, dequeue y el costo de pop(0)
```
:::

::::

## Material de apoyo

```{note}
Presentación y guía extendida 📎 [Diapositivas (PPTX)](_static/pilas_colas/PilasyColasenPython.pptx) · [Guía extendida (PDF)](_static/pilas_colas/VPilasyColasenPythonz.pdf)
```

## En esta sección

1. {doc}`Pila` — implementación básica con funciones y una lista.
2. {doc}`Cola` — implementación básica con funciones y una lista.
3. {doc}`Pilas_y_Colas_Avanzadas` — clases, `deque`, `heapq`, y aplicaciones reales (BFS, backtracking, Round-Robin).
