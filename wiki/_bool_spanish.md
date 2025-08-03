<!--
Meta Description: # _Bool en C: Tipo de Dato Booleano ## Sinopsis `_Bool` es un tipo de dato en el lenguaje de programación C, utilizado para representar valores boolea...
Meta Keywords: _bool, tipo, valores, que, para
-->

# _Bool en C: Tipo de Dato Booleano

## Sinopsis
`_Bool` es un tipo de dato en el lenguaje de programación C, utilizado para representar valores booleanos, que pueden ser `0` (falso) o `1` (verdadero). Introducido en el estándar C99, permite a los programadores trabajar con condiciones lógicas de manera más intuitiva.

## Documentación
### Propósito
El tipo `_Bool` fue diseñado para almacenar valores lógicos, mejorando la legibilidad y la funcionalidad en las operaciones condicionales. En C, el uso de variables booleanas facilita la implementación de estructuras de control como `if`, `while`, y `for`.

### Uso
Para declarar una variable de tipo `_Bool`, se utiliza la siguiente sintaxis:

```c
#include <stdio.h>

_Bool variableBooleana;
```

El tipo `_Bool` puede almacenar solo dos valores: `0` (falso) y `1` (verdadero). Es importante mencionar que cualquier valor diferente de cero se considera verdadero al ser convertido a booleano.

### Detalles
- `_Bool` es un tipo integral y ocupa 1 byte, aunque su tamaño puede variar según la implementación.
- Para facilitar el uso de valores booleanos, el estándar C99 introdujo los macros `true` y `false` en el encabezado `<stdbool.h>`. Estos macros son simplemente reemplazos para `1` y `0`, respectivamente.

```c
#include <stdbool.h>

bool esVerdadero = true;  // equivalente a 1
bool esFalso = false;     // equivalente a 0
```

## Ejemplos
### Ejemplo Básico
A continuación se muestra un ejemplo simple de cómo utilizar `_Bool`:

```c
#include <stdio.h>

int main() {
    _Bool esMayorDeEdad = 0; // Falso

    int edad = 18;
    if (edad >= 18) {
        esMayorDeEdad = 1; // Verdadero
    }

    printf("¿Es mayor de edad? %d\n", esMayorDeEdad); // Imprime: 1
    return 0;
}
```

### Ejemplo con `<stdbool.h>`
```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    bool esLuzVerde = true; // Verdadero
    bool esLuzRoja = false; // Falso

    if (esLuzVerde) {
        printf("Puedes avanzar.\n");
    } else if (esLuzRoja) {
        printf("Debes detenerte.\n");
    }

    return 0;
}
```

## Explicación
Al trabajar con `_Bool`, es esencial tener en cuenta que la asignación de otros tipos numéricos a una variable `_Bool` se convierte automáticamente en un valor booleano. Sin embargo, se deben evitar comparaciones directas con otros tipos de datos sin una conversión explícita, ya que esto podría llevar a confusiones.

### Errores Comunes
- Asignar valores fuera del rango (por ejemplo, un número negativo) puede generar resultados inesperados.
- No inicializar una variable `_Bool` puede llevar a comportamientos indeseados, ya que contendrá un valor basura.

## Resumen en Una Línea
`_Bool` es un tipo de dato en C que permite representar valores booleanos, mejorando la claridad y funcionalidad de las condiciones lógicas en el código.