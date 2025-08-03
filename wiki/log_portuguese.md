<!--
Meta Description: # Logaritmo em C: Funções e Uso ## Sinopse O logaritmo é uma função matemática fundamental amplamente utilizada em programação, incluindo a linguagem ...
Meta Keywords: funções, logaritmo, double, resultado, math
-->

# Logaritmo em C: Funções e Uso

## Sinopse
O logaritmo é uma função matemática fundamental amplamente utilizada em programação, incluindo a linguagem C. Neste artigo, abordaremos como utilizar as funções logarítmicas disponíveis na biblioteca padrão da linguagem C, permitindo calcular logaritmos de diferentes bases.

## Documentação
A linguagem C fornece funções para calcular logaritmos através da biblioteca matemática `<math.h>`. As principais funções logarítmicas são:

- `log(double x)`: Calcula o logaritmo natural (base e) de x.
- `log10(double x)`: Calcula o logaritmo decimal (base 10) de x.
- `log2(double x)`: Calcula o logaritmo binário (base 2) de x.

### Propósito
Essas funções são utilizadas em diversas áreas, como matemática, engenharia e ciências da computação, para resolver problemas que envolvem crescimento exponencial, escalas logarítmicas, entre outros.

### Uso
Para utilizar as funções logarítmicas, você deve incluir a biblioteca `<math.h>` no seu código:

```c
#include <math.h>
```

As funções retornam um valor do tipo `double`, que representa o resultado do logaritmo da entrada fornecida. É importante lembrar que o argumento `x` deve ser um número positivo; caso contrário, as funções podem retornar resultados indefinidos ou valores especiais como `NaN` (Not a Number).

## Exemplos

### Exemplo 1: Logaritmo Natural

```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 10.0;
    double resultado = log(x);
    printf("Logaritmo natural de %.2f é %.2f\n", x, resultado);
    return 0;
}
```

### Exemplo 2: Logaritmo Decimal

```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 100.0;
    double resultado = log10(x);
    printf("Logaritmo decimal de %.2f é %.2f\n", x, resultado);
    return 0;
}
```

### Exemplo 3: Logaritmo Binário

```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 8.0;
    double resultado = log2(x);
    printf("Logaritmo binário de %.2f é %.2f\n", x, resultado);
    return 0;
}
```

## Explicação
É importante ter em mente algumas considerações ao usar funções logarítmicas em C:

- **Domínio das Funções**: As funções `log`, `log10` e `log2` só são definidas para valores de `x` maiores que zero. Para `x <= 0`, o comportamento é indefinido.
- **Retorno de NaN**: Passar um valor negativo ou zero para essas funções resultará em `NaN`. É recomendável verificar o valor de entrada antes da chamada da função.
- **Precisão**: A precisão do resultado pode variar dependendo da implementação do compilador e da arquitetura do sistema.

## Resumo em Uma Linha
As funções logarítmicas em C, disponíveis na biblioteca `<math.h>`, permitem calcular logaritmos naturais, decimais e binários de números positivos.