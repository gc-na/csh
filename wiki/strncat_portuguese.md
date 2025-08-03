<!--
Meta Description: # strncat: Função de Concatenar Strings em C ## Sinopse A função `strncat` em C é utilizada para concatenar um número especificado de caracteres de um...
Meta Keywords: string, destino, strncat, para, origem
-->

# strncat: Função de Concatenar Strings em C

## Sinopse
A função `strncat` em C é utilizada para concatenar um número especificado de caracteres de uma string a outra, garantindo que a string de destino não ultrapasse o tamanho máximo pré-definido.

## Documentação

### Propósito
A função `strncat` é parte da biblioteca padrão de C, definida em `<string.h>`. Seu propósito é concatenar as strings, permitindo que o programador especifique quantos caracteres da string de origem devem ser adicionados à string de destino. Isso é útil para evitar estouros de buffer, um problema comum em manipulação de strings.

### Uso
A função `strncat` tem a seguinte assinatura:

```c
char *strncat(char *dest, const char *src, size_t n);
```

- `dest`: Ponteiro para a string de destino à qual a string de origem será concatenada. Deve ter espaço suficiente para armazenar o resultado.
- `src`: Ponteiro para a string de origem que será concatenada.
- `n`: Número máximo de caracteres a serem concatenados de `src`.

A função retorna um ponteiro para a string de destino (`dest`).

### Detalhes
- A `strncat` adiciona um caractere nulo (`'\0'`) ao final da string de destino após a concatenação.
- É crucial que a string de destino tenha espaço suficiente para evitar buffer overflow.
- Caso o comprimento da string de origem `src` seja menor que `n`, `strncat` irá concatenar a string inteira.

## Exemplos

### Exemplo 1: Concatenando duas strings
```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[20] = "Olá, ";
    char origem[] = "Mundo!";
    
    strncat(destino, origem, 3); // Concatena os primeiros 3 caracteres de 'origem'
    printf("%s\n", destino); // Saída: Olá, Mun
    return 0;
}
```

### Exemplo 2: Evitando buffer overflow
```c
#include <stdio.h>
#include <string.h>

int main() {
    char destino[15] = "Texto: ";
    char origem[] = "Exemplo de concatenação segura.";
    
    strncat(destino, origem, 8); // Concatena até 8 caracteres
    printf("%s\n", destino); // Saída: Texto: Exemplo
    return 0;
}
```

## Explicação
Um erro comum ao usar `strncat` é não garantir que a string de destino tenha espaço suficiente para armazenar a string concatenada, incluindo o caractere nulo. Se o espaço for insuficiente, isso pode levar a comportamentos indefinidos e vulnerabilidades de segurança. Além disso, é importante considerar que `n` deve ser um valor menor ou igual ao comprimento da string de origem para evitar a concatenação parcial inesperada.

## Resumo em Uma Linha
A função `strncat` em C é utilizada para concatenar um número específico de caracteres de uma string a outra, garantindo segurança contra estouros de buffer.