<!--
Meta Description: # strncat en C: Concatenación Segura de Cadenas ## Sinopsis `strncat` es una función de la biblioteca estándar de C que permite concatenar un número e...
Meta Keywords: destino, que, strncat, cadena, fuente
-->

# strncat en C: Concatenación Segura de Cadenas

## Sinopsis
`strncat` es una función de la biblioteca estándar de C que permite concatenar un número específico de caracteres de una cadena a otra. Es útil para evitar desbordamientos de búfer, asegurando que no se exceda la longitud del destino.

## Documentación
### Propósito
La función `strncat` se utiliza para añadir una cantidad limitada de caracteres de una cadena a otra, garantizando que la cadena resultante no exceda el tamaño del búfer de destino.

### Uso
```c
char *strncat(char *destino, const char *fuente, size_t n);
```

#### Parámetros
- `destino`: Apuntador a la cadena de destino a la que se le agregarán caracteres.
- `fuente`: Apuntador a la cadena fuente desde la cual se copiarán los caracteres.
- `n`: Número máximo de caracteres a copiar desde la cadena fuente.

#### Detalles
- La función `strncat` añade caracteres de `fuente` a `destino` comenzando desde el final de `destino`.
- La cadena `destino` debe tener suficiente espacio para contener la concatenación de ambas cadenas, incluyendo el carácter nulo ('\0') que marca el final de la cadena.
- `strncat` siempre agrega un carácter nulo al final de la cadena resultante.

## Ejemplos
### Ejemplo básico
```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[20] = "Hola";
    const char *fuente = " Mundo";
    
    strncat(destino, fuente, 6); // Se concatenan hasta 6 caracteres
    printf("%s\n", destino); // Salida: Hola Mundo

    return 0;
}
```

### Ejemplo con límite
```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[10] = "Hola";
    const char *fuente = " Mundo";
    
    strncat(destino, fuente, 3); // Se concatenan solo 3 caracteres
    printf("%s\n", destino); // Salida: Hola Mun

    return 0;
}
```

## Explicación
### Errores Comunes
1. **Buffer Overflow**: Si la cadena de destino no tiene suficiente espacio para almacenar la concatenación, se producirá un desbordamiento de búfer, lo que puede causar comportamientos indefinidos.
2. **No Inicializar el Destino**: Asegúrate de que la cadena de destino contenga un carácter nulo ('\0') al inicio, de lo contrario, `strncat` no funcionará como se espera.
3. **Uso Incorrecto de N**: Si `n` es mayor que la longitud de `fuente`, solo se copiarán hasta los caracteres que existan en `fuente`, lo que puede no ser el comportamiento deseado.

### Notas Adicionales
- `strncat` es parte de la biblioteca `<string.h>`, por lo que es necesario incluir esta cabecera al usar la función.
- Es recomendable utilizar `snprintf` o `strlcat` en lugar de `strncat` en aplicaciones críticas, ya que ofrecen mayor seguridad y manejo de errores.

## Resumen en Una Línea
`strncat` es una función en C que permite concatenar de forma segura un número específico de caracteres de una cadena a otra, evitando desbordamientos de búfer.