<!--
Meta Description: # __LINE__: Macro de Pré-processador em C ## Sinopse O macro `__LINE__` em C é uma constante pré-definida que fornece o número da linha atual no códig...
Meta Keywords: __line__, linha, número, macro, que
-->

# __LINE__: Macro de Pré-processador em C

## Sinopse
O macro `__LINE__` em C é uma constante pré-definida que fornece o número da linha atual no código fonte durante a compilação.

## Documentação
O `__LINE__` é um dos vários macros de pré-processador disponíveis na linguagem C. Seu principal propósito é facilitar o rastreamento de erros e a depuração, possibilitando que programadores obtenham o número da linha onde a macro foi utilizada. Isso pode ser extremamente útil em mensagens de log, relatórios de erro ou quando se está desenvolvendo funções de depuração.

### Uso
O `__LINE__` é utilizado diretamente no código-fonte e é substituído pelo número da linha em que aparece quando o código é compilado. Por exemplo:

```c
#include <stdio.h>

int main() {
    printf("Esta mensagem está na linha: %d\n", __LINE__);
    return 0;
}
```

Neste exemplo, a saída do programa indicará o número da linha onde `__LINE__` foi chamado.

### Detalhes
- O valor de `__LINE__` é um inteiro que representa o número da linha atual, começando em 1.
- Ele é especialmente útil em macros e funções de depuração que precisam fornecer informações contextuais sobre onde um erro ocorreu.
- O `__LINE__` é atualizado automaticamente pelo compilador em cada nova linha de código no arquivo fonte.

## Exemplos
### Exemplo Básico
```c
#include <stdio.h>

int main() {
    printf("O número da linha atual é: %d\n", __LINE__); // Exibe o número da linha
    return 0;
}
```

### Uso em Macros
```c
#include <stdio.h>

#define LOG_ERROR(msg) \
    printf("Erro na linha %d: %s\n", __LINE__, msg)

int main() {
    LOG_ERROR("Falha ao abrir o arquivo.");
    return 0;
}
```

## Explicação
Embora o uso de `__LINE__` seja simples, alguns pontos devem ser considerados:

1. **Contexto de Uso**: O valor de `__LINE__` é específico para o arquivo em que está sendo chamado. Se você usar em múltiplos arquivos, cada um terá seu próprio número de linha.
   
2. **Macros Complexas**: Ao usar `__LINE__` dentro de macros, o número da linha refletirá a linha onde a macro foi expandida, não onde a macro foi definida. Isso pode causar confusão se não for compreendido corretamente.

3. **Compiladores Diferentes**: Embora a maioria dos compiladores C suportem `__LINE__`, é sempre bom verificar a documentação do compilador específico para garantir conformidade.

## Resumo em Uma Linha
O macro `__LINE__` em C fornece o número da linha atual no arquivo fonte, sendo útil para depuração e rastreamento de erros.