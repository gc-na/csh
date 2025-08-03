<!--
Meta Description: # mktime en C: Función para Convertir Estructuras de Tiempo a Tiempos de Epoch ## Sinopsis La función `mktime` en C se utiliza para convertir una estr...
Meta Keywords: tiempo, mktime, que, función, epoch
-->

# mktime en C: Función para Convertir Estructuras de Tiempo a Tiempos de Epoch

## Sinopsis
La función `mktime` en C se utiliza para convertir una estructura de tiempo (`struct tm`) en un tiempo de epoch, que es el número de segundos transcurridos desde el 1 de enero de 1970 a las 00:00:00 UTC.

## Documentación
### Propósito
La función `mktime` toma una estructura de tiempo que representa una fecha y hora específicas y la convierte en un valor de tipo `time_t`, que representa el tiempo en segundos desde el epoch. Esta función es vital para la manipulación y el cálculo de fechas y horas en aplicaciones C.

### Uso
La declaración de la función es la siguiente:
```c
time_t mktime(struct tm *timeptr);
```

#### Parámetros
- **timeptr**: Un puntero a una estructura `struct tm` que contiene la fecha y hora que se desea convertir. Esta estructura debe tener sus campos correctamente inicializados.

#### Valor de retorno
La función devuelve un valor de tipo `time_t`, que representa el número de segundos desde el epoch. Si ocurre un error, devuelve `-1`.

### Detalles
- La estructura `tm` debe tener los siguientes campos: `tm_year`, `tm_mon`, `tm_mday`, `tm_hour`, `tm_min`, y `tm_sec`. Es importante tener en cuenta que:
  - `tm_year` es el número de años desde 1900.
  - `tm_mon` es el número del mes, comenzando desde 0 (enero) hasta 11 (diciembre).
- La función ajusta automáticamente los valores de `tm` si son inválidos, por ejemplo, si se proporciona un día 30 de febrero, `mktime` ajustará el mes y el año adecuadamente.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm tiempo = {0};
    tiempo.tm_year = 123; // 2023 - 1900
    tiempo.tm_mon = 0;    // Enero
    tiempo.tm_mday = 1;   // 1 de enero
    tiempo.tm_hour = 12;   // 12 PM
    tiempo.tm_min = 0;     // 0 minutos
    tiempo.tm_sec = 0;     // 0 segundos

    time_t tiempo_epoch = mktime(&tiempo);
    printf("Tiempo en epoch: %ld\n", tiempo_epoch);
    return 0;
}
```

### Ejemplo con Ajuste Automático
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm tiempo = {0};
    tiempo.tm_year = 123; // 2023 - 1900
    tiempo.tm_mon = 1;    // Febrero
    tiempo.tm_mday = 30;  // 30 de febrero (inválido)
    
    time_t tiempo_epoch = mktime(&tiempo);
    printf("Tiempo en epoch (ajustado): %ld\n", tiempo_epoch);
    return 0;
}
```

## Explicación
Un error común al usar `mktime` es no inicializar correctamente todos los campos de la estructura `tm`. Si alguno de los campos no se inicializa, el resultado puede ser indefinido. Además, es importante recordar que `mktime` puede ajustar automáticamente los valores, lo que puede ser confuso. Por ejemplo, si se intenta establecer el 30 de febrero, `mktime` ajustará automáticamente a 1 de marzo.

## Resumen en una línea
La función `mktime` en C convierte una estructura de tiempo en un tiempo de epoch, permitiendo la manipulación efectiva de fechas y horas.