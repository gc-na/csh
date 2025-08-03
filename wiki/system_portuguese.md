<!--
Meta Description: # Comando system() em C: Executando Comandos do Sistema ## Sinopse O comando `system()` em C permite que um programa execute comandos do sistema opera...
Meta Keywords: system, comando, comandos, sistema, que
-->

# Comando system() em C: Executando Comandos do Sistema

## Sinopse
O comando `system()` em C permite que um programa execute comandos do sistema operacional diretamente a partir do código, utilizando o shell padrão do sistema.

## Documentação
A função `system()` está definida na biblioteca padrão `<stdlib.h>`. Ela é utilizada para invocar comandos do shell, permitindo que programas C interajam com o sistema operacional.

### Propósito
O objetivo da função `system()` é permitir a execução de comandos como se fossem digitados em um terminal, oferecendo uma maneira de realizar tarefas do sistema a partir de um programa C.

### Uso
A sintaxe básica da função `system()` é:

```c
int system(const char *command);
```

- **command**: Uma string que representa o comando a ser executado.
- **Retorno**: A função retorna um valor inteiro. O valor retornado é zero se o comando for executado com sucesso, e um valor diferente de zero se ocorrer algum erro.

### Detalhes
- A execução do comando é feita no contexto do shell padrão do sistema.
- A função `system()` pode bloquear a execução do programa até que o comando seja concluído.
- É importante considerar a segurança ao usar `system()`, especialmente ao passar entradas do usuário como parte do comando, pois isso pode levar a vulnerabilidades de segurança como a injeção de comandos.

## Exemplos

### Exemplo 1: Executando um comando simples
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int status = system("ls -l"); // Executa o comando 'ls -l'
    return status;
}
```

### Exemplo 2: Comando com redirecionamento de saída
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int status = system("echo 'Hello, World!' > hello.txt"); // Cria um arquivo com a mensagem
    return status;
}
```

## Explicação
Embora `system()` seja uma ferramenta poderosa, seu uso deve ser feito com cautela:

1. **Segurança**: Evite usar `system()` com entradas não verificadas. Um usuário mal-intencionado pode injetar comandos prejudiciais.
   
2. **Portabilidade**: Os comandos do sistema podem variar entre diferentes sistemas operacionais. Um comando que funciona em Linux pode não funcionar em Windows.

3. **Bloqueio**: `system()` pode bloquear a execução do programa até que o comando seja concluído, o que pode afetar a performance de aplicações que exigem alta responsividade.

4. **Erro de retorno**: Verifique o valor retornado por `system()` para tratar erros de execução.

## Resumo em uma linha
A função `system()` em C permite a execução de comandos do sistema operacional, mas deve ser usada com cautela devido a questões de segurança e portabilidade.