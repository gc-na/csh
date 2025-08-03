<!--
Meta Description: # strftime: Formatação de Data e Hora em C ## Sinopse A função `strftime` em C é utilizada para formatar datas e horas em strings de acordo com especi...
Meta Keywords: strftime, string, buffer, uma, data
-->

# strftime: Formatação de Data e Hora em C

## Sinopse
A função `strftime` em C é utilizada para formatar datas e horas em strings de acordo com especificações definidas pelo usuário, permitindo uma apresentação personalizada das informações temporais.

## Documentação
A função `strftime` pertence à biblioteca padrão do C e é definida no cabeçalho `<time.h>`. Seu propósito é converter o tempo representado por uma estrutura `tm` em uma string formatada, utilizando uma variedade de especificadores de formato.

### Assinatura
```c
size_t strftime(char *str, size_t maxsize, const char *format, const struct tm *timeptr);
```

### Parâmetros
- `char *str`: Um ponteiro para a string onde o resultado formatado será armazenado.
- `size_t maxsize`: O tamanho máximo da string `str`.
- `const char *format`: Uma string de formato que contém especificadores de formatação.
- `const struct tm *timeptr`: Um ponteiro para uma estrutura `tm` que contém os componentes de data e hora a serem formatados.

### Retorno
A função retorna o número de caracteres gravados na string `str`, excluindo o caractere nulo de terminação. Se o tamanho fornecido em `maxsize` for insuficiente, `strftime` retornará 0.

### Especificadores de Formato Comuns
- `%Y`: Ano com quatro dígitos.
- `%m`: Mês com dois dígitos (01-12).
- `%d`: Dia do mês com dois dígitos (01-31).
- `%H`: Hora em formato 24 horas (00-23).
- `%M`: Minuto (00-59).
- `%S`: Segundo (00-59).
- `%A`: Nome completo do dia da semana.
- `%B`: Nome completo do mês.

## Exemplos

### Exemplo Básico
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    char buffer[80];

    strftime(buffer, sizeof(buffer), "%Y-%m-%d %H:%M:%S", tm_info);
    printf("Data e Hora formatadas: %s\n", buffer);

    return 0;
}
```
**Saída Exemplo:**
```
Data e Hora formatadas: 2023-10-10 14:20:15
```

### Exemplo com Dia da Semana
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    char buffer[80];

    strftime(buffer, sizeof(buffer), "%A, %d de %B de %Y", tm_info);
    printf("Data formatada: %s\n", buffer);

    return 0;
}
```
**Saída Exemplo:**
```
Data formatada: Terça, 10 de Outubro de 2023
```

## Explicação
Um erro comum ao utilizar `strftime` é não alocar espaço suficiente para a string de saída. Se o tamanho máximo (`maxsize`) informado for menor do que o necessário para armazenar a string formatada, a função retornará 0 e a string não será alterada. 

Outro ponto importante é que os especificadores de formato podem variar de acordo com a implementação da biblioteca padrão do C, então é sempre bom consultar a documentação específica para garantir compatibilidade.

## Resumo em Uma Linha
A função `strftime` permite formatar datas e horas em C de maneira flexível e personalizada, utilizando especificadores de formato.