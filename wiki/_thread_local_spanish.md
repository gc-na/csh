<!--
Meta Description: # _Thread_local en C: Manejo de Variables Locales a Hilos ## Sinopsis `_Thread_local` es una especificación en el lenguaje de programación C que permi...
Meta Keywords: _thread_local, que, hilo, variable, int
-->

# _Thread_local en C: Manejo de Variables Locales a Hilos

## Sinopsis
`_Thread_local` es una especificación en el lenguaje de programación C que permite la creación de variables locales a hilos, garantizando que cada hilo tenga su propia instancia de la variable, lo que es fundamental para la programación concurrente.

## Documentación
El modificador `_Thread_local` fue introducido en el estándar C11 (ISO/IEC 9899:2011) y proporciona una forma de declarar variables que son específicas para cada hilo en un programa multihilo. Esto significa que cada hilo puede modificar su propia copia de la variable sin interferir con los demás hilos.

### Propósito
El propósito de `_Thread_local` es evitar problemas de concurrencia y permitir que los hilos se comporten de manera independiente al acceder a sus propias copias de una variable.

### Uso
La declaración de una variable como `_Thread_local` se realiza de la siguiente manera:

```c
_Thread_local tipo nombre_variable;
```

Donde `tipo` es el tipo de dato de la variable (por ejemplo, `int`, `float`, etc.) y `nombre_variable` es el identificador de la variable.

### Detalles
- Las variables declaradas con `_Thread_local` se inicializan de manera única para cada hilo.
- Si un hilo no ha modificado la variable, la variable de ese hilo tendrá el valor predeterminado del tipo de dato.
- No se puede usar `_Thread_local` en funciones de forma directa; debe ser utilizado en el ámbito global o dentro de una función estática.

## Ejemplos

### Ejemplo 1: Uso básico de `_Thread_local`

```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int contador = 0;

void* incrementar(void* arg) {
    for (int i = 0; i < 5; i++) {
        contador++;
        printf("Hilo %ld: contador = %d\n", (long)arg, contador);
    }
    return NULL;
}

int main() {
    pthread_t hilo1, hilo2;

    pthread_create(&hilo1, NULL, incrementar, (void*)1);
    pthread_create(&hilo2, NULL, incrementar, (void*)2);

    pthread_join(hilo1, NULL);
    pthread_join(hilo2, NULL);

    return 0;
}
```

### Ejemplo 2: Inicialización de variables `_Thread_local`

```c
#include <stdio.h>
#include <pthread.h>

_Thread_local int id_hilo = 0;

void* asignar_id(void* arg) {
    id_hilo = (int)(long)arg;
    printf("Hilo %d asignado ID: %d\n", (int)(long)arg, id_hilo);
    return NULL;
}

int main() {
    pthread_t hilos[3];

    for (int i = 0; i < 3; i++) {
        pthread_create(&hilos[i], NULL, asignar_id, (void*)(long)(i + 1));
    }

    for (int i = 0; i < 3; i++) {
        pthread_join(hilos[i], NULL);
    }

    return 0;
}
```

## Explicación
Al usar `_Thread_local`, hay algunos puntos importantes a considerar:

- **Visibilidad**: Las variables `_Thread_local` son visibles únicamente dentro del hilo que las crea. Otros hilos no pueden acceder a estas variables directamente, lo que reduce el riesgo de condiciones de carrera.
- **Compatibilidad**: Asegúrate de que tu compilador soporte el estándar C11, ya que `_Thread_local` no está disponible en versiones anteriores de C.
- **Uso en funciones**: Aunque puedes declarar `_Thread_local` en una función, la variable debe ser estática para que el modificador funcione correctamente.

## Resumen en una línea
`_Thread_local` en C permite definir variables locales a hilos, asegurando que cada hilo tenga su propia copia de la variable y evitando conflictos en entornos multihilo.