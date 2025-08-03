<!--
Meta Description: # putchar: Der C-Befehl für die Zeichen-Ausgabe ## Synopsis `putchar` ist eine Standardbibliotheksfunktion in C, die ein einzelnes Zeichen auf die Sta...
Meta Keywords: putchar, zeichen, die, der, ist
-->

# putchar: Der C-Befehl für die Zeichen-Ausgabe

## Synopsis
`putchar` ist eine Standardbibliotheksfunktion in C, die ein einzelnes Zeichen auf die Standardausgabe (normalerweise den Bildschirm) ausgibt.

## Dokumentation
Die Funktion `putchar` ist Teil der C-Standardbibliothek und wird in der Header-Datei `<stdio.h>` deklariert. Sie wird häufig verwendet, um einfache Zeichenfolgen oder Zeichen zu drucken. Die Syntax der Funktion lautet:

```c
int putchar(int character);
```

### Parameter
- `character`: Das Zeichen, das ausgegeben werden soll, übergeben als ganzzahliger Wert (in der Regel als `char`).

### Rückgabewert
Die Funktion gibt das ausgegebene Zeichen als `unsigned char` zurück, wenn der Aufruf erfolgreich war. Bei einem Fehler wird `EOF` (End of File) zurückgegeben.

### Verwendung
`putchar` ist nützlich für einfache Ausgaben, insbesondere wenn man mit einzelnen Zeichen arbeitet. Sie kann auch in Schleifen verwendet werden, um mehrere Zeichen hintereinander auszugeben.

## Beispiele
Hier sind einige grundlegende Beispiele, die die Verwendung von `putchar` veranschaulichen:

### Beispiel 1: Ein einzelnes Zeichen ausgeben
```c
#include <stdio.h>

int main() {
    putchar('H');
    putchar('e');
    putchar('l');
    putchar('l');
    putchar('o');
    putchar('!');
    putchar('\n'); // Neue Zeile
    return 0;
}
```

### Beispiel 2: Zeichen in einer Schleife ausgeben
```c
#include <stdio.h>

int main() {
    for (char c = 'A'; c <= 'Z'; c++) {
        putchar(c);
    }
    putchar('\n'); // Neue Zeile
    return 0;
}
```

## Erklärung
Beim Gebrauch von `putchar` gibt es einige häufige Fallstricke:

- **Rückgabewert ignorieren**: Es ist wichtig, den Rückgabewert von `putchar` zu überprüfen, insbesondere bei der Fehlersuche. Ignoriert man diesen, kann es zu unerwartetem Verhalten kommen.
  
- **Eingabewerte**: Der übergebene Wert sollte ein gültiges Zeichen sein. Werte außerhalb des Bereichs von `unsigned char` können undefiniertes Verhalten hervorrufen.
  
- **Verwendung in Schleifen**: Beim Ausgeben von Zeichen in einer Schleife sollte darauf geachtet werden, dass die Schleifenbedingungen korrekt gesetzt sind, um unerwünschte Ausgaben zu vermeiden.

## Einzeilenzusammenfassung
`putchar` ist eine einfache und effektive Methode in C, um ein einzelnes Zeichen auf die Standardausgabe auszugeben.