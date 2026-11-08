
# 2.1. Referencias relativas, absolutas y mixtas

Las **referencias** identifican las celdas que utiliza una fórmula para realizar sus cálculos. Su comportamiento determina cómo se modifican cuando copiamos una fórmula a otra posición.

## 1. Referencias relativas

**Definición:** identifican una celda mediante su posición relativa respecto a la fórmula. Al copiarla, las referencias se actualizan automáticamente.

**Ejemplo:** calcular el importe de varios productos multiplicando cantidad por precio.

```excel
=B2*C2
```

Al copiar la fórmula hacia abajo, se convierte en `=B3*C3`, `=B4*C4`, etc.

## 2. Referencias absolutas

**Definición:** identifican una celda mediante una dirección fija. Su columna y su fila permanecen invariables al copiar la fórmula.

Se utiliza el símbolo `$` para fijar ambos elementos.

**Ejemplo:** calcular el precio final de varios productos utilizando un porcentaje de IVA situado en F1.

```excel
=B2*(1+$F$1)
```

Al copiar la fórmula, la referencia `$F$1` permanece fija.

## 3. Referencias mixtas

**Definición:** fijan únicamente la columna o la fila de una referencia, permitiendo que el otro elemento se modifique al copiar la fórmula.

Existen dos posibilidades:

- `$A1`: fija la columna A.
- `A$1`: fija la fila 1.

**Ejemplo:** crear una tabla de multiplicar utilizando los valores de la primera fila y la primera columna.

```excel
=$A2*B$1
```

Al copiar la fórmula horizontal y verticalmente, las referencias se adaptan manteniendo fijas la columna A y la fila 1.

## 4. Resumen

| Tipo | Ejemplo | Elementos fijos |
|---|---|---|
| Relativa | `A1` | Ninguno |
| Absoluta | `$A$1` | Fila y columna |
| Mixta | `$A1` | Columna |
| Mixta | `A$1` | Fila |

**Recuerda:** las referencias permiten controlar qué elementos de una fórmula cambian y cuáles permanecen fijos al copiarla.
