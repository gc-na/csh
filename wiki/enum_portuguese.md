<!--
Meta Description: # Enum em C: Compreendendo o Tipo Enumerado ## Sinopse O `enum` (tipo enumerado) em C é uma construção que permite definir um conjunto de constantes n...
Meta Keywords: enum, valores, que, constantes, tipo
-->

# Enum em C: Compreendendo o Tipo Enumerado

## Sinopse
O `enum` (tipo enumerado) em C é uma construção que permite definir um conjunto de constantes nomeadas, facilitando a legibilidade e a manutenção do código.

## Documentação
O `enum` em C é utilizado para criar um tipo de dado que consiste em um conjunto de valores constantes, que são representados por nomes simbólicos. A sintaxe básica para definir um `enum` é:

```c
enum NomeEnum {
    NomeConstante1,
    NomeConstante2,
    NomeConstante3,
    ...
};
```

### Propósito
O principal objetivo do `enum` é proporcionar um meio de trabalhar com conjuntos de valores relacionados de forma mais legível e organizada. Isso ajuda a evitar erros de digitação e torna o código mais fácil de entender.

### Uso
Para utilizar um `enum`, você deve declará-lo e, em seguida, referenciar suas constantes em seu código. Os valores atribuídos às constantes começam em 0 por padrão e incrementam automaticamente. Você também pode atribuir valores específicos a cada constante se desejar.

```c
enum DiasDaSemana {
    DOMINGO,     // 0
    SEGUNDA,     // 1
    TERÇA,       // 2
    QUARTA,      // 3
    QUINTA,      // 4
    SEXTA,       // 5
    SABADO       // 6
};
```

### Detalhes
Os `enums` são tratados como inteiros em C. Portanto, você pode usar suas constantes em expressões aritméticas e comparações. Também é possível criar variáveis do tipo enumerado:

```c
enum DiasDaSemana hoje;
hoje = QUINTA;
```

## Exemplos
Aqui estão alguns exemplos básicos de uso do `enum` em C:

```c
#include <stdio.h>

enum Cores {
    VERMELHO,
    VERDE,
    AZUL
};

int main() {
    enum Cores corFavorita;
    corFavorita = AZUL;

    printf("A cor favorita é: %d\n", corFavorita); // Saída: A cor favorita é: 2
    return 0;
}
```

Outro exemplo com valores específicos:

```c
#include <stdio.h>

enum Meses {
    JANEIRO = 1,
    FEVEREIRO,
    MARÇO,
    ABRIL,
    MAIO,
    JUNHO,
    JULHO,
    AGOSTO,
    SETEMBRO,
    OUTUBRO,
    NOVEMBRO,
    DEZEMBRO
};

int main() {
    enum Meses mesAtual = OUTUBRO;
    printf("O mês atual é: %d\n", mesAtual); // Saída: O mês atual é: 10
    return 0;
}
```

## Explicação
Embora os `enums` sejam simples de usar, existem algumas armadilhas comuns:

- **Não atribuir valores**: Se você não atribuir valores específicos, todos os elementos do `enum` começarão em 0 e se incrementarão automaticamente, o que pode não ser desejado.
- **Tipagem**: O tipo de um `enum` não é estritamente verificado, o que significa que você pode acidentalmente atribuir um valor fora do intervalo definido pelo `enum`.
- **Diferença entre `enum` e `#define`**: Embora ambos possam ser usados para definir constantes, o `enum` é preferido para valores que pertencem a um conjunto específico, pois oferece melhor legibilidade e controle de tipo.

## Resumo em Uma Frase
O `enum` em C é uma ferramenta poderosa para definir conjuntos de constantes nomeadas, melhorando a legibilidade e a manutenção do código.