<!--
Meta Description: # bsearch: Búsqueda Binaria en C ## Sinopsis La función `bsearch` en C permite realizar una búsqueda binaria eficiente sobre un array ordenado. Es una...
Meta Keywords: bsearch, int, array, que, elemento
-->

# bsearch: Búsqueda Binaria en C

## Sinopsis
La función `bsearch` en C permite realizar una búsqueda binaria eficiente sobre un array ordenado. Es una herramienta esencial para desarrolladores que buscan optimizar su acceso a datos.

## Documentación

### Propósito
`bsearch` se utiliza para encontrar un elemento en un array de forma rápida y eficiente, utilizando el algoritmo de búsqueda binaria. Este método es mucho más rápido que la búsqueda lineal, especialmente en arrays grandes, ya que reduce el número de comparaciones necesarias.

### Uso
La función `bsearch` se encuentra en la biblioteca estándar de C `<stdlib.h>`. Su prototipo es el siguiente:

```c
void *bsearch(const void *key, const void *base, size_t nmemb, size_t size, int (*compar)(const void *, const void *));
```

#### Parámetros
- `key`: Un puntero al elemento que se busca.
- `base`: Un puntero al primer elemento del array donde se realizará la búsqueda.
- `nmemb`: Número de elementos en el array.
- `size`: El tamaño en bytes de cada elemento del array.
- `compar`: Un puntero a una función que compara dos elementos.

#### Retorno
`bsearch` devuelve un puntero al elemento encontrado dentro del array. Si no se encuentra el elemento, devuelve `NULL`.

## Ejemplos

### Ejemplo Básico de Uso
A continuación se muestra un ejemplo básico de cómo utilizar `bsearch`:

```c
#include <stdio.h>
#include <stdlib.h>

int comparar(const void *a, const void *b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int array[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    int key = 5;
    int *resultado;

    resultado = bsearch(&key, array, 9, sizeof(int), comparar);

    if (resultado) {
        printf("Elemento encontrado: %d\n", *resultado);
    } else {
        printf("Elemento no encontrado.\n");
    }

    return 0;
}
```

### Ejemplo con Estructuras
`bsearch` también se puede utilizar con estructuras. Aquí hay un ejemplo:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    int id;
    char nombre[20];
} Estudiante;

int compararEstudiantes(const void *a, const void *b) {
    return ((Estudiante*)a)->id - ((Estudiante*)b)->id;
}

int main() {
    Estudiante estudiantes[] = {
        {1, "Juan"},
        {2, "Ana"},
        {3, "Pedro"}
    };

    Estudiante clave = {2, ""};
    Estudiante *resultado;

    resultado = bsearch(&clave, estudiantes, 3, sizeof(Estudiante), compararEstudiantes);

    if (resultado) {
        printf("Estudiante encontrado: %s\n", resultado->nombre);
    } else {
        printf("Estudiante no encontrado.\n");
    }

    return 0;
}
```

## Explicación
### Errores Comunes
- **Array no ordenado**: `bsearch` solo funciona con arrays que están ordenados. Si el array no está ordenado, el resultado será indefinido.
- **Función de comparación incorrecta**: La función de comparación debe devolver un valor negativo, cero o positivo. Si no se implementa correctamente, `bsearch` no funcionará adecuadamente.
- **Tamaño incorrecto**: Asegúrate de que el tamaño del elemento, `size`, sea correcto. Si no coincide con el tamaño de los elementos en el array, puede provocar comportamientos inesperados.

### Notas Adicionales
- La complejidad del algoritmo de búsqueda binaria es O(log n), lo que lo hace muy eficiente para grandes conjuntos de datos.
- `bsearch` es parte del estándar ANSI C, lo que garantiza su disponibilidad en la mayoría de las implementaciones del lenguaje.

## Resumen en Una Línea
La función `bsearch` en C permite realizar búsquedas binarias eficientes en arrays ordenados.