<!--
Meta Description: # isdigit: Función de C para Comprobar Dígitos ## Sinopsis La función `isdigit` en C se utiliza para determinar si un carácter específico es un dígito...
Meta Keywords: isdigit, carácter, que, dígito, valor
-->

# isdigit: Función de C para Comprobar Dígitos

## Sinopsis
La función `isdigit` en C se utiliza para determinar si un carácter específico es un dígito decimal (0-9). Es parte de la biblioteca estándar de C y se incluye en `<ctype.h>`.

## Documentación
### Propósito
La función `isdigit` tiene como objetivo facilitar la validación de caracteres para determinar si un carácter dado es uno de los dígitos decimales válidos. Esto es particularmente útil en la manipulación de cadenas que contienen números o en la validación de entradas del usuario.

### Uso
La función se utiliza de la siguiente manera:

```c
#include <ctype.h>

int isdigit(int c);
```

#### Parámetros
- `c`: El carácter a evaluar, que se pasa como un valor entero. Este valor generalmente representa el carácter en forma de su código ASCII.

#### Valor de Retorno
- Devuelve un valor distinto de cero (verdadero) si el carácter es un dígito (0-9).
- Devuelve 0 (falso) si el carácter no es un dígito.

### Detalles
- La función `isdigit` es parte del estándar ANSI C y debe incluirse mediante el encabezado `<ctype.h>`.
- Es importante pasar valores enteros a `isdigit`, ya que puede comportarse de manera indefinida si se pasa un valor que no es un carácter válido.

## Ejemplos
A continuación se presentan algunos ejemplos de uso de la función `isdigit`:

### Ejemplo 1: Comprobación simple
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char c = '5';
    
    if (isdigit(c)) {
        printf("%c es un dígito.\n", c);
    } else {
        printf("%c no es un dígito.\n", c);
    }
    
    return 0;
}
```

### Ejemplo 2: Comprobación de varios caracteres
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[] = "abc123";
    
    for (int i = 0; str[i] != '\0'; i++) {
        if (isdigit(str[i])) {
            printf("%c es un dígito.\n", str[i]);
        }
    }
    
    return 0;
}
```

### Ejemplo 3: Uso de valores enteros
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    int num = '8'; // Código ASCII del carácter '8'
    
    if (isdigit(num)) {
        printf("El carácter correspondiente a %d es un dígito.\n", num);
    }

    return 0;
}
```

## Explicación
Un error común al usar `isdigit` es pasar caracteres que no están dentro del rango de valores de ASCII o caracteres no válidos, lo que puede llevar a resultados indeseados. Además, se debe tener en cuenta que `isdigit` evalúa caracteres en su forma entera, por lo que es importante no confundir el valor del carácter con su código ASCII. Por ejemplo, el carácter '0' tiene un valor ASCII de 48, y el carácter '9' tiene un valor de 57.

Es recomendable evitar la evaluación de valores negativos o valores superiores a 255, ya que el comportamiento puede ser indefinido, especialmente en sistemas donde los caracteres son representados por valores de 8 bits.

## Resumen en una línea
La función `isdigit` en C permite verificar si un carácter es un dígito decimal, facilitando la validación de entradas en programas.