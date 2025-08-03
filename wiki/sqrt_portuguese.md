<!--
Meta Description: # Função sqrt em C: Computando Raiz Quadrada de Forma Simples ## Sinopse A função `sqrt` em C é utilizada para calcular a raiz quadrada de um número. ...
Meta Keywords: raiz, quadrada, sqrt, função, não
-->

# Função sqrt em C: Computando Raiz Quadrada de Forma Simples

## Sinopse
A função `sqrt` em C é utilizada para calcular a raiz quadrada de um número. Ela faz parte da biblioteca matemática padrão e é amplamente utilizada em aplicações que requerem operações matemáticas.

## Documentação
A função `sqrt` está definida na biblioteca `<math.h>`. Seu propósito principal é retornar a raiz quadrada de um número não negativo passado como argumento.

### Sintaxe
```c
#include <math.h>

double sqrt(double x);
```

### Parâmetros
- `x`: um número do tipo `double` não negativo, do qual se deseja calcular a raiz quadrada.

### Retorno
A função retorna o valor da raiz quadrada de `x`. Se `x` for negativo, o comportamento não é definido e pode resultar em um valor NaN (Not-a-Number).

### Exemplo de Uso
Para usar a função `sqrt`, é necessário incluir a biblioteca `<math.h>` e compilar o programa com a opção `-lm` para linkar a biblioteca matemática.

## Exemplos
### Exemplo Básico
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 16.0;
    double resultado = sqrt(num);
    printf("A raiz quadrada de %.2f é %.2f\n", num, resultado);
    return 0;
}
```
**Saída:**
```
A raiz quadrada de 16.00 é 4.00
```

### Exemplo com Valor Negativo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -4.0;
    double resultado = sqrt(num);
    printf("A raiz quadrada de %.2f é %.2f\n", num, resultado);
    return 0;
}
```
**Saída:**
```
A raiz quadrada de -4.00 é nan
```

## Explicação
Um ponto comum de confusão ao usar a função `sqrt` é tentar calcular a raiz quadrada de números negativos. Em C, isso resulta em um valor NaN e não deve ser feito sem uma verificação prévia. Para evitar esse problema, sempre verifique se o valor é não negativo antes de chamar a função `sqrt`.

Outra armadilha comum é não incluir a biblioteca `<math.h>` ou esquecer de compilar com a flag `-lm`, o que resultará em erro de linkagem.

## Resumo em Uma Linha
A função `sqrt` em C calcula a raiz quadrada de um número não negativo, retornando NaN para entradas negativas.