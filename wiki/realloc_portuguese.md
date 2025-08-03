<!--
Meta Description: # realloc: Redimensionando Memória Dinâmica em C ## Sinopse A função `realloc` em C é utilizada para redimensionar um bloco de memória previamente alo...
Meta Keywords: array, memória, realloc, para, bloco
-->

# realloc: Redimensionando Memória Dinâmica em C

## Sinopse
A função `realloc` em C é utilizada para redimensionar um bloco de memória previamente alocado. Ela permite aumentar ou diminuir o tamanho do bloco, otimizando o uso da memória em programas que requerem manipulação dinâmica de arrays ou estruturas.

## Documentação

### Propósito
A função `realloc` é parte da biblioteca padrão de C e é utilizada para alterar o tamanho de um bloco de memória alocado previamente com `malloc`, `calloc` ou `realloc`. Essa função é especialmente útil quando o tamanho necessário do bloco de memória não é conhecido em tempo de compilação e pode mudar durante a execução do programa.

### Uso
A sintaxe da função `realloc` é a seguinte:

```c
void* realloc(void* ptr, size_t new_size);
```

- `ptr`: Um ponteiro para o bloco de memória previamente alocado. Se `ptr` for `NULL`, `realloc` se comporta como `malloc` e aloca um novo bloco de memória.
- `new_size`: O novo tamanho desejado para o bloco de memória em bytes.

A função retorna um ponteiro para o novo bloco de memória, que pode ser o mesmo que o anterior, ou `NULL` se a alocação falhar. Se a alocação for bem-sucedida, o conteúdo da memória será copiado para o novo bloco, até o menor tamanho entre o novo e o antigo bloco.

### Detalhes
- Se `new_size` for zero, o comportamento da função é equivalente ao de `free(ptr)`, e o ponteiro será considerado inválido.
- É importante sempre verificar se o retorno de `realloc` é `NULL` antes de usar o novo ponteiro, para evitar vazamentos de memória.

## Exemplos

### Exemplo Básico de Redimensionamento

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *array = malloc(5 * sizeof(int)); // Aloca espaço para 5 inteiros
    for (int i = 0; i < 5; i++) {
        array[i] = i + 1; // Inicializa o array
    }

    // Redimensiona o array para 10 inteiros
    array = realloc(array, 10 * sizeof(int));
    if (array == NULL) {
        fprintf(stderr, "Falha na alocação de memória\n");
        return 1;
    }

    for (int i = 5; i < 10; i++) {
        array[i] = i + 1; // Inicializa a nova parte do array
    }

    // Exibe os elementos do array
    for (int i = 0; i < 10; i++) {
        printf("%d ", array[i]);
    }

    free(array); // Libera a memória alocada
    return 0;
}
```

### Exemplo de Redimensionamento para Menor Tamanho

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *array = malloc(5 * sizeof(int)); // Aloca espaço para 5 inteiros
    // Inicialização do array omitida para brevidade

    // Redimensiona o array para 3 inteiros
    array = realloc(array, 3 * sizeof(int));
    if (array == NULL) {
        fprintf(stderr, "Falha na alocação de memória\n");
        return 1;
    }

    // Exibe os elementos do array
    for (int i = 0; i < 3; i++) {
        printf("%d ", array[i]);
    }

    free(array); // Libera a memória alocada
    return 0;
}
```

## Explicação

### Armadilhas Comuns
- **Perda de Ponteiro**: Se `realloc` falhar, o ponteiro original não é modificado. Portanto, se você não armazenar o retorno de `realloc` em um novo ponteiro ou se sobrescrever o ponteiro original sem verificar se o retorno é `NULL`, você pode perder a referência ao bloco de memória original, resultando em um vazamento de memória.
  
- **Manipulação de Dados**: Ao redimensionar, os dados que não cabem no novo bloco serão perdidos. Portanto, é importante garantir que o novo tamanho seja suficiente para armazenar todos os dados necessários.

- **Uso de `ptr` Nulo**: Chamar `realloc` com um ponteiro `NULL` é válido, mas se você tentar redimensionar um ponteiro que não foi alocado com `malloc`, `calloc` ou `realloc`, o comportamento é indefinido.

## Resumo em Uma Linha
A função `realloc` em C é usada para redimensionar um bloco de memória previamente alocado, permitindo otimizar o uso de memória dinâmica.