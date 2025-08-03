<!--
Meta Description: # sprintf y snprintf en C: Formateo Seguro de Cadenas ## Sinopsis La función `snprintf` en C permite formatear cadenas de caracteres de manera segura,...
Meta Keywords: que, snprintf, caracteres, buffer, tamaño
-->

# sprintf y snprintf en C: Formateo Seguro de Cadenas

## Sinopsis
La función `snprintf` en C permite formatear cadenas de caracteres de manera segura, evitando desbordamientos de búfer al especificar un tamaño máximo para el resultado. Es una herramienta esencial para la manipulación de cadenas en aplicaciones que requieren un manejo preciso de la memoria.

## Documentación

### Propósito
`snprintf` es una función de la biblioteca estándar de C que se utiliza para escribir datos formateados en una cadena. A diferencia de `sprintf`, `snprintf` incluye un parámetro que limita la cantidad de caracteres escritos, lo que ayuda a prevenir errores de desbordamiento de búfer.

### Uso
La función `snprintf` se declara en el encabezado `<stdio.h>` y su prototipo es el siguiente:

```c
int snprintf(char *str, size_t size, const char *format, ...);
```

#### Parámetros
- `str`: Un puntero a la cadena de caracteres donde se almacenará el resultado formateado.
- `size`: El tamaño máximo de caracteres que se escribirán en `str`, incluyendo el carácter nulo (`\0`).
- `format`: Una cadena que especifica cómo se formatearán los valores que se pasan como argumentos adicionales.
- `...`: Argumentos adicionales que se formatearán de acuerdo con el especificador de formato.

#### Valor de Retorno
`snprintf` devuelve el número de caracteres que se habrían escrito si no se hubiera alcanzado el límite de tamaño. Si el tamaño es cero, devuelve la longitud de la cadena que habría generado.

## Ejemplos

### Ejemplo básico
```c
#include <stdio.h>

int main() {
    char buffer[50];
    int n = snprintf(buffer, sizeof(buffer), "Hola, %s! Tienes %d mensajes.", "Juan", 5);
    
    printf("%s\n", buffer); // Salida: Hola, Juan! Tienes 5 mensajes.
    printf("Número de caracteres escritos: %d\n", n); // Salida: Número de caracteres escritos: 42
    return 0;
}
```

### Ejemplo con límite
```c
#include <stdio.h>

int main() {
    char buffer[10];
    int n = snprintf(buffer, sizeof(buffer), "Hola, Mundo!");
    
    printf("Contenido del buffer: %s\n", buffer); // Salida: Contenido del buffer: Hola, Mu
    printf("Número de caracteres escritos: %d\n", n); // Salida: Número de caracteres escritos: 13
    return 0;
}
```

## Explicación
Una de las trampas más comunes al usar `snprintf` es no considerar el tamaño del búfer. Si se establece un tamaño menor que la longitud de la cadena formateada, la cadena se truncará, lo que puede llevar a resultados inesperados. Además, es importante recordar que `snprintf` siempre agrega un carácter nulo al final de la cadena, siempre y cuando el tamaño sea mayor que cero.

Otra consideración es que, si el tamaño especificado es cero, `snprintf` no escribe nada en el búfer, pero aún así devuelve la longitud que habría tenido la cadena completa.

## Resumen en una línea
`snprintf` es una función en C que permite formatear cadenas de manera segura, limitando el número de caracteres escritos en el búfer de salida.