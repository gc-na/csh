<!--
Meta Description: # atan2 en C: Función Matemática para el Cálculo del Ángulo ## Sinopsis La función `atan2` en C es utilizada para calcular el arco tangente de dos var...
Meta Keywords: double, atan2, ángulo, radianes, include
-->

# atan2 en C: Función Matemática para el Cálculo del Ángulo

## Sinopsis
La función `atan2` en C es utilizada para calcular el arco tangente de dos variables, permitiendo determinar el ángulo en radianes entre el eje X y el punto (x, y) en el plano cartesiano. Es fundamental para aplicaciones que requieren el manejo de coordenadas polares.

## Documentación
La función `atan2` forma parte de la biblioteca matemática estándar `math.h`. Su propósito principal es calcular el ángulo en radianes que corresponde al punto (x, y), donde:
- `x`: coordenada en el eje horizontal.
- `y`: coordenada en el eje vertical.

### Prototipo
```c
#include <math.h>

double atan2(double y, double x);
```

### Parámetros
- `y`: Un valor de tipo `double`, representa la coordenada vertical.
- `x`: Un valor de tipo `double`, representa la coordenada horizontal.

### Valor de Retorno
La función devuelve el ángulo en radianes entre el eje X y el punto (x, y). El rango de retorno está entre `-π` y `π`.

### Comportamiento
- Si `x` es positivo, `atan2` devuelve un ángulo en el primer o cuarto cuadrante.
- Si `x` es negativo, devuelve un ángulo en el segundo o tercer cuadrante.
- Si `x` es cero, el resultado depende del valor de `y`:
  - Si `y` es positivo, devuelve `π/2`.
  - Si `y` es negativo, devuelve `-π/2`.
  - Si ambos son cero, el comportamiento no está definido.

## Ejemplos
### Ejemplo 1: Cálculo Básico
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 1.0;
    double y = 1.0;
    double angle = atan2(y, x);
    
    printf("El ángulo en radianes es: %f\n", angle);
    return 0;
}
```

### Ejemplo 2: Usando Coordenadas Negativas
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = -1.0;
    double y = 1.0;
    double angle = atan2(y, x);
    
    printf("El ángulo en radianes es: %f\n", angle);
    return 0;
}
```

### Ejemplo 3: Caso de Coordenadas en el Eje Y
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 0.0;
    double y = -1.0;
    double angle = atan2(y, x);
    
    printf("El ángulo en radianes es: %f\n", angle);
    return 0;
}
```

## Explicación
Al utilizar `atan2`, es crucial tener en cuenta que el orden de los parámetros es relevante. Intercambiar `x` y `y` cambiará el resultado del ángulo. Además, es importante considerar las posibles divisiones por cero; `atan2` maneja este caso de manera segura, pero siempre es mejor asegurarse de que las entradas sean válidas. 

Otro punto a considerar es la conversión de radianes a grados si se requiere una representación en grados. Para convertir radianes a grados, se puede utilizar la fórmula:
```c
grados = radianes * (180.0 / M_PI);
```

## Resumen en una Línea
La función `atan2` en C calcula el ángulo en radianes entre el eje X y un punto dado (x, y) en el plano cartesiano, siendo esencial para la conversión de coordenadas cartesianas a polares.