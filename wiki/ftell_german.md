<!--
Meta Description: # ftell in C: Dateizugriffsposition ermitteln ## Synopsis Die Funktion `ftell` in C wird verwendet, um die aktuelle Position im Dateistream zu ermitte...
Meta Keywords: die, file, ftell, position, ist
-->

# ftell in C: Dateizugriffsposition ermitteln

## Synopsis
Die Funktion `ftell` in C wird verwendet, um die aktuelle Position im Dateistream zu ermitteln. Dies ist besonders nützlich, wenn man mit Dateien arbeitet und die Position für spätere Schreib- oder Leseoperationen speichern möchte.

## Dokumentation
Die Funktion `ftell` gehört zur Standardbibliothek von C und ist in der Header-Datei `<stdio.h>` definiert. Ihre Hauptaufgabe besteht darin, die aktuelle Position des Dateizeigers in einem geöffneten Stream zurückzugeben.

### Zweck
`ftell` gibt die aktuelle Position des Dateizeigers in Bytes vom Anfang der Datei zurück. Dies ermöglicht es Programmierern, die Position in einer Datei zu verfolgen, was für das Dateihandling essentiell ist.

### Verwendung
Die Syntax der Funktion lautet wie folgt:

```c
long ftell(FILE *stream);
```

- **stream**: Ein Zeiger auf das `FILE`-Objekt, das den geöffneten Stream repräsentiert (z.B. eine Datei, die zum Lesen oder Schreiben geöffnet wurde).

### Rückgabewert
- Bei Erfolg gibt `ftell` die aktuelle Position des Dateizeigers in Bytes zurück.
- Bei Fehlern gibt es `-1L` zurück und setzt den Fehlerstatus des Streams.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `ftell`:

### Beispiel 1: Einfache Nutzung von `ftell`
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    
    if (file == NULL) {
        perror("File opening failed");
        return 1;
    }
    
    fseek(file, 0, SEEK_END); // Gehe zum Ende der Datei
    long position = ftell(file); // Aktuelle Position ermitteln
    printf("Die Dateigröße ist: %ld Bytes\n", position);
    
    fclose(file);
    return 0;
}
```

### Beispiel 2: Nutzung nach Leseoperationen
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("example.txt", "r");
    
    if (file == NULL) {
        perror("File opening failed");
        return 1;
    }
    
    char buffer[100];
    fread(buffer, sizeof(char), 50, file); // Lese 50 Bytes
    long position = ftell(file); // Aktuelle Position nach dem Lesen
    printf("Aktuelle Position nach dem Lesen: %ld Bytes\n", position);
    
    fclose(file);
    return 0;
}
```

## Erklärung
Ein häufiges Problem beim Einsatz von `ftell` ist, dass der Rückgabewert `-1L` darauf hinweist, dass ein Fehler aufgetreten ist. Dies kann passieren, wenn der angegebene Stream ungültig ist oder wenn der Stream in einem Zustand ist, der die Positionsabfrage nicht zulässt (z.B. bei einem nicht-unterstützten Streamtyp). 

Zudem sollte beachtet werden, dass `ftell` nicht in allen Fällen zuverlässig ist, insbesondere bei Streams, die nicht in Byte-Orientierung sind (wie z.B. bei bestimmten Netzwerkstreams oder Pipes). 

Ein weiterer Punkt ist, dass der Wert, der von `ftell` zurückgegeben wird, nach einer `fseek`-Operation ungültig werden kann, wenn die Datei nicht ordnungsgemäß verwaltet wird.

## Zusammenfassung in einem Satz
Die Funktion `ftell` in C ermöglicht es Entwicklern, die aktuelle Position im Dateistream zu ermitteln, was eine nützliche Funktion beim Arbeiten mit Dateien ist.