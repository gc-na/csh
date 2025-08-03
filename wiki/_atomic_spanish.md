<!--
Meta Description: # _Atomic en C: Sincronización y Acceso Seguro a Datos Compartidos ## Sinopsis El modificador `_Atomic` en C se utiliza para declarar variables que pu...
Meta Keywords: hilos, int, _atomic, que, atómicas
-->

# _Atomic en C: Sincronización y Acceso Seguro a Datos Compartidos

## Sinopsis
El modificador `_Atomic` en C se utiliza para declarar variables que pueden ser accedidas de forma segura en un entorno de múltiples hilos, garantizando operaciones atómicas y evitando condiciones de carrera.

## Documentación
El modificador `_Atomic` forma parte del estándar C11 y permite que los programadores definan variables que son accesibles de manera segura desde diferentes hilos. Esto es crucial en la programación concurrente, donde múltiples hilos pueden intentar modificar la misma variable simultáneamente.

### Propósito
El propósito del modificador `_Atomic` es proporcionar un medio para realizar operaciones atómicas, es decir, operaciones que se completan en un solo paso desde la perspectiva de otros hilos. Esto evita que los hilos lean valores intermedios y asegura la coherencia de los datos.

### Uso
Para declarar una variable como atómica, se utiliza la palabra clave `_Atomic` antes del tipo de la variable. Por ejemplo:

```c
_Atomic int contador;
```

Con esto, `contador` se convierte en una variable que puede ser leída o escrita de manera segura por múltiples hilos.

### Detalles
- Las operaciones en variables atómicas son garantizadas a ser atómicas por el compilador.
- Se recomienda el uso de funciones específicas (como `atomic_load`, `atomic_store`, `atomic_fetch_add`, etc.) para manipular estas variables en lugar de usar operadores aritméticos convencionales.
- Las variables atómicas pueden ser de cualquier tipo básico, como `int`, `float`, y estructuras, siempre y cuando las operaciones sean adecuadas al tipo.

## Ejemplos
### Ejemplo Básico
```c
#include <stdio.h>
#include <stdatomic.h>
#include <pthread.h>

_Atomic int contador = 0;

void* incrementar(void* arg) {
    for (int i = 0; i < 1000; i++) {
        atomic_fetch_add(&contador, 1);
    }
    return NULL;
}

int main() {
    pthread_t hilos[10];

    for (int i = 0; i < 10; i++) {
        pthread_create(&hilos[i], NULL, incrementar, NULL);
    }
    
    for (int i = 0; i < 10; i++) {
        pthread_join(hilos[i], NULL);
    }

    printf("Valor final de contador: %d\n", contador);
    return 0;
}
```

### Ejemplo con Carga y Almacenamiento
```c
#include <stdio.h>
#include <stdatomic.h>

int main() {
    _Atomic int valor = 0;

    atomic_store(&valor, 5);
    int resultado = atomic_load(&valor);

    printf("Valor almacenado: %d\n", resultado); // Salida: Valor almacenado: 5
    return 0;
}
```

## Explicación
### Errores Comunes
1. **Uso de operadores aritméticos normales**: No se deben usar operadores como `++` o `+=` directamente en variables atómicas, ya que no garantizan la atomicidad.
2. **Olvidar inicializar**: Asegúrate de inicializar la variable atómica antes de su uso. El acceso a una variable no inicializada puede llevar a resultados indefinidos.
3. **Confusión con visibilidad**: Aunque las operaciones son atómicas, no garantizan la visibilidad de las actualizaciones entre hilos sin el uso adecuado de sincronización.

## Resumen en Una Línea
El modificador `_Atomic` en C permite la creación de variables que aseguran operaciones atómicas, cruciales para la programación concurrente en entornos multihilo.