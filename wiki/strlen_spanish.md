<!--
Meta Description: # strlen en C: Función para Medir la Longitud de Cadenas de Caracteres ## Sinopsis La función `strlen` en C se utiliza para calcular la longitud de un...
Meta Keywords: cadena, longitud, strlen, que, nulo
-->

# strlen en C: Función para Medir la Longitud de Cadenas de Caracteres

## Sinopsis
La función `strlen` en C se utiliza para calcular la longitud de una cadena de caracteres, devolviendo el número de caracteres presentes en la cadena, excluyendo el carácter nulo (`'\0'`) que indica su final.

## Documentación

### Propósito
La función `strlen` forma parte de la biblioteca estándar de C, definida en el encabezado `<string.h>`. Su propósito principal es proporcionar a los programadores una manera eficiente de determinar cuántos caracteres hay en una cadena, lo que es fundamental para tareas como la manipulación de cadenas y la gestión de memoria.

### Uso
La sintaxis para utilizar `strlen` es la siguiente:

```c
#include <string.h>

size_t strlen(const char *str);
```

- `str`: Un puntero a la cadena de caracteres cuya longitud se desea calcular.
- **Valor de retorno**: Devuelve un valor de tipo `size_t`, que representa la longitud de la cadena sin contar el carácter nulo.

### Detalles
Es importante notar que `strlen` solo cuenta caracteres hasta que encuentra el carácter nulo. Si la cadena es nula (es decir, el puntero `str` es `NULL`), el comportamiento de `strlen` es indefinido y puede provocar errores en tiempo de ejecución. Por lo tanto, siempre se debe asegurar que el puntero no sea nulo antes de llamar a esta función.

## Ejemplos

### Ejemplo 1: Uso básico de `strlen`

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena = "Hola, mundo!";
    size_t longitud = strlen(cadena);
    printf("La longitud de la cadena es: %zu\n", longitud);
    return 0;
}
```

**Salida:**
```
La longitud de la cadena es: 13
```

### Ejemplo 2: Longitud de una cadena vacía

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadenaVacia = "";
    size_t longitud = strlen(cadenaVacia);
    printf("La longitud de la cadena vacía es: %zu\n", longitud);
    return 0;
}
```

**Salida:**
```
La longitud de la cadena vacía es: 0
```

## Explicación
Al usar `strlen`, hay algunas consideraciones importantes a tener en cuenta:

- **Cadena nula**: Si se pasa un puntero nulo a `strlen`, el programa puede fallar o comportarse de manera inesperada. Siempre verifique que el puntero no sea nulo.
- **Rendimiento**: La función recorre cada carácter de la cadena hasta encontrar el carácter nulo, por lo que su complejidad temporal es O(n), donde n es la longitud de la cadena.
- **Uso de `size_t`**: El tipo `size_t` es un tipo de datos sin signo que es adecuado para representar tamaños y longitudes. Es recomendable usarlo para almacenar la longitud devuelta por `strlen`.

## Resumen en una línea
La función `strlen` en C se utiliza para calcular la longitud de una cadena de caracteres, excluyendo el carácter nulo al final.