<!--
Meta Description: # scanf: Como Usar a Função de Leitura de Dados em C ## Sinopse A função `scanf` em C é uma das principais ferramentas para a leitura de entrada do us...
Meta Keywords: scanf, para, leitura, dados, uma
-->

# scanf: Como Usar a Função de Leitura de Dados em C

## Sinopse
A função `scanf` em C é uma das principais ferramentas para a leitura de entrada do usuário, permitindo que dados sejam capturados de forma formatada.

## Documentação
### Propósito
A função `scanf` é utilizada para ler dados formatados da entrada padrão (normalmente o teclado) e armazená-los em variáveis. É fundamental em programas que requerem interação do usuário.

### Uso
A sintaxe básica de `scanf` é a seguinte:

```c
int scanf(const char *format, ...);
```

- **format**: Uma string que especifica o formato dos dados a serem lidos. Utiliza especificadores como `%d`, `%f`, `%s`, etc.
- **...**: Uma lista de ponteiros para as variáveis onde os dados lidos serão armazenados.

### Detalhes
- A função `scanf` retorna o número de itens lidos com sucesso, ou `EOF` se ocorrer um erro ou o final do arquivo for alcançado.
- É importante passar o endereço das variáveis (usando o operador `&` para tipos primitivos) para que `scanf` possa armazenar os valores lidos corretamente.

## Exemplos

### Exemplo 1: Leitura de um Inteiro

```c
#include <stdio.h>

int main() {
    int num;
    printf("Digite um número inteiro: ");
    scanf("%d", &num);
    printf("Você digitou: %d\n", num);
    return 0;
}
```

### Exemplo 2: Leitura de um Float e uma String

```c
#include <stdio.h>

int main() {
    float num;
    char str[50];
    printf("Digite um número decimal e uma palavra: ");
    scanf("%f %s", &num, str);
    printf("Número: %.2f, Palavra: %s\n", num, str);
    return 0;
}
```

### Exemplo 3: Leitura de Múltiplos Valores

```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Digite dois números inteiros: ");
    scanf("%d %d", &a, &b);
    printf("Soma: %d\n", a + b);
    return 0;
}
```

## Explicação
Ao usar `scanf`, é comum enfrentar alguns problemas, como:

- **Buffer Overflow**: Ao ler strings, é necessário garantir que o tamanho do array seja suficiente para evitar estouros. Por exemplo, ao usar `%s`, o tamanho do buffer deve ser especificado (ex: `%49s` para um buffer de 50).
- **Erro de Leitura**: Se o usuário digitar um valor que não corresponde ao formato esperado, `scanf` pode falhar. Por exemplo, tentar ler um inteiro ao invés de um float.
- **Espaços em Branco**: O `scanf` ignora espaços em branco automaticamente, mas é importante estar ciente disso ao ler strings.

## Resumo em Uma Linha
A função `scanf` em C é utilizada para ler dados formatados da entrada padrão, permitindo interação com o usuário de maneira eficiente.