<!--
Meta Description: # O que é a palavra-chave "auto" na Linguagem C? ## Sinopse A palavra-chave `auto` em C é utilizada para declarar variáveis com armazenamento automáti...
Meta Keywords: auto, que, variáveis, escopo, palavra
-->

# O que é a palavra-chave "auto" na Linguagem C?

## Sinopse
A palavra-chave `auto` em C é utilizada para declarar variáveis com armazenamento automático, que são alocadas na pilha e têm escopo local. Com a introdução do C11, o uso de `auto` foi ampliado, permitindo a dedução de tipos.

## Documentação
A palavra-chave `auto` em C é uma especificação de armazenamento que indica que uma variável é automaticamente alocada e liberada pelo sistema. As variáveis declaradas como `auto` têm escopo local e são destruídas assim que saem do bloco onde foram definidas.

### Propósito
O principal propósito do `auto` é facilitar a gestão de memória e garantir que as variáveis de escopo local sejam geridas automaticamente.

### Uso
A declaração de uma variável como `auto` pode ser feita da seguinte forma:

```c
auto tipo nome_variavel;
```

No entanto, é importante notar que em C, a palavra-chave `auto` é implícita em variáveis locais, ou seja, você pode simplesmente declarar uma variável sem especificar `auto` e ela terá o mesmo comportamento.

### Detalhes
- **Escopo**: Variáveis `auto` possuem escopo local ao bloco onde são definidas.
- **Duração**: Elas são destruídas quando o bloco é finalizado, liberando automaticamente a memória alocada.
- **C11**: Com a introdução do C11, `auto` também pode ser usado para deduzir o tipo de uma variável automaticamente, similar ao que acontece em C++.

## Exemplos
### Exemplo 1: Declaração de variável automática
```c
#include <stdio.h>

int main() {
    auto int x = 10; // Declaração explícita (pode ser omitida)
    printf("%d\n", x);
    return 0;
}
```

### Exemplo 2: Uso do `auto` para deduzir tipo (C11)
```c
#include <stdio.h>

int main() {
    auto int y = 20; // Tipo implícito, igual a: int y = 20;
    printf("%d\n", y);
    return 0;
}
```

## Explicação
Embora a palavra-chave `auto` possa ser utilizada, muitas vezes ela é desnecessária em C, visto que variáveis locais são automaticamente tratadas como `auto`. Um ponto importante a se considerar é que, em ambientes de programação que adotam o C11, o uso de `auto` para dedução de tipos pode levar a confusão, especialmente para programadores que vêm do C++.

### Armadilhas comuns
- **Confusão com C++**: Programadores que conhecem C++ podem interpretar `auto` de maneira diferente, devido à sua capacidade de deduzir tipos em C++.
- **Escopo e Duração**: É crucial entender que variáveis `auto` não persistem fora do bloco onde foram definidas, o que pode levar a comportamentos inesperados se não for bem compreendido.

## Resumo em uma linha
A palavra-chave `auto` em C é usada para declarar variáveis de armazenamento automático com escopo local, sendo implícita em variáveis locais.