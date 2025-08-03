<!--
Meta Description: # strncpy: La Función de Copia Segura de C ## Sinopsis La función `strncpy` en C se utiliza para copiar una cadena de caracteres (string) de una fuent...
Meta Keywords: destino, origen, cadena, una, que
-->

# strncpy: La Función de Copia Segura de C

## Sinopsis
La función `strncpy` en C se utiliza para copiar una cadena de caracteres (string) de una fuente a un destino, proporcionando una forma segura de evitar desbordamientos de búfer.

## Documentación

### Propósito
`strncpy` es parte de la biblioteca estándar de C y se utiliza para copiar hasta un número específico de caracteres de una cadena de origen a una cadena de destino. Es útil para manejar cadenas de longitud variable y prevenir vulnerabilidades de seguridad que pueden surgir de copias de cadenas sin control de longitud.

### Uso
La declaración de la función es la siguiente:

```c
char *strncpy(char *destino, const char *origen, size_t n);
```

- **destino**: Puntero a la cadena de destino donde se copiarán los caracteres.
- **origen**: Puntero a la cadena de origen que se desea copiar.
- **n**: Número máximo de caracteres a copiar de la cadena de origen.

### Detalles
- La función copia hasta `n` caracteres de la cadena `origen` a `destino`.
- Si la longitud de `origen` es menor que `n`, se rellenará el resto de `destino` con caracteres nulos (`'\0'`).
- Si la longitud de `origen` es igual o mayor que `n`, `destino` no se nulifica, lo que puede llevar a problemas si `destino` se utiliza como una cadena después de la copia.
- Es importante asegurarse de que `destino` tenga suficiente espacio para almacenar los caracteres copiados y el carácter nulo.

## Ejemplos

### Ejemplo básico de uso

```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[20];
    const char *origen = "Hola Mundo";

    strncpy(destino, origen, sizeof(destino) - 1);
    destino[sizeof(destino) - 1] = '\0'; // Asegurar el nulo al final

    printf("Cadena copiada: %s\n", destino);
    return 0;
}
```

### Ejemplo de copiado truncado

```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[5];
    const char *origen = "Hola Mundo";

    strncpy(destino, origen, sizeof(destino)); // Copia solo 4 caracteres

    printf("Cadena copiada: %s\n", destino); // Salida: "Hol"
    return 0;
}
```

## Explicación

### Problemas Comunes
1. **No nulificar el destino**: Si `origen` es más larga que `n`, el destino no se nulificará automáticamente. Es responsabilidad del programador asegurarse de que `destino` se termina con un carácter nulo para evitar comportamientos indefinidos al imprimir o manipular la cadena.
   
2. **Tamaño insuficiente**: Si el tamaño del búfer `destino` es menor que `n`, puede provocar un desbordamiento de búfer, lo cual es un grave problema de seguridad.

3. **Confusión con la longitud**: `strncpy` no garantiza que el destino sea una cadena válida si `origen` tiene una longitud igual o mayor a `n`. Esto puede causar errores sutiles en el manejo de cadenas.

## Resumen en una línea
`strncpy` es una función de C que copia de manera segura hasta n caracteres de una cadena de origen a una de destino, asegurando la gestión de la memoria y evitando desbordamientos.