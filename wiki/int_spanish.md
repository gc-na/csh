<!--
Meta Description: # El Tipo de Dato "int" en C: Todo lo que Necesitas Saber ## Sinopsis El tipo de dato `int` en C es una de las construcciones fundamentales del lengua...
Meta Keywords: int, para, tipo, que, enteros
-->

# El Tipo de Dato "int" en C: Todo lo que Necesitas Saber

## Sinopsis
El tipo de dato `int` en C es una de las construcciones fundamentales del lenguaje, utilizado para representar números enteros. Su versatilidad y eficiencia lo convierten en una opción preferida en la programación de sistemas y aplicaciones.

## Documentación
### Propósito
El tipo `int` se utiliza para declarar variables que almacenan números enteros. En C, los enteros pueden ser positivos, negativos o cero, y su tamaño puede variar dependiendo de la implementación del compilador (típicamente 16, 32 o 64 bits).

### Uso
Para declarar una variable de tipo `int`, se utiliza la siguiente sintaxis:

```c
int nombre_variable;
```

Donde `nombre_variable` es el identificador que se utilizará para referirse a esa variable en el código. También se pueden inicializar al momento de la declaración:

```c
int numero = 10;
```

### Detalles
- **Rango**: El rango de valores que puede almacenar un `int` depende del tamaño de la variable en la plataforma específica. Por ejemplo, en un sistema de 32 bits, el rango es típicamente de -2,147,483,648 a 2,147,483,647.
- **Modificadores**: Puedes usar modificadores como `signed`, `unsigned`, `short`, y `long` para variar el comportamiento y el rango de los enteros. Por ejemplo, `unsigned int` solo permite valores positivos.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>

int main() {
    int edad = 25; // Declaración e inicialización
    printf("Mi edad es: %d\n", edad); // Salida: Mi edad es: 25
    return 0;
}
```

### Ejemplo con Modificadores
```c
#include <stdio.h>

int main() {
    unsigned int contador = 0; // Solo puede ser positivo
    for (contador = 0; contador < 10; contador++) {
        printf("%u\n", contador); // Salida de 0 a 9
    }
    return 0;
}
```

## Explicación
### Errores Comunes
- **Sobrecarga**: Al realizar operaciones matemáticas, es fácil exceder el rango del tipo `int`, lo que puede provocar un comportamiento inesperado (overflow).
- **Tipo de Dato Incorrecto**: Usar `printf` con un especificador de formato incorrecto puede llevar a resultados no deseados. Asegúrate de usar `%d` para enteros firmados y `%u` para enteros no firmados.
- **Inicialización**: No inicializar una variable `int` puede llevar a resultados impredecibles, ya que contendrá un valor basura.

### Notas Adicionales
El tipo `int` es el más comúnmente utilizado para contadores y acumuladores en bucles y operaciones aritméticas. Sin embargo, para números que requieren un rango más amplio, considera usar `long` o `long long`.

## Resumen en una Línea
El tipo `int` en C es un tipo de dato fundamental utilizado para almacenar números enteros, con un rango y comportamiento que pueden variar según el compilador y los modificadores aplicados.