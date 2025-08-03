<!--
Meta Description: # memcpy: Copia de Memoria en C ## Sinopsis `memcpy` es una función de la biblioteca estándar de C que permite copiar bloques de memoria de un lugar a...
Meta Keywords: memoria, memcpy, destino, función, que
-->

# memcpy: Copia de Memoria en C

## Sinopsis
`memcpy` es una función de la biblioteca estándar de C que permite copiar bloques de memoria de un lugar a otro. Es ampliamente utilizada para manejar datos en estructuras, arreglos y buffers.

## Documentación
### Propósito
La función `memcpy` se utiliza para copiar una cantidad específica de bytes desde una dirección de memoria de origen a una dirección de memoria de destino. Es especialmente útil en programación de bajo nivel, donde se requiere manipular la memoria directamente.

### Uso
La declaración de la función es la siguiente:

```c
void *memcpy(void *destino, const void *origen, size_t n);
```

- **destino**: Puntero a la dirección de memoria donde se copiarán los datos.
- **origen**: Puntero a la dirección de memoria desde donde se copiarán los datos.
- **n**: Número de bytes a copiar.

### Detalles
- La función devuelve un puntero al destino.
- `memcpy` no verifica la superposición de las áreas de memoria de origen y destino. Si estas áreas se superponen, se debe usar `memmove` en su lugar.
- La función es eficiente, pero debe ser utilizada cuidadosamente para evitar errores de memoria y sobreescritura de datos.

## Ejemplos
### Ejemplo Básico

```c
#include <stdio.h>
#include <string.h>

int main() {
    char origen[] = "Hola, Mundo!";
    char destino[20];

    memcpy(destino, origen, strlen(origen) + 1); // +1 para incluir el carácter nulo
    printf("Destino: %s\n", destino);
    
    return 0;
}
```

### Copia de Datos en Arreglos

```c
#include <stdio.h>
#include <string.h>

int main() {
    int arreglo_origen[] = {1, 2, 3, 4, 5};
    int arreglo_destino[5];

    memcpy(arreglo_destino, arreglo_origen, sizeof(arreglo_origen));
    
    for (int i = 0; i < 5; i++) {
        printf("%d ", arreglo_destino[i]);
    }
    
    return 0;
}
```

## Explicación
### Errores Comunes
1. **Superposición de Memoria**: Usar `memcpy` con áreas de memoria que se superponen puede provocar resultados indefinidos. Se recomienda usar `memmove` en tales casos.
2. **Tamaño Incorrecto**: Asegurarse de que el tamaño `n` no exceda el tamaño del buffer de destino es crucial para evitar desbordamientos de buffer.
3. **Falta de Carácter Nulo**: Al copiar cadenas, es importante incluir el carácter nulo (`\0`) para evitar la impresión de datos no deseados.

### Notas Adicionales
- `memcpy` es parte de la biblioteca `<string.h>`, por lo que es necesario incluirla.
- La función es generalmente más rápida que un bucle que copia byte por byte.

## Resumen en Una Línea
`memcpy` es una función de C que permite copiar bloques de memoria de manera eficiente entre direcciones de memoria.