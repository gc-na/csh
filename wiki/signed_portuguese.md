<!--
Meta Description: # Tipo de Dados "signed" em C: Entendendo a Representação de Números Inteiros ## Sinopse O modificador `signed` em C é utilizado para definir o tipo d...
Meta Keywords: signed, que, int, números, negativos
-->

# Tipo de Dados "signed" em C: Entendendo a Representação de Números Inteiros

## Sinopse
O modificador `signed` em C é utilizado para definir o tipo de dados inteiros que podem representar números positivos e negativos. Este artigo explora seu uso, a sua sintaxe e exemplos práticos.

## Documentação
O `signed` é um modificador que pode ser aplicado aos tipos de dados inteiros em C, como `int`, `short`, `long`, e `char`. Por padrão, os tipos inteiros são `signed`, o que significa que eles podem armazenar tanto valores positivos quanto negativos.

### Propósito
O propósito do `signed` é permitir a manipulação de números inteiros negativos, aumentando assim a gama de valores que podem ser armazenados nas variáveis.

### Uso
Um tipo de dado `signed` pode ser declarado da seguinte forma:

```c
signed int numero; // Declaração explícita
int numero;        // Declaração implícita (padrão é signed)
```

### Detalhes
- Os tipos `signed` podem armazenar valores que vão de `-(2^(n-1))` a `2^(n-1) - 1`, onde `n` é o número de bits do tipo de dado.
- Por exemplo, um `signed int` normalmente ocupa 4 bytes e pode armazenar valores entre -2.147.483.648 e 2.147.483.647.
- Além do `unsigned`, que armazena apenas valores não negativos, o `signed` é essencial quando a aplicação requer cálculos que envolvem números negativos.

## Exemplos
### Exemplo 1: Declaração e Inicialização
```c
#include <stdio.h>

int main() {
    signed int a = -10;
    signed int b = 20;

    printf("Valor de a: %d\n", a);
    printf("Valor de b: %d\n", b);
    return 0;
}
```

### Exemplo 2: Operações Aritméticas
```c
#include <stdio.h>

int main() {
    signed int x = 15;
    signed int y = -5;
    signed int resultado;

    resultado = x + y;
    printf("Resultado da soma: %d\n", resultado); // Saída: 10

    resultado = x - y;
    printf("Resultado da subtração: %d\n", resultado); // Saída: 20
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Confusão entre signed e unsigned**: Um erro comum é não perceber que um tipo `unsigned` não pode armazenar números negativos. Isso pode levar a resultados inesperados em operações matemáticas.
- **Overflow**: Ao manipular números muito grandes ou muito pequenos, pode ocorrer overflow ou underflow. É importante garantir que o valor da variável não exceda os limites do tipo de dado.

### Notas Adicionais
- Em sistemas onde a eficiência é crítica, o uso de tipos de dados apropriados (signed vs unsigned) pode impactar o desempenho.
- O uso do modificador `signed` é especialmente relevante em aplicações que requerem manipulação de temperatura, contagens que podem ser negativas, e outras situações similares.

## Resumo em Uma Frase
O modificador `signed` em C permite a representação de números inteiros negativos, sendo fundamental para operações matemáticas que envolvem valores abaixo de zero.