<!--
Meta Description: # __LINE__: Macro de Preprocesador en C ## Sinopsis `__LINE__` es un macro predefinido en el lenguaje de programación C que proporciona el número de l...
Meta Keywords: línea, __line__, que, error, macro
-->

# __LINE__: Macro de Preprocesador en C

## Sinopsis
`__LINE__` es un macro predefinido en el lenguaje de programación C que proporciona el número de línea actual en el archivo fuente durante la compilación. Este macro es útil para depuración y generación de mensajes de error, facilitando la localización exacta del código.

## Documentación
El macro `__LINE__` se utiliza para obtener el número de la línea en la que aparece el macro dentro del archivo fuente. Este número se actualiza automáticamente y es especialmente útil en la creación de mensajes de error, logs o para la depuración del código.

### Propósito
El propósito principal de `__LINE__` es permitir a los desarrolladores identificar rápidamente la ubicación de un problema en el código fuente. Al incluir el número de línea en los mensajes de error o en la salida de depuración, se simplifica la tarea de rastrear errores.

### Uso
El macro `__LINE__` se puede utilizar en cualquier parte del código C. Al ser una constante, no requiere ningún tipo de inicialización. Simplemente se puede invocar en las expresiones o declaraciones según se necesite.

### Detalles
- `__LINE__` se expande al número de línea actual, comenzando desde 1 para la primera línea del archivo.
- Se actualiza automáticamente en cada nuevo archivo o línea que se compila.
- No es necesario usar paréntesis al llamar a `__LINE__`, ya que se trata de un macro y no de una función.

## Ejemplos

### Ejemplo 1: Uso básico
```c
#include <stdio.h>

int main() {
    printf("Este código está en la línea: %d\n", __LINE__);
    return 0;
}
```
Salida esperada:
```
Este código está en la línea: 5
```

### Ejemplo 2: Mensajes de error personalizados
```c
#include <stdio.h>

#define ERROR(msg) printf("Error en la línea %d: %s\n", __LINE__, msg)

int main() {
    ERROR("Algo salió mal.");
    return 0;
}
```
Salida esperada:
```
Error en la línea 6: Algo salió mal.
```

## Explicación
Un error común al utilizar `__LINE__` es asumir que su valor permanece constante a lo largo del archivo; en realidad, se actualiza cada vez que se encuentra en una nueva línea. Además, es importante recordar que se debe utilizar en un contexto donde el número de línea tenga sentido, como dentro de funciones o bloques de código, para que la salida sea relevante para el desarrollador.

Adicionalmente, al combinar `__LINE__` con otros macros como `__FILE__` (que indica el nombre del archivo), se puede generar información de depuración aún más rica y útil.

## Resumen en una línea
`__LINE__` es un macro en C que proporciona el número de la línea actual en el archivo fuente, facilitando la depuración y el manejo de errores.