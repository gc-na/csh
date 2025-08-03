<!--
Meta Description: # abs: Função para Calcular o Valor Absoluto em C ## Sinopse A função `abs` em C é utilizada para calcular o valor absoluto de um número inteiro, ou s...
Meta Keywords: valor, abs, função, absoluto, int
-->

# abs: Função para Calcular o Valor Absoluto em C

## Sinopse
A função `abs` em C é utilizada para calcular o valor absoluto de um número inteiro, ou seja, transforma números negativos em positivos, enquanto mantém os números positivos inalterados.

## Documentação
A função `abs` faz parte da biblioteca padrão de C, especificamente na `<stdlib.h>`. Seu principal propósito é fornecer uma maneira simples e eficiente de obter o valor absoluto de um inteiro.

### Prototipagem
```c
#include <stdlib.h>
int abs(int x);
```

### Parâmetros
- **x**: um valor inteiro, que pode ser positivo, negativo ou zero.

### Retorno
A função retorna o valor absoluto de `x`. Se `x` for negativo, o valor retornado será `-x`; se `x` for positivo ou zero, o valor retornado será `x` mesmo.

## Exemplos
Aqui estão alguns exemplos básicos de como usar a função `abs`:

### Exemplo 1: Uso Básico
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num = -10;
    printf("O valor absoluto de %d é %d\n", num, abs(num));
    return 0;
}
```

### Exemplo 2: Valores Positivos e Zero
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num1 = 5;
    int num2 = 0;
    printf("O valor absoluto de %d é %d\n", num1, abs(num1));
    printf("O valor absoluto de %d é %d\n", num2, abs(num2));
    return 0;
}
```

## Explicação
Embora a função `abs` seja simples de usar, é importante estar ciente de algumas peculiaridades:

- **Limitações**: A função `abs` está limitada ao tipo `int`. Para valores de ponto flutuante, como `float` ou `double`, deve-se utilizar `fabs`, que está disponível na biblioteca `<math.h>`.
- **Overflow**: Ao usar `abs`, se o valor de `x` for o menor inteiro possível (`INT_MIN`), a função pode resultar em comportamento indefinido devido ao overflow, porque não existe um valor positivo correspondente no intervalo de números inteiros.

## Resumo em Uma Linha
A função `abs` em C retorna o valor absoluto de um número inteiro, convertendo negativos em positivos e mantendo os positivos inalterados.