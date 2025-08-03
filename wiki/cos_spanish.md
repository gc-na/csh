<!--
Meta Description: # Función cos en C: Cálculo del Coseno en Programación ## Sinopsis La función `cos` en C es utilizada para calcular el coseno de un ángulo dado en rad...
Meta Keywords: cos, coseno, radianes, función, include
-->

# Función cos en C: Cálculo del Coseno en Programación

## Sinopsis
La función `cos` en C es utilizada para calcular el coseno de un ángulo dado en radianes. Forma parte de la biblioteca matemática estándar de C, lo que la hace esencial para operaciones trigonométricas en cálculos científicos y de ingeniería.

## Documentación
La función `cos` está definida en la biblioteca `<math.h>`. Su propósito principal es devolver el valor del coseno de un número, que debe ser proporcionado en radianes.

### Prototipo
```c
#include <math.h>
double cos(double x);
```

### Parámetros
- `x`: Un valor de tipo `double` que representa el ángulo en radianes.

### Valor de retorno
La función devuelve el coseno del ángulo proporcionado, también de tipo `double`. El rango de salida es de -1 a 1.

### Inclusión de la biblioteca
Para utilizar `cos`, es necesario incluir la biblioteca matemática al inicio del programa:
```c
#include <math.h>
```

### Compilación
Al compilar un programa que utiliza funciones matemáticas, es importante enlazar la biblioteca matemática utilizando el flag `-lm` en GCC:
```bash
gcc -o mi_programa mi_programa.c -lm
```

## Ejemplos
A continuación se presentan algunos ejemplos básicos de uso de la función `cos`:

### Ejemplo 1: Cálculo del coseno de 0
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = 0.0;
    printf("El coseno de %.2f radianes es: %.2f\n", angulo, cos(angulo));
    return 0;
}
```

### Ejemplo 2: Cálculo del coseno de π/3
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = M_PI / 3; // 60 grados en radianes
    printf("El coseno de π/3 radianes es: %.2f\n", cos(angulo));
    return 0;
}
```

### Ejemplo 3: Cálculo del coseno de 1 radian
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = 1.0; // 1 radian
    printf("El coseno de 1 radian es: %.2f\n", cos(angulo));
    return 0;
}
```

## Explicación
Al utilizar la función `cos`, es importante recordar que:
- El ángulo debe ser proporcionado en radianes, no en grados. Para convertir grados a radianes, se puede usar la fórmula:
  \[
  \text{radianes} = \text{grados} \times \frac{\pi}{180}
  \]
- La función puede devolver un resultado de precisión limitada debido a la naturaleza de los cálculos en punto flotante. Esto puede resultar en pequeñas imprecisiones en ciertos casos.
- Asegúrate de incluir la biblioteca `<math.h>` y utilizar el flag `-lm` al compilar, o de lo contrario, el compilador no reconocerá la función.

## Resumen en una línea
La función `cos` en C calcula el coseno de un ángulo en radianes, siendo esencial para cualquier cálculo que requiera funciones trigonométricas.