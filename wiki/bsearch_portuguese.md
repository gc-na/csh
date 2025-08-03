<!--
Meta Description: # bsearch: Busca Binária em C ## Sinopse A função `bsearch` em C é utilizada para realizar uma busca binária em um array ordenado, permitindo localiza...
Meta Keywords: const, array, elemento, int, bsearch
-->

# bsearch: Busca Binária em C

## Sinopse
A função `bsearch` em C é utilizada para realizar uma busca binária em um array ordenado, permitindo localizar rapidamente um elemento específico.

## Documentação

### Propósito
A função `bsearch` serve para encontrar a posição de um elemento em um array ordenado, utilizando o algoritmo de busca binária, que é eficiente em termos de complexidade de tempo, com um desempenho de O(log n).

### Uso
A função `bsearch` é definida na biblioteca `<stdlib.h>` e sua assinatura é a seguinte:

```c
void *bsearch(const void *key, const void *base, size_t nmemb, size_t size, int (*compar)(const void *, const void *));
```

#### Parâmetros
- **key**: Um ponteiro para o elemento que está sendo buscado.
- **base**: Um ponteiro para o início do array onde a busca será realizada.
- **nmemb**: O número de elementos no array.
- **size**: O tamanho, em bytes, de cada elemento no array.
- **compar**: Um ponteiro para uma função de comparação que define a ordem dos elementos.

### Retorno
A função retorna um ponteiro para o elemento encontrado no array ou `NULL` se o elemento não estiver presente.

## Exemplos

### Exemplo 1: Busca de um Número Inteiro
```c
#include <stdio.h>
#include <stdlib.h>

int compar(const void *a, const void *b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int array[] = {1, 2, 3, 4, 5};
    int key = 3;
    int *result = bsearch(&key, array, 5, sizeof(int), compar);

    if (result) {
        printf("Elemento encontrado: %d\n", *result);
    } else {
        printf("Elemento não encontrado.\n");
    }

    return 0;
}
```

### Exemplo 2: Busca de uma String
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int compar(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

int main() {
    const char *array[] = {"banana", "laranja", "maçã", "uva"};
    const char *key = "maçã";
    const char **result = bsearch(&key, array, 4, sizeof(char*), compar);

    if (result) {
        printf("Elemento encontrado: %s\n", *result);
    } else {
        printf("Elemento não encontrado.\n");
    }

    return 0;
}
```

## Explicação
Embora a `bsearch` seja uma função poderosa, é importante lembrar que ela exige que o array esteja ordenado antes da busca ser realizada. Uma busca em um array não ordenado pode levar a resultados inesperados. Além disso, a função de comparação deve ser definida corretamente para assegurar que a ordem dos elementos seja respeitada. Um erro comum é não considerar o tipo de dados corretamente na função de comparação, o que pode levar a falhas ou resultados incorretos.

## Resumo em Uma Linha
A função `bsearch` em C realiza buscas binárias em arrays ordenados, retornando a posição de um elemento ou `NULL` se não encontrado.