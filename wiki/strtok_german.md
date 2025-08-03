<!--
Meta Description: # strtok: Zeichenfolgen in C aufteilen ## Synopsis Die Funktion `strtok` in C dient dazu, eine Zeichenfolge in Token zu zerlegen, wobei bestimmte Tren...
Meta Keywords: strtok, die, token, zeichenfolge, char
-->

# strtok: Zeichenfolgen in C aufteilen

## Synopsis
Die Funktion `strtok` in C dient dazu, eine Zeichenfolge in Token zu zerlegen, wobei bestimmte Trennzeichen verwendet werden. Sie wird häufig zur Analyse von Eingabedaten verwendet.

## Dokumentation
Die Funktion `strtok` gehört zur C-Standardbibliothek und ist in der Header-Datei `<string.h>` definiert. Sie wird verwendet, um eine Zeichenfolge in kleinere Teile (Token) zu zerlegen, die durch bestimmte Trennzeichen getrennt sind.

### Zweck
`strtok` ermöglicht es Programmierern, eine Zeichenfolge in Token zu zerlegen, die durch benutzerdefinierte Trennzeichen definiert sind. Dies ist besonders nützlich beim Parsen von Daten in Formaten wie CSV oder beim Verarbeiten von Benutzereingaben.

### Nutzung
Die allgemeine Form der Funktion lautet:

```c
char *strtok(char *str, const char *delim);
```

- **Parameter**:
  - `str`: Die zu zerlegende Zeichenfolge. Beim ersten Aufruf wird die gesamte Zeichenfolge übergeben. Bei folgenden Aufrufen sollte `NULL` übergeben werden.
  - `delim`: Eine Zeichenfolge, die die Trennzeichen enthält.

- **Rückgabewert**: 
  - Bei Erfolg gibt `strtok` einen Zeiger auf das nächste Token zurück. Bei Erreichen des Endes der Zeichenfolge oder wenn keine Token mehr vorhanden sind, wird `NULL` zurückgegeben.

### Verwendung
Um `strtok` zu verwenden, müssen Sie sicherstellen, dass die Zeichenfolge, die Sie analysieren möchten, modifiziert werden kann, da `strtok` die Eingabezeilen verändert.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung von `strtok`:

### Beispiel 1: Zerlegen einer einfachen Zeichenfolge
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hallo, wie geht es dir?";
    char *token = strtok(str, " ,?");

    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ,?");
    }
    return 0;
}
```

### Beispiel 2: Verwendung mehrerer Trennzeichen
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "C;C++;Python;Java";
    char *token = strtok(str, ";");

    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, ";");
    }
    return 0;
}
```

## Erklärung
Ein häufiges Problem bei der Verwendung von `strtok` ist die Tatsache, dass die Funktion die ursprüngliche Zeichenfolge modifiziert. Dies kann zu unerwartetem Verhalten führen, wenn Sie die Originalzeichenfolge später benötigen. Außerdem ist `strtok` nicht threadsicher, da sie einen statischen internen Zustand verwendet. Für eine threadsichere Alternative kann `strtok_r` in Betracht gezogen werden.

Ein weiteres häufiges Missverständnis besteht darin, dass `strtok` bei aufeinanderfolgenden Aufrufen mit `NULL` immer das nächste Token zurückgibt. Dies kann dazu führen, dass bei falscher Handhabung ungenutzte Tokens übersprungen werden.

## Einzeilensummary
`strtok` ist eine C-Funktion zum Zerlegen von Zeichenfolgen in Token unter Verwendung definierter Trennzeichen.