<!--
Meta Description: # Función tan en C: Cálculo de la Tangente ## Sinopsis La función `tan` en C permite calcular la tangente de un ángulo dado en radianes. Esta función ...
Meta Keywords: radianes, tangente, tan, función, angulo
-->

# Función tan en C: Cálculo de la Tangente

## Sinopsis
La función `tan` en C permite calcular la tangente de un ángulo dado en radianes. Esta función es parte de la biblioteca matemática estándar, lo que la convierte en una herramienta esencial para operaciones relacionadas con trigonometría en programación.

## Documentación
La función `tan` se declara en el encabezado `<math.h>`. Su propósito principal es devolver la tangente del valor de entrada (ángulo) proporcionado en radianes. La sintaxis de la función es la siguiente:

```c
#include <math.h>
double tan(double x);
```

### Parámetros
- `x`: El ángulo en radianes del cual se desea calcular la tangente.

### Valor de retorno
La función devuelve un valor de tipo `double`, que representa la tangente del ángulo especificado. Si el argumento es un valor no numérico (NaN), el resultado también será NaN. Además, si el argumento es un múltiplo impar de π/2, el resultado será infinito positivo o negativo, dependiendo del signo del argumento.

## Ejemplos
A continuación, se presentan algunos ejemplos de uso de la función `tan`:

### Ejemplo 1: Calcular la tangente de 0 radianes
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = 0.0;
    printf("La tangente de %f radianes es: %f\n", angulo, tan(angulo));
    return 0;
}
```
**Salida:**
```
La tangente de 0.000000 radianes es: 0.000000
```

### Ejemplo 2: Calcular la tangente de π/4 radianes
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = M_PI / 4; // π/4 radianes
    printf("La tangente de %f radianes es: %f\n", angulo, tan(angulo));
    return 0;
}
```
**Salida:**
```
La tangente de 0.785398 radianes es: 1.000000
```

### Ejemplo 3: Calcular la tangente de π/2 radianes
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = M_PI / 2; // π/2 radianes
    printf("La tangente de %f radianes es: %f\n", angulo, tan(angulo));
    return 0;
}
```
**Salida:**
```
La tangente de 1.570796 radianes es: inf
```

## Explicación
Es importante tener en cuenta que la función `tan` espera el ángulo en radianes, no en grados. Para convertir grados a radianes, se puede utilizar la fórmula:

```c
radianes = grados * (M_PI / 180);
```

Además, los valores que resultan en la tangente de π/2 + n * π (donde n es un entero) son indefinidos y devolverán infinito. Esto puede causar problemas si no se maneja adecuadamente en el código, así que se recomienda verificar los valores de entrada.

## Resumen en una línea
La función `tan` en C calcula la tangente de un ángulo en radianes y es fundamental para operaciones trigonométricas.