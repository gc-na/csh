<!--
Meta Description: # strcat en C: Guía Completa sobre la Concatenación de Cadenas ## Sinopsis `strcat` es una función de la biblioteca estándar de C que permite concaten...
Meta Keywords: destino, que, strcat, cadena, origen
-->

# strcat en C: Guía Completa sobre la Concatenación de Cadenas

## Sinopsis
`strcat` es una función de la biblioteca estándar de C que permite concatenar dos cadenas de caracteres. Esta función es esencial para la manipulación de textos en aplicaciones que requieren la combinación de strings.

## Documentación
La función `strcat` se encuentra en el encabezado `<string.h>` y su propósito principal es agregar el contenido de una cadena al final de otra. La sintaxis básica es la siguiente:

```c
char *strcat(char *destino, const char *origen);
```

### Parámetros
- `destino`: Puntero a la cadena de caracteres que recibirá la concatenación. Esta cadena debe tener suficiente espacio para albergar el contenido adicional.
- `origen`: Puntero a la cadena que se desea concatenar al final de la cadena de destino.

### Retorno
Devuelve un puntero a la cadena de destino.

### Funcionamiento
La función `strcat` comienza buscando el carácter nulo (`'\0'`) al final de la cadena `destino`, donde luego copia el contenido de `origen` incluyendo su carácter nulo al final. Es importante destacar que `destino` debe tener suficiente espacio para contener la cadena resultante, ya que `strcat` no realiza ninguna verificación de límite.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[50] = "Hola, ";
    char origen[] = "mundo!";
    
    strcat(destino, origen);
    printf("%s\n", destino); // Salida: Hola, mundo!
    
    return 0;
}
```

### Ejemplo con Espacio Insuficiente
```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[10] = "Hola, ";
    char origen[] = "mundo!";
    
    strcat(destino, origen); // Esto causará un comportamiento indefinido
    printf("%s\n", destino);
    
    return 0;
}
```

## Explicación
Al utilizar `strcat`, es fundamental garantizar que la cadena de `destino` tenga suficiente espacio para la concatenación. De lo contrario, se puede producir un desbordamiento de búfer, lo que puede llevar a comportamientos inesperados o vulnerabilidades de seguridad. 

### Consejos
- Siempre asegúrate de que el tamaño del arreglo `destino` sea lo suficientemente grande para contener tanto su contenido original como la cadena `origen`.
- Considera utilizar funciones más seguras como `strncat` que permiten especificar el número máximo de caracteres a concatenar, ayudando a prevenir desbordamientos.

## Resumen en Una Línea
`strcat` es una función de C que concatena dos cadenas de caracteres, pero requiere cuidado en la gestión de memoria para evitar desbordamientos.