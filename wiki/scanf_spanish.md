<!--
Meta Description: # Uso de scanf en C: Entradas de Usuario Eficientes ## Sinopsis `scanf` es una función de la biblioteca estándar del lenguaje de programación C, utili...
Meta Keywords: scanf, para, leer, datos, entrada
-->

# Uso de scanf en C: Entradas de Usuario Eficientes

## Sinopsis
`scanf` es una función de la biblioteca estándar del lenguaje de programación C, utilizada para leer datos de entrada desde la consola. Permite al usuario ingresar datos que pueden ser almacenados en variables especificadas, facilitando la interacción en programas.

## Documentación
### Propósito
La función `scanf` se utiliza para formatear y leer datos desde la entrada estándar (generalmente el teclado). Su flexibilidad permite capturar diferentes tipos de datos, como enteros, flotantes y cadenas de texto.

### Uso
La sintaxis básica de `scanf` es la siguiente:

```c
int scanf(const char *formato, ...);
```

- **formato**: Una cadena de formato que especifica el tipo y la forma de los datos a leer.
- **...**: Uno o más punteros a variables donde se almacenarán los datos ingresados.

Los especificadores de formato más comunes son:
- `%d`: Entero decimal.
- `%f`: Número de punto flotante.
- `%s`: Cadena de caracteres (se asume un array).
- `%c`: Carácter único.

### Detalles
- `scanf` devuelve el número de elementos que ha leído correctamente. Si no se ha leído ningún elemento, devuelve `EOF` (End Of File).
- Es importante pasar la dirección de las variables (usando `&` para tipos básicos) para que `scanf` pueda modificar el valor.

## Ejemplos
### Ejemplo 1: Leer un entero
```c
#include <stdio.h>

int main() {
    int numero;
    printf("Introduce un número entero: ");
    scanf("%d", &numero);
    printf("Has introducido: %d\n", numero);
    return 0;
}
```

### Ejemplo 2: Leer una cadena
```c
#include <stdio.h>

int main() {
    char nombre[50];
    printf("Introduce tu nombre: ");
    scanf("%s", nombre);
    printf("Hola, %s!\n", nombre);
    return 0;
}
```

### Ejemplo 3: Leer un número de punto flotante
```c
#include <stdio.h>

int main() {
    float decimal;
    printf("Introduce un número decimal: ");
    scanf("%f", &decimal);
    printf("Has introducido: %.2f\n", decimal);
    return 0;
}
```

## Explicación
### Errores Comunes
1. **No usar `&` para tipos básicos**: Al leer enteros o flotantes, se debe usar el operador `&` para pasar la dirección de la variable. Omitirlo causará un comportamiento indefinido.
   
2. **Buffer Overflow**: Al usar `%s`, si la cadena de entrada excede el tamaño del array, puede provocar un desbordamiento de buffer. Es recomendable usar `scanf("%49s", nombre)` para restringir la entrada.

3. **Lectura de caracteres**: Leer caracteres consecutivos después de leer enteros o flotantes puede resultar en la captura de caracteres no deseados (como espacios o saltos de línea). Se puede usar un espacio antes de `%c` para ignorar espacios en blanco.

### Notas Adicionales
- `scanf` no maneja bien los errores de entrada. Es recomendable validar la entrada después de la llamada a `scanf` para asegurarse de que se ha leído correctamente.

## Resumen en Una Línea
`scanf` es una función en C que permite la lectura de datos de entrada del usuario de forma flexible y formateada, siendo esencial para la interacción en programas.