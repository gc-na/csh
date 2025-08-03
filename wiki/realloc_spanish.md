<!--
Meta Description: # Realloc: Redimensionamiento de Memoria en C ## Sinopsis `realloc` es una función en C utilizada para redimensionar un bloque de memoria previamente ...
Meta Keywords: memoria, realloc, bloque, int, que
-->

# Realloc: Redimensionamiento de Memoria en C

## Sinopsis
`realloc` es una función en C utilizada para redimensionar un bloque de memoria previamente asignado. Permite ajustar el tamaño de un bloque de memoria dinámicamente, facilitando la gestión eficiente de la memoria en aplicaciones.

## Documentación
La función `realloc` se incluye en la biblioteca estándar de C mediante `#include <stdlib.h>`. Su propósito es cambiar el tamaño de un bloque de memoria que ha sido previamente asignado con `malloc` o `calloc`, o que ha sido redimensionado con `realloc` anteriormente.

### Prototipo
```c
void* realloc(void* ptr, size_t size);
```

### Parámetros
- `ptr`: Un puntero al bloque de memoria que se desea redimensionar. Si `ptr` es NULL, se comporta como `malloc`.
- `size`: El nuevo tamaño en bytes del bloque de memoria. Si `size` es 0 y `ptr` no es NULL, se comporta como `free`.

### Valor de Retorno
- Devuelve un puntero al nuevo bloque de memoria redimensionado. 
- Si se produce un error de asignación, devuelve NULL y el bloque de memoria original permanece sin cambios.

## Ejemplos

### Ejemplo 1: Redimensionando un bloque de memoria
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int* arr = (int*)malloc(5 * sizeof(int));  // Asignar memoria para 5 enteros

    // Inicializar el arreglo
    for (int i = 0; i < 5; i++) {
        arr[i] = i + 1;
    }

    // Redimensionar el arreglo a 10 enteros
    arr = (int*)realloc(arr, 10 * sizeof(int));

    // Comprobar si realloc fue exitoso
    if (arr != NULL) {
        for (int i = 5; i < 10; i++) {
            arr[i] = i + 1; // Inicializar nuevos elementos
        }
    }

    // Imprimir el arreglo
    for (int i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }

    free(arr); // Liberar memoria
    return 0;
}
```

### Ejemplo 2: Redimensionando a un tamaño menor
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char* buffer = (char*)malloc(20 * sizeof(char)); // Asignar memoria

    // Asignar un nuevo tamaño más pequeño
    buffer = (char*)realloc(buffer, 10 * sizeof(char));

    if (buffer != NULL) {
        // Usar el buffer redimensionado
        snprintf(buffer, 10, "Hola");
        printf("%s\n", buffer);
    }

    free(buffer); // Liberar memoria
    return 0;
}
```

## Explicación
Al utilizar `realloc`, es importante tener en cuenta algunas consideraciones:

- **Pérdida de Puntero:** Si `realloc` falla y devuelve NULL, el puntero original se pierde, lo que puede causar una fuga de memoria. Es recomendable asignar el resultado de `realloc` a un puntero temporal antes de sobrescribir el puntero original.
  
- **Desbordamiento de Memoria:** Si se redimensiona un bloque de memoria a un tamaño menor, los datos en el nuevo tamaño pueden ser truncados. Por lo tanto, siempre asegúrese de que los datos que necesita se mantengan dentro de los límites del nuevo tamaño.

- **Seguridad de la Memoria:** Asegúrese de que el bloque de memoria no sea liberado antes de redimensionarlo, ya que esto provocará un comportamiento indefinido.

## Resumen en una Línea
`realloc` es una función en C que permite redimensionar bloques de memoria dinámicamente, facilitando la gestión eficiente de la memoria.