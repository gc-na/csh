<!--
Meta Description: # Função cosh em C: Calculando o Cosseno Hiperbólico ## Sinopse A função `cosh` é uma função matemática em C que calcula o cosseno hiperbólico de um n...
Meta Keywords: cosh, função, double, resultado, cosseno
-->

# Função cosh em C: Calculando o Cosseno Hiperbólico

## Sinopse
A função `cosh` é uma função matemática em C que calcula o cosseno hiperbólico de um número real. É uma função importante para diversas aplicações científicas e de engenharia, especialmente em contextos que envolvem cálculos hiperbólicos.

## Documentação
A função `cosh` está disponível na biblioteca padrão C, incluindo `<math.h>`. O cosseno hiperbólico de um número `x` é definido como:

\[ \text{cosh}(x) = \frac{e^x + e^{-x}}{2} \]

### Propósito
A função `cosh` é utilizada para calcular o cosseno hiperbólico, que é frequentemente aplicado em problemas envolvendo equações diferenciais, teoria da relatividade, e modelagem de fenômenos naturais.

### Uso
Para utilizar a função `cosh`, inclua a biblioteca `<math.h>` em seu código. A função aceita um único argumento do tipo `double` e retorna um valor do mesmo tipo.

### Sintaxe
```c
#include <math.h>

double cosh(double x);
```

### Parâmetros
- `x`: Um número real (do tipo `double`) cuja função cosseno hiperbólico deseja-se calcular.

### Retorno
A função retorna o cosseno hiperbólico de `x`. Se `x` for um valor muito grande, o resultado pode ser infinito (`inf`).

## Exemplos
Aqui estão alguns exemplos simples que demonstram o uso da função `cosh`:

### Exemplo 1: Cálculo básico
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 1.0;
    double resultado = cosh(x);
    printf("cosh(%.1f) = %.2f\n", x, resultado);
    return 0;
}
```

### Exemplo 2: Usando um valor negativo
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = -1.0;
    double resultado = cosh(x);
    printf("cosh(%.1f) = %.2f\n", x, resultado);
    return 0;
}
```

### Exemplo 3: Grande valor
```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 1000.0;
    double resultado = cosh(x);
    printf("cosh(%.1f) = %.2f\n", x, resultado);
    return 0;
}
```

## Explicação
É importante notar que a função `cosh` retorna resultados diferentes para números negativos e positivos, mas devido à sua simetria, `cosh(-x)` é igual a `cosh(x)`. Além disso, para valores muito grandes, o resultado pode se aproximar de infinito, o que pode levar a resultados inesperados se não for devidamente tratado.

### Principais armadilhas
- **Inclusão da biblioteca**: Certifique-se de incluir `<math.h>`, caso contrário, a função não será reconhecida.
- **Tipo de dados**: Utilize sempre o tipo `double` para os argumentos, pois tipos menores podem levar a perda de precisão.
- **Valores extremos**: Esteja ciente de que valores extremamente altos podem resultar em overflow, retornando `inf`.

## Resumo em Uma Frase
A função `cosh` em C calcula o cosseno hiperbólico de um número real, sendo essencial para aplicações científicas e matemáticas.