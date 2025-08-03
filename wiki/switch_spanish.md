<!--
Meta Description: # Uso del comando switch en C: Guía completa y ejemplos ## Sinopsis El comando `switch` en C es una declaración de control de flujo que permite la eje...
Meta Keywords: case, switch, número, expresión, break
-->

# Uso del comando switch en C: Guía completa y ejemplos

## Sinopsis
El comando `switch` en C es una declaración de control de flujo que permite la ejecución de diferentes bloques de código basándose en el valor de una expresión. Es una alternativa más organizada y legible a múltiples declaraciones `if-else`.

## Documentación
El `switch` se utiliza para simplificar la toma de decisiones en programas de C. Su estructura básica permite evaluar una variable y ejecutar diferentes secciones de código según el valor de esa variable.

### Sintaxis
```c
switch (expresión) {
    case constante1:
        // Código a ejecutar si expresión == constante1
        break;
    case constante2:
        // Código a ejecutar si expresión == constante2
        break;
    // ...
    default:
        // Código a ejecutar si ninguna de las constantes coincide
}
```

### Componentes
- **expresión**: Es la variable o expresión que se evalúa. Debe ser de un tipo entero o un tipo que pueda ser convertido a entero.
- **case**: Cada `case` representa un posible valor de la expresión. Si se encuentra un caso que coincide, se ejecuta el código asociado.
- **break**: Se utiliza para salir del `switch`. Sin él, el flujo de ejecución continuará en el siguiente `case`, lo que puede llevar a resultados inesperados.
- **default**: Es opcional y se ejecuta si ninguna de las constantes coincide con la expresión.

## Ejemplos
### Ejemplo 1: Uso básico de switch
```c
#include <stdio.h>

int main() {
    int numero = 2;

    switch (numero) {
        case 1:
            printf("Número uno\n");
            break;
        case 2:
            printf("Número dos\n");
            break;
        case 3:
            printf("Número tres\n");
            break;
        default:
            printf("Número no reconocido\n");
    }

    return 0;
}
```

### Ejemplo 2: Sin usar break
```c
#include <stdio.h>

int main() {
    int numero = 2;

    switch (numero) {
        case 1:
            printf("Número uno\n");
        case 2:
            printf("Número dos\n");
        case 3:
            printf("Número tres\n");
        default:
            printf("Número no reconocido\n");
    }

    return 0;
}
```
**Salida:**
```
Número dos
Número tres
Número no reconocido
```

## Explicación
### Errores Comunes
- **Olvidar el break**: Uno de los errores más comunes es olvidar la instrucción `break`, lo que puede llevar a la ejecución de múltiples bloques de código.
- **Uso de tipos incorrectos**: La expresión dentro del `switch` debe ser de un tipo que pueda ser evaluado como entero, como `int`, `char`, o enumeraciones. Usar tipos no compatibles generará errores de compilación.

### Notas Adicionales
- El `switch` no admite rangos de valores, solo puede evaluar constantes individuales.
- Se pueden usar expresiones en `case`, pero deben ser evaluadas en tiempo de compilación.

## Resumen en una línea
El comando `switch` en C permite seleccionar y ejecutar diferentes bloques de código de manera eficiente según el valor de una expresión.