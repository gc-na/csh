<!--
Meta Description: # Función acos en C: Cálculo del Arcoseno ## Sinopsis La función `acos` en C se utiliza para calcular el arco coseno de un número. Este valor es el án...
Meta Keywords: función, acos, rango, resultado, coseno
-->

# Función acos en C: Cálculo del Arcoseno

## Sinopsis
La función `acos` en C se utiliza para calcular el arco coseno de un número. Este valor es el ángulo cuya función coseno es igual al número proporcionado, y es fundamental en aplicaciones matemáticas y gráficas.

## Documentación
La función `acos` forma parte de la biblioteca matemática estándar de C, `<math.h>`. Su propósito principal es devolver el arco coseno de un número en radianes. El rango de entrada de la función es de -1 a 1, y el rango de salida es de 0 a π (pi).

### Prototipo
```c
#include <math.h>
double acos(double x);
```

### Parámetros
- `x`: Un valor de punto flotante que debe estar en el intervalo [-1, 1].

### Valor de retorno
La función devuelve un valor de tipo `double` que representa el ángulo en radianes. Si `x` está fuera del rango [-1, 1], la función devuelve `NaN` (Not a Number).

## Ejemplos
### Ejemplo 1: Uso básico de `acos`
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 0.5;
    double resultado = acos(x);
    printf("El arco coseno de %.2f es %.2f radianes.\n", x, resultado);
    return 0;
}
```
**Salida:**
```
El arco coseno de 0.50 es 1.05 radianes.
```

### Ejemplo 2: Arco coseno de -1
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = -1.0;
    double resultado = acos(x);
    printf("El arco coseno de %.2f es %.2f radianes.\n", x, resultado);
    return 0;
}
```
**Salida:**
```
El arco coseno de -1.00 es 3.14 radianes.
```

### Ejemplo 3: Manejo de valores fuera de rango
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 2.0; // Fuera del rango [-1, 1]
    double resultado = acos(x);
    if (isnan(resultado)) {
        printf("El valor está fuera del rango para la función acos.\n");
    }
    return 0;
}
```
**Salida:**
```
El valor está fuera del rango para la función acos.
```

## Explicación
Al usar la función `acos`, es crucial asegurarse de que el argumento esté dentro del rango permitido. Proporcionar un valor fuera de este rango resultará en un comportamiento indefinido, devolviendo `NaN`. Además, dado que la función devuelve el resultado en radianes, si se requiere el resultado en grados, será necesario convertirlo multiplicando por `180/π`.

### Errores comunes
1. **Valores fuera de rango**: Asegúrate de que `x` esté entre -1 y 1.
2. **Interpretar el resultado en radianes**: Recuerda que el resultado no está en grados, lo que puede llevar a confusiones en aplicaciones que requieren grados.
3. **Uso de la biblioteca matemática**: No olvides incluir `<math.h>` y compilar con la opción `-lm` en GCC para enlazar correctamente la biblioteca matemática.

## Resumen en una línea
La función `acos` en C calcula el arco coseno de un número, devolviendo el ángulo en radianes correspondiente.