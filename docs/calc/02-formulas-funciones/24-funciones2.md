# 2.4 Funciones de recuento

## 1. CONTAR

**Tipo:** Recuento

Cuenta cuántas celdas contienen valores numéricos dentro de un rango.

**Sintaxis general:**

```calc
=CONTAR(valor1; valor2; ...)
```

**Ejemplo práctico:**

```calc
=CONTAR(B2:B10)
```

Cuenta cuántas celdas del rango B2:B10 contienen números.

**Importante:** no cuenta las celdas vacías ni las que contienen texto.

## 2. CONTARA

**Tipo:** Recuento

Cuenta cuántas celdas contienen algún tipo de dato (números, texto, fechas, etc.).

**Sintaxis general:**

```calc
=CONTARA(valor1; valor2; ...)
```

**Ejemplo práctico:**

```calc
=CONTARA(A2:A10)
```

Cuenta cuántas celdas del rango A2:A10 no están vacías.

**Importante:** a diferencia de CONTAR, también cuenta las celdas que contienen texto.

## 3. CONTAR.SI

**Tipo:** Recuento

Cuenta cuántas celdas cumplen una condición determinada.

**Sintaxis general:**

```calc
=CONTAR.SI(rango; criterio)
```

- `rango`: celdas donde se comprobará la condición.
- `criterio`: condición que deben cumplir las celdas.

**Ejemplo práctico:**

```calc
=CONTAR.SI(B2:B20; ">=5")
```

Cuenta cuántas celdas del rango B2:B20 contienen un valor mayor o igual que 5.

Otro ejemplo:

```calc
=CONTAR.SI(A2:A20; "Victoria")
```

Cuenta cuántas veces aparece «Victoria» en el rango A2:A20.

## 4. CONTAR.SI.CONJUNTO

**Tipo:** Recuento

Cuenta cuántas filas cumplen **varias condiciones simultáneamente**.

**Sintaxis general:**

```calc
=CONTAR.SI.CONJUNTO(rango_criterios1; criterio1; rango_criterios2; criterio2; ...)
```

- `rango_criterios`: celdas donde se comprobarán las condiciones.
- `criterio`: condición que deben cumplir.



# 🧠 Resumen rápido: ¿qué función utilizo?

| Necesito... | Función |
|---|---|
| Comprobar una condición | `SI` |
| Comprobar que se cumplen todas las condiciones | `Y` |
| Comprobar que se cumple alguna condición | `O` |
| Sumar valores | `SUMA` |
| Sumar valores que cumplen una condición | `SUMAR.SI` |
| Sumar valores que cumplen varias condiciones | `SUMAR.SI.CONJUNTO` |
| Contar celdas con números | `CONTAR` |
| Contar celdas no vacías | `CONTARA` |
| Contar celdas que cumplen una condición | `CONTAR.SI` |
| Contar celdas que cumplen varias condiciones | `CONTAR.SI.CONJUNTO` |

---

