<!--
Meta Description: # strcpy: Die Funktion zum Kopieren von Strings in C ## Synopsis Die Funktion `strcpy` in C wird verwendet, um einen String von einer Quelle in eine Z...
Meta Keywords: string, strcpy, der, destination, die
-->

# strcpy: Die Funktion zum Kopieren von Strings in C

## Synopsis
Die Funktion `strcpy` in C wird verwendet, um einen String von einer Quelle in eine Zielvariable zu kopieren. Sie ist Teil der Standardbibliothek `<string.h>` und spielt eine entscheidende Rolle bei der Arbeit mit Zeichenfolgen.

## Documentation
Die Funktion `strcpy` hat die folgende Syntax:

```c
char *strcpy(char *dest, const char *src);
```

### Parameter:
- `dest`: Ein Zeiger auf das Zielarray, in das der Quellstring kopiert werden soll. Dieses Array muss groß genug sein, um den kopierten String sowie das Nullterminierungszeichen (`\0`) zu speichern.
- `src`: Ein Zeiger auf den Quellstring, der kopiert werden soll. Er muss ein Null-terminierter String sein.

### Rückgabewert:
Die Funktion gibt einen Zeiger auf das Zielarray (`dest`) zurück.

### Zweck:
`strcpy` wird verwendet, um eine Kopie eines Strings zu erstellen. Es ist wichtig, dass der Zielpuffer ausreichend groß ist, um Überläufe zu vermeiden und sicherzustellen, dass der kopierte String ordnungsgemäß endet.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `strcpy`:

### Beispiel 1: Einfaches Kopieren
```c
#include <stdio.h>
#include <string.h>

int main() {
    char source[] = "Hallo, Welt!";
    char destination[50]; // Zielarray muss groß genug sein

    strcpy(destination, source);
    printf("Kopierter String: %s\n", destination);
    return 0;
}
```

### Beispiel 2: Kopieren in ein kleineres Array (Überlauf)
```c
#include <stdio.h>
#include <string.h>

int main() {
    char source[] = "Ein sehr langer String, der nicht passt.";
    char destination[10]; // Zu klein für den Inhalt von source

    strcpy(destination, source); // Potenzieller Überlauf
    printf("Kopierter String: %s\n", destination); // Unvorhersehbares Verhalten
    return 0;
}
```

## Explanation
Ein häufiges Problem bei der Verwendung von `strcpy` ist der Pufferüberlauf. Wenn der Zielpuffer (`dest`) nicht groß genug ist, um den Quellstring (`src`) und das Nullterminierungszeichen zu speichern, kann dies zu undefiniertem Verhalten führen, einschließlich Programmabstürzen oder Sicherheitslücken.

Zusätzlich wird empfohlen, die sicherere Variante `strncpy` zu verwenden, die die maximale Anzahl von zu kopierenden Zeichen angibt. Diese Methode hilft, Pufferüberläufe zu vermeiden:

```c
strncpy(destination, source, sizeof(destination) - 1);
destination[sizeof(destination) - 1] = '\0'; // Sicherstellen, dass das Ziel nullterminiert ist
```

## One Line Summary
`strcpy` ist eine C-Funktion, die verwendet wird, um einen String von einer Quelle in ein Ziel zu kopieren, wobei Vorsicht hinsichtlich Pufferüberläufen geboten ist.