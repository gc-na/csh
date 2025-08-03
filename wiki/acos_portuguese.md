<!--
Meta Description: # Função acos em C: Cálculo do Arco Cosseno ## Sinopse A função `acos` em C é utilizada para calcular o arco cosseno de um número, retornando o ângulo...
Meta Keywords: valor, acos, cosseno, função, arco
-->

# Função acos em C: Cálculo do Arco Cosseno

## Sinopse
A função `acos` em C é utilizada para calcular o arco cosseno de um número, retornando o ângulo em radianos. Esta função é parte da biblioteca matemática padrão e é essencial para cálculos trigonométricos.

## Documentação
A função `acos` está definida na biblioteca `<math.h>`. Seu propósito principal é fornecer o arco cosseno de um valor, que deve estar no intervalo de -1 a 1. Caso o valor esteja fora desse intervalo, a função retornará um valor indefinido.

### Prototipação
```c
#include <math.h>
double acos(double x);
```

### Parâmetros
- `x`: Um valor do tipo `double` que representa o cosseno do ângulo desejado. O valor de `x` deve estar entre -1 e 1.

### Retorno
A função retorna o arco cosseno de `x` em radianos. Se `x` estiver fora do intervalo permitido, o comportamento é indefinido.

### Requisitos
- **Header**: `<math.h>`
- **Linkagem**: Ao compilar, use a opção `-lm` para linkar a biblioteca matemática.

## Exemplos
### Exemplo Básico
```c
#include <stdio.h>
#include <math.h>

int main() {
    double valor = 0.5;
    double resultado = acos(valor);
    
    printf("O arco cosseno de %.2f é %.2f radianos\n", valor, resultado);
    return 0;
}
```

### Saída Esperada
```
O arco cosseno de 0.50 é 1.05 radianos
```

### Exemplo com Erro
```c
#include <stdio.h>
#include <math.h>

int main() {
    double valor = 2.0; // Valor fora do intervalo
    double resultado = acos(valor); // Comportamento indefinido
    
    printf("O arco cosseno de %.2f é %.2f radianos\n", valor, resultado);
    return 0;
}
```

## Explicação
Um dos principais pontos a se considerar ao usar `acos` é garantir que o valor de entrada esteja dentro do intervalo -1 a 1. Passar um valor fora desse intervalo resultará em comportamento indefinido, que pode levar a erros de execução ou resultados inesperados.

Além disso, lembre-se de que o resultado da função `acos` está em radianos, e pode ser necessário convertê-lo para graus, se necessário, usando a conversão: `graus = radianos * (180 / M_PI)`.

## Resumo em uma Linha
A função `acos` em C calcula o arco cosseno de um número, retornando o ângulo em radianos, desde que o valor esteja entre -1 e 1.