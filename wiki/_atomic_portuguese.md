<!--
Meta Description: # _Atomic em C: Entenda a Programação Concorrente Segura ## Sinopse O modificador `_Atomic` em C é uma característica fundamental para a programação c...
Meta Keywords: que, valor, _atomic, operações, variáveis
-->

# _Atomic em C: Entenda a Programação Concorrente Segura

## Sinopse
O modificador `_Atomic` em C é uma característica fundamental para a programação concorrente, permitindo que variáveis sejam manipuladas de forma segura em ambientes multi-threaded, evitando condições de corrida e garantindo consistência de dados.

## Documentação
O modificador `_Atomic` foi introduzido no padrão C11 e serve para declarar variáveis que podem ser acessadas de forma segura por múltiplas threads. Ao usar `_Atomic`, o compilador garante que as operações de leitura e escrita nessas variáveis sejam atômicas, ou seja, não podem ser interrompidas, prevenindo assim inconsistências e corrupção de dados.

### Propósito
O principal objetivo do `_Atomic` é permitir que desenvolvedores criem programas que utilizam múltiplas threads de maneira eficaz e segura, sem a necessidade de utilizar locks ou mutexes em todas as situações.

### Uso
Para declarar uma variável atômica, usa-se o seguinte formato:

```c
#include <stdatomic.h>

atomic_tipo nome_variavel;
```

Onde `tipo` pode ser qualquer tipo de dado suportado, como `int`, `float`, ou `pointer`. As operações atômicas incluem leitura, escrita, e operações aritméticas que garantem a segurança em ambientes concorrentes.

### Detalhes
As operações atômicas disponíveis incluem:
- `atomic_store()`: Armazena um valor atômico.
- `atomic_load()`: Carrega um valor atômico.
- `atomic_exchange()`: Troca valores atômicos.
- `atomic_fetch_add()`: Adiciona um valor atômico.

Essas funções são parte da biblioteca `<stdatomic.h>`, que deve ser incluída no código.

## Exemplos
### Exemplo 1: Declaração e Uso Básico

```c
#include <stdio.h>
#include <stdatomic.h>
#include <threads.h>

atomic_int contador = 0;

void incrementar() {
    atomic_fetch_add(&contador, 1);
}

int main() {
    thrd_t t1, t2;
    thrd_create(&t1, incrementar, NULL);
    thrd_create(&t2, incrementar, NULL);
    
    thrd_join(t1, NULL);
    thrd_join(t2, NULL);
    
    printf("Contador: %d\n", atomic_load(&contador));
    return 0;
}
```

### Exemplo 2: Uso com Troca Atômica

```c
#include <stdio.h>
#include <stdatomic.h>

int main() {
    atomic_int valor = 10;
    int antigo = atomic_exchange(&valor, 20);
    
    printf("Antigo valor: %d, Novo valor: %d\n", antigo, atomic_load(&valor));
    return 0;
}
```

## Explicação
É importante lembrar que, embora o `_Atomic` forneça segurança em operações básicas, não é uma solução mágica para todas as situações de concorrência. Operações complexas que envolvem múltiplas variáveis podem ainda necessitar de técnicas adicionais de sincronização. Além disso, o uso inadequado de variáveis atômicas pode levar a um desempenho inferior devido à contenção de dados.

## Resumo em Uma Linha
O modificador `_Atomic` em C permite a manipulação segura de variáveis em ambientes multi-threaded, garantindo operações atômicas e evitando condições de corrida.