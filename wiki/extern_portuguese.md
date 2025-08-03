<!--
Meta Description: # O uso do "extern" em C: Entendendo a Visibilidade de Variáveis e Funções ## Sinopse O "extern" é uma palavra-chave em C que permite a declaração de ...
Meta Keywords: extern, variáveis, funções, que, variável
-->

# O uso do "extern" em C: Entendendo a Visibilidade de Variáveis e Funções

## Sinopse
O "extern" é uma palavra-chave em C que permite a declaração de variáveis e funções com escopo fora do arquivo atual, facilitando a ligação entre diferentes módulos de um programa.

## Documentação
A palavra-chave `extern` é utilizada na linguagem de programação C para declarar variáveis e funções que estão definidas em outros arquivos ou módulos. Sua principal finalidade é informar ao compilador que a variável ou função existe, mas não está definida no contexto atual, permitindo assim que diferentes partes de um programa compartilhem dados e funcionalidades.

### Propósito
- **Visibilidade**: A palavra-chave `extern` é usada para aumentar a visibilidade de variáveis e funções entre diferentes arquivos fonte.
- **Modularidade**: Facilita a organização do código em múltiplos arquivos, permitindo que funções e variáveis sejam utilizadas em diferentes módulos.

### Uso
Para declarar uma variável ou função como `extern`, você utiliza a seguinte sintaxe:

```c
extern tipo nome_variavel;
extern tipo nome_funcao(parametros);
```

Quando você declara uma variável como `extern`, está dizendo ao compilador que a definição real dessa variável está em outro lugar. Isso é especialmente útil em programas grandes, onde o código é dividido em vários arquivos.

## Exemplos
### Exemplo 1: Variáveis Externas

**Arquivo: arquivo1.c**
```c
#include <stdio.h>

int numero = 10; // Definindo uma variável global

void mostrarNumero() {
    printf("Número: %d\n", numero);
}
```

**Arquivo: arquivo2.c**
```c
#include <stdio.h>

// Declaração da variável externa
extern int numero;

void alterarNumero(int novoNumero) {
    numero = novoNumero; // Alterando a variável global
}
```

**Arquivo: main.c**
```c
#include <stdio.h>

extern void mostrarNumero();
extern void alterarNumero(int);

int main() {
    mostrarNumero(); // Saída: Número: 10
    alterarNumero(20);
    mostrarNumero(); // Saída: Número: 20
    return 0;
}
```

### Exemplo 2: Funções Externas

**Arquivo: funções.c**
```c
#include <stdio.h>

void ola() {
    printf("Olá, Mundo!\n");
}
```

**Arquivo: main.c**
```c
#include <stdio.h>

// Declaração da função externa
extern void ola();

int main() {
    ola(); // Chamada da função definida em outro arquivo
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Definição vs. Declaração**: É importante lembrar que `extern` é apenas uma declaração. Para que o código funcione corretamente, a variável ou função deve ser definida em algum lugar. Caso contrário, o linker gerará um erro.
- **Escopo de Variáveis**: Variáveis declaradas como `extern` não são inicializadas automaticamente. Se você não definir um valor em algum lugar, o comportamento do programa pode ser imprevisível.
- **Uso Incorreto**: Utilizar `extern` em variáveis locais dentro de funções não é necessário e pode causar confusão. Ele deve ser usado apenas para variáveis globais.

## Resumo em Uma Linha
O `extern` em C permite a declaração de variáveis e funções em um contexto diferente, facilitando a modularidade e a reutilização de código entre arquivos fonte.