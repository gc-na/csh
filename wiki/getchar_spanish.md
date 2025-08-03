<!--
Meta Description: # Uso de getchar() en C: Captura de Caracteres de Entrada ## Sinopsis La función `getchar()` en C es utilizada para leer un único carácter de la entra...
Meta Keywords: getchar, carácter, entrada, que, para
-->

# Uso de getchar() en C: Captura de Caracteres de Entrada

## Sinopsis
La función `getchar()` en C es utilizada para leer un único carácter de la entrada estándar (teclado). Es una herramienta fundamental para la manipulación básica de la entrada en programas de consola.

## Documentación
### Propósito
`getchar()` permite al programador obtener un carácter de la entrada estándar, lo que puede ser útil para leer datos en programas interactivos.

### Uso
La función se declara en el encabezado `<stdio.h>` y su sintaxis es la siguiente:

```c
int getchar(void);
```

### Detalles
- **Retorno**: 
  - Devuelve el carácter leído como un valor de tipo `int`. El valor devuelto es el carácter leído o `EOF` (End of File) si se alcanza el final de la entrada o se produce un error.
  
- **Ejemplo de uso**: 
  Para utilizar `getchar()`, puedes llamarla directamente en un bucle para leer caracteres hasta que se introduzca un carácter específico o se alcance el final de la entrada.

### Consideraciones
Es importante tener en cuenta que `getchar()` no realiza ninguna conversión de caracteres (por ejemplo, de mayúsculas a minúsculas). También, si se ingresa un carácter que no es parte de la entrada estándar, puede que se produzcan resultados inesperados.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>

int main() {
    char c;
    printf("Introduce un carácter: ");
    c = getchar();
    printf("Has introducido: %c\n", c);
    return 0;
}
```

### Ejemplo de Bucle
```c
#include <stdio.h>

int main() {
    int c;
    printf("Introduce varios caracteres (Ctrl+D para terminar):\n");
    while ((c = getchar()) != EOF) {
        putchar(c); // Imprime el carácter leído
    }
    return 0;
}
```

## Explicación
### Errores Comunes
- **No manejar EOF**: Olvidar verificar si se ha alcanzado el final de la entrada puede llevar a bucles infinitos o errores en la ejecución.
- **Confusión con el tipo de retorno**: `getchar()` retorna un `int`, lo que permite distinguir entre un carácter válido y `EOF`. Si se utiliza un `char` directamente, puede haber pérdida de información.

### Notas Adicionales
- La función `getchar()` se bloquea hasta que se introduce un carácter. Esto significa que no se puede usar en situaciones donde se requiere una entrada no bloqueante.
- Para leer múltiples caracteres, se debe implementar un bucle como se muestra en el segundo ejemplo.

## Resumen en Una Línea
`getchar()` es una función en C que permite leer un único carácter de la entrada estándar, facilitando la interacción básica con el usuario.