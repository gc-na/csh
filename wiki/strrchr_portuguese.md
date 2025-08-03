<!--
Meta Description: # strrchr: Função para Localizar o Último Caractere em uma String em C ## Sinopse A função `strrchr` em C é utilizada para localizar a última ocorrênc...
Meta Keywords: caractere, string, strrchr, função, para
-->

# strrchr: Função para Localizar o Último Caractere em uma String em C

## Sinopse
A função `strrchr` em C é utilizada para localizar a última ocorrência de um caractere específico em uma string. Esta função é parte da biblioteca padrão `<string.h>` e é essencial para manipulação de strings em aplicações C.

## Documentação
### Propósito
A função `strrchr` serve para encontrar a última posição de um caractere dentro de uma string, retornando um ponteiro para essa posição. Se o caractere não for encontrado, a função retorna `NULL`.

### Uso
A sintaxe da função é a seguinte:

```c
char *strrchr(const char *str, int c);
```

#### Parâmetros
- `str`: A string onde a busca será realizada.
- `c`: O caractere que se deseja localizar. Este parâmetro é passado como um valor inteiro, mas é interpretado como um caractere.

#### Retorno
- Retorna um ponteiro para a última ocorrência do caractere `c` na string `str`.
- Retorna `NULL` se o caractere não for encontrado.

### Exemplo de Uso
Aqui estão alguns exemplos simples de como usar a função `strrchr`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *string = "programacao em C";
    char *resultado;

    // Encontrar a última ocorrência de 'a'
    resultado = strrchr(string, 'a');
    if (resultado != NULL) {
        printf("Última ocorrência de 'a': %s\n", resultado);
    } else {
        printf("Caractere não encontrado.\n");
    }

    // Encontrar a última ocorrência de 'x' (não existente)
    resultado = strrchr(string, 'x');
    if (resultado != NULL) {
        printf("Última ocorrência de 'x': %s\n", resultado);
    } else {
        printf("Caractere não encontrado.\n");
    }

    return 0;
}
```

### Explicação
- **Cuidado com o Caractere Nulo**: Lembre-se que o caractere `\0` (nulo) é considerado um caractere válido. Se você usar `strrchr` para procurar por `'\0'`, a função retornará um ponteiro para o final da string.
- **Comparação de Caracteres**: A função diferencia maiúsculas de minúsculas. Por exemplo, `strrchr("Hello", 'h')` retornará `NULL`, pois não há um `h` minúsculo na string.
- **Ponteiro Retornado**: O ponteiro retornado por `strrchr` aponta para a última ocorrência do caractere na string original. Portanto, você pode manipular a string a partir desse ponto.

## Resumo em Uma Linha
A função `strrchr` em C permite localizar a última ocorrência de um caractere em uma string, retornando um ponteiro para essa posição ou `NULL` se não encontrado.