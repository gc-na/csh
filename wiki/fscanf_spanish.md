<!--
Meta Description: # fscanf: Lectura Formateada de Datos en C ## Sinopsis `fscanf` es una función en C que permite la lectura de datos desde un archivo de manera formate...
Meta Keywords: file, datos, fscanf, archivo, que
-->

# fscanf: Lectura Formateada de Datos en C

## Sinopsis
`fscanf` es una función en C que permite la lectura de datos desde un archivo de manera formateada, facilitando la extracción de información con un control preciso sobre el formato de los datos.

## Documentación
### Propósito
La función `fscanf` se utiliza para leer datos de un flujo de entrada (como un archivo) y almacenarlos en variables según un formato especificado. Es parte de la biblioteca estándar de C y se define en el encabezado `<stdio.h>`.

### Uso
La sintaxis de `fscanf` es la siguiente:

```c
int fscanf(FILE *stream, const char *format, ...);
```

- `stream`: un puntero al archivo desde el cual se desea leer.
- `format`: una cadena de formato que especifica cómo se deben interpretar los datos.
- `...`: una lista de punteros a variables donde se almacenarán los datos leídos.

### Detalles
- Devuelve el número de elementos leídos con éxito o `EOF` si se alcanza el final del archivo o si ocurre un error.
- Los formatos pueden incluir especificadores como `%d`, `%f`, `%s`, etc., que indican el tipo de datos a leer.
- Es importante asegurarse de que las variables apuntadas tengan el tipo de dato adecuado para evitar comportamientos indefinidos.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>

int main() {
    FILE *file;
    int age;
    char name[50];

    file = fopen("datos.txt", "r");
    if (file == NULL) {
        perror("Error al abrir el archivo");
        return -1;
    }

    fscanf(file, "%49s %d", name, &age);
    printf("Nombre: %s, Edad: %d\n", name, age);

    fclose(file);
    return 0;
}
```

### Ejemplo de Lectura Múltiple
```c
#include <stdio.h>

int main() {
    FILE *file;
    float height;
    int weight;

    file = fopen("medidas.txt", "r");
    if (file == NULL) {
        perror("Error al abrir el archivo");
        return -1;
    }

    fscanf(file, "%f %d", &height, &weight);
    printf("Altura: %.2f, Peso: %d\n", height, weight);

    fclose(file);
    return 0;
}
```

## Explicación
### Errores Comunes
- **Formato Incorrecto**: Asegúrate de que el formato de entrada coincida exactamente con el tipo de datos de las variables. Por ejemplo, intentar leer un entero con `%f` causará un error.
- **Manejo de Errores**: Siempre verifica si el archivo se abrió correctamente y si `fscanf` devuelve el número esperado de elementos leídos.
- **Buffer Overflow**: Al usar `%s`, es fundamental especificar el tamaño máximo para evitar desbordamientos de búfer, como en `%49s`.

## Resumen en Una Línea
`fscanf` es una función en C que permite la lectura de datos formateados desde un archivo, facilitando la extracción controlada de información.