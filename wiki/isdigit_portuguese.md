<!--
Meta Description: # Função isdigit em C: Verificando Dígitos em Caracteres ## Sinopse A função `isdigit` da linguagem C é utilizada para verificar se um determinado car...
Meta Keywords: isdigit, função, dígito, caractere, int
-->

# Função isdigit em C: Verificando Dígitos em Caracteres

## Sinopse
A função `isdigit` da linguagem C é utilizada para verificar se um determinado caractere representa um dígito decimal (0-9). Esta função é parte da biblioteca padrão de C e é frequentemente utilizada em validações de entrada.

## Documentação

### Propósito
A função `isdigit` é usada para determinar se um caractere específico é um dígito decimal. Isso é útil em diversas situações, como validação de entradas de usuários ou processamento de strings que devem conter apenas números.

### Uso
Para utilizar a função `isdigit`, é necessário incluir a biblioteca `<ctype.h>`, que contém a declaração dessa e de outras funções relacionadas ao tratamento de caracteres.

**Prototipação:**
```c
#include <ctype.h>

int isdigit(int c);
```

### Parâmetros
- **c**: O caractere a ser testado, que deve ser passado como um valor inteiro. Normalmente, isso é feito através de um valor retornado de uma expressão de caractere, que é promovido a um inteiro.

### Retorno
A função `isdigit` retorna um valor diferente de zero (geralmente 1) se o caractere passado for um dígito (0 a 9). Se não for um dígito, a função retorna 0.

## Exemplos

### Exemplo 1: Verificando um único caractere
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char c = '5';

    if (isdigit(c)) {
        printf("%c é um dígito.\n", c);
    } else {
        printf("%c não é um dígito.\n", c);
    }

    return 0;
}
```

### Exemplo 2: Validação de string
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[] = "1234a";

    for (int i = 0; str[i] != '\0'; i++) {
        if (!isdigit(str[i])) {
            printf("%c não é um dígito.\n", str[i]);
        }
    }

    return 0;
}
```

## Explicação
Ao usar `isdigit`, alguns pontos devem ser considerados:

- **Tipo de dados**: A função espera um valor do tipo `int`. Isso é importante para evitar comportamentos inesperados, especialmente ao passar valores que não são caracteres.
- **Compatibilidade**: `isdigit` é parte da biblioteca padrão, mas a sua implementação pode variar em sistemas diferentes. É sempre recomendável testar o código em diferentes plataformas se a portabilidade for uma preocupação.
- **Limitações**: A função apenas verifica caracteres de dígitos decimais. Para outros tipos de validação, como números negativos ou pontos decimais, métodos adicionais devem ser utilizados.

## Resumo em uma Linha
A função `isdigit` em C permite verificar se um caractere representa um dígito decimal, facilitando a validação de entradas em programas.