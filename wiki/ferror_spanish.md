<!--
Meta Description: # ferror en C: Manejo de Errores en Operaciones de Archivos ## Sinopsis La función `ferror` en C se utiliza para verificar si ha ocurrido un error en ...
Meta Keywords: file, ferror, error, archivo, flujo
-->

# ferror en C: Manejo de Errores en Operaciones de Archivos

## Sinopsis
La función `ferror` en C se utiliza para verificar si ha ocurrido un error en una operación de entrada/salida en un flujo de archivo. Es una herramienta esencial para el manejo de errores al trabajar con archivos.

## Documentación
La función `ferror` se declara en el encabezado `<stdio.h>` y su prototipo es el siguiente:

```c
int ferror(FILE *stream);
```

### Propósito
`ferror` permite al programador determinar si una operación anterior en un flujo de archivo ha fallado. Esto es crucial para la depuración y la gestión de errores, ya que asegura que las operaciones de archivo se realicen de manera confiable.

### Uso
- **Parámetro**: La función recibe un solo argumento, `stream`, que es un puntero a un objeto `FILE`, representando el flujo de archivo que se desea comprobar.
- **Retorno**: Devuelve un valor distinto de cero si se ha producido un error en el flujo especificado; de lo contrario, devuelve cero.

### Detalles
- `ferror` no restablece el estado de error del flujo; simplemente verifica su estado actual.
- Para restablecer el estado de error, se puede usar la función `clearerr`, que también se encuentra en `<stdio.h>`.

## Ejemplos
### Ejemplo básico
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("archivo.txt", "r");
    if (file == NULL) {
        perror("Error al abrir el archivo");
        return 1;
    }

    // Realizamos una operación de lectura
    char buffer[100];
    if (fgets(buffer, sizeof(buffer), file) == NULL) {
        if (ferror(file)) {
            perror("Error de lectura");
        }
    }

    fclose(file);
    return 0;
}
```

### Ejemplo con `clearerr`
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("archivo.txt", "r");
    if (file == NULL) {
        perror("Error al abrir el archivo");
        return 1;
    }

    // Intentamos leer
    char buffer[100];
    if (fgets(buffer, sizeof(buffer), file) == NULL && ferror(file)) {
        printf("Se detectó un error de lectura.\n");
        clearerr(file); // Restablecemos el estado de error
    }

    fclose(file);
    return 0;
}
```

## Explicación
- **Errores Comunes**: Un error frecuente es no verificar el retorno de funciones de entrada/salida antes de llamar a `ferror`. Es importante comprobar si la operación realmente falló.
- **Flujos cerrados**: Llamar a `ferror` en un flujo que ya ha sido cerrado puede llevar a comportamientos indefinidos. Asegúrate de que el flujo esté activo.
- **Combinación con `feof`**: Es útil combinar `ferror` con `feof` para diferenciar entre el final del archivo y un error de lectura.

## Resumen en una línea
La función `ferror` en C se utiliza para comprobar el estado de error de un flujo de archivo, asegurando un manejo adecuado de errores en operaciones de entrada/salida.