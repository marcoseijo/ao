
# 🔎 Funciones de búsqueda: BUSCAR, BUSCARV, BUSCARH y COINCIDIR

Las funciones de búsqueda permiten localizar información dentro de una tabla y recuperar datos relacionados con ella.

Imagina que tenemos un libro de Calc con las estadísticas del **Deportivo de La Coruña**: jugadores, partidos, goles, asistencias y puntos. En lugar de recorrer toda la tabla manualmente, podemos utilizar estas funciones para encontrar rápidamente lo que necesitamos.

## 1. BUSCAR()

Busca un valor dentro de un rango y devuelve el dato correspondiente de otro rango.

**Sintaxis:**

```calc
=BUSCAR(valor_buscado; vector_búsqueda; vector_resultado)
```

- `valor_buscado`: el dato que queremos encontrar.
- `vector_búsqueda`: dónde queremos buscarlo.
- `vector_resultado`: de dónde queremos obtener el resultado.

**Ejemplo:**

Imagina que tenemos una tabla con los dorsales y nombres de los jugadores:

| A (Dorsal) | B (Jugador) |
|---|---|
| 7 | Lucas |
| 10 | Yeremay |
| 21 | Mella |
| 9 | Barbero |

Si queremos saber qué jugador tiene el dorsal 10:

```calc
=BUSCAR(10;A2:A5;B2:B5)
```

**Resultado:** Yeremay.

Importante: BUSCAR trabaja con búsqueda aproximada y requiere que el vector de búsqueda esté ordenado de menor a mayor. No es la mejor opción cuando necesitamos una coincidencia exacta.

## 2. BUSCARV()

La V significa *vertical*. Busca un valor en la primera columna de una tabla y devuelve un dato de otra columna de la misma fila.

**Sintaxis:**

```calc
=BUSCARV(valor_buscado; matriz; indicador_columna; ordenado)
```

- `valor_buscado`: el dato que queremos localizar.
- `matriz`: el rango completo de la tabla.
- `indicador_columna`: número de la columna de la que queremos obtener el resultado (empezando por 1).
- `ordenado`: 0 para coincidencia exacta; 1 para búsqueda aproximada.

**Ejemplo:**

En nuestro libro del Deportivo tenemos esta tabla:

| A (Jugador) | B (Goles) | C (Asistencias) |
|---|---:|---:|
| Lucas | 8 | 4 |
| Yeremay | 12 | 7 |
| Mella | 5 | 6 |
| Barbero | 9 | 2 |

Queremos saber cuántos goles ha marcado Yeremay:

```calc
=BUSCARV("Yeremay";A2:C5;2;0)
```

**Resultado:** 12.

¿Y si queremos conocer sus asistencias?

```calc
=BUSCARV("Yeremay";A2:C5;3;0)
```

**Resultado:** 7.

Recuerda: BUSCARV siempre busca en la primera columna del rango seleccionado y devuelve información situada a su derecha.

## 3. BUSCARH()

La H significa *horizontal*. Funciona igual que BUSCARV, pero en lugar de buscar en la primera columna, busca en la primera fila de una tabla.

**Sintaxis:**

```calc
=BUSCARH(valor_buscado; matriz; indicador_fila; ordenado)
```

- `valor_buscado`: el dato que queremos localizar.
- `matriz`: el rango completo de la tabla.
- `indicador_fila`: número de la fila de la que queremos obtener el resultado (empezando por 1).
- `ordenado`: 0 para coincidencia exacta; 1 para búsqueda aproximada.

**Ejemplo:**

Imagina que organizamos las estadísticas del Deportivo de forma horizontal:

| | A | B | C | D |
|---|---|---|---|---|
| 1 | Lucas | Yeremay | Mella | Barbero |
| 2 | 8 | 12 | 5 | 9 |
| 3 | 4 | 7 | 6 | 2 |

Queremos conocer los goles de Yeremay:

```calc
=BUSCARH("Yeremay";B1:D3;2;0)
```

**Resultado:** 12.

Si queremos conocer sus asistencias:

```calc
=BUSCARH("Yeremay";B1:D3;3;0)
```

**Resultado:** 7.

Recuerda: BUSCARH busca en la primera fila y devuelve información situada en las filas inferiores.

## 4. COINCIDIR()

Esta función es un poco diferente. No devuelve el dato que estamos buscando, sino la posición que ocupa dentro de un rango.

**Sintaxis:**

```calc
=COINCIDIR(valor_buscado; matriz_búsqueda; tipo)
```

- `valor_buscado`: el dato que queremos localizar.
- `matriz_búsqueda`: el rango donde buscamos.
- `tipo`: 0 para coincidencia exacta; 1 para búsqueda aproximada ascendente; -1 para búsqueda aproximada descendente.

**Ejemplo:**

Tenemos una lista de jugadores:

| A (Posición) | B (Jugador) |
|---|---|
| 1 | Lucas |
| 2 | Yeremay |
| 3 | Mella |
| 4 | Barbero |

Queremos saber en qué posición aparece Yeremay dentro de la lista:

```calc
=COINCIDIR("Yeremay";B2:B5;0)
```

**Resultado:** 2.

¡Ojo! El resultado es 2 porque Yeremay ocupa la segunda posición del rango, no porque tenga el dorsal 2.

## 🏆 Un paso más: combinando funciones

Lo interesante empieza cuando combinamos varias funciones.

Imagina que queremos saber en qué asignatura ha conseguido un alumno su mejor nota, o en qué estadística destaca un jugador del Deportivo.

Podemos utilizar `MAX()` para encontrar el valor máximo y `COINCIDIR()` para averiguar en qué posición se encuentra.

Por ejemplo, tenemos las estadísticas de Yeremay:

| | AO | IPE | SOM | MM | REDES |
|---|---:|---:|---:|---:|---:|
| Yeremay | 7 | 8 | 6 | 9 | 7 |

**Paso 1.** Encontramos su mejor nota:

```calc
=MAX(C2:G2)
```

Resultado: 9.

**Paso 2.** Averiguamos en qué posición está esa nota:

```calc
=COINCIDIR(MAX(C2:G2);C2:G2;0)
```

Resultado: 4.

La posición 4 corresponde a MM.

Así conseguimos localizar no solo el valor más alto, sino también dónde se encuentra.

---

## 🧠 Resumen: ¿qué función utilizamos?

| Función | ¿Qué hace? |
|---|---|
| `BUSCAR` | Busca un valor y devuelve otro relacionado. |
| `BUSCARV` | Busca verticalmente (por columnas). |
| `BUSCARH` | Busca horizontalmente (por filas). |
| `COINCIDIR` | Devuelve la posición de un valor. |

**La idea clave:** BUSCAR, BUSCARV y BUSCARH nos permiten recuperar información. COINCIDIR nos dice dónde se encuentra.
