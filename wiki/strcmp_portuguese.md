<!--
Meta Description: # strcmp: Função de Comparação de Strings em C ## Sinopse A função `strcmp` em C é utilizada para comparar duas strings, retornando um valor que indic...
Meta Keywords: str1, str2, que, strcmp, strings
-->

# strcmp: Função de Comparação de Strings em C

## Sinopse
A função `strcmp` em C é utilizada para comparar duas strings, retornando um valor que indica sua relação lexicográfica. É uma ferramenta fundamental para operações de comparação em programas que manipulam texto.

## Documentação
A função `strcmp` está definida na biblioteca padrão `<string.h>`. Sua finalidade é comparar duas strings (cadeias de caracteres) e determinar se são iguais, ou qual delas é maior em termos de ordem lexicográfica.

### Sintaxe
```c
int strcmp(const char *str1, const char *str2);
```

### Parâmetros
- `str1`: Ponteiro para a primeira string a ser comparada.
- `str2`: Ponteiro para a segunda string a ser comparada.

### Retorno
A função `strcmp` retorna um inteiro que pode assumir os seguintes valores:
- Um número negativo se `str1` for lexicograficamente menor que `str2`.
- Zero (0) se `str1` for igual a `str2`.
- Um número positivo se `str1` for maior que `str2`.

### Comportamento
A comparação é realizada caractere a caractere, utilizando a tabela ASCII para determinar a ordem. A comparação é sensível a maiúsculas e minúsculas.

## Exemplos

### Exemplo 1: Comparação de Strings Iguais
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "hello";
    char str2[] = "hello";
    
    int result = strcmp(str1, str2);
    if (result == 0) {
        printf("As strings são iguais.\n");
    }
    return 0;
}
```

### Exemplo 2: Comparação de Strings Diferentes
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "apple";
    char str2[] = "banana";
    
    int result = strcmp(str1, str2);
    if (result < 0) {
        printf("'%s' é menor que '%s'.\n", str1, str2);
    }
    return 0;
}
```

### Exemplo 3: Sensibilidade a Maiúsculas
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "hello";
    
    int result = strcmp(str1, str2);
    if (result < 0) {
        printf("'%s' é menor que '%s'.\n", str1, str2);
    }
    return 0;
}
```

## Explicação
Um dos principais cuidados ao usar `strcmp` é garantir que as strings sejam terminadas corretamente com o caractere nulo (`'\0'`). Caso contrário, a comparação pode resultar em comportamento indefinido. Além disso, é importante lembrar que a comparação é sensível a maiúsculas e minúsculas, o que pode impactar o resultado se não for considerado.

Evite usar `strcmp` em strings que podem ser `NULL`, pois isso pode resultar em erros de segmentação. Para evitar isso, sempre valide as strings antes de compará-las.

## Resumo em Uma Linha
A função `strcmp` em C compara duas strings e retorna um valor que indica sua ordem lexicográfica.