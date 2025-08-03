<!--
Meta Description: # Função pow em C: Calculando Potências de Números ## Sinopse A função `pow` em C é utilizada para calcular a potência de um número, permitindo elevar...
Meta Keywords: pow, resultado, função, expoente, double
-->

# Função pow em C: Calculando Potências de Números

## Sinopse
A função `pow` em C é utilizada para calcular a potência de um número, permitindo elevar um número à potência de outro, o que é fundamental para várias operações matemáticas em programação.

## Documentação
A função `pow` faz parte da biblioteca matemática padrão em C, definida em `<math.h>`. Seu propósito é calcular a base elevada à potência de um expoente.

### Prototipação
```c
double pow(double base, double expoente);
```

### Parâmetros
- **base**: O número que será elevado à potência.
- **expoente**: O expoente ao qual a base será elevada.

### Retorno
A função retorna um valor do tipo `double`, que representa o resultado da operação base^expoente. Se a base for zero e o expoente for menor ou igual a zero, o resultado é indefinido.

### Inclusão da Biblioteca
Para utilizar a função `pow`, é necessário incluir a seguinte diretiva no início do seu código:
```c
#include <math.h>
```

## Exemplos

### Exemplo 1: Elevar um número inteiro
```c
#include <stdio.h>
#include <math.h>

int main() {
    double resultado = pow(2, 3); // 2 elevado a 3
    printf("2 elevado a 3 é: %.2f\n", resultado); // Saída: 8.00
    return 0;
}
```

### Exemplo 2: Potência de um número decimal
```c
#include <stdio.h>
#include <math.h>

int main() {
    double resultado = pow(3.5, 2); // 3.5 elevado a 2
    printf("3.5 elevado a 2 é: %.2f\n", resultado); // Saída: 12.25
    return 0;
}
```

### Exemplo 3: Expoente negativo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double resultado = pow(4, -2); // 4 elevado a -2
    printf("4 elevado a -2 é: %.2f\n", resultado); // Saída: 0.0625
    return 0;
}
```

## Explicação
Ao usar a função `pow`, é importante estar ciente de alguns pontos:

1. **Tipo de Retorno**: A função sempre retorna um valor do tipo `double`, mesmo que a base e o expoente sejam inteiros.
2. **Limites de Entrada**: Se a base for zero e o expoente for negativo, a função pode retornar um valor indefinido, resultando em um erro de domínio.
3. **Precisão**: A precisão do resultado pode ser afetada por limitações na representação de números de ponto flutuante.
4. **Performance**: Em aplicações críticas de desempenho, considere que `pow` pode ser mais lenta que multiplicações repetidas.

## Resumo em Uma Linha
A função `pow` em C permite calcular a potência de um número, retornando o resultado como um valor do tipo `double`.