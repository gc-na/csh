<!--
Meta Description: # ftell en C: Función para Obtener la Posición del Cursor en un Archivo ## Sinopsis La función `ftell` en C se utiliza para determinar la posición act...
Meta Keywords: archivo, ftell, posición, del, cursor
-->

# ftell en C: Función para Obtener la Posición del Cursor en un Archivo

## Sinopsis
La función `ftell` en C se utiliza para determinar la posición actual del cursor en un archivo abierto. Es una herramienta esencial para gestionar la lectura y escritura de datos en archivos, permitiendo a los programadores conocer dónde se encuentran dentro de un archivo en cualquier momento.

## Documentación

### Propósito
`ftell` proporciona la capacidad de obtener la posición actual del puntero de archivo en un flujo de datos. Esto es útil cuando se desea realizar operaciones de lectura o escritura de manera controlada y precisa.

### Uso
La función `ftell` se declara en el encabezado `<stdio.h>`. Su sintaxis es la siguiente:

```c
long ftell(FILE *stream);
```

### Parámetros
- `stream`: Un puntero a un objeto de tipo `FILE` que representa el archivo abierto del cual se quiere conocer la posición.

### Valor de Retorno
Devuelve la posición actual del cursor en el archivo como un valor de tipo `long`. Si ocurre un error, devuelve `-1L` y establece el indicador de error correspondiente al flujo.

## Ejemplos

### Ejemplo Básico
A continuación se presenta un ejemplo simple que muestra cómo utilizar `ftell` para obtener la posición del cursor en un archivo:

```c
#include <stdio.h>

int main() {
    FILE *archivo;
    long posicion;

    // Abrimos el archivo en modo lectura
    archivo = fopen("ejemplo.txt", "r");
    if (archivo == NULL) {
        perror("Error al abrir el archivo");
        return 1;
    }

    // Leemos un carácter
    fgetc(archivo);

    // Obtenemos la posición actual del cursor
    posicion = ftell(archivo);
    if (posicion == -1L) {
        perror("Error al obtener la posición");
        fclose(archivo);
        return 1;
    }

    printf("La posición actual del cursor es: %ld\n", posicion);

    // Cerramos el archivo
    fclose(archivo);
    return 0;
}
```

### Ejemplo de Uso en Escritura
En este ejemplo, se muestra cómo `ftell` se puede utilizar después de escribir en un archivo:

```c
#include <stdio.h>

int main() {
    FILE *archivo;
    long posicion;

    // Abrimos el archivo en modo escritura
    archivo = fopen("ejemplo.txt", "w");
    if (archivo == NULL) {
        perror("Error al abrir el archivo");
        return 1;
    }

    // Escribimos una cadena en el archivo
    fprintf(archivo, "Hola, mundo!");

    // Obtenemos la posición actual del cursor
    posicion = ftell(archivo);
    if (posicion == -1L) {
        perror("Error al obtener la posición");
        fclose(archivo);
        return 1;
    }

    printf("La posición actual del cursor después de escribir es: %ld\n", posicion);

    // Cerramos el archivo
    fclose(archivo);
    return 0;
}
```

## Explicación
Al usar `ftell`, es importante tener en cuenta lo siguiente:

- **Archivos no abiertos**: Si se llama a `ftell` en un flujo que no está abierto correctamente, se producirá un error. Siempre verifique que el archivo se haya abierto sin problemas.
- **Modo de apertura**: El resultado de `ftell` puede variar según el modo en que se abrió el archivo (lectura, escritura, o ambos). Asegúrese de que el modo sea apropiado para sus operaciones.
- **Operaciones de lectura y escritura**: Si se realizan operaciones de lectura y escritura en el mismo flujo, la posición del cursor puede cambiar, lo que afectará el valor devuelto por `ftell`.

## Resumen en Una Línea
La función `ftell` en C permite obtener la posición actual del cursor en un archivo abierto, facilitando la gestión de operaciones de entrada/salida.