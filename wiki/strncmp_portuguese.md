<!--
Meta Description: # strncmp: Comparação Segura de Strings em C ## Sinopse A função `strncmp` é utilizada em C para comparar até um número específico de caracteres entre...
Meta Keywords: strings, strncmp, que, uma, comparação
-->

# strncmp: Comparação Segura de Strings em C

## Sinopse
A função `strncmp` é utilizada em C para comparar até um número específico de caracteres entre duas strings, oferecendo uma maneira segura e eficiente de verificar a igualdade parcial de strings.

## Documentação

### Propósito
A função `strncmp` é uma parte da biblioteca padrão do C, definida no cabeçalho `<string.h>`. Ela serve para comparar as strings `s1` e `s2` até um máximo de `n` caracteres, permitindo que o programador verifique se as duas strings são iguais ou se uma é maior que a outra.

### Uso
A assinatura da função é:

```c
int strncmp(const char *s1, const char *s2, size_t n);
```

#### Parâmetros:
- `s1`: ponteiro para a primeira string a ser comparada.
- `s2`: ponteiro para a segunda string a ser comparada.
- `n`: número máximo de caracteres a serem comparados.

#### Retorno:
A função retorna um inteiro:
- Menor que 0 se `s1` for menor que `s2`.
- Zero se `s1` for igual a `s2`.
- Maior que 0 se `s1` for maior que `s2`.

## Exemplos

### Exemplo 1: Comparação Básica
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello";
    const char *str2 = "Hello, World!";
    
    int result = strncmp(str1, str2, 5);
    if (result == 0) {
        printf("As primeiras 5 letras são iguais.\n");
    } else {
        printf("As primeiras 5 letras são diferentes.\n");
    }
    return 0;
}
```

### Exemplo 2: Comparação com Diferentes Comprimentos
```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str1 = "Hello";
    const char *str2 = "Hello";
    
    int result = strncmp(str1, str2, 10);
    if (result == 0) {
        printf("As strings são iguais até 10 caracteres.\n");
    }
    return 0;
}
```

## Explicação
Embora `strncmp` seja uma função útil, existem algumas nuances que os programadores devem estar cientes:

- **Comparação até n caracteres**: Se `n` for menor que o comprimento das strings, a comparação será feita apenas até o limite especificado. Isso pode levar a resultados inesperados se as strings forem muito diferentes em comprimento.
- **Strings não terminadas em nulo**: Se uma das strings não estiver terminada em nulo antes de atingir o limite `n`, o comportamento pode ser indefinido.
- **Case Sensitivity**: `strncmp` é sensível a maiúsculas e minúsculas. Para uma comparação que não diferencia maiúsculas de minúsculas, considere usar funções como `strncasecmp`.

## Resumo em Uma Linha
A função `strncmp` é uma ferramenta eficiente para comparar até n caracteres de duas strings, permitindo validações seguras de igualdade em C.