<!--
Meta Description: # Logaritmo en C: Uso de la función log() ## Sinopsis La función `log()` en C permite calcular el logaritmo natural (base e) de un número. Es una herr...
Meta Keywords: logaritmo, función, log, número, double
-->

# Logaritmo en C: Uso de la función log()

## Sinopsis
La función `log()` en C permite calcular el logaritmo natural (base e) de un número. Es una herramienta fundamental en matemáticas y programación que se utiliza en diversas aplicaciones científicas y de ingeniería.

## Documentación
La función `log()` se define en el encabezado `<math.h>`. Su propósito principal es devolver el logaritmo natural de un número positivo. La función tiene la siguiente firma:

```c
#include <math.h>
double log(double x);
```

### Propósito
El logaritmo natural es fundamental en muchas aplicaciones, incluyendo cálculos de crecimiento exponencial, modelos de decaimiento, y en la resolución de ecuaciones matemáticas complejas.

### Uso
- **Argumento**: La función toma un único argumento `x` que debe ser un número positivo. Si `x` es menor o igual a cero, la función devuelve `NaN` (Not a Number).
- **Valor de retorno**: El valor devuelto es el logaritmo natural de `x`.

### Detalles
- Asegúrate de incluir el encabezado `<math.h>` para utilizar la función.
- Al compilar un programa que utiliza `log()`, es posible que necesites enlazar con la biblioteca matemática usando la opción `-lm` en el compilador.

## Ejemplos

### Ejemplo 1: Logaritmo de un número positivo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double numero = 2.71828;
    double resultado = log(numero);
    printf("El logaritmo natural de %.5f es %.5f\n", numero, resultado);
    return 0;
}
```

### Ejemplo 2: Logaritmo de un número menor que uno
```c
#include <stdio.h>
#include <math.h>

int main() {
    double numero = 0.5;
    double resultado = log(numero);
    printf("El logaritmo natural de %.5f es %.5f\n", numero, resultado);
    return 0;
}
```

### Ejemplo 3: Manejo de un número no válido
```c
#include <stdio.h>
#include <math.h>

int main() {
    double numero = -1.0;
    double resultado = log(numero);
    if (isnan(resultado)) {
        printf("El logaritmo de un número negativo no está definido.\n");
    }
    return 0;
}
```

## Explicación
- **Números negativos**: Recuerda que la función `log()` no está definida para números negativos o cero. Intentar calcular el logaritmo de estos valores resultará en `NaN`.
- **Precisión**: La precisión de los resultados puede depender de la implementación de la biblioteca matemática en tu entorno. Es recomendable verificar los resultados en condiciones específicas.
- **Compilación**: Asegúrate de compilar usando `-lm` para evitar errores de enlace relacionados con la función matemática.

## Resumen en una línea
La función `log()` en C calcula el logaritmo natural de un número positivo, siendo esencial en aplicaciones matemáticas y científicas.