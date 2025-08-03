<!--
Meta Description: # Comparación de Cadenas en C: Uso de strncmp ## Sinopsis `strncmp` es una función del lenguaje de programación C que permite comparar dos cadenas de ...
Meta Keywords: caracteres, cadenas, que, strncmp, las
-->

# Comparación de Cadenas en C: Uso de strncmp

## Sinopsis
`strncmp` es una función del lenguaje de programación C que permite comparar dos cadenas de caracteres hasta un número específico de caracteres. Es útil para la comparación segura de cadenas y evita problemas de desbordamiento de búfer.

## Documentación
### Propósito
La función `strncmp` se utiliza para comparar un número determinado de caracteres de dos cadenas. Esta comparación es segura y puede ser utilizada para determinar el orden lexicográfico entre las cadenas.

### Uso
La función `strncmp` se incluye en el encabezado `<string.h>` y su prototipo es el siguiente:

```c
int strncmp(const char *str1, const char *str2, size_t n);
```

### Parámetros
- **str1**: Primer puntero a la cadena de caracteres a comparar.
- **str2**: Segundo puntero a la cadena de caracteres a comparar.
- **n**: Número máximo de caracteres a comparar.

### Retorno
- Devuelve un valor menor que 0 si `str1` es menor que `str2`.
- Devuelve 0 si son iguales.
- Devuelve un valor mayor que 0 si `str1` es mayor que `str2`.

## Ejemplos
### Ejemplo 1: Comparación básica
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena1 = "Hola";
    const char *cadena2 = "Hola Mundo";
    
    int resultado = strncmp(cadena1, cadena2, 4); // Compara solo los primeros 4 caracteres
    if (resultado == 0) {
        printf("Las cadenas son iguales en los primeros 4 caracteres.\n");
    } else {
        printf("Las cadenas son diferentes en los primeros 4 caracteres.\n");
    }
    return 0;
}
```

### Ejemplo 2: Diferentes longitudes
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena1 = "ABC";
    const char *cadena2 = "ABCD";
    
    int resultado = strncmp(cadena1, cadena2, 3); // Compara los primeros 3 caracteres
    if (resultado == 0) {
        printf("Las cadenas son iguales en los primeros 3 caracteres.\n");
    } else {
        printf("Las cadenas son diferentes en los primeros 3 caracteres.\n");
    }
    return 0;
}
```

## Explicación
Al utilizar `strncmp`, es importante tener en cuenta que la comparación se realiza solo hasta el número de caracteres especificado, incluso si una cadena es más larga que la otra. Esto significa que si `n` es menor que la longitud de una de las cadenas, solo se compararán los primeros `n` caracteres. 

También hay que tener cuidado con las cadenas nulas. Si alguna de las cadenas pasadas a `strncmp` es un puntero nulo, el comportamiento es indefinido. Asegúrate siempre de que las cadenas sean válidas antes de hacer la comparación.

## Resumen en una línea
La función `strncmp` en C permite comparar de manera segura dos cadenas de caracteres hasta un número específico de caracteres, facilitando la gestión de comparaciones sin riesgo de desbordamiento.