<!--
Meta Description: # strftime en C: Formateo de Fechas y Horas ## Sinopsis `strftime` es una función en C que permite formatear fechas y horas de acuerdo a un formato es...
Meta Keywords: buffer, formato, strftime, que, time
-->

# strftime en C: Formateo de Fechas y Horas

## Sinopsis
`strftime` es una función en C que permite formatear fechas y horas de acuerdo a un formato específico definido por el usuario. Es parte de la biblioteca estándar `<time.h>`.

## Documentación
La función `strftime` se utiliza para convertir estructuras de tiempo (`struct tm`) en cadenas de caracteres con un formato deseado. Su propósito principal es facilitar la presentación de fechas y horas en un formato legible y personalizado.

### Sintaxis
```c
size_t strftime(char *s, size_t max, const char *format, const struct tm *tm);
```

### Parámetros
- **char *s**: Puntero a la cadena de caracteres donde se almacenará el resultado formateado.
- **size_t max**: Tamaño máximo del buffer `s`.
- **const char *format**: Cadena de formato que especifica cómo se debe formatear la fecha y hora.
- **const struct tm *tm**: Puntero a una estructura `tm` que contiene la información de la fecha y hora a formatear.

### Retorno
Devuelve el número de caracteres escritos en la cadena de destino, sin contar el carácter nulo final. Si el tamaño del buffer es insuficiente, la función devuelve 0.

### Formato de Cadena
Los especificadores de formato más comunes incluyen:
- `%Y`: Año completo (ej. 2023)
- `%m`: Mes (01-12)
- `%d`: Día del mes (01-31)
- `%H`: Hora en formato 24 horas (00-23)
- `%M`: Minutos (00-59)
- `%S`: Segundos (00-59)

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm tm = *localtime(&t);
    char buffer[80];

    strftime(buffer, sizeof(buffer), "%Y-%m-%d %H:%M:%S", &tm);
    printf("Fecha y hora: %s\n", buffer);
    return 0;
}
```
**Salida Esperada:**
```
Fecha y hora: 2023-10-11 15:45:30
```

### Ejemplo con Formato Personalizado
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm tm = *localtime(&t);
    char buffer[100];

    strftime(buffer, sizeof(buffer), "Hoy es %A, %d de %B de %Y", &tm);
    printf("%s\n", buffer);
    return 0;
}
```
**Salida Esperada:**
```
Hoy es miércoles, 11 de octubre de 2023
```

## Explicación
### Errores Comunes
1. **Buffer Insuficiente**: Si el tamaño del buffer `s` es menor que el número de caracteres que `strftime` intentará escribir, se devolverá 0 y no se almacenará nada. Siempre asegúrate de que el buffer tiene suficiente espacio.
   
2. **Formato Incorrecto**: Usar especificadores de formato no válidos puede llevar a resultados inesperados o a que no se imprima nada.

3. **Uso de Estructura Vacía**: Asegúrate de que la estructura `tm` está correctamente inicializada antes de pasarla a `strftime`.

### Notas Adicionales
- Es importante incluir la biblioteca `<time.h>` para poder usar `strftime`.
- La función es parte de la biblioteca estándar de C, por lo que es ampliamente soportada en diversos compiladores y plataformas.

## Resumen en Una Línea
`strftime` es una función en C que permite formatear fechas y horas en cadenas de caracteres personalizadas según un formato especificado.