<!--
Meta Description: # atan2: A Função de C para Calcular o Ângulo entre Dois Pontos ## Sinopse A função `atan2` em C é utilizada para calcular o ângulo em radianos entre ...
Meta Keywords: atan2, função, ângulo, double, para
-->

# atan2: A Função de C para Calcular o Ângulo entre Dois Pontos

## Sinopse
A função `atan2` em C é utilizada para calcular o ângulo em radianos entre o eixo X e o vetor que se estende até o ponto (y, x). É uma ferramenta essencial em cálculos trigonométricos, especialmente em contextos que envolvem coordenadas cartesianas.

## Documentação
### Propósito
A função `atan2` é parte da biblioteca matemática padrão em C e tem como finalidade calcular o arco tangente do quociente de seus dois argumentos. Ao contrário da função `atan`, que aceita um único argumento e retorna um valor entre -π/2 e π/2, `atan2` aceita dois argumentos e retorna um valor entre -π e π, permitindo uma determinação precisa do quadrante do ângulo.

### Uso
A função é definida como:

```c
#include <math.h>

double atan2(double y, double x);
```

- **y**: Coordenada Y do ponto.
- **x**: Coordenada X do ponto.

### Detalhes
- `atan2` leva em consideração o sinal de ambos os argumentos para determinar em qual quadrante o ângulo se encontra.
- O retorno é em radianos. Para converter para graus, multiplique o resultado por (180/π).
- O comportamento da função é bem definido para todos os valores de `x` e `y`, incluindo casos em que `x` é zero, onde o resultado será π/2 ou -π/2, dependendo do sinal de `y`.

## Exemplos
### Exemplo Básico
```c
#include <stdio.h>
#include <math.h>

int main() {
    double y = 1.0;
    double x = 1.0;
    double angle = atan2(y, x);
    
    printf("O ângulo em radianos é: %f\n", angle); // Saída: O ângulo em radianos é: 0.785398
    return 0;
}
```

### Exemplo com Diferentes Quadrantes
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angles[4][2] = {
        {1.0, 1.0},   // Primeiro Quadrante
        {-1.0, 1.0},  // Segundo Quadrante
        {-1.0, -1.0}, // Terceiro Quadrante
        {1.0, -1.0}   // Quarto Quadrante
    };

    for (int i = 0; i < 4; i++) {
        double angle = atan2(angles[i][1], angles[i][0]);
        printf("atan2(%f, %f) = %f radianos\n", angles[i][1], angles[i][0], angle);
    }

    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Erros de Sinal**: É importante lembrar que a ordem dos argumentos importa. `atan2(y, x)` é diferente de `atan2(x, y)`.
- **Valores de Entrada**: Fornecer `x = 0` e `y = 0` resultará em comportamento indefinido. Sempre verifique as entradas antes de chamar a função.
- **Conversão de Radianos para Graus**: Se precisar do ângulo em graus, não esqueça de realizar a conversão após o cálculo.

## Resumo em Uma Linha
A função `atan2` em C calcula o ângulo entre o eixo X e um vetor definido por coordenadas cartesianas, levando em conta o quadrante do ponto.