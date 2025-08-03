<!--
Meta Description: # Função tan em C: Cálculo da Tangente ## Sinopse A função `tan` em C é utilizada para calcular a tangente de um ângulo, fornecendo um resultado em ra...
Meta Keywords: tangente, radianos, graus, tan, double
-->

# Função tan em C: Cálculo da Tangente

## Sinopse
A função `tan` em C é utilizada para calcular a tangente de um ângulo, fornecendo um resultado em radianos. Esta função é parte da biblioteca matemática padrão e é essencial para aplicações que envolvem trigonometria.

## Documentação
A função `tan` está definida na biblioteca `<math.h>`. Seu propósito é calcular a tangente de um ângulo que é passado como argumento.

### Sintaxe
```c
#include <math.h>

double tan(double x);
```

### Parâmetros
- `x`: um valor do tipo `double`, que representa o ângulo em radianos.

### Retorno
A função retorna o valor da tangente de `x`. O resultado também é do tipo `double`.

### Utilização
Para usar a função `tan`, é necessário incluir a biblioteca de matemática. Além disso, é importante que os ângulos sejam convertidos para radianos, caso estejam em graus.

## Exemplos

### Exemplo 1: Cálculo da tangente de 0 radianos
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = 0.0;
    double result = tan(angle);
    printf("A tangente de %.2f radianos é: %.2f\n", angle, result);
    return 0;
}
```

### Exemplo 2: Cálculo da tangente de 45 graus
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = 45.0 * (M_PI / 180.0); // Convertendo graus para radianos
    double result = tan(angle);
    printf("A tangente de 45 graus é: %.2f\n", result);
    return 0;
}
```

### Exemplo 3: Cálculo da tangente de -30 graus
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = -30.0 * (M_PI / 180.0); // Convertendo graus para radianos
    double result = tan(angle);
    printf("A tangente de -30 graus é: %.2f\n", result);
    return 0;
}
```

## Explicação
Um ponto importante a ser considerado ao usar a função `tan` é que a tangente é indefinida para ângulos em que o cosseno é zero, como 90 graus (π/2 radianos), 270 graus (3π/2 radianos), e assim por diante. Se você tentar calcular a tangente nessas situações, o resultado pode ser `inf` (infinito) ou gerar um erro de domínio, dependendo da implementação do compilador.

Além disso, é crucial lembrar que a função espera o ângulo em radianos. Portanto, se você estiver trabalhando com graus, deve realizar a conversão apropriada utilizando a fórmula: 
```c
radianos = graus * (M_PI / 180.0);
```

## Resumo em uma linha
A função `tan` em C calcula a tangente de um ângulo em radianos, sendo parte da biblioteca matemática padrão e essencial para cálculos trigonométricos.