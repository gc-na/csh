<!--
Meta Description: # strtok: Função para Dividir Strings em C ## Sinopse A função `strtok` em C é utilizada para dividir uma string em tokens, permitindo a manipulação e...
Meta Keywords: strtok, string, delimitadores, para, uma
-->

# strtok: Função para Dividir Strings em C

## Sinopse
A função `strtok` em C é utilizada para dividir uma string em tokens, permitindo a manipulação e análise de cadeias de texto de forma eficiente. É comumente empregada em processamento de strings, como a leitura de dados formatados.

## Documentação
A função `strtok` faz parte da biblioteca padrão do C, `<string.h>`, e sua principal finalidade é quebrar uma string em partes menores, chamadas de tokens. Os tokens são definidos por delimitadores, que podem ser qualquer conjunto de caracteres especificados pelo usuário.

### Prototipo
```c
char *strtok(char *str, const char *delim);
```

### Parâmetros
- `str`: Ponteiro para a string que será dividida. Na primeira chamada, deve ser a string a ser tokenizada. Para chamadas subsequentes, deve ser `NULL`.
- `delim`: Ponteiro para uma string que contém os caracteres delimitadores.

### Retorno
`strtok` retorna um ponteiro para o próximo token encontrado na string. Se não houver mais tokens, retorna `NULL`.

### Uso
1. Na primeira chamada, passe a string original e os delimitadores.
2. Para obter os próximos tokens, chame `strtok` com `NULL` como primeiro argumento.
3. Continue chamando até que `strtok` retorne `NULL`.

## Exemplos
### Exemplo 1: Dividindo uma frase
```c
#include <stdio.h>
#include <string.h>

int main() {
    char frase[] = "C é uma linguagem de programação, C é poderosa.";
    const char *delimitadores = " ,.";

    char *token = strtok(frase, delimitadores);
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, delimitadores);
    }
    
    return 0;
}
```
*Saída:*
```
C
é
uma
linguagem
de
programação
C
é
poderosa
```

### Exemplo 2: Analisando uma lista de números
```c
#include <stdio.h>
#include <string.h>

int main() {
    char numeros[] = "10;20;30;40;50";
    const char *delimitadores = ";";

    char *token = strtok(numeros, delimitadores);
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, delimitadores);
    }
    
    return 0;
}
```
*Saída:*
```
10
20
30
40
50
```

## Explicação
Embora `strtok` seja uma função poderosa, apresenta algumas desvantagens e armadilhas:

1. **Modificação da String Original**: `strtok` modifica a string original, substituindo os delimitadores por `\0` (caractere nulo). Isso pode ser problemático se você precisar da string original após a tokenização.

2. **Não Thread-safe**: `strtok` não é segura para uso em ambientes multithread, pois mantém estado interno entre chamadas. Para um uso seguro em múltiplas threads, considere a função `strtok_r`.

3. **Delimitadores Contínuos**: Se houver múltiplos delimitadores consecutivos, `strtok` pode retornar tokens vazios, o que pode não ser desejado.

4. **Uso de Ponteiros**: O retorno da função é um ponteiro para a string que foi alterada, portanto, tenha cuidado ao armazenar ou manipular o resultado.

## Resumo em Uma Linha
A função `strtok` em C é utilizada para dividir strings em tokens com base em delimitadores especificados, modificando a string original e não sendo segura para uso em múltiplas threads.