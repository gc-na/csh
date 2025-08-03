<!--
Meta Description: # fprintf em C: Formatação e Escrita de Dados em Arquivos ## Sinopse A função `fprintf` em C é utilizada para escrever dados formatados em arquivos. E...
Meta Keywords: arquivo, fprintf, arquivos, dados, função
-->

# fprintf em C: Formatação e Escrita de Dados em Arquivos

## Sinopse
A função `fprintf` em C é utilizada para escrever dados formatados em arquivos. Ela permite a saída de texto e a formatação de variáveis de forma controlada, semelhante à função `printf`, mas direcionada a um fluxo de arquivo.

## Documentação

### Propósito
A função `fprintf` faz parte da biblioteca padrão de C, definida em `<stdio.h>`, e serve para gravar dados em arquivos com formatação específica. Essa função é especialmente útil quando é necessário escrever informações formatadas em arquivos de texto, como logs ou relatórios.

### Uso
A sintaxe básica da função `fprintf` é a seguinte:

```c
int fprintf(FILE *stream, const char *format, ...);
```

- **stream**: Um ponteiro para um objeto `FILE` que representa o arquivo onde os dados serão escritos.
- **format**: Uma string de formato que especifica como os dados a seguir devem ser formatados.
- **...**: Uma lista de argumentos que serão formatados de acordo com a string de formato.

### Detalhes
- Retorno: A função retorna o número de caracteres escritos ou um valor negativo em caso de erro.
- Formatação: Os especificadores de formato suportados incluem `%d` (inteiro), `%f` (ponto flutuante), `%s` (string), e muitos outros.
- Arquivos: Para usar `fprintf`, o arquivo deve ser aberto previamente com as funções `fopen`, `freopen` ou similares.

## Exemplos

### Exemplo 1: Escrevendo um Número Inteiro em um Arquivo
```c
#include <stdio.h>

int main() {
    FILE *arquivo = fopen("exemplo.txt", "w");
    if (arquivo != NULL) {
        int numero = 42;
        fprintf(arquivo, "O número é: %d\n", numero);
        fclose(arquivo);
    }
    return 0;
}
```

### Exemplo 2: Escrevendo Texto e Ponto Flutuante
```c
#include <stdio.h>

int main() {
    FILE *arquivo = fopen("exemplo.txt", "w");
    if (arquivo != NULL) {
        float valor = 3.14;
        fprintf(arquivo, "A constante PI é aproximadamente: %.2f\n", valor);
        fclose(arquivo);
    }
    return 0;
}
```

## Explicação

### Armadilhas Comuns
- **Arquivo Não Aberto**: Tentar usar `fprintf` em um arquivo que não foi aberto corretamente resultará em comportamento indefinido. Sempre verifique se o ponteiro do arquivo é `NULL` após `fopen`.
- **Especificadores de Formato Incorretos**: Usar o especificador de formato errado pode causar erros de execução ou resultados inesperados. Por exemplo, passar um inteiro onde se espera um ponto flutuante pode levar a falhas.

### Notas Adicionais
- Sempre feche o arquivo após terminar a escrita usando `fclose` para garantir que todos os dados sejam gravados adequadamente.
- O uso de `fprintf` é restrito a arquivos abertos para escrita. Para ler de arquivos, utilize `fscanf` ou funções semelhantes.

## Resumo em Uma Linha
A função `fprintf` em C permite a escrita de dados formatados em arquivos, facilitando a criação de saídas controladas em arquivos de texto.