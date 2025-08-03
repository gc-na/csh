<!--
Meta Description: # sprintf: Formatação de Strings em C ## Sinopse A função `sprintf` em C é utilizada para formatar e armazenar strings em variáveis, permitindo a conv...
Meta Keywords: buffer, sprintf, string, para, função
-->

# sprintf: Formatação de Strings em C

## Sinopse
A função `sprintf` em C é utilizada para formatar e armazenar strings em variáveis, permitindo a conversão de dados em uma representação textual conforme o formato especificado.

## Documentação

### Propósito
A função `sprintf` faz parte da biblioteca padrão do C e é utilizada para produzir uma string formatada. Ela é similar à função `printf`, mas em vez de exibir a saída na tela, armazena-a em um buffer fornecido pelo usuário.

### Uso
A sintaxe da função `sprintf` é a seguinte:

```c
int sprintf(char *str, const char *format, ...);
```

- **str**: Um ponteiro para a string onde a saída formatada será armazenada.
- **format**: Uma string que especifica como os argumentos seguintes devem ser formatados.
- **...**: Uma lista de argumentos que serão formatados de acordo com a string de formato.

### Detalhes
- A função retorna o número de caracteres que foram escritos na string, excluindo o caractere nulo terminador.
- É importante que o buffer (`str`) tenha espaço suficiente para armazenar a string resultante, pois não há verificação de estouro de buffer.
- A string de formato pode incluir especificadores como `%d` para inteiros, `%f` para floats, `%s` para strings, entre outros.

## Exemplos

### Exemplo Básico
```c
#include <stdio.h>

int main() {
    char buffer[100];
    int valor = 42;
    float pi = 3.14;

    sprintf(buffer, "O valor é %d e pi é %.2f", valor, pi);
    printf("%s\n", buffer); // Saída: O valor é 42 e pi é 3.14

    return 0;
}
```

### Exemplo com Strings
```c
#include <stdio.h>

int main() {
    char buffer[100];
    char nome[] = "João";

    sprintf(buffer, "Olá, %s!", nome);
    printf("%s\n", buffer); // Saída: Olá, João!

    return 0;
}
```

## Explicação
Ao usar `sprintf`, é crucial ter cuidado com o tamanho do buffer. Caso a string formatada exceda o espaço alocado, pode ocorrer um estouro de buffer, resultando em comportamento indefinido ou falhas no programa. Para evitar isso, considere usar `snprintf`, que permite especificar o tamanho máximo do buffer.

Além disso, os especificadores de formato devem corresponder ao tipo dos argumentos fornecidos. Um tipo incorreto pode levar a erros ou saídas inesperadas.

## Resumo em Uma Linha
A função `sprintf` em C formata dados e os armazena em uma string com base em um formato especificado, permitindo a manipulação eficiente de texto.