<!--
Meta Description: # __TIME__: Macro de Preprocesador en C para Obtener la Hora de Compilación ## Sinopsis La macro `__TIME__` en C es una característica del preprocesad...
Meta Keywords: __time__, para, que, macro, compilación
-->

# __TIME__: Macro de Preprocesador en C para Obtener la Hora de Compilación

## Sinopsis
La macro `__TIME__` en C es una característica del preprocesador que permite obtener la hora de compilación del programa. Esta macro es útil para incluir información sobre la fecha y hora en la que se compiló el código, lo que puede ser ventajoso para la depuración y el registro de versiones.

## Documentación
### Propósito
La macro `__TIME__` se utiliza para obtener la hora actual en el momento de la compilación del programa. Esta macro se define como una cadena de texto en el formato "HH:MM:SS", donde:
- **HH**: Horas (00-23)
- **MM**: Minutos (00-59)
- **SS**: Segundos (00-59)

### Uso
La macro se puede utilizar directamente en el código C. Se suele usar en situaciones donde es necesario mostrar información sobre la versión del software o para propósitos de auditoría.

### Detalles
- `__TIME__` es una macro del preprocesador, lo que significa que se evalúa y se reemplaza antes de la compilación.
- No se debe confundir con `__DATE__`, que proporciona la fecha de compilación en formato "MMM DD YYYY".
- La macro es de solo lectura y no se puede modificar.

## Ejemplos
### Ejemplo Básico
A continuación se muestra un ejemplo simple de cómo utilizar `__TIME__` en un programa en C:

```c
#include <stdio.h>

int main() {
    printf("Este programa fue compilado a las: %s\n", __TIME__);
    return 0;
}
```

Al compilar y ejecutar este programa, la salida reflejará la hora exacta en la que se realizó la compilación, por ejemplo:
```
Este programa fue compilado a las: 14:35:22
```

### Ejemplo de Uso en Registro de Versiones
Se puede utilizar `__TIME__` para incluir la hora de compilación en un registro de versiones:

```c
#include <stdio.h>

void mostrarVersion() {
    printf("Versión 1.0 - Compilado a las: %s\n", __TIME__);
}

int main() {
    mostrarVersion();
    return 0;
}
```

La salida será similar a:
```
Versión 1.0 - Compilado a las: 09:02:15
```

## Explicación
### Errores Comunes
- **Confusión entre `__TIME__` y `__DATE__`**: Asegúrate de usar `__TIME__` para obtener la hora y `__DATE__` para la fecha. Usar una en lugar de la otra puede llevar a confusiones en el registro de compilación.
- **Formato de salida**: Recuerda que el formato de `__TIME__` es fijo ("HH:MM:SS"). No intentes modificarlo, ya que es una cadena de texto inmutable.

### Notas Adicionales
- `__TIME__` es útil para auditorías y para mantener un registro de cuándo se generó una versión específica de un programa.
- El valor de `__TIME__` se actualiza cada vez que se compila el código, por lo que es ideal para entornos de desarrollo donde las compilaciones son frecuentes.

## Resumen en Una Línea
La macro `__TIME__` en C proporciona la hora de compilación del programa en formato "HH:MM:SS", facilitando el seguimiento de versiones y auditorías.