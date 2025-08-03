<!--
Meta Description: # strcmp: Comparación de Cadenas en C ## Sinopsis La función `strcmp` en C es utilizada para comparar dos cadenas de caracteres. Es fundamental en la ...
Meta Keywords: cadenas, strcmp, que, cadena1, cadena2
-->

# strcmp: Comparación de Cadenas en C

## Sinopsis
La función `strcmp` en C es utilizada para comparar dos cadenas de caracteres. Es fundamental en la manipulación de cadenas y en la toma de decisiones basadas en la comparación lexical de textos.

## Documentación
La función `strcmp` se encuentra en la biblioteca estándar de C `<string.h>`. Su propósito principal es comparar dos cadenas de caracteres y determinar su orden lexicográfico.

### Propósito
`strcmp` permite determinar si dos cadenas son iguales, o cuál es mayor en términos de orden alfabético. 

### Uso
La sintaxis de la función `strcmp` es la siguiente:

```c
int strcmp(const char *str1, const char *str2);
```

- **Parámetros:**
  - `str1`: Puntero a la primera cadena.
  - `str2`: Puntero a la segunda cadena.

- **Valor de retorno:**
  - Devuelve un valor menor que cero si `str1` es menor que `str2`.
  - Devuelve cero si ambas cadenas son iguales.
  - Devuelve un valor mayor que cero si `str1` es mayor que `str2`.

### Detalles
- La comparación se realiza carácter por carácter utilizando el valor ASCII de cada carácter.
- La función es sensible a mayúsculas y minúsculas. Por ejemplo, "abc" es diferente de "ABC".
- Si alguna de las cadenas es `NULL`, el comportamiento es indefinido.

## Ejemplos

### Ejemplo 1: Comparación básica
```c
#include <stdio.h>
#include <string.h>

int main() {
    char *cadena1 = "Hola";
    char *cadena2 = "Hola";

    int resultado = strcmp(cadena1, cadena2);
    if (resultado == 0) {
        printf("Las cadenas son iguales.\n");
    } else {
        printf("Las cadenas son diferentes.\n");
    }
    return 0;
}
```

### Ejemplo 2: Comparación de cadenas diferentes
```c
#include <stdio.h>
#include <string.h>

int main() {
    char *cadena1 = "Hola";
    char *cadena2 = "Mundo";

    int resultado = strcmp(cadena1, cadena2);
    if (resultado < 0) {
        printf("'%s' es menor que '%s'.\n", cadena1, cadena2);
    } else {
        printf("'%s' es mayor que '%s'.\n", cadena1, cadena2);
    }
    return 0;
}
```

### Ejemplo 3: Comparación de cadenas con diferente caso
```c
#include <stdio.h>
#include <string.h>

int main() {
    char *cadena1 = "Hola";
    char *cadena2 = "hola";

    int resultado = strcmp(cadena1, cadena2);
    if (resultado < 0) {
        printf("'%s' es menor que '%s'.\n", cadena1, cadena2);
    } else if (resultado > 0) {
        printf("'%s' es mayor que '%s'.\n", cadena1, cadena2);
    } else {
        printf("Las cadenas son iguales.\n");
    }
    return 0;
}
```

## Explicación
Al utilizar `strcmp`, es importante tener en cuenta lo siguiente:

- **Sensibilidad a mayúsculas y minúsculas:** Como se mencionó, `strcmp` distingue entre caracteres en mayúsculas y minúsculas. Esto puede ser un problema si no se desea esta distinción. Para comparaciones insensibles, se puede usar `strcasecmp` en sistemas que lo soporten.
- **Cadenas `NULL`:** Evitar pasar cadenas nulas a `strcmp`, ya que provocará un comportamiento indefinido. Siempre asegúrate de que ambas cadenas estén inicializadas y no sean `NULL`.
- **Finalización de cadenas:** Las cadenas deben estar correctamente finalizadas con un carácter nulo (`'\0'`), ya que `strcmp` utiliza este carácter para determinar el final de la cadena.

## Resumen en una línea
La función `strcmp` en C se utiliza para comparar dos cadenas de caracteres, devolviendo un valor que indica su relación lexicográfica.