<!--
Meta Description: # La Función `floor` en C: Redondeo hacia Abajo ## Sinopsis La función `floor` en C es utilizada para redondear un número de punto flotante hacia el e...
Meta Keywords: floor, número, función, entero, num
-->

# La Función `floor` en C: Redondeo hacia Abajo

## Sinopsis
La función `floor` en C es utilizada para redondear un número de punto flotante hacia el entero más cercano que es menor o igual al número dado. Es parte de la biblioteca estándar `math.h`.

## Documentación
La función `floor` se declara en la biblioteca `<math.h>`. Su propósito principal es proporcionar una manera sencilla de obtener el entero más bajo de un número decimal, lo que resulta útil en diversas aplicaciones matemáticas y de programación.

### Propósito
- Redondear números de punto flotante hacia abajo.

### Uso
La sintaxis de la función es la siguiente:
```c
double floor(double x);
```
- **x**: El número de punto flotante que se desea redondear.

### Detalles
- La función devuelve el entero más grande que es menor o igual a `x`, representado como un número de tipo `double`.
- Si `x` es un número entero, `floor` devolverá el mismo número.
- La función también maneja valores negativos correctamente, redondeando hacia el entero más bajo.

## Ejemplos
A continuación, se presentan algunos ejemplos de uso de la función `floor`:

### Ejemplo 1: Redondeo de un número positivo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 3.7;
    printf("El resultado de floor(%.1f) es %.1f\n", num, floor(num));
    return 0;
}
```
**Salida:**
```
El resultado de floor(3.7) es 3.0
```

### Ejemplo 2: Redondeo de un número negativo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -2.3;
    printf("El resultado de floor(%.1f) es %.1f\n", num, floor(num));
    return 0;
}
```
**Salida:**
```
El resultado de floor(-2.3) es -3.0
```

### Ejemplo 3: Uso con un número entero
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 5.0;
    printf("El resultado de floor(%.1f) es %.1f\n", num, floor(num));
    return 0;
}
```
**Salida:**
```
El resultado de floor(5.0) es 5.0
```

## Explicación
Al utilizar la función `floor`, es importante tener en cuenta que:
- Los resultados son de tipo `double`, por lo que si se necesita un valor entero, puede ser necesario realizar una conversión explícita.
- La función puede no comportarse como se espera si no se incluyen los encabezados correctos o si se olvidan las bibliotecas necesarias al compilar.
- En algunos casos, el uso de `floor` puede generar confusión con otras funciones de redondeo, como `ceil` (que redondea hacia arriba) y `round` (que redondea al entero más cercano).

## Resumen en Una Línea
La función `floor` en C redondea un número de punto flotante hacia el entero más bajo, facilitando el manejo de valores decimales en cálculos matemáticos.