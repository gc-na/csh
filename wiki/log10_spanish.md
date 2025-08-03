<!--
Meta Description: # log10 en C: Función para el Cálculo del Logaritmo en Base 10 ## Sinopsis La función `log10` en C calcula el logaritmo en base 10 de un número dado. ...
Meta Keywords: logaritmo, base, log10, función, número
-->

# log10 en C: Función para el Cálculo del Logaritmo en Base 10

## Sinopsis
La función `log10` en C calcula el logaritmo en base 10 de un número dado. Es parte de la biblioteca estándar de matemáticas y se utiliza comúnmente en aplicaciones científicas y de ingeniería.

## Documentación
La función `log10` se define en la biblioteca `<math.h>`. Su propósito es devolver el logaritmo en base 10 de un número real positivo. La sintaxis de la función es la siguiente:

```c
#include <math.h>

double log10(double x);
```

### Parámetros
- `x`: un valor de tipo `double` que representa el número del cual se desea calcular el logaritmo en base 10. Debe ser mayor que cero.

### Valor de Retorno
La función devuelve el logaritmo en base 10 de `x`. Si `x` es menor o igual a cero, la función devuelve `NAN` (Not a Number) y establece el indicador de error.

### Requisitos
- Incluir la biblioteca `<math.h>` para utilizar la función.
- Compilar con la opción de enlace a la biblioteca matemática, utilizando `-lm` en la línea de comandos de compilación.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 100.0;
    double resultado = log10(num);
    printf("El logaritmo en base 10 de %.2f es %.2f\n", num, resultado);
    return 0;
}
```
**Salida esperada:**
```
El logaritmo en base 10 de 100.00 es 2.00
```

### Ejemplo con un Número No Válido
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -10.0;
    double resultado = log10(num);
    if (isnan(resultado)) {
        printf("El logaritmo en base 10 de %.2f no está definido.\n", num);
    }
    return 0;
}
```
**Salida esperada:**
```
El logaritmo en base 10 de -10.00 no está definido.
```

## Explicación
Al utilizar `log10`, es importante asegurarse de que el argumento sea un número positivo. Pasar un número negativo o cero producirá un resultado no definido, que es un punto común de confusión para los nuevos programadores.

### Consideraciones:
- La función `log10` es parte de la biblioteca matemática estándar, por lo que es necesario enlazarla correctamente durante la compilación.
- Si se intenta calcular el logaritmo de un número negativo, se debe manejar adecuadamente el caso, ya que puede llevar a errores en la ejecución.

## Resumen en una Línea
La función `log10` en C calcula el logaritmo en base 10 de un número positivo, devolviendo un resultado significativo o `NAN` para entradas no válidas.