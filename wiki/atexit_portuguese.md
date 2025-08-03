<!--
Meta Description: # atexit: Função para Registro de Funções de Limpeza em C ## Sinopse A função `atexit` em C permite que funções de limpeza sejam registradas para sere...
Meta Keywords: atexit, função, que, funções, limpeza
-->

# atexit: Função para Registro de Funções de Limpeza em C

## Sinopse
A função `atexit` em C permite que funções de limpeza sejam registradas para serem chamadas automaticamente quando um programa termina. Isso é útil para garantir que recursos sejam liberados corretamente e que o estado final do programa seja gerenciado de forma adequada.

## Documentação
A função `atexit` é definida na biblioteca `<stdlib.h>`. Ela tem a seguinte assinatura:

```c
int atexit(void (*func)(void));
```

### Propósito
O principal propósito da função `atexit` é registrar funções que serão executadas quando o programa terminar normalmente. Isso é especialmente útil para liberar recursos, como memória alocada dinamicamente ou arquivos abertos.

### Uso
- O usuário deve passar um ponteiro para uma função que não aceita parâmetros e não retorna um valor (void).
- É possível registrar múltiplas funções usando `atexit`, e elas serão chamadas na ordem inversa em que foram registradas.

### Detalhes
- A função `atexit` retorna 0 se o registro for bem-sucedido e um valor diferente de zero se falhar.
- Funções registradas com `atexit` não são chamadas se o programa termina por meio de funções como `exit` ou `abort`.

## Exemplos

### Exemplo 1: Registro de uma Função Simples
```c
#include <stdio.h>
#include <stdlib.h>

void cleanup() {
    printf("Executando a função de limpeza...\n");
}

int main() {
    if (atexit(cleanup) != 0) {
        fprintf(stderr, "Erro ao registrar a função de limpeza.\n");
        return 1;
    }
    printf("Programa em execução...\n");
    return 0; // Quando o programa termina, cleanup() é chamado
}
```

### Exemplo 2: Vários Registros
```c
#include <stdio.h>
#include <stdlib.h>

void cleanup1() {
    printf("Função de limpeza 1 executada.\n");
}

void cleanup2() {
    printf("Função de limpeza 2 executada.\n");
}

int main() {
    atexit(cleanup1);
    atexit(cleanup2);
    
    printf("Programa em execução...\n");
    return 0; // cleanup2() é chamada antes de cleanup1()
}
```

## Explicação
### Armadilhas Comuns
- **Funções com Parâmetros**: Não é possível registrar uma função que aceita argumentos. Isso resultará em um erro de compilação.
- **Programas que Terminam Abruptamente**: Se o programa for encerrado de forma inesperada (por exemplo, por `abort()`), as funções registradas não serão chamadas.
- **Múltiplas Chamadas**: Lembre-se de que as funções de limpeza são chamadas na ordem inversa ao registro. Isso pode ser uma fonte de confusão se não for compreendido.

### Notas Adicionais
- A função `atexit` é uma maneira eficaz de gerenciar a limpeza de recursos em programas complexos. No entanto, é importante planejar adequadamente o que deve ser limpo e em que ordem.
- Em programas multithread, a chamada de `atexit` é feita para cada thread de forma independente.

## Resumo em Uma Linha
A função `atexit` em C permite registrar funções de limpeza que serão executadas automaticamente ao término do programa, garantindo a liberação adequada de recursos.