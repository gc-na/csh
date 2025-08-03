<!--
Meta Description: # memcpy: Função de C para Cópia de Memória ## Sinopse A função `memcpy` em C é utilizada para copiar uma quantidade específica de bytes de uma área d...
Meta Keywords: para, destino, origem, memcpy, memória
-->

# memcpy: Função de C para Cópia de Memória

## Sinopse
A função `memcpy` em C é utilizada para copiar uma quantidade específica de bytes de uma área de memória para outra, sendo uma das funções mais essenciais para manipulação de dados em aplicações de baixo nível.

## Documentação
A `memcpy` é definida na biblioteca `<string.h>` e tem a seguinte assinatura:

```c
void *memcpy(void *destino, const void *origem, size_t n);
```

### Propósito
`memcpy` é utilizada para copiar `n` bytes da memória apontada por `origem` para a memória apontada por `destino`.

### Uso
- **destino**: Um ponteiro para o local onde os dados serão copiados.
- **origem**: Um ponteiro para o local de onde os dados serão copiados.
- **n**: O número de bytes a serem copiados.

### Detalhes
- A função retorna um ponteiro para o destino.
- É importante garantir que a área de memória apontada por `destino` tenha espaço suficiente para receber os dados copiados.
- A função não verifica se as áreas de memória se sobrepõem. Se `origem` e `destino` se sobrepuserem, o comportamento da função é indefinido.

## Exemplos

### Exemplo Básico de Uso

```c
#include <stdio.h>
#include <string.h>

int main() {
    char origem[] = "Olá, Mundo!";
    char destino[20];

    memcpy(destino, origem, strlen(origem) + 1); // +1 para incluir o caractere nulo
    printf("Destino: %s\n", destino);
    return 0;
}
```

### Cópia de Dados Inteiros

```c
#include <stdio.h>
#include <string.h>

int main() {
    int origem[] = {1, 2, 3, 4, 5};
    int destino[5];

    memcpy(destino, origem, sizeof(origem)); // Copia todos os inteiros
    for (int i = 0; i < 5; i++) {
        printf("%d ", destino[i]);
    }
    return 0;
}
```

## Explicação
É crucial ter cuidado ao utilizar `memcpy`, pois alguns erros comuns podem surgir:

1. **Sobreposição de Memória**: Se `origem` e `destino` se sobrepõem, utilize `memmove` em vez de `memcpy` para evitar comportamento indefinido.
2. **Tamanho Inadequado**: Sempre verifique se o buffer de destino é grande o suficiente para armazenar todos os dados que serão copiados, incluindo o caractere nulo (se aplicável).
3. **Tipo de Dado**: Certifique-se de que o número de bytes copiados (`n`) corresponda ao tipo de dado da origem. Por exemplo, copiar um array de `int` requer que `n` seja `sizeof(int) * número_de_elementos`.

## Resumo em Uma Linha
A função `memcpy` em C é usada para copiar bytes de uma área de memória para outra de forma rápida e eficiente, mas deve ser utilizada com cautela para evitar problemas de sobreposição e alocação insuficiente.