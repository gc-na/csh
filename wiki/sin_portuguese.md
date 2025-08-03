<!--
Meta Description: # Função `sin` em C: Calcule o seno de um ângulo ## Sinopse A função `sin` da linguagem de programação C é utilizada para calcular o seno de um ângulo...
Meta Keywords: função, sin, radianos, double, seno
-->

# Função `sin` em C: Calcule o seno de um ângulo

## Sinopse
A função `sin` da linguagem de programação C é utilizada para calcular o seno de um ângulo expresso em radianos. Esta função é parte da biblioteca matemática padrão, facilitando operações trigonométricas em aplicações científicas e de engenharia.

## Documentação
A função `sin` está definida na biblioteca `<math.h>`. O seu protótipo é o seguinte:

```c
#include <math.h>
double sin(double x);
```

### Propósito
A função `sin` retorna o seno do ângulo `x`, onde `x` é um valor em radianos.

### Uso
Para utilizar a função `sin`, é necessário incluir a biblioteca `<math.h>` no seu código. A função aceita um argumento do tipo `double` e retorna um valor do tipo `double`, que representa o seno do ângulo fornecido.

### Detalhes
- O ângulo deve ser fornecido em radianos. Para converter graus para radianos, use a fórmula: `radianos = graus * (M_PI / 180)`, onde `M_PI` é uma constante que representa π.
- A função `sin` é uma função matemática fundamental e é amplamente utilizada em cálculos relacionados a ondas, oscilações e outras aplicações científicas.
- A precisão do resultado pode variar dependendo da implementação da biblioteca matemática e do valor fornecido.

## Exemplos

### Exemplo 1: Cálculo do seno de 0 radianos
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo = 0.0;
    double resultado = sin(angulo);
    printf("O seno de %.2f radianos é: %.2f\n", angulo, resultado);
    return 0;
}
```

### Exemplo 2: Cálculo do seno de 90 graus
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angulo_graus = 90.0;
    double angulo_radianos = angulo_graus * (M_PI / 180);
    double resultado = sin(angulo_radianos);
    printf("O seno de %.2f graus é: %.2f\n", angulo_graus, resultado);
    return 0;
}
```

## Explicação
- **Conversão de graus para radianos**: Um erro comum ao usar a função `sin` é esquecer que os ângulos devem estar em radianos. Sempre que utilizar ângulos em graus, lembre-se de convertê-los corretamente.
- **Precisionamento**: Os resultados podem variar com base na precisão da implementação da função `sin`. Em aplicações que requerem alta precisão, considere o uso de bibliotecas matemáticas especializadas.
- **Domínio e Limitações**: A função `sin` opera em toda a linha dos números reais. No entanto, a precisão pode ser afetada para valores muito grandes ou muito pequenos devido ao limite de representação do tipo `double`.

## Resumo em Uma Linha
A função `sin` em C calcula o seno de um ângulo em radianos, sendo essencial para aplicações matemáticas e científicas.