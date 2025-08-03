<!--
Meta Description: # strcpy en C: Copia de Cadenas de Caracteres ## Sinopsis `strcpy` es una función de la biblioteca estándar de C que se utiliza para copiar una cadena...
Meta Keywords: destino, que, cadena, fuente, strcpy
-->

# strcpy en C: Copia de Cadenas de Caracteres

## Sinopsis
`strcpy` es una función de la biblioteca estándar de C que se utiliza para copiar una cadena de caracteres de una fuente a un destino. Es fundamental en la manipulación de cadenas y se encuentra en `<string.h>`.

## Documentación
La función `strcpy` tiene la siguiente firma:

```c
char *strcpy(char *destino, const char *fuente);
```

### Propósito
El propósito de `strcpy` es transferir una cadena de caracteres desde la variable `fuente` a la variable `destino`. Esto incluye el carácter nulo (`\0`) que indica el final de la cadena.

### Uso
Para utilizar `strcpy`, primero debes incluir la cabecera `<string.h>` en tu programa. La función toma dos argumentos:
- `destino`: Un puntero a la cadena en la que se va a copiar el contenido.
- `fuente`: Un puntero a la cadena que se va a copiar.

### Detalles
- La función `strcpy` devuelve un puntero al destino.
- No realiza una verificación de límites, por lo que es responsabilidad del programador asegurarse de que el destino tenga suficiente espacio para almacenar la cadena fuente.
- Si la cadena fuente es más larga que la capacidad del destino, esto puede provocar un desbordamiento de búfer, lo que puede llevar a comportamientos indefinidos.

## Ejemplos

### Ejemplo 1: Copia Simple
```c
#include <stdio.h>
#include <string.h>

int main() {
    char fuente[] = "Hola, Mundo!";
    char destino[50];  // Asegúrate de que el destino tenga suficiente espacio

    strcpy(destino, fuente);
    printf("Cadena Copiada: %s\n", destino);

    return 0;
}
```

### Ejemplo 2: Copia de una Cadena Vacía
```c
#include <stdio.h>
#include <string.h>

int main() {
    char fuente[] = "";
    char destino[50];

    strcpy(destino, fuente);
    printf("Cadena Copiada: '%s'\n", destino); // Debería imprimir una cadena vacía

    return 0;
}
```

## Explicación
Al usar `strcpy`, es crucial tener en cuenta lo siguiente:

- **Desbordamiento de búfer**: Si la longitud de la cadena `fuente` es mayor que la capacidad de `destino`, se sobrescribirá el espacio de memoria adyacente, lo que puede causar errores o vulnerabilidades de seguridad.
- **Cadena Nula**: Asegúrate de que `fuente` esté correctamente terminada con un carácter nulo para evitar comportamientos inesperados.
- **Uso de `strncpy`**: Considera usar `strncpy` si deseas limitar la cantidad de caracteres que se copian, lo que puede ayudar a prevenir desbordamientos.

## Resumen en Una Línea
La función `strcpy` en C es utilizada para copiar cadenas de caracteres, pero requiere precaución para evitar desbordamientos de búfer.