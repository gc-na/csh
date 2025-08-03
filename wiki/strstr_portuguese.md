<!--
Meta Description: # strstr: Função de Busca de Substring em C ## Sinopse A função `strstr` em C é utilizada para localizar a primeira ocorrência de uma substring em uma...
Meta Keywords: substring, strstr, string, char, função
-->

# strstr: Função de Busca de Substring em C

## Sinopse
A função `strstr` em C é utilizada para localizar a primeira ocorrência de uma substring em uma string, facilitando a manipulação de textos em programas.

## Documentação
A função `strstr` faz parte da biblioteca padrão de C, definida em `<string.h>`. Seu propósito é encontrar a primeira ocorrência de uma sequência de caracteres (substring) dentro de outra sequência (string).

### Sintaxe
```c
char *strstr(const char *haystack, const char *needle);
```

### Parâmetros
- `haystack`: A string na qual será feita a busca.
- `needle`: A substring que deve ser encontrada.

### Retorno
A função retorna um ponteiro para a primeira ocorrência da substring (`needle`) na string (`haystack`). Se a substring não for encontrada, o retorno será `NULL`.

### Uso
Para usar a função `strstr`, certifique-se de incluir a biblioteca `<string.h>` no seu programa. A função é sensível a maiúsculas e minúsculas, ou seja, "Teste" e "teste" serão considerados diferentes.

## Exemplos
### Exemplo 1: Busca Simples
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *texto = "Aprendendo C é divertido!";
    const char *subtexto = "C";
    
    char *resultado = strstr(texto, subtexto);
    
    if (resultado) {
        printf("Substring encontrada: %s\n", resultado);
    } else {
        printf("Substring não encontrada.\n");
    }
    
    return 0;
}
```

### Exemplo 2: Substring Não Encontrada
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *texto = "Programação em C";
    const char *subtexto = "Python";
    
    char *resultado = strstr(texto, subtexto);
    
    if (resultado) {
        printf("Substring encontrada: %s\n", resultado);
    } else {
        printf("Substring não encontrada.\n");
    }
    
    return 0;
}
```

## Explicação
Um dos erros comuns ao usar `strstr` é não verificar se o retorno é `NULL`, o que pode levar a acessos inválidos de memória e potencialmente causar falhas no programa. Além disso, é importante notar que se `needle` for uma string vazia (`""`), a função sempre retornará o ponteiro para o início de `haystack`.

Outro ponto a ser considerado é a sensibilidade de `strstr` em relação a maiúsculas e minúsculas. Para buscas que não diferenciam entre maiúsculas e minúsculas, o programador deve considerar implementar uma lógica alternativa, como converter ambas as strings para minúsculas antes da busca.

## Resumo em Uma Linha
A função `strstr` em C permite localizar a primeira ocorrência de uma substring dentro de uma string, sendo sensível a letras maiúsculas e minúsculas.