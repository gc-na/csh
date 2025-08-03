<!--
Meta Description: # Memmove en C: Copia Segura de Memoria ## Sinopsis `memmove` es una función de la biblioteca estándar de C que permite copiar un bloque de memoria de...
Meta Keywords: memoria, memmove, destino, que, origen
-->

# Memmove en C: Copia Segura de Memoria

## Sinopsis
`memmove` es una función de la biblioteca estándar de C que permite copiar un bloque de memoria de una ubicación a otra de manera segura, incluso si las áreas de origen y destino se superponen.

## Documentación
La función `memmove` está declarada en el encabezado `<string.h>` y su prototipo es el siguiente:

```c
void *memmove(void *destino, const void *origen, size_t n);
```

### Propósito
`memmove` se utiliza para copiar `n` bytes desde la dirección de memoria `origen` a la dirección de memoria `destino`. A diferencia de `memcpy`, `memmove` maneja correctamente las superposiciones entre las áreas de memoria, lo que la convierte en la opción preferida cuando se copian bloques de memoria que pueden solaparse.

### Uso
- **Parámetros:**
  - `destino`: Puntero a la dirección de memoria de destino donde se copiarán los bytes.
  - `origen`: Puntero a la dirección de memoria desde la cual se copiarán los bytes.
  - `n`: Número de bytes a copiar.

- **Retorno:** Devuelve un puntero al destino.

### Ejemplo de Uso
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hola, Mundo!";
    printf("Antes de memmove: %s\n", str);
    
    // Superposición de memoria
    memmove(str + 5, str, 7);
    printf("Después de memmove: %s\n", str); // Salida: "Hola, Hola, Mundo!"

    return 0;
}
```

## Explicación
### Errores Comunes
1. **No Inicializar el Destino**: Asegúrate de que el puntero `destino` apunta a un área de memoria válida y suficientemente grande para albergar los datos copiados.
   
2. **Uso Incorrecto de Tamaños**: Es crucial especificar correctamente el tamaño `n` para evitar desbordamientos o copias incompletas.

3. **Confusión con `memcpy`**: Aunque ambas funciones se utilizan para copiar memoria, recuerda que `memmove` es la opción segura para áreas superpuestas. Usar `memcpy` en estas circunstancias puede resultar en datos corruptos.

4. **Control de Superposición**: Si `origen` y `destino` se superponen, `memmove` maneja internamente la copia de manera que no se produzcan errores, pero es fundamental asegurarse de que el tamaño `n` no exceda las dimensiones de las áreas de memoria involucradas.

## Resumen en Una Línea
`memmove` es una función en C que permite copiar bloques de memoria, asegurando la correcta manipulación en caso de superposición entre el origen y el destino.