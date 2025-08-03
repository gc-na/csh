<!--
Meta Description: # fscanf: Função de Leitura de Dados em C ## Sinopse A função `fscanf` em C é utilizada para ler dados formatados de um arquivo, permitindo que os pro...
Meta Keywords: file, fscanf, dados, para, função
-->

# fscanf: Função de Leitura de Dados em C

## Sinopse
A função `fscanf` em C é utilizada para ler dados formatados de um arquivo, permitindo que os programadores extraiam informações de forma controlada e estruturada.

## Documentação
### Propósito
A função `fscanf` é parte da biblioteca padrão de entrada e saída (`stdio.h`) do C e serve para ler dados a partir de um arquivo com um formato específico. Ela é semelhante à função `scanf`, mas em vez de ler da entrada padrão (teclado), ela lê de um arquivo previamente aberto.

### Uso
A sintaxe básica da função `fscanf` é:

```c
int fscanf(FILE *stream, const char *format, ...);
```

- **stream**: Um ponteiro para um objeto do tipo `FILE`, que representa o arquivo de onde os dados serão lidos.
- **format**: Uma string que especifica a forma como os dados devem ser interpretados e armazenados.
- **...**: Um ou mais ponteiros para as variáveis onde os dados lidos serão armazenados.

A função retorna o número de itens lidos com sucesso ou `EOF` (End Of File) se ocorrer um erro ou se o final do arquivo for alcançado.

### Detalhes
- É necessário incluir a biblioteca `<stdio.h>` para utilizar a função `fscanf`.
- O formato da string deve ser compatível com os tipos das variáveis passadas.
- Os espaços em branco na string de formato são ignorados, e a leitura é interrompida ao encontrar um caractere que não corresponda ao formato especificado.

## Exemplos
### Exemplo Básico
O exemplo a seguir ilustra como usar `fscanf` para ler um inteiro e um float de um arquivo:

```c
#include <stdio.h>

int main() {
    FILE *file;
    int numero;
    float decimal;

    file = fopen("dados.txt", "r");
    if (file == NULL) {
        printf("Erro ao abrir o arquivo.\n");
        return 1;
    }

    fscanf(file, "%d %f", &numero, &decimal);
    printf("Número: %d, Decimal: %.2f\n", numero, decimal);

    fclose(file);
    return 0;
}
```

### Exemplo com Vários Dados
Neste exemplo, `fscanf` é utilizado para ler múltiplas linhas de dados formatados:

```c
#include <stdio.h>

int main() {
    FILE *file;
    char nome[50];
    int idade;

    file = fopen("pessoas.txt", "r");
    if (file == NULL) {
        printf("Erro ao abrir o arquivo.\n");
        return 1;
    }

    while (fscanf(file, "%s %d", nome, &idade) != EOF) {
        printf("Nome: %s, Idade: %d\n", nome, idade);
    }

    fclose(file);
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Formato Incompatível**: Se o tipo de dado especificado no formato não corresponder ao tipo da variável fornecida, o comportamento pode ser indefinido, resultando em erros ou dados incorretos.
- **Leitura de Dados Inválidos**: `fscanf` pode falhar se a entrada não estiver no formato esperado. É importante verificar o retorno da função para garantir que os dados foram lidos corretamente.
- **Não Ignorar o EOF**: Ao não verificar se `fscanf` retornou `EOF`, o programa pode entrar em um loop infinito.

### Notas Adicionais
- `fscanf` pode ser menos eficiente que outras funções de leitura, especialmente se o formato for complexo.
- Utilize `fgets` seguido de `sscanf` como uma alternativa para maior controle sobre a leitura de linhas inteiras de texto antes da análise.

## Resumo em uma Linha
A função `fscanf` em C é usada para ler dados formatados de um arquivo, permitindo extrair informações de maneira precisa.