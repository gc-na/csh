<!--
Meta Description: # Estrutura de Repetição "while" em C: Entenda Seu Funcionamento ## Sinopse A estrutura de repetição "while" em C permite a execução de um bloco de có...
Meta Keywords: condição, while, bloco, código, uma
-->

# Estrutura de Repetição "while" em C: Entenda Seu Funcionamento

## Sinopse
A estrutura de repetição "while" em C permite a execução de um bloco de código enquanto uma condição específica for verdadeira, oferecendo um controle eficaz sobre loops.

## Documentação
A instrução `while` em C é uma das principais estruturas de controle de fluxo. Seu propósito é repetir um conjunto de instruções enquanto a condição especificada permanecer verdadeira. A sintaxe básica da estrutura `while` é:

```c
while (condição) {
    // bloco de código a ser executado
}
```

### Propósito
O `while` é frequentemente utilizado quando o número de iterações não é conhecido previamente e depende de uma condição que pode mudar durante a execução do programa.

### Uso
1. **Inicialização da Condição**: Antes do loop, a condição deve ser inicializada.
2. **Avaliação da Condição**: A condição é avaliada antes da execução do bloco de código. Se for verdadeira, o bloco é executado.
3. **Modificação da Condição**: É essencial que a condição mude dentro do bloco para evitar loops infinitos.

## Exemplos
### Exemplo Básico
```c
#include <stdio.h>

int main() {
    int contador = 0;

    while (contador < 5) {
        printf("Contador: %d\n", contador);
        contador++;
    }

    return 0;
}
```
Neste exemplo, o programa imprime os valores de `contador` de 0 a 4.

### Exemplo com Entrada do Usuário
```c
#include <stdio.h>

int main() {
    int numero;

    printf("Digite um número positivo (0 para sair): ");
    scanf("%d", &numero);

    while (numero > 0) {
        printf("Você digitou: %d\n", numero);
        printf("Digite outro número positivo (0 para sair): ");
        scanf("%d", &numero);
    }

    printf("Programa encerrado.\n");
    return 0;
}
```
Aqui, o programa continua solicitando números até que o usuário digite 0.

## Explicação
### Armadilhas Comuns
- **Loops Infinitos**: Um dos erros mais comuns ao usar `while` é esquecer de modificar a condição dentro do loop. Isso pode resultar em um loop infinito, travando o programa.
- **Condições de Saída**: Sempre verifique se a condição de saída é alcançável. Se a condição não for adequada, o loop pode não terminar como esperado.
- **Uso de Variáveis**: Cuidado ao usar variáveis que são modificadas em outros locais do código, pois isso pode afetar a condição do `while`.

### Notas Adicionais
- O bloco de código dentro do `while` pode ser uma única instrução ou um bloco de instruções cercado por chaves `{}`.
- É possível utilizar `break` e `continue` dentro de um loop `while` para controlar o fluxo de execução.

## Resumo em Uma Linha
A estrutura de repetição `while` em C permite executar um bloco de código enquanto uma condição especificada for verdadeira, sendo fundamental para o controle de loops.