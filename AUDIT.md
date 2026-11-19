# Informe de Auditoría — B-Tree

**Asignatura:** Estructuras de Datos Avanzadas (IC10D – EDA)  
**Estudiante:** [Daniza Michelle Peso Paredes]  
**RUT:** [20.921.970-0]  
**Fecha:** [2026-11-17]  
**Taller:** 4 — Auditoría de un B-Tree

---

## 1. Matriz de costos

Completa la matriz con el modelo de costo que corresponda. Si una operación
no aplica a un modelo, escribe `N/A` y justifica.

| Operación | Costo RAM (peor) | Costo RAM (amortizado) | Costo E/S | Condición (N, B, M) | Evidencia |
| :--- | :---: | :---: | :---: | :--- | :--- |
| `search(key)` | `O(...)` | `O(...)` | `O(...)` | | |
| `insert(key)` | `O(...)` | `O(...)` | `O(...)` | | |
| `delete(key)` | `O(...)` | `O(...)` | `O(...)` | | |
| `height()` | `O(...)` | `O(...)` | `O(...)` | | |
| `occupancy()` | `O(...)` | `O(...)` | `O(...)` | | |
| `validate()` | `O(...)` | `O(...)` | `O(...)` | | |

> **No se pide una demostración formal.** No uses funciones potenciales ni
> recurrencias. Usa trazas, conteos y condiciones explícitas.

---

## 2. Justificación por traza

Elige al menos **dos operaciones** y síguelas con un ejemplo pequeño.
Indica el estado antes, los pasos y el estado después.

### Operación 1: `[nombre]`

- **Entrada / estado inicial:**
- **Traza paso a paso:**
- **Conteo relevante** (comparaciones, nodos visitados, splits, etc.):
- **Conclusión de costo:**

### Operación 2: `[nombre]`

- **Entrada / estado inicial:**
- **Traza paso a paso:**
- **Conteo relevante:**
- **Conclusión de costo:**

---

## 3. Hallazgos de diseño e implementación

Registra los hallazgos que puedas sostener con evidencia. El **mínimo es
tres**; si encuentras más, agrega filas. No confundas un **error de
correctitud** con una **decisión controvertida**: si el código funciona,
pero la decisión es discutible, clasifícala como diseño.

| ID | Ubicación | Decisión observada | Por qué es discutible | Impacto | Propuesta | Prioridad |
| :--- | :--- | :--- | :--- | :--- | :--- | :---: |
| H-01 | `src/tree.py:17-28` |Fijar el tamaño del nodo en base a las keys |Porque si esas claves + punteros no caben en el bloque, el invariante se rompe  |el costo se duplica |verificar cuantos bytes ocupa el bloque | Media |
| H-02 | `src/tree.py:48-54` |Permitir claves duplicadas | Almacenar dos veces la misma key es ineficiente|Baja de rendimiento |No insertar la misma clave, buscar antes de insertar |Media |
| H-03 | `src/tree.py:97-107` |Delete poco eficiente |Hace rebuilds por cada delete | Baja de rendimiento|Comparar en vez de rehacer |Media |

> Si encuentras más de tres, duplica una fila. No se penaliza no llegar a
> las decisiones más finas; se evalúa la calidad de las que sí sostienes.

### 3.1 Clasificación

Para cada hallazgo, indica si es:

- **Decisión de diseño:** el código es correcto, pero hay una alternativa
  con mejor costo, claridad o fidelidad al modelo.
- **Deuda de implementación:** el código funciona, pero la forma de
  implementarlo introduce un costo oculto.
- **Error de correctitud:** el código no cumple su contrato. En ese caso,
  adjunta una traza o un test que lo demuestre.


1,2 y 3 Deuda de implementación
---

## 4. Evidencia de ejecución

Puedes usar los tests, el demo o trazas propias. No pegues salidas
completas: cita lo relevante.

```text
Comando:
Resultado:
Interpretación:
```

---

## 5. Registro de la defensa oral

| Momento | Pregunta o solicitud del docente | Respuesta / modificación | Resultado |
| :--- | :--- | :--- | :--- |
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 6. Conclusión

En no más de un párrafo: ¿qué decisión cambiarías primero y por qué? ¿Qué
decisión defenderías tal como está?
