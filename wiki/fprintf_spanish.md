<!--
Meta Description: # fprintf en C: Guía Completa de Uso y Ejemplos ## Sinopsis `fprintf` es una función de la biblioteca estándar de C que permite imprimir datos formate...
Meta Keywords: archivo, fprintf, que, datos, salida
-->

# fprintf en C: Guía Completa de Uso y Ejemplos

## Sinopsis
`fprintf` es una función de la biblioteca estándar de C que permite imprimir datos formateados en un archivo o flujo de salida. Es ampliamente utilizada para la creación de archivos y la salida de datos en formatos específicos.

## Documentación
### Propósito
La función `fprintf` se utiliza para escribir datos formateados en un archivo o en un flujo de salida, como la consola. A diferencia de `printf`, que imprime en la salida estándar, `fprintf` permite especificar el destino de la salida.

### Uso
La sintaxis básica de `fprintf` es la siguiente:

```c
int fprintf(FILE *stream, const char *format, ...);
```

- **stream**: un puntero a un objeto de tipo `FILE` que representa el archivo o flujo en el que se escribirá.
- **format**: una cadena de formato que especifica cómo se deben imprimir los argumentos.
- **...**: una lista variable de argumentos que se formatearán según la cadena de formato.

### Detalles
- `fprintf` devuelve un número entero que representa el número de caracteres escritos, o un valor negativo si ocurre un error.
- La cadena de formato puede contener especificadores que indican el tipo de datos a imprimir, como `%d` para enteros, `%f` para números de punto flotante, y `%s` para cadenas de caracteres.

## Ejemplos
### Ejemplo Básico
A continuación, se muestra un ejemplo simple de cómo usar `fprintf` para escribir en un archivo:

```c
#include <stdio.h>

int main() {
    FILE *archivo;
    archivo = fopen("salida.txt", "w"); // Abrir archivo en modo escritura

    if (archivo != NULL) {
        fprintf(archivo, "Hola, mundo!\n");
        fprintf(archivo, "El valor de pi es aproximadamente: %.2f\n", 3.14159);
        fclose(archivo); // Cerrar el archivo
    } else {
        printf("Error al abrir el archivo.\n");
    }

    return 0;
}
```

### Ejemplo con varios tipos de datos
```c
#include <stdio.h>

int main() {
    FILE *archivo;
    archivo = fopen("datos.txt", "w");

    if (archivo != NULL) {
        int edad = 30;
        float altura = 1.75;
        fprintf(archivo, "Edad: %d años\nAltura: %.2f metros\n", edad, altura);
        fclose(archivo);
    }

    return 0;
}
```

## Explicación
Al utilizar `fprintf`, es importante tener en cuenta los siguientes puntos:

- **Verificación de errores**: Siempre verifica si el archivo se abrió correctamente antes de intentar escribir en él.
- **Especificadores de formato**: Asegúrate de usar el especificador correcto para el tipo de dato que deseas imprimir. Usar un especificador incorrecto puede resultar en comportamientos inesperados.
- **Buffering**: La salida puede estar en un buffer; asegúrate de cerrar el archivo con `fclose` para garantizar que todos los datos se escriban correctamente.
- **Formato de cadena**: La cadena de formato debe coincidir con el número y tipo de argumentos proporcionados para evitar errores en tiempo de ejecución.

## Resumen en Una Línea
`fprintf` es una función en C que permite imprimir datos formateados en un archivo o flujo de salida específico, ofreciendo flexibilidad y control sobre la salida de datos.