<!--
Meta Description: # _Static_assert: Validação em Tempo de Compilação em C ## Sinopse O `_Static_assert` é uma instrução do C que permite a validação de expressões em te...
Meta Keywords: que, _static_assert, compilação, ser, uma
-->

# _Static_assert: Validação em Tempo de Compilação em C

## Sinopse
O `_Static_assert` é uma instrução do C que permite a validação de expressões em tempo de compilação, garantindo que certas condições sejam verdadeiras antes que o código seja compilado. Isso é útil para verificar invariantes, tamanhos de tipos e outras condições que devem ser satisfeitas durante a compilação.

## Documentação
O `_Static_assert` foi introduzido na norma C11 e é utilizado para realizar asserções em tempo de compilação. A sintaxe básica é:

```c
_Static_assert(expressão, mensagem);
```

### Propósito
O objetivo principal do `_Static_assert` é fornecer uma maneira de assegurar que determinadas condições sejam verdadeiras em tempo de compilação, ajudando a detectar erros antes da execução do programa.

### Uso
Você pode usar `_Static_assert` para verificar condições que devem ser verdadeiras em um determinado ponto do seu código. Se a condição não for atendida, o compilador gerará um erro, impedindo a compilação.

### Detalhes
- **expressão**: Uma expressão que deve ser avaliada como verdadeira (não zero) para que a compilação prossiga.
- **mensagem**: Uma string que será exibida como mensagem de erro se a expressão for falsa.

O `_Static_assert` é especialmente útil em situações onde tipos de dados e tamanhos são críticos, como em estruturas de dados, onde a integridade dos tipos deve ser garantida.

## Exemplos

### Exemplo 1: Verificação de tamanho de tipo
```c
#include <stdio.h>

_Static_assert(sizeof(int) == 4, "O tamanho de int deve ser 4 bytes");

int main() {
    printf("O tamanho de int é 4 bytes.\n");
    return 0;
}
```

### Exemplo 2: Verificação de constantes
```c
#include <stdio.h>

#define MAX_SIZE 100

_Static_assert(MAX_SIZE > 0, "MAX_SIZE deve ser maior que zero");

int main() {
    printf("MAX_SIZE é válido.\n");
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Erros de tipos**: O `_Static_assert` não pode ser utilizado para verificar condições que dependem da execução de código, como chamadas de funções ou variáveis que não sejam constantes.
- **Mensagens de erro**: As mensagens de erro devem ser claras e descritivas para facilitar a identificação do problema durante o processo de compilação.

### Notas Adicionais
- `_Static_assert` não é suportado em versões anteriores a C11. Portanto, é necessário garantir que o compilador utilizado seja compatível com essa norma.
- Usar `_Static_assert` melhora a legibilidade do código, pois documenta as suposições e invariantes diretamente no código.

## Resumo em Uma Linha
O `_Static_assert` é uma instrução do C que permite validar expressões em tempo de compilação, garantindo a integridade do código antes da execução.