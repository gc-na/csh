<!--
Meta Description: # Função `floor` em C: Arredondamento para Baixo ## Sinopse A função `floor` em C é utilizada para arredondar um número de ponto flutuante para o inte...
Meta Keywords: floor, resultado, double, que, função
-->

# Função `floor` em C: Arredondamento para Baixo

## Sinopse
A função `floor` em C é utilizada para arredondar um número de ponto flutuante para o inteiro mais próximo que é menor ou igual ao número original. Essa função é parte da biblioteca matemática padrão (`math.h`), sendo amplamente utilizada em cálculos que requerem um arredondamento para baixo.

## Documentação
A função `floor` faz parte da biblioteca matemática em C e é definida como:

```c
#include <math.h>
double floor(double x);
```

### Propósito
O propósito da função `floor` é fornecer uma forma precisa de arredondar números de ponto flutuante para o inteiro inferior mais próximo, o que pode ser útil em diversas aplicações, como processamento de dados, gráficos, e cálculos financeiros.

### Uso
A função `floor` recebe um único argumento do tipo `double` e retorna o maior inteiro, representado como um `double`, que é menor ou igual ao valor fornecido. 

### Detalhes
- A função `floor` não altera o valor original, mas retorna um novo valor.
- O resultado é do tipo `double`, mesmo que o valor retornado seja um inteiro.
- A função pode ser utilizada em expressões e combinações matemáticas, assim como em controle de fluxo.

## Exemplos
Aqui estão alguns exemplos de como utilizar a função `floor`:

### Exemplo 1: Uso Básico

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 3.7;
    double resultado = floor(num);
    printf("O resultado de floor(%.1f) é %.1f\n", num, resultado);
    return 0;
}
```

**Saída:**
```
O resultado de floor(3.7) é 3.0
```

### Exemplo 2: Uso com Número Negativo

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -3.2;
    double resultado = floor(num);
    printf("O resultado de floor(%.1f) é %.1f\n", num, resultado);
    return 0;
}
```

**Saída:**
```
O resultado de floor(-3.2) é -4.0
```

### Exemplo 3: Uso com Zero

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 0.0;
    double resultado = floor(num);
    printf("O resultado de floor(%.1f) é %.1f\n", num, resultado);
    return 0;
}
```

**Saída:**
```
O resultado de floor(0.0) é 0.0
```

## Explicação
Um erro comum ao usar `floor` é esperar que ela retorne um valor do tipo `int`. Lembre-se que `floor` retorna um `double`, então, se você precisar de um inteiro, será necessário converter o resultado usando um cast. Além disso, a função sempre arredonda para baixo no sentido da linha dos números, o que significa que mesmo para números negativos, o resultado será menos que o número original.

### Armadilhas Comuns
- **Conversão de Tipo:** Ao utilizar o resultado de `floor`, lembre-se de que pode ser necessário convertê-lo para um tipo inteiro se você precisar desse formato.
- **Comportamento com Números Negativos:** Ao arredondar números negativos, o resultado será sempre um número menor, o que pode ser contra-intuitivo para alguns usuários.

## Resumo em Uma Linha
A função `floor` em C arredonda um número de ponto flutuante para o inteiro mais próximo inferior, retornando um valor do tipo `double`.