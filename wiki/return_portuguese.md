<!--
Meta Description: # O Comando "return" em C: Entenda Como Funciona ## Sinopse O comando `return` em C é utilizado para finalizar a execução de uma função e, opcionalmen...
Meta Keywords: return, função, funções, tipo, uma
-->

# O Comando "return" em C: Entenda Como Funciona

## Sinopse
O comando `return` em C é utilizado para finalizar a execução de uma função e, opcionalmente, retornar um valor ao chamador. É um elemento fundamental na construção de funções em C, permitindo a passagem de dados entre funções.

## Documentação
O `return` é uma instrução que encerra a execução de uma função e pode retornar um valor, se a função estiver definida para isso. Ao usar `return`, o controle é devolvido ao ponto de chamada da função. 

### Propósito
O principal propósito do `return` é permitir que funções comuniquem resultados de volta ao seu chamador. Ele é usado em funções de qualquer tipo de retorno, incluindo `int`, `float`, `char`, ou qualquer outro tipo definido pelo usuário.

### Uso
A sintaxe básica do comando `return` é:

```c
return expressão;
```

Se a função não retorna um valor (ou seja, é uma função `void`), o comando `return` pode ser usado sem uma expressão:

```c
return;
```

### Detalhes
- **Tipo de Retorno**: O tipo do valor retornado deve corresponder ao tipo definido na assinatura da função.
- **Funções sem Retorno**: Em funções do tipo `void`, o uso do `return` é opcional, mas pode ser útil para sair da função antes do final.
- **Escopo**: O valor retornado pode ser atribuído a uma variável ou usado diretamente em expressões.

## Exemplos

### Exemplo 1: Função que Retorna um Inteiro
```c
#include <stdio.h>

int soma(int a, int b) {
    return a + b; // Retorna a soma dos dois números
}

int main() {
    int resultado = soma(5, 3);
    printf("Resultado: %d\n", resultado); // Saída: Resultado: 8
    return 0;
}
```

### Exemplo 2: Função `void` Usando `return`
```c
#include <stdio.h>

void mensagem() {
    printf("Olá, Mundo!\n");
    return; // Opcional - termina a função
}

int main() {
    mensagem();
    return 0;
}
```

## Explicação
Ao usar o comando `return`, é importante observar alguns pontos comuns que podem causar problemas:

- **Tipo de Dados**: Certifique-se de que o valor retornado é do tipo correto. Retornar um tipo incompatível causará erros de compilação.
- **Uso de `return` em Funções `void`**: Embora seja permitido, o uso de `return` em funções `void` não deve incluir um valor. Usá-lo dessa forma resultará em erro de compilação.
- **Escopo de Variáveis**: Variáveis que são locais à função não podem ser acessadas após a execução do `return`, pois elas são destruídas assim que a função termina.

## Resumo em Uma Linha
O comando `return` em C encerra a execução de uma função e pode retornar um valor ao chamador, sendo essencial para a comunicação de resultados entre funções.