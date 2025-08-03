<!--
Meta Description: # __TIME__: Macro de Tempo em C ## Sinopse A macro `__TIME__` em C fornece a hora atual da compilação do código-fonte, permitindo que os programadores...
Meta Keywords: macro, __time__, que, compilação, programa
-->

# __TIME__: Macro de Tempo em C

## Sinopse
A macro `__TIME__` em C fornece a hora atual da compilação do código-fonte, permitindo que os programadores incluam informações temporais em seus programas.

## Documentação
A macro `__TIME__` é uma constante pré-definida que retorna uma string representando o horário em que o código foi compilado. O formato da string é "HH:MM:SS", onde "HH" representa as horas em formato de 24 horas, "MM" representa os minutos e "SS" representa os segundos.

### Uso
Para usar a macro `__TIME__`, basta referenciá-la em qualquer parte do seu código C, geralmente em uma declaração de string. Esta macro é útil para incluir a data e a hora da compilação em mensagens de log ou para exibir informações sobre a versão de um programa.

### Detalhes
- O valor de `__TIME__` é definido pelo compilador no momento da compilação e não pode ser modificado em tempo de execução.
- Esta macro é frequentemente utilizada em conjunto com a macro `__DATE__`, que fornece a data da compilação no formato "Mmm dd yyyy".

## Exemplos

### Exemplo Básico
```c
#include <stdio.h>

int main() {
    printf("Este programa foi compilado em: %s\n", __TIME__);
    return 0;
}
```

### Exemplo com Data
```c
#include <stdio.h>

int main() {
    printf("Compilado em: %s, às %s\n", __DATE__, __TIME__);
    return 0;
}
```

## Explicação
É importante notar que a macro `__TIME__` não muda durante a execução do programa; ela reflete apenas o momento em que o código foi compilado. Um erro comum é tentar usar `__TIME__` para rastrear o tempo de execução de um programa, o que não é o propósito desta macro. Além disso, essa macro pode ser afetada por diferentes configurações de compilação e ambientes de desenvolvimento, portanto, sua saída pode variar dependendo do sistema.

## Resumo em Uma Linha
A macro `__TIME__` em C fornece a hora da compilação do programa, facilitando a inclusão de informações temporais.