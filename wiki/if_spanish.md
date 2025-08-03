<!--
Meta Description: # La instrucción "if" en C: Control de Flujo Condicional ## Sinopsis La instrucción "if" en el lenguaje de programación C permite la ejecución condici...
Meta Keywords: código, bloque, else, instrucción, una
-->

# La instrucción "if" en C: Control de Flujo Condicional

## Sinopsis
La instrucción "if" en el lenguaje de programación C permite la ejecución condicional de bloques de código, facilitando la toma de decisiones en función del resultado de expresiones booleanas.

## Documentación
La instrucción "if" es una de las estructuras de control más fundamentales en C, utilizada para ejecutar un bloque de código solo si se cumple una determinada condición. Su sintaxis básica es:

```c
if (condición) {
    // bloque de código a ejecutar si la condición es verdadera
}
```

### Propósito
El propósito principal de la instrucción "if" es permitir que un programa evalúe condiciones y ejecute diferentes secciones de código según el resultado de dicha evaluación. Esto es esencial para la programación de lógica y decisiones en aplicaciones.

### Uso
1. **Condición**: La condición se evalúa como una expresión booleana, es decir, debe ser verdadera (non-zero) o falsa (zero).
2. **Bloque de Código**: Si la condición es verdadera, el bloque de código dentro de las llaves se ejecuta. Si es falsa, se omite.

### Sintaxis Completa
Además de la forma básica, la instrucción "if" puede combinarse con "else" y "else if" para manejar múltiples condiciones:

```c
if (condición1) {
    // bloque de código si condición1 es verdadera
} else if (condición2) {
    // bloque de código si condición2 es verdadera
} else {
    // bloque de código si todas las condiciones anteriores son falsas
}
```

## Ejemplos
### Ejemplo 1: Uso básico de "if"
```c
#include <stdio.h>

int main() {
    int numero = 10;

    if (numero > 5) {
        printf("El número es mayor que 5.\n");
    }

    return 0;
}
```

### Ejemplo 2: Uso de "if" con "else"
```c
#include <stdio.h>

int main() {
    int numero = 3;

    if (numero % 2 == 0) {
        printf("El número es par.\n");
    } else {
        printf("El número es impar.\n");
    }

    return 0;
}
```

### Ejemplo 3: Uso de "if" con "else if"
```c
#include <stdio.h>

int main() {
    int nota = 85;

    if (nota >= 90) {
        printf("Calificación: A\n");
    } else if (nota >= 80) {
        printf("Calificación: B\n");
    } else {
        printf("Calificación: C\n");
    }

    return 0;
}
```

## Explicación
### Errores Comunes
- **No usar llaves**: Si el bloque de código a ejecutar solo tiene una línea, se pueden omitir las llaves, pero es recomendable usarlas para evitar errores de lógica.
- **Confundir operadores**: Asegúrate de usar `==` para comparación en lugar de `=` que es un operador de asignación.
- **Condiciones siempre verdaderas o falsas**: Utilizar condiciones que siempre resulten verdaderas o falsas puede llevar a un comportamiento inesperado en el programa.

### Notas Adicionales
- La instrucción "if" es evaluada de arriba hacia abajo. Una vez que se cumple una condición, se ejecuta su bloque correspondiente y se ignoran las demás condiciones.
- Se pueden anidar múltiples instrucciones "if" para evaluar condiciones más complejas.

## Resumen en una línea
La instrucción "if" en C permite la ejecución condicional de bloques de código basados en la evaluación de expresiones booleanas.