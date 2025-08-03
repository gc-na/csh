<!--
Meta Description: # strcat: Die C-Funktion zum Verketten von Strings ## Synopsis Die Funktion `strcat` in C wird verwendet, um zwei Strings zu verketten, das heißt, ein...
Meta Keywords: strcat, die, dest, das, der
-->

# strcat: Die C-Funktion zum Verketten von Strings

## Synopsis
Die Funktion `strcat` in C wird verwendet, um zwei Strings zu verketten, das heißt, einen zweiten String an das Ende eines ersten Strings anzufügen.

## Dokumentation
Die Funktion `strcat` ist Teil der C-Standardbibliothek und in der Header-Datei `<string.h>` deklariert. Sie hat die folgende Signatur:

```c
char *strcat(char *dest, const char *src);
```

### Zweck
`strcat` wird verwendet, um den Inhalt des Quellstrings (`src`) an das Ende des Zielstrings (`dest`) anzuhängen. Es ist wichtig, dass der Zielstring genügend Speicherplatz hat, um die resultierende verkettete Zeichenkette zu speichern.

### Verwendung
- **Parameter:**
  - `dest`: Ein Zeiger auf den Zielstring, der modifiziert wird. Dieser muss ausreichend Speicherplatz für die zusätzliche Zeichenkette haben.
  - `src`: Ein Zeiger auf den Quellstring, der an das Ende von `dest` angefügt wird.

- **Rückgabewert:**
  - Die Funktion gibt einen Zeiger auf den Zielstring (`dest`) zurück.

### Details
`strcat` beginnt mit dem ersten Null-Zeichen (`\0`) im Zielstring und fügt die Zeichen aus dem Quellstring hinzu, bis das Null-Zeichen im Quellstring erreicht ist. Das Ergebnis ist ein neuer String, der die Inhalte beider Strings enthält, wobei das Null-Zeichen des Zielstrings durch das erste Zeichen des Quellstrings ersetzt wird, und ein neues Null-Zeichen am Ende des resultierenden Strings hinzugefügt wird.

## Beispiele
Hier sind einige einfache Beispiele zur Verwendung von `strcat`:

### Beispiel 1: Grundlegende Verwendung
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[20] = "Hallo, ";
    char src[] = "Welt!";
    
    strcat(dest, src);
    printf("%s\n", dest);  // Ausgabe: Hallo, Welt!
    
    return 0;
}
```

### Beispiel 2: Verwendung mit genügend Speicher
```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[50] = "C-Programmierung: ";
    char src[] = "strcat Beispiel.";
    
    strcat(dest, src);
    printf("%s\n", dest);  // Ausgabe: C-Programmierung: strcat Beispiel.
    
    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **Speicherüberlauf:** Ein häufiger Fehler ist, dass der Zielstring (`dest`) nicht genügend Speicher hat, um die verkettete Zeichenkette zu speichern. Dies kann zu undefiniertem Verhalten führen.
- **Null-Zeichen:** Achten Sie darauf, dass der Zielstring korrekt mit einem Null-Zeichen (`\0`) terminiert ist, bevor Sie `strcat` aufrufen. Andernfalls kann das Ergebnis unvorhersehbar sein.

### Zusätzliche Hinweise
- `strcat` ist nicht sicher für die Verwendung in sicherheitskritischen Anwendungen, da es keine Überprüfung der Puffergröße durchführt. Verwenden Sie stattdessen `strncat`, wenn Sie die Anzahl der zu kopierenden Zeichen steuern möchten.

## Zusammenfassung in einem Satz
Die `strcat`-Funktion in C ermöglicht das Verketten von Strings und sollte mit Vorsicht verwendet werden, um Speicherüberläufe zu vermeiden.