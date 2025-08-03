<!--
Meta Description: # strcpy: Função para Cópia de Strings em C ## Sinopse A função `strcpy` em C é utilizada para copiar uma string de uma variável para outra, sendo uma...
Meta Keywords: string, destino, para, origem, strcpy
-->

# strcpy: Função para Cópia de Strings em C

## Sinopse
A função `strcpy` em C é utilizada para copiar uma string de uma variável para outra, sendo uma das funções mais comuns para manipulação de strings.

## Documentação
A função `strcpy` faz parte da biblioteca padrão de C, definida no cabeçalho `<string.h>`. Seu propósito principal é copiar o conteúdo de uma string (incluindo o caractere nulo de terminação) de uma origem para um destino.

### Prototipo
```c
char *strcpy(char *destino, const char *origem);
```

### Parâmetros
- **destino**: Um ponteiro para a string de destino onde a cópia será armazenada.
- **origem**: Um ponteiro para a string de origem que será copiada.

### Retorno
A função retorna um ponteiro para a string de destino.

### Uso
Para utilizar a `strcpy`, é necessário garantir que o espaço alocado para a string de destino seja suficiente para conter a string de origem, incluindo o caractere nulo `\0` que indica o fim da string.

## Exemplos

### Exemplo Básico
```c
#include <stdio.h>
#include <string.h>

int main() {
    char origem[] = "Olá, Mundo!";
    char destino[50]; // Certifique-se de que o espaço é suficiente

    strcpy(destino, origem);
    printf("A string de destino é: %s\n", destino);

    return 0;
}
```

### Exemplo com Strings Vazia
```c
#include <stdio.h>
#include <string.h>

int main() {
    char origem[] = "";
    char destino[50];

    strcpy(destino, origem);
    printf("A string de destino é: '%s'\n", destino); // Deve imprimir uma string vazia

    return 0;
}
```

## Explicação
Embora `strcpy` seja uma função bastante útil, ela possui algumas armadilhas que os programadores devem estar cientes:

1. **Sobrecarga de Buffer**: Se o tamanho do destino não for suficiente para armazenar a origem, isso pode levar a um comportamento indefinido, incluindo corrupção de memória e falhas de segmentação.
   
2. **Cópia de Strings Nulas**: Passar um ponteiro nulo como argumento pode causar falhas no programa. Sempre assegure-se de que tanto a origem quanto o destino não sejam nulos antes de chamar `strcpy`.

3. **Não Verifica a Tamanho**: Diferentemente de funções mais seguras como `strncpy`, a `strcpy` não verifica o tamanho da string de origem. Isso significa que cabe ao programador garantir que a string de destino tem espaço suficiente.

## Resumo em Uma Linha
A `strcpy` é uma função em C que copia uma string de origem para uma string de destino, mas deve ser usada com cautela para evitar problemas de segurança e corrupção de memória.