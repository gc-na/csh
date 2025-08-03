<!--
Meta Description: # Função isupper em C: Verifique se um Caractere é uma Letra Maiúscula ## Sinopse A função `isupper` em C é utilizada para determinar se um caractere ...
Meta Keywords: letra, maiúscula, isupper, uma, não
-->

# Função isupper em C: Verifique se um Caractere é uma Letra Maiúscula

## Sinopse
A função `isupper` em C é utilizada para determinar se um caractere específico é uma letra maiúscula do alfabeto. Essa função é parte da biblioteca padrão `<ctype.h>` e é frequentemente utilizada em programas que necessitam de validação de caracteres.

## Documentação
A função `isupper` tem como objetivo verificar se o caractere fornecido como argumento é uma letra maiúscula (A-Z). Ela retorna um valor diferente de zero (verdadeiro) se o caractere for uma letra maiúscula e zero (falso) caso contrário.

### Prototipagem
```c
#include <ctype.h>

int isupper(int c);
```

### Parâmetros
- `c`: Um inteiro que representa o caractere a ser testado. Geralmente, esse valor é fornecido na forma de um caractere, mas é tratado como um inteiro.

### Retorno
- Retorna um valor diferente de zero (verdadeiro) se `c` for uma letra maiúscula.
- Retorna zero (falso) se `c` não for uma letra maiúscula.

### Requisitos
- Para utilizar a função `isupper`, é necessário incluir a biblioteca `<ctype.h>` no seu arquivo de código.

## Exemplos
### Exemplo Básico
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char letra = 'G';

    if (isupper(letra)) {
        printf("%c é uma letra maiúscula.\n", letra);
    } else {
        printf("%c não é uma letra maiúscula.\n", letra);
    }

    return 0;
}
```
**Saída:**
```
G é uma letra maiúscula.
```

### Exemplo com Caracteres Não Alfabéticos
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char letra = 'g';
    char simbolo = '#';

    printf("%c: %s\n", letra, isupper(letra) ? "Maiúscula" : "Não Maiúscula");
    printf("%c: %s\n", simbolo, isupper(simbolo) ? "Maiúscula" : "Não Maiúscula");

    return 0;
}
```
**Saída:**
```
g: Não Maiúscula
#: Não Maiúscula
```

## Explicação
Um erro comum ao usar a função `isupper` é passar um caractere que não está dentro do intervalo esperado (A-Z). A função espera um valor inteiro, e caracteres fora desse intervalo podem levar a resultados inesperados. Além disso, a função `isupper` não verifica letras acentuadas ou caracteres especiais, portanto, é importante garantir que o argumento fornecido seja um caractere alfabético padrão.

Outro ponto a ser observado é que, como a função `isupper` faz parte da biblioteca de manipulação de caracteres, ela pode não funcionar corretamente se os dados de entrada não estiverem em um formato apropriado.

## Resumo em Uma Linha
A função `isupper` em C é usada para verificar se um caractere é uma letra maiúscula do alfabeto.