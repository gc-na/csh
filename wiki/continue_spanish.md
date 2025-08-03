<!--
Meta Description: # La instrucción "continue" en C: Uso y Ejemplos ## Sinopsis La instrucción `continue` en el lenguaje de programación C se utiliza dentro de estructur...
Meta Keywords: continue, bucle, del, while, instrucción
-->

# La instrucción "continue" en C: Uso y Ejemplos

## Sinopsis
La instrucción `continue` en el lenguaje de programación C se utiliza dentro de estructuras de control de bucle para omitir la iteración actual y continuar con la siguiente. Es una herramienta útil para el control del flujo de ejecución en bucles `for`, `while` y `do-while`.

## Documentación
### Propósito
El propósito de la instrucción `continue` es alterar el flujo de un bucle. Cuando se encuentra la instrucción `continue`, el control salta inmediatamente a la siguiente iteración del bucle, evitando la ejecución del código que sigue a esta instrucción en el ciclo actual.

### Uso
La sintaxis de la instrucción `continue` es sencilla:

```c
continue;
```

En un bucle `for`, `while` o `do-while`, se puede usar de la siguiente manera:

```c
for (inicialización; condición; incremento) {
    // Código antes de continue
    if (condición_a_verificar) {
        continue; // Salta a la siguiente iteración
    }
    // Código que se ejecutará si la condición_a_verificar es falsa
}
```

### Detalles
- En un bucle `for`, `continue` lleva el control directamente a la parte de incremento del bucle.
- En un bucle `while` o `do-while`, `continue` vuelve a evaluar la condición del bucle.
- Puede ser útil en la depuración y en la simplificación del flujo de lógica, evitando la anidación de condicionales.

## Ejemplos
### Ejemplo 1: Uso básico de `continue` en un bucle `for`
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) {
            continue; // Salta los números pares
        }
        printf("%d ", i); // Imprime solo números impares
    }
    return 0;
}
```
**Salida:** `1 3 5 7 9 `

### Ejemplo 2: Uso de `continue` en un bucle `while`
```c
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 10) {
        i++;
        if (i == 5) {
            continue; // Salta la iteración cuando i es 5
        }
        printf("%d ", i); // Imprime los números excepto 5
    }
    return 0;
}
```
**Salida:** `1 2 3 4 6 7 8 9 10 `

## Explicación
### Errores Comunes
- **Olvidar el flujo:** Un error común es colocar `continue` en un lugar inadecuado que puede llevar a omitir lógica importante.
- **Confusión con `break`:** Es importante no confundir `continue` con `break`. Mientras que `continue` salta a la siguiente iteración, `break` termina el bucle por completo.

### Notas Adicionales
- `continue` se puede utilizar con etiquetas para bucles anidados, pero su uso debe ser cuidadoso para evitar confusiones. La sintaxis sería `continue etiqueta;`.
- Es recomendable usar `continue` con moderación para mantener la legibilidad del código.

## Resumen en una línea
La instrucción `continue` en C permite saltarse la iteración actual de un bucle y continuar con la siguiente, facilitando el control del flujo de ejecución.