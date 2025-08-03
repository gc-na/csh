<!--
Meta Description: # La palabra clave "extern" en C: Definición y Uso ## Sinopsis La palabra clave `extern` en C se utiliza para declarar variables y funciones que tiene...
Meta Keywords: extern, que, externa, variable, del
-->

# La palabra clave "extern" en C: Definición y Uso

## Sinopsis
La palabra clave `extern` en C se utiliza para declarar variables y funciones que tienen una visibilidad externa, permitiendo que sean accesibles desde otros archivos de código fuente. Es esencial para la gestión de enlaces en programas grandes.

## Documentación
La palabra clave `extern` se utiliza principalmente en dos contextos dentro del lenguaje de programación C:

1. **Declaración de variables**: Cuando se declara una variable con `extern`, se indica que la variable está definida en otro archivo o en otro lugar del mismo archivo. Esto permite que diferentes módulos del programa puedan compartir la misma variable global.

   ```c
   extern int contador; // Declaración de una variable externa
   ```

2. **Declaración de funciones**: Por defecto, las funciones son externas en C. Sin embargo, el uso de `extern` puede hacer explícito que una función está definida en otro archivo, lo que puede ser útil para la claridad del código.

   ```c
   extern void funcionEjemplo(); // Declaración de una función externa
   ```

Para que `extern` funcione correctamente, la variable o función debe estar definida en algún lugar del programa, normalmente en otro archivo de implementación que esté vinculado durante el proceso de compilación.

## Ejemplos
### Ejemplo de Variable Externa
```c
// archivo1.c
#include <stdio.h>

int contador = 0; // Definición de la variable

void incrementar() {
    contador++;
}

// archivo2.c
#include <stdio.h>

extern int contador; // Declaración de la variable externa

void mostrarContador() {
    printf("Contador: %d\n", contador);
}
```

### Ejemplo de Función Externa
```c
// archivo1.c
#include <stdio.h>

void saludo() {
    printf("¡Hola desde archivo1!\n");
}

// archivo2.c
#include <stdio.h>

extern void saludo(); // Declaración de la función externa

int main() {
    saludo(); // Llamada a la función externa
    return 0;
}
```

## Explicación
Al utilizar `extern`, es importante tener en cuenta lo siguiente:

- **Visibilidad**: Las variables declaradas como `extern` no ocupan espacio en memoria hasta que sean definidas en algún lugar del programa. Esto significa que no se puede inicializar una variable externa en su declaración.
  
- **Alcance**: Las variables y funciones externas son accesibles desde otros archivos siempre que se incluya la declaración correspondiente. Esto facilita el manejo de grandes proyectos, donde el código se divide en múltiples archivos.

- **Confusión con `static`**: Asegúrate de no confundir `extern` con `static`. Mientras que `extern` permite el acceso a variables y funciones fuera del archivo actual, `static` limita su visibilidad al archivo donde están definidas.

## Resumen en una línea
La palabra clave `extern` en C se utiliza para declarar variables y funciones con visibilidad externa, permitiendo su acceso desde otros archivos del programa.