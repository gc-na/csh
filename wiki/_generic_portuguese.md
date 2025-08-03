<!--
Meta Description: # _Generic em C: A Forma Eficiente de Manipular Tipos em C ## Sinopse O operador `_Generic` em C é uma funcionalidade introduzida no C11 que permite a...
Meta Keywords: _generic, tipo, tipos, que, uma
-->

# _Generic em C: A Forma Eficiente de Manipular Tipos em C

## Sinopse
O operador `_Generic` em C é uma funcionalidade introduzida no C11 que permite a seleção de expressões com base no tipo de um valor, facilitando a criação de funções genéricas.

## Documentação
O operador `_Generic` é usado para permitir a seleção dinâmica de tipos em tempo de compilação. Isso significa que você pode escrever código que se comporta de maneira diferente dependendo do tipo de um argumento passado para uma expressão.

### Propósito
O principal objetivo do `_Generic` é proporcionar uma maneira de escrever código genérico que pode ser utilizado com diferentes tipos de dados sem a necessidade de sobrecarga de funções ou macros complexas.

### Uso
A sintaxe básica do `_Generic` é a seguinte:

```c
_Generic(expr, type1: result1, type2: result2, ..., default: defaultResult)
```

- `expr`: A expressão cujo tipo será verificado.
- `typeN`: Os tipos que você deseja verificar.
- `resultN`: O resultado que será retornado se `expr` for do tipo `typeN`.
- `default`: Um resultado padrão que será retornado se `expr` não corresponder a nenhum dos tipos especificados.

### Detalhes
- O `_Generic` é avaliado em tempo de compilação, permitindo que o compilador escolha o resultado apropriado com base no tipo de `expr`.
- Se `expr` corresponder a mais de um tipo, o comportamento é indefinido.
- `_Generic` pode ser especialmente útil em funções que precisam operar em vários tipos, como em funções matemáticas para diferentes tipos numéricos.

## Exemplos

### Exemplo Básico
Aqui está um exemplo simples de como utilizar `_Generic`:

```c
#include <stdio.h>

#define tipo_de_var(x) _Generic((x), \
    int: "É um inteiro", \
    float: "É um float", \
    double: "É um double", \
    default: "Tipo desconhecido")

int main() {
    printf("%s\n", tipo_de_var(10));      // Saída: É um inteiro
    printf("%s\n", tipo_de_var(10.5f));   // Saída: É um float
    printf("%s\n", tipo_de_var(10.5));     // Saída: É um double
    printf("%s\n", tipo_de_var("texto"));  // Saída: Tipo desconhecido
    return 0;
}
```

### Exemplo com Função
Você também pode utilizar `_Generic` para criar funções que operam de maneira diferente com base no tipo de entrada:

```c
#include <stdio.h>

#define print_val(val) _Generic((val), \
    int: printf("Valor inteiro: %d\n", val), \
    float: printf("Valor float: %.2f\n", val), \
    double: printf("Valor double: %.2f\n", val), \
    default: printf("Tipo desconhecido\n"))

int main() {
    print_val(42);        // Saída: Valor inteiro: 42
    print_val(3.14f);     // Saída: Valor float: 3.14
    print_val(2.718);     // Saída: Valor double: 2.72
    print_val("teste");    // Saída: Tipo desconhecido
    return 0;
}
```

## Explicação
Embora o `_Generic` seja uma ferramenta poderosa, existem algumas considerações importantes a serem lembradas:

- **Tipos Não Compatíveis**: Se você passar uma expressão que não corresponde a nenhum dos tipos especificados, o resultado padrão será utilizado. Se não houver um resultado padrão, ocorrerá um erro de compilação.
- **Limitações**: O `_Generic` não pode ser usado para retornar valores de tipos diferentes (ou seja, você não pode misturar tipos de retorno de uma função com `_Generic`).
- **Complexidade**: O uso excessivo de `_Generic` pode tornar o código mais difícil de entender e manter. Portanto, use-o com moderação.

## Resumo em Uma Linha
O operador `_Generic` em C permite a seleção de expressões baseadas no tipo de uma variável, facilitando a criação de funções genéricas.