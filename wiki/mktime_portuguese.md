<!--
Meta Description: # Função mktime em C: Manipulação de Data e Hora ## Sinopse A função `mktime` em C é utilizada para converter uma estrutura de tempo (`struct tm`) em ...
Meta Keywords: timeinfo, mktime, função, hora, struct
-->

# Função mktime em C: Manipulação de Data e Hora

## Sinopse
A função `mktime` em C é utilizada para converter uma estrutura de tempo (`struct tm`) em um valor de tempo em segundos desde a época Unix (1 de janeiro de 1970, 00:00:00 UTC). Essa funcionalidade é fundamental para programadores que necessitam manipular e formatar datas e horas em suas aplicações.

## Documentação
A função `mktime` é definida na biblioteca `<time.h>` e sua assinatura é a seguinte:

```c
time_t mktime(struct tm *tm);
```

### Propósito
O principal objetivo da função `mktime` é transformar uma estrutura que contém componentes de data e hora (como ano, mês, dia, hora, minuto e segundo) em um valor do tipo `time_t`, que representa um número de segundos desde a época Unix.

### Uso
- **Parâmetro**: Um ponteiro para uma estrutura `struct tm` que deve ser preenchida com os componentes da data e hora a serem convertidos.
- **Retorno**: A função retorna um valor do tipo `time_t`, que é o número de segundos desde 1 de janeiro de 1970. Se a conversão falhar, o retorno é -1.

### Detalhes
A estrutura `tm` deve ser preenchida corretamente, levando em consideração os seguintes campos:
- `tm_year`: Ano - 1900 (por exemplo, para 2023, deve-se usar 123).
- `tm_mon`: Mês (0-11, onde 0 é janeiro e 11 é dezembro).
- `tm_mday`: Dia do mês (1-31).
- `tm_hour`: Hora (0-23).
- `tm_min`: Minuto (0-59).
- `tm_sec`: Segundo (0-60, considerando segundos bissextos).

## Exemplos

### Exemplo Básico
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo = {0};
    timeinfo.tm_year = 123;  // 2023
    timeinfo.tm_mon = 0;     // Janeiro
    timeinfo.tm_mday = 1;    // 1º dia
    timeinfo.tm_hour = 0;
    timeinfo.tm_min = 0;
    timeinfo.tm_sec = 0;

    time_t timestamp = mktime(&timeinfo);
    printf("Timestamp: %ld\n", timestamp);
    return 0;
}
```

### Exemplo de Conversão de Hora
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo = {0};
    timeinfo.tm_year = 122;  // 2022
    timeinfo.tm_mon = 11;    // Dezembro
    timeinfo.tm_mday = 25;   // 25º dia
    timeinfo.tm_hour = 10;   // 10 horas
    timeinfo.tm_min = 30;     // 30 minutos
    timeinfo.tm_sec = 0;

    time_t timestamp = mktime(&timeinfo);
    printf("Timestamp: %ld\n", timestamp);
    return 0;
}
```

## Explicação
Alguns pontos importantes a serem considerados ao usar `mktime`:

- **Ano Bissexto**: A função automaticamente trata anos bissextos, mas é importante preencher corretamente o campo `tm_year`.
- **Faixa de Valores**: Se os valores fornecidos para `tm_mon` ou `tm_mday` estiverem fora do intervalo esperado, `mktime` pode retornar resultados inesperados ou -1.
- **Fuso Horário**: O resultado da função `mktime` pode ser afetado pelo fuso horário do sistema em que o código está sendo executado. A função considera as configurações locais do sistema.

## Resumo em Uma Linha
A função `mktime` em C converte uma estrutura de data e hora (`struct tm`) em um valor de tempo Unix (`time_t`), facilitando a manipulação de datas em aplicações.