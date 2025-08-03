<!--
Meta Description: # __STDC__: Definición y Uso en el Lenguaje C ## Sinopsis `__STDC__` es una macro predefinida en C que indica si el compilador está siguiendo el están...
Meta Keywords: estándar, __stdc__, con, que, compilador
-->

# __STDC__: Definición y Uso en el Lenguaje C

## Sinopsis
`__STDC__` es una macro predefinida en C que indica si el compilador está siguiendo el estándar del lenguaje C definido por la ANSI (American National Standards Institute) y ISO (International Organization for Standardization).

## Documentación
La macro `__STDC__` es parte del preprocesador de C y se define automáticamente por los compiladores que cumplen con el estándar ANSI C (C89) y versiones posteriores. Su propósito principal es permitir a los desarrolladores verificar si el código que escriben es compatible con el estándar C. Si `__STDC__` está definido, significa que se está utilizando un compilador que se adhiere a este estándar.

### Propósito
- Proporcionar una forma sencilla de verificar la compatibilidad del compilador con el estándar C.
- Facilitar la escritura de código multiplataforma y portable.

### Uso
Se puede utilizar en condiciones de preprocesamiento para incluir o excluir partes del código dependiendo de si el compilador sigue el estándar C. Por ejemplo:

```c
#ifdef __STDC__
    // Código que se compila solo si el compilador es compatible con el estándar ANSI C
#else
    // Código alternativo para compiladores no estándar
#endif
```

### Detalles
- El valor de `__STDC__` es generalmente 1 si el compilador es compatible con el estándar.
- Algunos compiladores pueden tener sus propias macros definidas que pueden ser utilizadas en conjunto con `__STDC__` para verificar compatibilidad con características específicas del estándar.

## Ejemplos
### Ejemplo 1: Verificación de compatibilidad
```c
#include <stdio.h>

int main() {
#ifdef __STDC__
    printf("Este compilador es compatible con el estándar C.\n");
#else
    printf("Este compilador NO es compatible con el estándar C.\n");
#endif
    return 0;
}
```

### Ejemplo 2: Código condicional
```c
#include <stdio.h>

void funcion() {
#ifdef __STDC__
    printf("Usando funcionalidades estándar.\n");
#else
    printf("Usando funcionalidades no estándar.\n");
#endif
}

int main() {
    funcion();
    return 0;
}
```

## Explicación
Algunos errores comunes al utilizar `__STDC__` incluyen:
- **Asumir que todos los compiladores modernos la definen**: No todos los compiladores que se utilizan hoy en día son compatibles con el estándar. Es importante verificar la documentación del compilador específico.
- **Olvidar el uso correcto de directivas de preprocesador**: Asegúrate de que las condiciones están correctamente formuladas para evitar problemas de compilación.
- **Uso excesivo de la macro**: No todas las partes del código necesitan ser verificadas con `__STDC__`. Utiliza la macro solo donde sea realmente necesario para mantener la legibilidad del código.

## Resumen en una línea
`__STDC__` es una macro en C que indica si el compilador cumple con el estándar ANSI C, permitiendo así la escritura de código portable y compatible.