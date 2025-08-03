<!--
Meta Description: # fwrite em C: Como Usar para Gravar Dados em Arquivos ## Sinopse A função `fwrite` em C é utilizada para gravar blocos de dados em um arquivo, permit...
Meta Keywords: file, fwrite, para, dados, função
-->

# fwrite em C: Como Usar para Gravar Dados em Arquivos

## Sinopse
A função `fwrite` em C é utilizada para gravar blocos de dados em um arquivo, permitindo ao programador manipular arquivos binários de maneira eficiente.

## Documentação

### Propósito
A função `fwrite` permite escrever dados de um buffer para um arquivo, ideal para armazenar estruturas complexas ou grandes quantidades de dados de forma rápida e eficiente.

### Uso
A sintaxe básica da função `fwrite` é a seguinte:

```c
size_t fwrite(const void *ptr, size_t size, size_t count, FILE *stream);
```

#### Parâmetros
- `ptr`: Um ponteiro para o bloco de memória que contém os dados a serem escritos.
- `size`: O tamanho, em bytes, de cada item a ser escrito.
- `count`: O número de itens a serem escritos.
- `stream`: Um ponteiro para o arquivo onde os dados serão gravados.

#### Retorno
A função retorna o número de itens efetivamente escritos. Se este número for menor que `count`, pode indicar um erro ou que o final do arquivo foi alcançado.

### Detalhes
- Antes de usar `fwrite`, o arquivo deve ser aberto em modo de escrita (`"w"`, `"wb"`, `"a"`, ou `"ab"`).
- A função não adiciona automaticamente uma nova linha ou qualquer caractere de terminação; portanto, ao gravar strings, é necessário gerenciar a terminação manualmente.
- Para garantir a integridade dos dados, é recomendável verificar o valor de retorno da função para tratar possíveis erros.

## Exemplos

### Exemplo 1: Gravar um Array de Inteiros
```c
#include <stdio.h>

int main() {
    FILE *file;
    int numbers[] = {1, 2, 3, 4, 5};
    
    file = fopen("numbers.bin", "wb");
    if (file != NULL) {
        fwrite(numbers, sizeof(int), 5, file);
        fclose(file);
    }
    return 0;
}
```

### Exemplo 2: Gravar uma Estrutura
```c
#include <stdio.h>

typedef struct {
    int id;
    char name[20];
} Person;

int main() {
    FILE *file;
    Person p = {1, "Alice"};
    
    file = fopen("person.bin", "wb");
    if (file != NULL) {
        fwrite(&p, sizeof(Person), 1, file);
        fclose(file);
    }
    return 0;
}
```

## Explicação
Ao utilizar `fwrite`, é fundamental estar atento a algumas armadilhas comuns:

- **Abertura de Arquivo**: Sempre verifique se o arquivo foi aberto com sucesso antes de tentar escrever.
- **Erro de Escrita**: O retorno da função deve ser verificado para garantir que todos os dados foram escritos corretamente.
- **Diferenças de Tamanho**: O tamanho dos tipos de dados pode variar entre plataformas; portanto, ao compartilhar arquivos binários entre diferentes sistemas, tenha cuidado com a compatibilidade.
- **Estruturas**: Ao escrever estruturas, considere o alinhamento e padding que podem variar entre diferentes compiladores.

## Resumo em Uma Linha
A função `fwrite` é uma ferramenta poderosa em C para gravar dados de blocos de memória em arquivos binários de forma eficiente e direta.