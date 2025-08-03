<!--
Meta Description: # qsort: Função de Ordenação em C ## Sinopse A função `qsort` é uma poderosa ferramenta na linguagem de programação C, utilizada para ordenar arrays d...
Meta Keywords: função, array, qsort, int, const
-->

# qsort: Função de Ordenação em C

## Sinopse
A função `qsort` é uma poderosa ferramenta na linguagem de programação C, utilizada para ordenar arrays de qualquer tipo de dados, oferecendo uma solução eficiente e flexível para a ordenação.

## Documentação
A função `qsort` é definida na biblioteca padrão `<stdlib.h>` e permite a ordenação de elementos em um array. O protótipo da função é o seguinte:

```c
void qsort(void *base, size_t num, size_t size, int (*compar)(const void *, const void *));
```

### Parâmetros
- **base**: Um ponteiro para o primeiro elemento do array a ser ordenado.
- **num**: O número de elementos no array.
- **size**: O tamanho em bytes de cada elemento do array.
- **compar**: Um ponteiro para uma função de comparação que determina a ordem dos elementos. Esta função deve retornar um inteiro menor que, igual a, ou maior que zero, dependendo se o primeiro elemento é menor, igual ou maior que o segundo.

### Retorno
A função `qsort` não retorna um valor. O array fornecido como argumento é ordenado no local.

## Exemplos

### Exemplo 1: Ordenando um array de inteiros
```c
#include <stdio.h>
#include <stdlib.h>

int comparar(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

int main() {
    int array[] = {3, 5, 1, 4, 2};
    size_t num_elementos = sizeof(array) / sizeof(array[0]);

    qsort(array, num_elementos, sizeof(int), comparar);

    for (size_t i = 0; i < num_elementos; i++) {
        printf("%d ", array[i]);
    }
    return 0;
}
```

### Exemplo 2: Ordenando um array de strings
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int comparar_strings(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

int main() {
    const char *frutas[] = {"banana", "maçã", "laranja", "uva"};
    size_t num_frutas = sizeof(frutas) / sizeof(frutas[0]);

    qsort(frutas, num_frutas, sizeof(char *), comparar_strings);

    for (size_t i = 0; i < num_frutas; i++) {
        printf("%s\n", frutas[i]);
    }
    return 0;
}
```

## Explicação
Ao utilizar `qsort`, é importante estar ciente de alguns pontos:

- A função de comparação deve ser corretamente implementada. Se não retornar os valores adequados, o resultado da ordenação será imprevisível.
- A função `qsort` não é segura em ambientes multithread, pois não gerencia a concorrência.
- O desempenho de `qsort` é geralmente O(n log n) na média, mas pode se degradar para O(n²) em casos extremos, dependendo da implementação e da função de comparação.

## Resumo em Uma Linha
A função `qsort` em C é uma ferramenta eficiente para ordenar arrays de qualquer tipo de dados, utilizando uma função de comparação personalizada.