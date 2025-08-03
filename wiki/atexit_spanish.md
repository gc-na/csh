<!--
Meta Description: # atexit: Manejo de Funciones de Terminación en C ## Sinopsis La función `atexit` en C permite registrar funciones que se ejecutarán al final del prog...
Meta Keywords: función, atexit, que, programa, funciones
-->

# atexit: Manejo de Funciones de Terminación en C

## Sinopsis
La función `atexit` en C permite registrar funciones que se ejecutarán al final del programa, justo antes de que se complete la ejecución del `main`. Esto es útil para realizar tareas de limpieza o liberar recursos.

## Documentación
La función `atexit` se define en el encabezado `<stdlib.h>`. Su propósito principal es registrar una función que se ejecutará al finalizar el programa. La sintaxis de `atexit` es la siguiente:

```c
int atexit(void (*func)(void));
```

### Parámetros
- **func**: Un puntero a la función que se desea ejecutar al terminar el programa. Esta función no debe tener parámetros y no debe devolver ningún valor.

### Retorno
- Devuelve `0` si la función se registra correctamente.
- Devuelve un valor distinto de cero si hay un error al registrar la función.

### Comportamiento
Las funciones registradas con `atexit` se ejecutan en el orden inverso al que fueron registradas. Esto significa que la última función registrada será la primera en ejecutarse al finalizar el programa.

## Ejemplos

### Ejemplo Básico

```c
#include <stdio.h>
#include <stdlib.h>

void funcion_de_terminacion() {
    printf("Función de terminación ejecutada.\n");
}

int main() {
    // Registrar la función para que se ejecute al finalizar
    if (atexit(funcion_de_terminacion) != 0) {
        fprintf(stderr, "Error al registrar la función de terminación.\n");
        return EXIT_FAILURE;
    }
    
    printf("Programa en ejecución.\n");
    return EXIT_SUCCESS;
}
```

### Ejemplo con Múltiples Funciones

```c
#include <stdio.h>
#include <stdlib.h>

void funcion1() {
    printf("Función 1 ejecutada.\n");
}

void funcion2() {
    printf("Función 2 ejecutada.\n");
}

int main() {
    atexit(funcion1);
    atexit(funcion2);
    
    printf("Programa en ejecución.\n");
    return EXIT_SUCCESS;
}
```

**Salida esperada:**
```
Programa en ejecución.
Función 2 ejecutada.
Función 1 ejecutada.
```

## Explicación
Al usar `atexit`, es importante tener en cuenta lo siguiente:

- **Funciones sin parámetros**: Las funciones registradas no pueden aceptar parámetros ni devolver valores.
- **Errores en el registro**: Siempre es recomendable verificar el retorno de `atexit` para asegurarse de que la función se haya registrado correctamente.
- **Recursos**: Utilizar `atexit` es ideal para liberar recursos como memoria dinámica, archivos abiertos, o conexiones de red antes de que el programa finalice.
- **Interrupciones**: Si el programa se termina de forma abrupta (por señales o errores fatales), las funciones registradas pueden no ejecutarse.

## Resumen en una línea
La función `atexit` en C permite registrar funciones que se ejecutan automáticamente al finalizar el programa, facilitando la limpieza de recursos.