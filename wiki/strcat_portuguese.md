<!--
Meta Description: # strcat: Função de Concatenação de Strings em C ## Sinopse A função `strcat` da linguagem C é utilizada para concatenar duas strings, unindo o conteú...
Meta Keywords: string, strcat, para, destino, str1
-->

# strcat: Função de Concatenação de Strings em C

## Sinopse
A função `strcat` da linguagem C é utilizada para concatenar duas strings, unindo o conteúdo da segunda string ao final da primeira.

## Documentação
A função `strcat` faz parte da biblioteca padrão da linguagem C, definida no cabeçalho `<string.h>`. Seu propósito principal é unir duas strings, onde o resultado da concatenação é armazenado na primeira string.

### Prototipagem
```c
char *strcat(char *destino, const char *origem);
```

### Parâmetros
- `destino`: Um ponteiro para a string de destino, que deve ter espaço suficiente para armazenar o resultado da concatenação.
- `origem`: Um ponteiro para a string de origem que será anexada ao final da string de destino.

### Retorno
A função retorna um ponteiro para a string de destino.

### Comportamento
- `strcat` adiciona o conteúdo da string `origem` ao final da string `destino`, incluindo o caractere nulo (`\0`) que termina a string.
- A string `destino` deve ser inicializada e ter espaço suficiente para conter o resultado da concatenação. Caso contrário, pode ocorrer um comportamento indefinido.

## Exemplos
### Exemplo Básico

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[20] = "Olá, ";
    char str2[] = "mundo!";
    
    strcat(str1, str2);
    printf("%s\n", str1); // Saída: Olá, mundo!
    
    return 0;
}
```

### Exemplo com Alocação Dinâmica

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str1 = malloc(50);
    char *str2 = "C é poderoso!";
    
    strcpy(str1, "Programação em ");
    strcat(str1, str2);
    
    printf("%s\n", str1); // Saída: Programação em C é poderoso!
    
    free(str1);
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Espaço Insuficiente**: Um dos erros mais comuns ao usar `strcat` é não garantir que há espaço suficiente na string `destino`. Isso pode levar a estouros de buffer, resultando em comportamento indefinido ou vulnerabilidades de segurança.
- **Strings Não Inicializadas**: Usar `strcat` em strings que não foram inicializadas corretamente pode causar acessos a áreas de memória inválidas.
- **Caractere Nulo**: Certifique-se de que ambas as strings terminem com o caractere nulo (`\0`), pois `strcat` depende disso para determinar o final da string.

### Observações Adicionais
- Para evitar problemas de concatenação, considere usar a função `strncat`, que permite especificar o número máximo de caracteres a serem concatenados, ajudando a controlar o tamanho e evitar estouros de buffer.

## Resumo em Uma Frase
A função `strcat` em C é utilizada para concatenar uma string ao final de outra, exigindo cuidado com a alocação de memória.