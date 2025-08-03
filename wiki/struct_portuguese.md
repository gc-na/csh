<!--
Meta Description: # Estruturas em C: Como Usar e Exemplos Práticos ## Sinopse As estruturas em C são um recurso poderoso que permite agrupar diferentes tipos de dados s...
Meta Keywords: estrutura, membros, nome, struct, estruturas
-->

# Estruturas em C: Como Usar e Exemplos Práticos

## Sinopse
As estruturas em C são um recurso poderoso que permite agrupar diferentes tipos de dados sob um mesmo nome, facilitando a organização e manipulação de informações complexas.

## Documentação
### O que são Estruturas?
As estruturas (ou `structs`) em C são um tipo de dado composto que permite agrupar variáveis de tipos diferentes sob um mesmo nome. Elas são especialmente úteis para representar objetos do mundo real em um programa, como um "ponto" em um espaço 2D, que pode ter coordenadas `x` e `y`.

### Declaração de uma Estrutura
Para declarar uma estrutura em C, utiliza-se a palavra-chave `struct`, seguida de um nome para a estrutura e a definição de seus membros. A sintaxe básica é a seguinte:

```c
struct NomeDaEstrutura {
    tipo1 membro1;
    tipo2 membro2;
    // mais membros...
};
```

### Uso de Estruturas
Após declarar uma estrutura, você pode criar variáveis do tipo dessa estrutura, inicializá-las e acessar seus membros usando o operador `.` (ponto).

### Exemplo de Uso
```c
#include <stdio.h>

// Declaração da estrutura
struct Ponto {
    int x;
    int y;
};

int main() {
    // Criação de uma variável do tipo Ponto
    struct Ponto p1;
    
    // Inicialização dos membros
    p1.x = 10;
    p1.y = 20;

    // Acesso aos membros da estrutura
    printf("Ponto P1: (%d, %d)\n", p1.x, p1.y);
    return 0;
}
```

## Exemplos
### Exemplo 1: Estrutura Simples
```c
#include <stdio.h>

struct Aluno {
    char nome[50];
    int idade;
    float nota;
};

int main() {
    struct Aluno aluno1;

    // Inicializando os membros
    snprintf(aluno1.nome, sizeof(aluno1.nome), "Maria");
    aluno1.idade = 20;
    aluno1.nota = 8.5;

    printf("Nome: %s, Idade: %d, Nota: %.2f\n", aluno1.nome, aluno1.idade, aluno1.nota);
    return 0;
}
```

### Exemplo 2: Estruturas e Ponteiros
```c
#include <stdio.h>

struct Carro {
    char modelo[20];
    int ano;
};

void exibirCarro(struct Carro *c) {
    printf("Modelo: %s, Ano: %d\n", c->modelo, c->ano);
}

int main() {
    struct Carro carro1;
    snprintf(carro1.modelo, sizeof(carro1.modelo), "Fusca");
    carro1.ano = 1976;

    exibirCarro(&carro1);
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Acesso aos Membros**: Lembre-se de usar o operador `.` para acessar membros de uma estrutura e `->` quando estiver utilizando ponteiros para estruturas.
- **Tamanho da Estrutura**: O tamanho total de uma estrutura é a soma dos tamanhos de seus membros, mas pode ser afetado por alinhamento e padding, o que pode levar a surpresas em sistemas diferentes.
- **Inicialização**: É importante inicializar todos os membros da estrutura antes de usá-los para evitar comportamentos indefinidos.

## Resumo em Uma Linha
As estruturas em C permitem agrupar diferentes tipos de dados sob um mesmo nome, facilitando a organização e manipulação de informações complexas.