<!--
Meta Description: # strncpy: Sicheres Kopieren von Strings in C ## Synopsis Die Funktion `strncpy` in C wird verwendet, um eine bestimmte Anzahl von Zeichen von einer Q...
Meta Keywords: die, dest, von, der, strncpy
-->

# strncpy: Sicheres Kopieren von Strings in C

## Synopsis
Die Funktion `strncpy` in C wird verwendet, um eine bestimmte Anzahl von Zeichen von einer Quellzeichenkette in eine Zielzeichenkette zu kopieren, was eine sichere Handhabung von Strings ermöglicht.

## Dokumentation
### Zweck
Die Funktion `strncpy` ist Teil der Standardbibliothek in C und dient dazu, eine bestimmte Anzahl von Zeichen von einer Quellzeichenkette (Quell-String) in eine Zielzeichenkette (Ziel-String) zu kopieren. Sie trägt dazu bei, Pufferüberläufe zu vermeiden, indem sie die Anzahl der zu kopierenden Zeichen begrenzt.

### Verwendung
Die Funktion hat die folgende Prototyp-Deklaration:

```c
char *strncpy(char *dest, const char *src, size_t n);
```

- **Parameter**:
  - `dest`: Ein Zeiger auf die Zielzeichenkette, in die kopiert wird.
  - `src`: Ein Zeiger auf die Quellzeichenkette, von der kopiert wird.
  - `n`: Die maximale Anzahl von Zeichen, die kopiert werden sollen.

- **Rückgabewert**: Ein Zeiger auf die Zielzeichenkette `dest`.

### Details
`strncpy` kopiert die ersten `n` Zeichen von `src` nach `dest`. Wenn `src` weniger als `n` Zeichen enthält, wird der Rest von `dest` mit Null-Bytes (`'\0'`) aufgefüllt. Wenn `src` `n` oder mehr Zeichen enthält, wird `dest` **nicht** automatisch nullterminiert, was bedeutet, dass es wichtig ist, sicherzustellen, dass der Zielpuffer ausreichend Platz hat, um die Nullterminierung aufzunehmen.

## Beispiele
### Beispiel 1: Grundlegende Verwendung
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20];
    const char *src = "Hallo, Welt!";
    
    strncpy(dest, src, 10);
    dest[10] = '\0'; // Manuell nullterminieren

    printf("Kopierter String: %s\n", dest);
    return 0;
}
```

### Beispiel 2: Quellstring kürzer als n
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20];
    const char *src = "Hi";
    
    strncpy(dest, src, 10);
    // dest wird automatisch mit Null-Bytes aufgefüllt
    
    printf("Kopierter String: %s\n", dest);
    return 0;
}
```

## Erklärung
Obwohl `strncpy` als sicherer gilt, gibt es einige häufige Fallstricke:

1. **Fehlende Nullterminierung**: Wenn der Quellstring länger oder gleich `n` ist, wird der Zielstring nicht nullterminiert. Dies kann zu undefined behavior führen, wenn der String später als nullterminiert betrachtet wird.
  
2. **Größe des Zielpuffers**: Stellen Sie sicher, dass der Zielpuffer groß genug ist, um die gewünschten Zeichen sowie die Nullterminierung aufzunehmen, um Pufferüberläufe zu vermeiden.

3. **Portabilität**: Während `strncpy` in den meisten Implementierungen zuverlässig ist, können Unterschiede in der Handhabung der Nullterminierung zwischen verschiedenen Compilern auftreten.

## Ein-Satz-Zusammenfassung
Die Funktion `strncpy` in C ermöglicht das sichere Kopieren von Strings mit einer definierten Anzahl von Zeichen, erfordert jedoch besondere Aufmerksamkeit hinsichtlich der Nullterminierung.