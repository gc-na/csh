<!--
Meta Description: # snprintf: Formatação Segura de Strings em C ## Sinopse O `snprintf` é uma função da linguagem C utilizada para formatar strings de maneira segura, e...
Meta Keywords: buffer, que, snprintf, string, função
-->

# snprintf: Formatação Segura de Strings em C

## Sinopse
O `snprintf` é uma função da linguagem C utilizada para formatar strings de maneira segura, evitando o estouro de buffer, permitindo que os programadores criem saídas formatadas em buffers de tamanho específico.

## Documentação
A função `snprintf` é definida no cabeçalho `<stdio.h>` e sua assinatura é a seguinte:

```c
int snprintf(char *str, size_t size, const char *format, ...);
```

### Propósito
O propósito principal do `snprintf` é escrever dados formatados em uma string, garantindo que não haja ultrapassagem do espaço alocado no buffer. Isso é crucial para a segurança do software, pois previne vulnerabilidades como buffer overflow.

### Uso
- **str**: Um ponteiro para o buffer onde a string formatada será armazenada.
- **size**: O tamanho máximo do buffer `str` (incluindo o caractere nulo de terminação).
- **format**: Uma string de formato que especifica como os argumentos subsequentes devem ser formatados.
- **...**: Os argumentos a serem formatados conforme a string de formato.

A função retorna o número de caracteres que teriam sido escritos se o buffer tivesse espaço suficiente (excluindo o caractere nulo), ou um valor negativo se ocorrer um erro de formatação.

### Detalhes
- Se o número de caracteres a serem escritos for maior que `size - 1`, a string resultante será truncada e será garantido que o buffer `str` seja sempre nulo-terminado.
- Se `size` for zero, nada será escrito e a função retornará zero.
- `snprintf` é uma escolha preferível em relação à `sprintf`, pois oferece proteção contra estouros de buffer.

## Exemplos

### Exemplo Básico de Uso
```c
#include <stdio.h>

int main() {
    char buffer[50];
    int n = snprintf(buffer, sizeof(buffer), "Olá, %s! Você tem %d anos.", "João", 25);
    
    printf("String formatada: %s\n", buffer);
    printf("Número de caracteres escritos: %d\n", n);
    
    return 0;
}
```

### Exemplo de Truncamento
```c
#include <stdio.h>

int main() {
    char buffer[10];
    int n = snprintf(buffer, sizeof(buffer), "Texto muito longo para caber");

    printf("String formatada: %s\n", buffer); // Saída será truncada
    printf("Número de caracteres escritos: %d\n", n);
    
    return 0;
}
```

## Explicação
Um erro comum ao usar `snprintf` é não considerar o tamanho do buffer corretamente. Sempre assegure-se de que o buffer tenha espaço suficiente para acomodar a string formatada e o caractere nulo. Se o valor de `size` for menor que o necessário para a string formatada, a função truncará a saída, o que pode levar a resultados inesperados. Além disso, é importante lembrar que `snprintf` sempre retornará o número total de caracteres que teriam sido escritos, mesmo que a escrita tenha sido truncada.

## Resumo em Uma Linha
A função `snprintf` em C permite a formatação segura de strings, prevenindo estouros de buffer ao escrever em buffers de tamanho específico.