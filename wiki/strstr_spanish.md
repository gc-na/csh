<!--
Meta Description: # strstr: Función para la búsqueda de subcadenas en C ## Sinopsis La función `strstr` en C permite localizar la primera ocurrencia de una subcadena de...
Meta Keywords: subcadena, cadena, una, strstr, char
-->

# strstr: Función para la búsqueda de subcadenas en C

## Sinopsis
La función `strstr` en C permite localizar la primera ocurrencia de una subcadena dentro de una cadena, facilitando la búsqueda de texto y manipulación de cadenas.

## Documentación
### Propósito
La función `strstr` es parte de la biblioteca estándar de C, definida en `<string.h>`. Su principal objetivo es devolver un puntero a la primera aparición de una subcadena en una cadena dada. Si la subcadena no se encuentra, devuelve un puntero nulo.

### Uso
La declaración de la función es la siguiente:

```c
char *strstr(const char *haystack, const char *needle);
```

- **haystack**: La cadena en la que se busca.
- **needle**: La subcadena que se desea encontrar.

### Detalles
- Si `needle` es una cadena vacía, `strstr` devuelve `haystack`.
- Si `needle` no se encuentra en `haystack`, se devuelve `NULL`.
- La búsqueda es sensible a mayúsculas y minúsculas.
- La función utiliza la comparación de caracteres en base a sus valores ASCII.

## Ejemplos
### Ejemplo 1: Búsqueda simple de subcadena
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena = "Hola, mundo";
    const char *subcadena = "mundo";
    char *resultado = strstr(cadena, subcadena);
    
    if (resultado) {
        printf("Subcadena encontrada: %s\n", resultado);
    } else {
        printf("Subcadena no encontrada.\n");
    }

    return 0;
}
```

### Ejemplo 2: Subcadena no presente
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena = "Hola, mundo";
    const char *subcadena = "adiós";
    char *resultado = strstr(cadena, subcadena);
    
    if (resultado) {
        printf("Subcadena encontrada: %s\n", resultado);
    } else {
        printf("Subcadena no encontrada.\n");
    }

    return 0;
}
```

## Explicación
Al utilizar `strstr`, es importante tener en cuenta los siguientes puntos:

- **Sensibilidad a mayúsculas**: La función no ignora las diferencias entre mayúsculas y minúsculas, por lo que "Mundo" y "mundo" se consideran diferentes.
- **Cadena vacía**: Pasar una cadena vacía como `needle` siempre devolverá la cadena original `haystack`.
- **Puntero nulo**: Siempre verifica si el resultado es `NULL` para evitar errores en tiempo de ejecución al intentar acceder a una ubicación de memoria no válida.

## Resumen en una línea
La función `strstr` en C permite buscar la primera aparición de una subcadena en una cadena, devolviendo un puntero a su ubicación o NULL si no se encuentra.