<!--
Meta Description: # La función isupper en C: Verifica si un carácter es mayúscula ## Sinopsis La función `isupper` en C se utiliza para determinar si un carácter dado e...
Meta Keywords: letra, isupper, mayúscula, una, carácter
-->

# La función isupper en C: Verifica si un carácter es mayúscula

## Sinopsis
La función `isupper` en C se utiliza para determinar si un carácter dado es una letra mayúscula del alfabeto. Esta función es parte de la biblioteca estándar de C `<ctype.h>` y es esencial para la manipulación de caracteres en programas que requieren validaciones de texto.

## Documentación

### Propósito
`isupper` permite verificar si un carácter específico, pasado como argumento, es una letra mayúscula (A-Z). Es útil en diversas aplicaciones, como validaciones de contraseñas, análisis de texto, y en cualquier situación donde se necesite distinguir entre letras mayúsculas y minúsculas.

### Uso
La función se declara en la biblioteca `<ctype.h>`, y su sintaxis es la siguiente:

```c
#include <ctype.h>

int isupper(int c);
```

#### Parámetros
- `c`: Este parámetro es el carácter que se va a evaluar. Debe ser un valor que se puede representar como un entero (por ejemplo, el valor ASCII de un carácter).

#### Valor de retorno
- Retorna un valor distinto de cero (verdadero) si `c` es una letra mayúscula.
- Retorna cero (falso) si `c` no es una letra mayúscula.

## Ejemplos

### Ejemplo 1: Verificación de un solo carácter
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char letra = 'G';
    if (isupper(letra)) {
        printf("'%c' es una letra mayúscula.\n", letra);
    } else {
        printf("'%c' no es una letra mayúscula.\n", letra);
    }
    return 0;
}
```

### Ejemplo 2: Uso en un bucle
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char texto[] = "Hola Mundo";
    for (int i = 0; texto[i] != '\0'; i++) {
        if (isupper(texto[i])) {
            printf("'%c' es una letra mayúscula.\n", texto[i]);
        }
    }
    return 0;
}
```

## Explicación
Al utilizar `isupper`, es importante tener en cuenta lo siguiente:

- **Compatibilidad**: `isupper` funciona correctamente con caracteres del alfabeto inglés. Para otros alfabetos, se debe tener cuidado, ya que la función puede no comportarse como se espera.
- **Valor de entrada**: Asegúrate de pasar un entero que represente un carácter, ya que pasar valores fuera del rango de caracteres puede llevar a resultados inesperados.
- **No se limita a caracteres ASCII**: Aunque comúnmente se usa con ASCII, `isupper` puede también aplicarse a otros conjuntos de caracteres, siempre y cuando se respete la codificación adecuada.

## Resumen en una línea
La función `isupper` en C verifica si un carácter dado es una letra mayúscula, retornando un valor verdadero o falso según corresponda.