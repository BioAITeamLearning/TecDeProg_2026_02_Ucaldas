---
title: Backtracking
---
# Backtracking

El **backtracking** es un paradigma algorítmico sistemático para resolver problemas de búsqueda y optimización combinatoria: construye una solución **incrementalmente**, probando candidatos parciales, y **abandona** (retrocede) tan pronto como detecta que un camino no puede conducir a una solución válida. Esa es la diferencia clave con la fuerza bruta pura: el backtracking incorpora **poda temprana** de ramas improductivas en vez de generar y probar todo.

## Backtracking frente a otros paradigmas

| Paradigma | Relación con el backtracking |
|---|---|
| **Fuerza bruta** | Genera todas las soluciones posibles sin discriminar y luego valida cada una. El backtracking construye incrementalmente y descarta candidatos inválidos **temprano** — explora menos nodos. |
| **Recursión simple** | Es la técnica de implementación (auto-llamada de funciones). El backtracking es un *paradigma algorítmico* que típicamente se implementa con recursión, con una estructura específica: **probar → avanzar → retroceder**. |
| **Programación dinámica** | La PD resuelve subproblemas solapados una sola vez, memoizando resultados. El backtracking explora el espacio de soluciones sin almacenar resultados intermedios — cuando hay mucho solapamiento, conviene PD; cuando no, backtracking. |

## Espacio de estados y árbol de decisiones

El backtracking visualiza el problema como un **árbol de decisiones**: cada nodo es una solución parcial, cada arista una decisión, y el algoritmo lo recorre en **profundidad primero (DFS)** sin construirlo completo en memoria — solo mantiene el camino actual en la pila de recursión.

```{image} _static/unidad2/backtracking/backtracking_ciclo.png
:alt: Ciclo de backtracking: Probar, Avanzar, Retroceder, con poda temprana en el paso Probar
```

## Analogía: explorar un laberinto

Imagina que exploras un laberinto buscando la salida:

1. **Avanzar**: caminas por un pasillo que parece prometedor, marcando tu ruta.
2. **Evaluar**: en cada bifurcación, decides si el camino actual puede llevarte a la salida.
3. **Retroceder**: si llegas a un callejón sin salida, regresas al último punto de decisión.
4. **Probar alternativa**: pruebas el siguiente camino disponible en esa bifurcación.

Esa es exactamente la esencia del backtracking: **exploración sistemática con retroceso inteligente**.

## Conceptos fundamentales

| Concepto | Idea |
|---|---|
| **Solución parcial** | Una configuración incompleta que puede extenderse hacia una solución completa (un nodo interno del árbol). |
| **Retroceso (backtrack)** | Deshacer la última decisión cuando la solución parcial no puede conducir a una solución válida, y probar la siguiente alternativa. |
| **Poda temprana (pruning)** | Abandonar una rama tan pronto como se detecta que no puede producir soluciones válidas — esto es lo que diferencia al backtracking de la fuerza bruta pura. |
| **Criterio de validez** | La función que decide si una solución parcial puede extenderse legítimamente o debe abandonarse — implementa las restricciones del problema. |

## Plantilla universal

```python
def backtrack(solucion, opciones):
    # Caso base: solución completa
    if condicion_exito(solucion):
        registrar(solucion[:])   # copia, no referencia
        return

    # Caso recursivo: probar cada opción
    for opcion in opciones:
        if es_valido(opcion, solucion):      # 1. PROBAR
            aplicar(opcion, solucion)        # 2. AVANZAR
            backtrack(solucion, calcular_opciones(solucion))
            deshacer(opcion, solucion)       # 3. RETROCEDER
```

Los cuatro componentes que cambian según el problema son `condicion_exito`, `es_valido`, `aplicar`/`deshacer` y las opciones disponibles en cada paso — la arquitectura de tres fases permanece constante.

## ¿Cuándo usar backtracking?

| Úsalo si... | Evítalo si... |
|---|---|
| Necesitas **todas** las soluciones posibles | Solo necesitas una y hay heurísticas disponibles |
| Las restricciones pueden evaluarse **incrementalmente** | Hay mucho solapamiento de subproblemas (usa programación dinámica) |
| El espacio de búsqueda es exponencial pero **podable** | Las restricciones solo se evalúan al final |
| No hay solapamiento significativo de subproblemas | El espacio de búsqueda es polinomial y manejable, o existe un algoritmo *greedy* que funciona |

## Material de apoyo

```{note}
Teoría completa con la plantilla, la visualización del árbol de decisiones y el análisis de complejidad 📎 [Fundamentos del Backtracking (PDF)](_static/unidad2/backtracking/FundamentosdelBacktracking.pdf)
```

## Manos a la obra! 🐍♟️

1. {doc}`Backtracking_Notebook` — la plantilla universal, ejemplos resueltos (cadenas, subconjuntos, permutaciones), poda con restricciones (N-Reinas), aplicaciones (mochila 0-1, caminos en un laberinto) y ejercicios propuestos.
