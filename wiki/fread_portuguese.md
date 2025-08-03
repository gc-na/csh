<!--
Meta Description: # fread: Função de Leitura de Arquivos em C ## Sinopse A função `fread` em C é utilizada para ler blocos de dados de um arquivo, permitindo o acesso e...
Meta Keywords: arquivo, file, para, dados, fread
-->

# fread: Função de Leitura de Arquivos em C

## Sinopse
A função `fread` em C é utilizada para ler blocos de dados de um arquivo, permitindo o acesso eficiente a informações armazenadas em formatos binários.

## Documentação
### Propósito
A função `fread` é projetada para ler dados de um fluxo de arquivo (tipicamente um arquivo binário) e armazená-los em um buffer na memória. Ela é especialmente útil para manipulação de grandes volumes de dados, como imagens, vídeos ou registros.

### Uso
A sintaxe básica da função `fread` é a seguinte:

```c
size_t fread(void *ptr, size_t size, size_t count, FILE *stream);
```

#### Parâmetros
- `ptr`: Um ponteiro para um bloco de memória onde os dados lidos serão armazenados.
- `size`: O tamanho, em bytes, de cada item a ser lido.
- `count`: O número de itens a serem lidos.
- `stream`: Um ponteiro para um objeto `FILE` que representa o arquivo de onde os dados serão lidos.

#### Retorno
A função retorna o número total de itens lidos com sucesso, que pode ser menor que `count` se ocorrer um erro ou se o final do arquivo for alcançado.

### Detalhes
- A função `fread` é parte da biblioteca padrão `<stdio.h>`.
- O arquivo deve estar aberto em um modo que permita leitura (por exemplo, "rb" para leitura de arquivos binários).
- É importante verificar o retorno da função para garantir que a leitura foi bem-sucedida.

## Exemplos
### Exemplo 1: Leitura de um arquivo binário

```c
#include <stdio.h>

int main() {
    FILE *file;
    int buffer[10];

    file = fopen("dados.bin", "rb");
    if (file == NULL) {
        perror("Erro ao abrir o arquivo");
        return 1;
    }

    size_t itemsRead = fread(buffer, sizeof(int), 10, file);
    if (itemsRead < 10) {
        if (feof(file)) {
            printf("Fim do arquivo atingido.\n");
        } else {
            perror("Erro ao ler o arquivo");
        }
    }

    fclose(file);
    return 0;
}
```

### Exemplo 2: Leitura de uma estrutura

```c
#include <stdio.h>

typedef struct {
    int id;
    char nome[50];
} Pessoa;

int main() {
    FILE *file;
    Pessoa pessoa;

    file = fopen("pessoas.dat", "rb");
    if (file == NULL) {
        perror("Erro ao abrir o arquivo");
        return 1;
    }

    size_t itemsRead = fread(&pessoa, sizeof(Pessoa), 1, file);
    if (itemsRead == 1) {
        printf("ID: %d, Nome: %s\n", pessoa.id, pessoa.nome);
    } else {
        perror("Erro ao ler o arquivo");
    }

    fclose(file);
    return 0;
}
```

## Explicação
- **Erros Comuns**: Um erro comum ao usar `fread` é não verificar se o ponteiro do arquivo é NULL, o que pode causar falhas. Além disso, é crucial garantir que o buffer seja grande o suficiente para armazenar os dados que se deseja ler.
- **Final do Arquivo**: A função pode retornar menos itens do que solicitado se o final do arquivo for alcançado antes de completar a leitura. É importante usar `feof` para detectar isso.
- **Modo de Abertura**: Sempre abra o arquivo em modo binário ("rb") quando estiver lidando com dados binários para evitar problemas de interpretação de dados em diferentes sistemas operacionais.

## Resumo em uma Linha
A função `fread` em C é utilizada para ler blocos de dados de um arquivo, armazenando-os em um buffer na memória, sendo essencial para manipulação de dados binários.