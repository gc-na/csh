<!--
Meta Description: # Estructuras en C: Todo lo que Necesitas Saber sobre el Uso de "struct" ## Sinopsis En el lenguaje de programación C, una estructura (`struct`) es un...
Meta Keywords: struct, una, estructuras, que, estructura
-->

# Estructuras en C: Todo lo que Necesitas Saber sobre el Uso de "struct"

## Sinopsis
En el lenguaje de programación C, una estructura (`struct`) es un tipo de dato compuesto que permite agrupar diferentes tipos de datos bajo un mismo nombre, facilitando la organización y manipulación de datos relacionados.

## Documentación
### Propósito
Las estructuras en C se utilizan para crear un nuevo tipo de dato que agrupa variables de diferentes tipos en un solo objeto. Esto es útil cuando se necesita representar un conjunto de atributos que pertenecen a un mismo concepto, como un punto en un espacio 2D o un registro de empleado.

### Uso
Para definir una estructura, se utiliza la palabra clave `struct`, seguida del nombre de la estructura y un bloque que contiene las variables (también conocidas como miembros) que la componen. La sintaxis básica es la siguiente:

```c
struct NombreEstructura {
    tipo_dato nombre_variable1;
    tipo_dato nombre_variable2;
    // Otros miembros
};
```

Una vez definida, se pueden crear variables del tipo de la estructura usando la siguiente sintaxis:

```c
struct NombreEstructura variable;
```

### Detalles
- Las estructuras pueden contener miembros de cualquier tipo, incluidas otras estructuras, lo que permite crear estructuras complejas.
- Los miembros de una estructura se acceden utilizando el operador de acceso a miembros (`.`) o el operador de puntero a miembros (`->`).
- Se pueden inicializar estructuras al momento de declararlas.

## Ejemplos
### Ejemplo 1: Definición Básica de una Estructura
```c
#include <stdio.h>

struct Punto {
    int x;
    int y;
};

int main() {
    struct Punto p1;
    p1.x = 10;
    p1.y = 20;

    printf("Punto p1: (%d, %d)\n", p1.x, p1.y);
    return 0;
}
```

### Ejemplo 2: Inicialización de una Estructura
```c
#include <stdio.h>

struct Persona {
    char nombre[50];
    int edad;
};

int main() {
    struct Persona p1 = {"Juan", 30};

    printf("Nombre: %s, Edad: %d\n", p1.nombre, p1.edad);
    return 0;
}
```

### Ejemplo 3: Estructuras Anidadas
```c
#include <stdio.h>

struct Direccion {
    char ciudad[50];
    char pais[50];
};

struct Persona {
    char nombre[50];
    int edad;
    struct Direccion direccion;
};

int main() {
    struct Persona p1 = {"Ana", 25, {"Madrid", "España"}};

    printf("Nombre: %s, Edad: %d, Ciudad: %s, País: %s\n", p1.nombre, p1.edad, p1.direccion.ciudad, p1.direccion.pais);
    return 0;
}
```

## Explicación
### Errores Comunes
- **Olvidar la palabra clave `struct`**: Al declarar una variable de una estructura, es fácil olvidar incluir la palabra clave `struct` si no se ha utilizado una declaración `typedef`.
- **Acceder a miembros de manera incorrecta**: Intentar acceder a los miembros de una estructura sin el operador adecuado puede llevar a errores de compilación.
- **No inicializar**: Las variables de tipo estructura deben ser inicializadas antes de su uso; de lo contrario, contendrán valores indeterminados.

### Notas Adicionales
- Las estructuras son útiles para organizar datos en programas más grandes y complejos, especialmente en programación orientada a objetos en C.
- Las estructuras pueden ser pasadas a funciones, permitiendo que se utilicen como argumentos para funciones que requieren múltiples datos.

## Resumen en Una Línea
Las estructuras en C (`struct`) son un tipo de dato compuesto que permite agrupar diferentes tipos de datos relacionados en un solo objeto, facilitando la organización y manipulación de datos en programas.