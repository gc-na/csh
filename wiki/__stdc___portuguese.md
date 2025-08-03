<!--
Meta Description: # __STDC__: Definição e Importância na Linguagem C ## Sinopse O `__STDC__` é um macro predefinido na linguagem de programação C que indica que o compi...
Meta Keywords: __stdc__, que, compilador, padrão, com
-->

# __STDC__: Definição e Importância na Linguagem C

## Sinopse
O `__STDC__` é um macro predefinido na linguagem de programação C que indica que o compilador está em conformidade com o padrão ANSI C (ou ISO C). Este macro é essencial para garantir a portabilidade e a compatibilidade do código entre diferentes compiladores.

## Documentação
### Propósito
O macro `__STDC__` serve como um indicador para desenvolvedores e compiladores que o código é compilado de acordo com as normas do padrão ANSI C. Quando o compilador define `__STDC__`, ele garante que as funcionalidades e comportamentos da linguagem estão alinhados com as especificações oficiais.

### Uso
O `__STDC__` pode ser utilizado em diretivas de pré-processador para condicionalmente incluir ou excluir partes do código, dependendo da conformidade do compilador com o padrão C. O valor padrão de `__STDC__` é `1`, o que significa que o compilador está em conformidade.

```c
#ifdef __STDC__
#include <stdio.h>
#define printf std::printf
#else
#include <conio.h>
#define printf cprintf
#endif
```

### Detalhes
- Se um compilador não segue o padrão ANSI, `__STDC__` não será definido.
- Pode ser utilizado em conjunto com outros macros, como `__STDC_VERSION__`, que fornece informações sobre a versão do padrão C suportada.

## Exemplos
### Exemplo 1: Verificando a conformidade do compilador
```c
#include <stdio.h>

int main() {
    #ifdef __STDC__
        printf("Este compilador é compatível com o padrão ANSI C.\n");
    #else
        printf("Este compilador NÃO é compatível com o padrão ANSI C.\n");
    #endif
    return 0;
}
```

### Exemplo 2: Usando `__STDC_VERSION__`
```c
#include <stdio.h>

int main() {
    #if __STDC_VERSION__ >= 199901L
        printf("Este compilador suporta C99.\n");
    #else
        printf("Este compilador não suporta C99.\n");
    #endif
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Portabilidade**: A ausência do `__STDC__` não significa que o código não funcione, mas pode levar a comportamentos inesperados em diferentes compiladores.
- **Ambientes Não Padrão**: Em ambientes que não seguem o padrão ANSI, o código que depende de `__STDC__` pode falhar ao compilar.

### Notas Adicionais
- É uma boa prática usar `__STDC__` para garantir que seu código seja escrito de forma a maximizar a compatibilidade entre diferentes plataformas de compiladores.
- O uso de `__STDC_VERSION__` é recomendado para verificar a versão do padrão que o compilador suporta.

## Resumo em uma Linha
O `__STDC__` é um macro que indica a conformidade do compilador com o padrão ANSI C, essencial para a portabilidade e compatibilidade do código.