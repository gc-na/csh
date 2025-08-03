<!--
Meta Description: # strchr: La Función en C para Buscar Caracteres en Cadenas ## Sinopsis La función `strchr` en C permite buscar la primera aparición de un carácter es...
Meta Keywords: carácter, cadena, strchr, función, buscar
-->

# strchr: La Función en C para Buscar Caracteres en Cadenas

## Sinopsis
La función `strchr` en C permite buscar la primera aparición de un carácter específico dentro de una cadena de caracteres. Esta función es parte de la biblioteca estándar de C, lo que la hace esencial para la manipulación de cadenas.

## Documentación

### Propósito
`strchr` se utiliza para localizar la primera ocurrencia de un carácter dentro de una cadena. Si el carácter es encontrado, se devuelve un puntero a la posición del carácter en la cadena; de lo contrario, se devuelve `NULL`.

### Uso
La función se declara en el encabezado `<string.h>` y su sintaxis es la siguiente:

```c
char *strchr(const char *str, int c);
```

#### Parámetros
- `str`: Un puntero a la cadena de caracteres donde se realizará la búsqueda.
- `c`: El carácter que se desea buscar, que se pasará como un valor entero. Este valor se convierte a un carácter.

#### Valor de retorno
- Retorna un puntero al primer carácter encontrado en la cadena `str`.
- Retorna `NULL` si el carácter no se encuentra.

### Ejemplo de uso
Aquí hay un ejemplo básico que muestra cómo usar `strchr` en un programa C:

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *cadena = "Hola, mundo!";
    char *resultado;

    // Buscar el carácter 'm'
    resultado = strchr(cadena, 'm');

    if (resultado != NULL) {
        printf("El carácter encontrado: %c\n", *resultado);
        printf("Subcadena desde el carácter encontrado: %s\n", resultado);
    } else {
        printf("Carácter no encontrado.\n");
    }

    return 0;
}
```

### Explicación
Al utilizar `strchr`, es importante tener en cuenta lo siguiente:

- **Carácter nulo**: Si se busca el carácter nulo (`'\0'`), `strchr` devolverá un puntero al final de la cadena, que es un comportamiento esperado.
- **Sensibilidad a mayúsculas y minúsculas**: La búsqueda es sensible a las mayúsculas y minúsculas. Por ejemplo, buscar 'a' no encontrará 'A'.
- **Modificación de cadenas**: `strchr` no modifica la cadena original. Si se desea modificar la cadena, se debe trabajar con una copia.

### Resumen en una línea
La función `strchr` en C permite encontrar la primera aparición de un carácter en una cadena de caracteres, devolviendo un puntero a la posición encontrada o `NULL` si no se encuentra.