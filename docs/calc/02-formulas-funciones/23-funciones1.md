# 2.3 Funciones aritméticas y lógicas

## 1. SI

**Tipo:** Lógica

Permite comprobar una condición y devolver un resultado si se cumple y otro si no se cumple.

**Sintaxis general:**

```calc
=SI(prueba_lógica; valor_si_verdadero; valor_si_falso)
```

**Ejemplo práctico:**

```calc
=SI(B2>=5; "Aprobado"; "Suspenso")
```

- Si B2 es mayor o igual que 5 → devuelve «Aprobado».
- Si B2 es menor que 5 → devuelve «Suspenso».

## 2. Y

**Tipo:** Lógica

Comprueba varias condiciones y devuelve VERDADERO únicamente si **todas se cumplen**.

**Sintaxis general:**

```calc
=Y(valor_lógico1; valor_lógico2; ...)
```

**Ejemplo práctico:**

```calc
=Y(B2>=5; C2>=5)
```

- Si B2 y C2 son mayores o iguales que 5 → VERDADERO.
- Si alguna de las dos condiciones no se cumple → FALSO.

## 3. O

**Tipo:** Lógica

Comprueba varias condiciones y devuelve VERDADERO si **al menos una se cumple**.

**Sintaxis general:**

```calc
=O(valor_lógico1; valor_lógico2; ...)
```

**Ejemplo práctico:**

```calc
=O(B2>=5; C2>=5)
```

- Si B2 o C2 (o ambas) son mayores o iguales que 5 → VERDADERO.
- Si ninguna cumple la condición → FALSO.

## 4. SUMA

**Tipo:** Matemática

Suma todos los valores numéricos indicados.

**Sintaxis general:**

```calc
=SUMA(número1; número2; ...)
```

También admite rangos de celdas.

**Ejemplo práctico:**

```calc
=SUMA(B2:B10)
```

Suma todos los valores numéricos comprendidos entre B2 y B10.

## 5. SUMAR.SI

**Tipo:** Matemática

Suma los valores de un rango únicamente cuando cumplen una condición.

**Sintaxis general:**

```calc
=SUMAR.SI(rango; criterio; rango_suma)
```

- `rango`: celdas donde se comprueba la condición.
- `criterio`: condición que deben cumplir.
- `rango_suma`: celdas cuyos valores se sumarán.

**Ejemplo práctico:**

```calc
=SUMAR.SI(A2:A10; "Deportivo"; B2:B10)
```

Suma los importes de B2:B10 únicamente cuando la celda correspondiente de A2:A10 contiene «Deportivo».

## 6. SUMAR.SI.CONJUNTO

**Tipo:** Matemática

Suma valores que cumplen **varias condiciones simultáneamente**.

**Sintaxis general:**

```calc
=SUMAR.SI.CONJUNTO(rango_suma; rango_criterios1; criterio1; rango_criterios2; criterio2; ...)
```

- `rango_suma`: celdas cuyos valores se sumarán.
- `rango_criterios`: celdas donde se comprobarán las condiciones.
- `criterio`: condición que debe cumplirse.


---
