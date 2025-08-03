<!--
Meta Description: # strrchr: Función de C para Buscar el Último Caracter en una Cadena ## Sinopsis La función `strrchr` de la biblioteca estándar de C se utiliza para l...
Meta Keywords: cadena, carácter, strrchr, función, una
-->

# strrchr: Función de C para Buscar el Último Caracter en una Cadena

## Sinopsis
La función `strrchr` de la biblioteca estándar de C se utiliza para localizar la última aparición de un carácter específico en una cadena de caracteres. Es una herramienta valiosa para la manipulación de cadenas, permitiendo búsquedas eficientes en textos.

## Documentación

### Propósito
`strrchr` forma parte de la biblioteca `<string.h>` y se emplea para buscar el último carácter en una cadena de tipo `char*`. Esta función es fundamental en situaciones donde se necesita encontrar la última ocurrencia de un carácter, como en la manipulación de rutas de archivos o en el análisis de texto.

### Uso
La función se declara de la siguiente manera:

```c
char *strrchr(const char *s, int c);
```

- **s**: Es un puntero a la cadena de caracteres en la que se realizará la búsqueda.
- **c**: Es el carácter que se desea buscar, pasado como un entero, que se convertirá a un carácter.

### Detalles
- Retorna un puntero a la última aparición del carácter `c` en la cadena `s`.
- Si el carácter no se encuentra, la función devuelve `NULL`.
- La búsqueda es sensible a mayúsculas y minúsculas.
- La cadena de entrada debe estar terminada en un carácter nulo (`\0`).

## Ejemplos

### Ejemplo 1: Uso básico de `strrchr`

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena = "Hola, mundo!";
    char *resultado = strrchr(cadena, 'o');

    if (resultado != NULL) {
        printf("Última aparición de 'o': %s\n", resultado);
    } else {
        printf("'o' no encontrado.\n");
    }

    return 0;
}
```

### Ejemplo 2: Buscar un carácter que no está presente

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena = "Ejemplo de cadena";
    char *resultado = strrchr(cadena, 'z');

    if (resultado != NULL) {
        printf("Última aparición de 'z': %s\n", resultado);
    } else {
        printf("'z' no encontrado.\n");
    }

    return 0;
}
```

## Explicación
Al usar `strrchr`, es importante tener en cuenta lo siguiente:

- **Sensibilidad a mayúsculas**: La función no distingue entre 'a' y 'A', por lo que si se busca 'A', no se encontrará 'a'.
- **Cadena nula**: Si se pasa una cadena que no está correctamente terminada con un carácter nulo, el comportamiento de la función puede ser indefinido.
- **Punteros**: El valor de retorno es un puntero a la posición del carácter encontrado, por lo que se puede manipular fácilmente la cadena a partir de allí.

## Resumen en una línea
`strrchr` es una función de C que busca la última aparición de un carácter en una cadena, devolviendo un puntero a su ubicación o `NULL` si no se encuentra.