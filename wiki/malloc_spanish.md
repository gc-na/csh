<!--
Meta Description: # malloc en C: Asignación Dinámica de Memoria ## Sinopsis `malloc` es una función en C utilizada para la asignación dinámica de memoria. Permite a los...
Meta Keywords: memoria, malloc, que, int, asignación
-->

# malloc en C: Asignación Dinámica de Memoria

## Sinopsis
`malloc` es una función en C utilizada para la asignación dinámica de memoria. Permite a los programadores solicitar bloques de memoria en tiempo de ejecución, lo que es esencial para la creación de estructuras de datos flexibles.

## Documentación
### Propósito
La función `malloc` (memory allocation) se utiliza para asignar un bloque de memoria de un tamaño especificado. Esta memoria es asignada en el heap, lo que significa que es accesible durante toda la ejecución del programa hasta que se libera explícitamente.

### Uso
La sintaxis básica de `malloc` es la siguiente:

```c
void* malloc(size_t size);
```

- **size**: Especifica el número de bytes que se desean asignar.
- **return**: Devuelve un puntero al bloque de memoria asignado. Si la asignación falla, devuelve `NULL`.

### Detalles
- `malloc` no inicializa la memoria asignada; el contenido inicial es indefinido.
- Es importante comprobar si el retorno de `malloc` es `NULL` antes de usar el puntero.
- Para liberar la memoria asignada, se debe utilizar la función `free`.

## Ejemplos
### Ejemplo 1: Asignación de un entero
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr = (int*) malloc(sizeof(int));
    if (ptr == NULL) {
        printf("Error en la asignación de memoria.\n");
        return 1;
    }
    *ptr = 42;
    printf("Valor: %d\n", *ptr);
    free(ptr);
    return 0;
}
```

### Ejemplo 2: Asignación de un arreglo de enteros
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n = 5;
    int *arr = (int*) malloc(n * sizeof(int));
    if (arr == NULL) {
        printf("Error en la asignación de memoria.\n");
        return 1;
    }
    for (int i = 0; i < n; i++) {
        arr[i] = i + 1;
        printf("%d ", arr[i]);
    }
    free(arr);
    return 0;
}
```

## Explicación
### Errores Comunes
1. **No verificar la asignación**: Olvidar comprobar si `malloc` devolvió `NULL` puede causar fallos en el programa.
2. **No liberar la memoria**: Falla al usar `free` para liberar la memoria asignada, lo que puede causar fugas de memoria.
3. **Uso de memoria no inicializada**: Asumir que la memoria asignada tiene un valor definido puede llevar a comportamientos inesperados.

### Notas Adicionales
- `malloc` es parte de la biblioteca estándar de C, por lo que es necesario incluir `<stdlib.h>`.
- Recuerda que el tamaño que pases a `malloc` debe ser un valor positivo; de lo contrario, el comportamiento será indefinido.

## Resumen en una línea
`malloc` es una función en C que permite la asignación dinámica de memoria en tiempo de ejecución, esencial para la gestión eficiente de recursos en programas.