<!--
Meta Description: # strlen: Função em C para Calcular o Comprimento de Strings ## Sinopse A função `strlen` em C é amplamente utilizada para determinar o comprimento de...
Meta Keywords: string, strlen, comprimento, nulo, função
-->

# strlen: Função em C para Calcular o Comprimento de Strings

## Sinopse
A função `strlen` em C é amplamente utilizada para determinar o comprimento de uma string, ou seja, o número de caracteres contidos em uma sequência de caracteres.

## Documentação
A `strlen` é uma função da biblioteca padrão do C, definida no cabeçalho `<string.h>`. Seu propósito principal é calcular o número de caracteres em uma string, excluindo o caractere nulo (`'\0'`) que indica o final da string.

### Sintaxe
```c
size_t strlen(const char *str);
```

### Parâmetros
- `str`: Um ponteiro para a string cujo comprimento se deseja calcular. A string deve ser terminada com o caractere nulo (`'\0'`).

### Retorno
A função retorna um valor do tipo `size_t`, que representa o número de caracteres na string, sem contar o caractere nulo. Se a string estiver vazia, `strlen` retornará 0.

### Observações
- A função `strlen` não verifica se o ponteiro passado é nulo. Se um ponteiro nulo for passado, o comportamento é indefinido e pode causar um erro de segmentação.
- A complexidade de tempo da função é O(n), onde n é o comprimento da string, uma vez que a função precisa percorrer cada caractere da string até encontrar o caractere nulo.

## Exemplos

### Exemplo 1: Uso Básico da strlen
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *texto = "Hello, World!";
    size_t comprimento = strlen(texto);
    printf("O comprimento da string é: %zu\n", comprimento);
    return 0;
}
```

### Exemplo 2: String Vazia
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *textoVazio = "";
    size_t comprimento = strlen(textoVazio);
    printf("O comprimento da string vazia é: %zu\n", comprimento);
    return 0;
}
```

### Exemplo 3: Uso com Ponteiro Nulo
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *textoNulo = NULL;
    // strlen(textoNulo); // Cuidado: Descomentar esta linha causará comportamento indefinido.
    return 0;
}
```

## Explicação
Um erro comum ao usar `strlen` é passar um ponteiro nulo, o que resultará em um comportamento indefinido. Sempre verifique se a string não é nula antes de chamar `strlen`. Além disso, é importante lembrar que `strlen` conta apenas os caracteres até o caractere nulo. Portanto, uma string com espaço ou caracteres especiais ainda será contada corretamente.

Outro ponto a ser observado é que a função pode não funcionar corretamente se a string não for devidamente terminada com `'\0'`. Isso pode levar a resultados inesperados ou até mesmo a falhas de segurança, como a exploração de buffer overflow.

## Resumo em Uma Linha
A função `strlen` em C é utilizada para calcular o comprimento de uma string, retornando o número de caracteres antes do caractere nulo.