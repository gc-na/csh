<!--
Meta Description: # La instrucción "do" en C: Uso y Ejemplos ## Sinopsis La instrucción `do` en C es parte de la estructura de control de bucle `do-while`, que permite ...
Meta Keywords: que, una, condición, while, bucle
-->

# La instrucción "do" en C: Uso y Ejemplos

## Sinopsis
La instrucción `do` en C es parte de la estructura de control de bucle `do-while`, que permite ejecutar un bloque de código al menos una vez, y luego repetirlo mientras se cumpla una condición específica.

## Documentación
La instrucción `do` se utiliza en la construcción de un bucle `do-while`, que es una de las formas de iteración en el lenguaje de programación C. La sintaxis básica es:

```c
do {
    // Bloque de código a ejecutar
} while (condición);
```

### Propósito
El propósito del bucle `do-while` es garantizar que el código dentro del bloque se ejecute al menos una vez, independientemente de la condición. Esto es útil cuando se necesita que una acción se realice antes de validar una condición.

### Uso
1. **Inicialización**: Se inicializa el bucle con la instrucción `do`.
2. **Ejecución del bloque**: Se ejecuta el bloque de código una vez.
3. **Condición**: Después de la ejecución del bloque, se evalúa la condición especificada en la cláusula `while`.
4. **Repetición**: Si la condición es verdadera (diferente de cero), el bucle se repite desde el inicio.

## Ejemplos

### Ejemplo Básico
A continuación se muestra un ejemplo básico de un bucle `do-while` que imprime los números del 1 al 5:

```c
#include <stdio.h>

int main() {
    int i = 1;

    do {
        printf("%d\n", i);
        i++;
    } while (i <= 5);

    return 0;
}
```

### Ejemplo con Condición
En este ejemplo, se solicita al usuario que ingrese un número y se repite hasta que el usuario ingrese un número negativo:

```c
#include <stdio.h>

int main() {
    int numero;

    do {
        printf("Ingrese un número (negativo para salir): ");
        scanf("%d", &numero);
    } while (numero >= 0);

    return 0;
}
```

## Explicación
Algunos puntos a considerar al usar la instrucción `do` son:

- **Ejecución Mínima**: El bloque de código se ejecuta al menos una vez, lo que lo diferencia de un bucle `while`, que puede no ejecutarse en absoluto si la condición es falsa desde el principio.
- **Uso de Punto y Coma**: Es importante recordar que se debe incluir un punto y coma al final de la cláusula `while`.
- **Precaución con Condiciones**: Asegúrate de que la condición eventualmente se volverá falsa; de lo contrario, se creará un bucle infinito, lo que puede causar que el programa se cuelgue.

## Resumen en una línea
La instrucción `do` en C permite ejecutar un bloque de código al menos una vez y repetirlo mientras se cumpla una condición especificada.