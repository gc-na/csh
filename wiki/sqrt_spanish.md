<!--
Meta Description: # Función sqrt en C: Cálculo de la Raíz Cuadrada ## Sinopsis La función `sqrt` en C es utilizada para calcular la raíz cuadrada de un número de punto ...
Meta Keywords: función, sqrt, raíz, cuadrada, para
-->

# Función sqrt en C: Cálculo de la Raíz Cuadrada

## Sinopsis
La función `sqrt` en C es utilizada para calcular la raíz cuadrada de un número de punto flotante. Esta función es parte de la biblioteca matemática estándar y es fundamental en aplicaciones que requieren operaciones matemáticas avanzadas.

## Documentación
### Propósito
La función `sqrt` permite obtener la raíz cuadrada de un número no negativo. Es esencial en cálculos matemáticos, físicos y en algoritmos que requieren esta operación.

### Uso
Para utilizar la función `sqrt`, es necesario incluir la biblioteca `<math.h>` en el archivo de encabezado. La declaración de la función es la siguiente:

```c
double sqrt(double x);
```

#### Parámetros
- `x`: un valor de tipo `double`, que debe ser un número no negativo.

#### Valor de retorno
La función devuelve la raíz cuadrada de `x`. Si `x` es negativo, el comportamiento es indefinido y puede resultar en un valor `NaN` (Not a Number) o en un error de dominio.

### Ejemplo de uso

A continuación, se presentan ejemplos básicos de cómo utilizar la función `sqrt`:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double numero = 16.0;
    double resultado = sqrt(numero);
    
    printf("La raíz cuadrada de %.2f es %.2f\n", numero, resultado);
    return 0;
}
```

**Salida esperada:**
```
La raíz cuadrada de 16.00 es 4.00
```

## Explicación
### Errores comunes y notas
- **Entrada negativa**: Pasar un número negativo a `sqrt` puede llevar a resultados inesperados. En C, el comportamiento no está definido para números negativos, así que es recomendable validar el valor antes de llamar a la función.
  
- **Pérdida de precisión**: Los cálculos de punto flotante pueden introducir errores de redondeo. Para aplicaciones que requieren alta precisión, considere el uso de bibliotecas matemáticas adicionales.

- **Incluir la biblioteca correcta**: Asegúrese de incluir `<math.h>` para poder utilizar `sqrt`. De lo contrario, el compilador no reconocerá la función.

## Resumen en una línea
La función `sqrt` en C calcula la raíz cuadrada de un número no negativo, siendo esencial en aplicaciones matemáticas y científicas.