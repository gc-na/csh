<!--
Meta Description: # strtok en C: Una Guía Completa para la Manipulación de Cadenas ## Sinopsis La función `strtok` es utilizada en el lenguaje de programación C para di...
Meta Keywords: strtok, cadena, token, delimitadores, una
-->

# strtok en C: Una Guía Completa para la Manipulación de Cadenas

## Sinopsis
La función `strtok` es utilizada en el lenguaje de programación C para dividir una cadena en tokens, facilitando la manipulación y análisis de cadenas de texto. Es especialmente útil para procesar entradas de texto delimitadas.

## Documentación
La función `strtok` se define en la biblioteca estándar `<string.h>`. Su propósito es dividir una cadena en múltiples subcadenas o "tokens", basándose en un conjunto de delimitadores especificados por el usuario.

### Prototipo
```c
char *strtok(char *str, const char *delim);
```

### Parámetros
- **str**: La cadena que se desea dividir en tokens. En la primera llamada a `strtok`, este parámetro debe apuntar a la cadena completa. En las llamadas subsiguientes, debe ser `NULL`.
- **delim**: Una cadena que contiene todos los caracteres delimitadores. `strtok` considera cualquier carácter en esta cadena como un posible delimitador.

### Valor de Retorno
Retorna un puntero al primer token encontrado en la cadena. Si no hay más tokens, retorna `NULL`.

### Uso y Detalles
1. **Primera llamada**: Se pasa la cadena original y los delimitadores.
2. **Llamadas subsiguientes**: Se pasa `NULL` y `strtok` continuará desde el último token encontrado.
3. **Modificación de la cadena**: `strtok` reemplaza los delimitadores en la cadena original con el carácter nulo (`\0`), lo que significa que la cadena original se modifica.

## Ejemplos
### Ejemplo básico de uso
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hola, mundo! Bienvenido a C.";
    char *token;

    // Obtener el primer token
    token = strtok(str, " ,.!");

    // Continuar obteniendo tokens
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ,.!");
    }
    
    return 0;
}
```
**Salida:**
```
Hola
mundo
Bienvenido
a
C
```

### Ejemplo con múltiples delimitadores
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "C;programming:language,examples";
    char *token;

    token = strtok(str, ";:,");

    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, ";:,");
    }

    return 0;
}
```
**Salida:**
```
C
programming
language
examples
```

## Explicación
### Errores Comunes y Notas
- **Modificación de la cadena**: Dado que `strtok` modifica la cadena original, si se necesita conservarla, se debe hacer una copia antes de usar `strtok`.
- **Uso de múltiples hilos**: `strtok` no es seguro para hilos. Para un uso seguro en entornos multihilo, se puede considerar `strtok_r`, que es una versión reentrante.
- **Delimitadores consecutivos**: Si hay delimitadores consecutivos, `strtok` devolverá tokens vacíos. Se debe tener cuidado si esto no es el comportamiento deseado.

## Resumen en una línea
La función `strtok` en C permite dividir cadenas en tokens utilizando delimitadores especificados, modificando la cadena original.