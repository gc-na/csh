<!--
Meta Description: # fabs: Função de Valor Absoluto em C ## Sinopse A função `fabs` em C é utilizada para calcular o valor absoluto de um número do tipo `double`. É part...
Meta Keywords: valor, fabs, double, absoluto, função
-->

# fabs: Função de Valor Absoluto em C 

## Sinopse
A função `fabs` em C é utilizada para calcular o valor absoluto de um número do tipo `double`. É parte da biblioteca matemática padrão e é essencial para operações que requerem a manipulação de valores não negativos.

## Documentação

### Propósito
A função `fabs` retorna o valor absoluto de um número, ou seja, transforma números negativos em positivos enquanto mantém os números positivos inalterados. Essa função é particularmente útil em cálculos matemáticos onde a magnitude de um número é mais relevante do que seu sinal.

### Uso
Para utilizar a função `fabs`, você deve incluir a biblioteca `<math.h>` no seu código. A sintaxe básica é:

```c
double fabs(double x);
```

### Parâmetros
- `x`: Um número do tipo `double` cuja magnitude você deseja obter.

### Retorno
A função retorna um valor do tipo `double`, que é o valor absoluto de `x`. Se `x` for `NaN` (Not a Number), a função retornará `NaN`.

## Exemplos

### Exemplo 1: Valor Absoluto Simples
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -5.4;
    double resultado = fabs(num);
    printf("O valor absoluto de %.2f é %.2f\n", num, resultado);
    return 0;
}
```
**Saída:**
```
O valor absoluto de -5.40 é 5.40
```

### Exemplo 2: Valor Absoluto de um Número Positivo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 3.14;
    double resultado = fabs(num);
    printf("O valor absoluto de %.2f é %.2f\n", num, resultado);
    return 0;
}
```
**Saída:**
```
O valor absoluto de 3.14 é 3.14
```

### Exemplo 3: Valor Absoluto de NaN
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = NAN;
    double resultado = fabs(num);
    printf("O resultado de fabs(NaN) é: %f\n", resultado);
    return 0;
}
```
**Saída:**
```
O resultado de fabs(NaN) é: nan
```

## Explicação
Um dos principais pontos a ser observado é que a função `fabs` é específica para valores do tipo `double`. Para outros tipos numéricos, como `float` ou `int`, você deve usar as funções apropriadas. Por exemplo, para `float`, use `fabf`, e para `int`, você pode usar uma simples operação condicional.

Outro detalhe importante é que a função `fabs` não modifica o valor original de `x`; ela retorna um novo valor. Além disso, a função deve ser usada com cuidado em operações que envolvem números muito grandes ou pequenos, pois pode haver problemas de precisão.

## Resumo em Uma Frase
A função `fabs` em C calcula e retorna o valor absoluto de um número do tipo `double`, garantindo que a magnitude do valor é preservada independente do seu sinal.