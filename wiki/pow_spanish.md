<!--
Meta Description: # La Función pow en C: Potencia de Números ## Sinopsis La función `pow` en C es utilizada para calcular la potencia de un número. Permite elevar un nú...
Meta Keywords: base, exponente, double, resultado, pow
-->

# La Función pow en C: Potencia de Números

## Sinopsis
La función `pow` en C es utilizada para calcular la potencia de un número. Permite elevar un número base a un exponente, siendo una herramienta esencial en cálculos matemáticos y científicos.

## Documentación

### Propósito
La función `pow` forma parte de la biblioteca matemática estándar de C, definida en el encabezado `<math.h>`. Su principal propósito es calcular el resultado de elevar un número (base) a la potencia de otro número (exponente).

### Uso
La sintaxis de la función `pow` es la siguiente:

```c
#include <math.h>

double pow(double base, double exponente);
```

- **base**: El número que se elevará a la potencia.
- **exponente**: El número al que se elevará la base.

### Detalles
- El resultado de `pow` es un valor de tipo `double`.
- Si la base es negativa y el exponente es un número fraccionario, la función devolverá un valor indefinido (NaN).
- Si la base es 0 y el exponente es menor o igual a 0, el resultado también será indefinido (NaN).
- La función puede manejar números grandes, pero el resultado puede ser infinito si se exceden los límites del tipo `double`.

## Ejemplos

### Ejemplo 1: Potencia de un número entero
```c
#include <stdio.h>
#include <math.h>

int main() {
    double base = 2.0;
    double exponente = 3.0;
    double resultado = pow(base, exponente);
    printf("%.2f elevado a %.2f es %.2f\n", base, exponente, resultado);
    return 0;
}
```
**Salida:**
```
2.00 elevado a 3.00 es 8.00
```

### Ejemplo 2: Potencia con un número negativo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double base = -2.0;
    double exponente = 4.0;
    double resultado = pow(base, exponente);
    printf("%.2f elevado a %.2f es %.2f\n", base, exponente, resultado);
    return 0;
}
```
**Salida:**
```
-2.00 elevado a 4.00 es 16.00
```

### Ejemplo 3: Base cero con exponente positivo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double base = 0.0;
    double exponente = 5.0;
    double resultado = pow(base, exponente);
    printf("%.2f elevado a %.2f es %.2f\n", base, exponente, resultado);
    return 0;
}
```
**Salida:**
```
0.00 elevado a 5.00 es 0.00
```

## Explicación
Al utilizar `pow`, es importante tener en cuenta lo siguiente:

- **Números negativos**: Si la base es negativa y el exponente es un número no entero, el resultado será indefinido.
- **Cero elevado a la potencia**: La expresión `0^0` no está definida y puede dar lugar a resultados inesperados.
- **Precisión**: Debido a la naturaleza de los números de punto flotante, el resultado puede no ser exacto en todos los casos, especialmente al elevar números grandes o al trabajar con fracciones.

## Resumen en una línea
La función `pow` en C permite calcular la potencia de un número, elevando una base a un exponente específico.