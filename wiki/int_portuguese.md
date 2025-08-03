<!--
Meta Description: # O Tipo de Dado `int` em C: Tudo que Você Precisa Saber ## Sinopse O `int` é um dos tipos de dados primitivos da linguagem de programação C, utilizad...
Meta Keywords: int, tipo, pode, para, números
-->

# O Tipo de Dado `int` em C: Tudo que Você Precisa Saber

## Sinopse
O `int` é um dos tipos de dados primitivos da linguagem de programação C, utilizado para representar números inteiros. Ele é amplamente utilizado em diversas aplicações, sendo fundamental para operações aritméticas e controle de fluxo em programas.

## Documentação
### Propósito
O tipo `int` serve para armazenar valores inteiros, que são números sem parte decimal. Com ele, é possível realizar operações matemáticas, contagens, índices de arrays e muito mais.

### Uso
Em C, a declaração de uma variável do tipo `int` é feita da seguinte maneira:
```c
int nome_variavel;
```
O `int` pode ser usado em expressões, loops, condições e como argumento em funções.

### Detalhes
- **Tamanho**: O tamanho de um `int` pode variar, dependendo da arquitetura do sistema e do compilador. Em geral, em sistemas de 32 bits, um `int` ocupa 4 bytes, e em sistemas de 64 bits, também costuma ocupar 4 bytes.
- **Faixa de Valores**: A faixa de valores que um `int` pode armazenar é de -2.147.483.648 a 2.147.483.647, considerando um `int` de 32 bits. Para valores maiores, pode-se usar `long int` ou `long long int`.
- **Modificadores**: O tipo `int` pode ser modificado com palavras-chave como `signed` e `unsigned`:
  - `signed int`: permite armazenar números negativos e positivos.
  - `unsigned int`: permite armazenar apenas números positivos, dobrando a faixa máxima (0 a 4.294.967.295 em 32 bits).

## Exemplos
### Exemplo Básico de Declaração e Atribuição
```c
#include <stdio.h>

int main() {
    int numero = 10;
    printf("O número é: %d\n", numero);
    return 0;
}
```

### Exemplo de Uso em um Loop
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("Contagem: %d\n", i);
    }
    return 0;
}
```

### Exemplo de Uso com Modificadores
```c
#include <stdio.h>

int main() {
    unsigned int numeroPositivo = 3000000000;
    printf("Número positivo: %u\n", numeroPositivo);
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Overflow**: Quando a operação em um `int` excede seu limite máximo ou mínimo, ocorre overflow, resultando em comportamento indefinido. Sempre verifique se os cálculos podem ultrapassar os limites do tipo.
- **Tipo de Dados Incompatíveis**: Ao realizar operações entre diferentes tipos (por exemplo, `int` e `float`), pode ocorrer perda de dados ou conversões inesperadas. Use casting quando necessário.
- **Inicialização**: Variáveis do tipo `int` não inicializadas contêm valores indefinidos. Sempre inicialize suas variáveis antes de usá-las.

## Resumo em Uma Linha
O `int` é um tipo de dado fundamental em C, usado para representar números inteiros e realizar operações aritméticas básicas.