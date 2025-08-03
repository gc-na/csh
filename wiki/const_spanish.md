<!--
Meta Description: # Uso de `const` en C: Guía Completa ## Sinopsis La palabra clave `const` en C se utiliza para declarar variables que no pueden ser modificadas despué...
Meta Keywords: const, int, constante, ptr, que
-->

# Uso de `const` en C: Guía Completa

## Sinopsis
La palabra clave `const` en C se utiliza para declarar variables que no pueden ser modificadas después de su inicialización, proporcionando así un mecanismo para proteger datos y mejorar la legibilidad del código.

## Documentación
La palabra clave `const` es fundamental en el lenguaje de programación C. Su propósito principal es indicar que una variable es constante y su valor no debe cambiar a lo largo de su vida útil. Esto puede ser especialmente útil para definir valores que deben permanecer fijos y para mejorar la seguridad del código al evitar modificaciones accidentales.

### Propósito
- **Inmutabilidad**: Al declarar una variable como `const`, el compilador garantiza que su valor no puede ser alterado.
- **Seguridad**: Ayuda a prevenir errores al proteger datos críticos.
- **Optimización**: Los compiladores pueden realizar optimizaciones basadas en la inmutabilidad de las variables.

### Uso
La declaración de una variable como `const` se realiza simplemente anteponiendo la palabra clave a su tipo. Por ejemplo:

```c
const int max_value = 100;
```

En este caso, `max_value` es una constante de tipo entero que no puede ser modificada. Si se intenta cambiar su valor en el código, el compilador generará un error.

Además, `const` puede ser utilizado con punteros, lo que permite declarar punteros a constantes o punteros constantes. Por ejemplo:

```c
const int *ptr_to_const; // Puntero a un entero constante
int *const const_ptr; // Puntero constante a un entero
```

## Ejemplos
### Ejemplo 1: Declaración simple
```c
#include <stdio.h>

int main() {
    const int pi = 3; // Declaración de una constante
    // pi = 3.14; // Esto causará un error de compilación
    printf("El valor de pi es: %d\n", pi);
    return 0;
}
```

### Ejemplo 2: Puntero a constante
```c
#include <stdio.h>

int main() {
    int value = 42;
    const int *ptr = &value; // Puntero a un entero constante
    // *ptr = 100; // Esto causará un error de compilación
    printf("Valor apuntado por ptr: %d\n", *ptr);
    return 0;
}
```

### Ejemplo 3: Puntero constante
```c
#include <stdio.h>

int main() {
    int value = 42;
    int *const ptr = &value; // Puntero constante a un entero
    *ptr = 100; // Esto es válido
    // ptr = NULL; // Esto causará un error de compilación
    printf("Nuevo valor apuntado por ptr: %d\n", *ptr);
    return 0;
}
```

## Explicación
Al usar `const`, es importante tener en cuenta algunos aspectos:

1. **Errores de compilación**: Cualquier intento de modificar una variable declarada como `const` resultará en un error de compilación. Esto ayuda a mantener la integridad de los datos.
2. **Uso con funciones**: Cuando se pasan punteros a funciones, el uso de `const` puede indicar que la función no modificará el contenido apuntado, mejorando la claridad del código.
3. **Constantes de arreglos**: Si se declara un arreglo como `const`, no se puede modificar el contenido de sus elementos. Sin embargo, la dirección del arreglo puede cambiar si se utiliza un puntero no constante.

## Resumen en una línea
La palabra clave `const` en C se utiliza para declarar variables inmutables, mejorando la seguridad y la claridad del código.