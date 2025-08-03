<!--
Meta Description: # Estrutura Condicional "if" em C: Entenda como Funciona ## Sinopse A estrutura condicional "if" em C é utilizada para executar um bloco de código com...
Meta Keywords: código, estrutura, else, bloco, numero
-->

# Estrutura Condicional "if" em C: Entenda como Funciona

## Sinopse
A estrutura condicional "if" em C é utilizada para executar um bloco de código com base em uma condição booleana. Ela permite que o programa tome decisões durante a execução, tornando-o mais dinâmico e responsivo.

## Documentação
A estrutura "if" é um dos pilares da programação em C, permitindo que os desenvolvedores escrevam código que responda a diferentes condições. A sintaxe básica da estrutura "if" é a seguinte:

```c
if (condicao) {
    // bloco de código a ser executado se a condição for verdadeira
}
```

### Propósito
O propósito da estrutura "if" é permitir a execução condicional de um bloco de código. Se a condição dentro dos parênteses for avaliada como verdadeira (diferente de zero), o bloco de código será executado. Caso contrário, ele será ignorado.

### Uso
A estrutura "if" pode ser usada sozinha ou em conjunto com outras estruturas, como "else" e "else if", para criar fluxos de controle mais complexos.

```c
if (condicao1) {
    // bloco de código se condicao1 for verdadeira
} else if (condicao2) {
    // bloco de código se condicao2 for verdadeira
} else {
    // bloco de código se nenhuma das condições anteriores for verdadeira
}
```

## Exemplos
Aqui estão alguns exemplos básicos que demonstram o uso da estrutura "if":

### Exemplo 1: Uso Simples
```c
#include <stdio.h>

int main() {
    int numero = 10;

    if (numero > 0) {
        printf("O número é positivo.\n");
    }

    return 0;
}
```

### Exemplo 2: Uso com else
```c
#include <stdio.h>

int main() {
    int numero = -5;

    if (numero >= 0) {
        printf("O número é não negativo.\n");
    } else {
        printf("O número é negativo.\n");
    }

    return 0;
}
```

### Exemplo 3: Uso com else if
```c
#include <stdio.h>

int main() {
    int numero = 0;

    if (numero > 0) {
        printf("O número é positivo.\n");
    } else if (numero < 0) {
        printf("O número é negativo.\n");
    } else {
        printf("O número é zero.\n");
    }

    return 0;
}
```

## Explicação
Ao usar a estrutura "if", é importante estar atento a alguns pontos:

- **Avaliação de Condições**: Qualquer expressão que resulte em um valor diferente de zero é considerada verdadeira. Isso inclui não apenas valores booleanos, mas também inteiros e outras expressões que podem ser avaliadas.
- **Blocos de Código**: Se um bloco de código for necessário, ele deve ser envolvido por chaves `{}`. Se houver apenas uma linha de código a ser executada, as chaves são opcionais, mas é uma boa prática usá-las para evitar confusões.
- **Aninhamento**: A estrutura "if" pode ser aninhada, mas isso pode levar a um código difícil de entender. É aconselhável mantê-lo simples e claro.

## Resumo em Uma Linha
A estrutura "if" em C permite a execução condicional de blocos de código com base na avaliação de uma expressão booleana.