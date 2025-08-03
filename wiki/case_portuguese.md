<!--
Meta Description: # Comando "case" em C: Entenda a Estrutura de Seleção de Múltiplas Condições ## Sinopse O comando `case` em C é uma estrutura de controle que permite ...
Meta Keywords: case, break, printf, comando, uma
-->

# Comando "case" em C: Entenda a Estrutura de Seleção de Múltiplas Condições

## Sinopse
O comando `case` em C é uma estrutura de controle que permite a seleção de uma entre várias opções com base no valor de uma variável. Ele é frequentemente utilizado em conjunto com o comando `switch`.

## Documentação
### Propósito
O comando `case` é utilizado para simplificar a seleção condicional em programas C, permitindo que o código execute diferentes blocos de instrução com base no valor de uma expressão. É especialmente útil quando há múltiplas condições que devem ser verificadas em relação a uma única variável.

### Uso
A estrutura básica do comando `case` é a seguinte:

```c
switch (expressão) {
    case constante1:
        // Código a ser executado se expressão for igual a constante1
        break;
    case constante2:
        // Código a ser executado se expressão for igual a constante2
        break;
    // Mais casos podem ser adicionados conforme necessário
    default:
        // Código a ser executado se nenhum caso for atendido
}
```

### Detalhes
- **`switch`**: Inicia a estrutura e avalia a expressão.
- **`case`**: Define um valor constante a ser comparado com o resultado da expressão.
- **`break`**: Interrompe a execução do `switch`, evitando a execução dos casos seguintes (fall-through).
- **`default`**: Um caso opcional que executa se nenhum dos casos anteriores for correspondido.

## Exemplos
### Exemplo Básico de Uso do `case`
```c
#include <stdio.h>

int main() {
    int dia = 3;

    switch (dia) {
        case 1:
            printf("Domingo\n");
            break;
        case 2:
            printf("Segunda-feira\n");
            break;
        case 3:
            printf("Terça-feira\n");
            break;
        case 4:
            printf("Quarta-feira\n");
            break;
        case 5:
            printf("Quinta-feira\n");
            break;
        case 6:
            printf("Sexta-feira\n");
            break;
        case 7:
            printf("Sábado\n");
            break;
        default:
            printf("Dia inválido\n");
    }

    return 0;
}
```

### Exemplo de Fall-through
```c
#include <stdio.h>

int main() {
    int numero = 2;

    switch (numero) {
        case 1:
        case 2:
            printf("Número é baixo\n");
            break;
        case 3:
        case 4:
            printf("Número é médio\n");
            break;
        default:
            printf("Número é alto\n");
    }

    return 0;
}
```

## Explicação
Um erro comum ao utilizar o `case` é esquecer o comando `break`, o que resulta em um comportamento conhecido como "fall-through". Nesse caso, se um `case` for atendido, todos os `case`s subsequentes também serão executados até encontrar um `break` ou o final do `switch`. Isso pode levar a resultados inesperados se não for a intenção do programador.

Além disso, é importante notar que o `case` aceita apenas constantes inteiras, não podendo usar variáveis ou expressões que não sejam constantes. 

## Resumo em Uma Linha
O comando `case` em C permite a seleção de múltiplas condições de forma organizada, simplificando a execução condicional baseada no valor de uma variável.