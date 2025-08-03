<!--
Meta Description: # isupper in C: Überprüfung von Großbuchstaben ## Synopsis Die Funktion `isupper` in C überprüft, ob ein gegebenes Zeichen ein Großbuchstabe ist. Dies...
Meta Keywords: ist, ein, isupper, zeichen, int
-->

# isupper in C: Überprüfung von Großbuchstaben

## Synopsis
Die Funktion `isupper` in C überprüft, ob ein gegebenes Zeichen ein Großbuchstabe ist. Diese Funktion ist Teil der Standardbibliothek und wird häufig in der Verarbeitung von Zeichenfolgen verwendet.

## Dokumentation
Die Funktion `isupper` ist in der Header-Datei `<ctype.h>` definiert. Sie nimmt ein einzelnes Zeichen (typischerweise als `int` übergeben) und gibt einen Wert ungleich Null zurück, wenn das Zeichen ein Großbuchstabe (A-Z) ist. Andernfalls gibt sie 0 zurück.

### Syntax
```c
#include <ctype.h>

int isupper(int c);
```

### Parameter
- `c`: Das zu überprüfende Zeichen (als `int`). Es sollte in der Regel ein ASCII-Zeichen sein.

### Rückgabewert
- Der Rückgabewert ist ein nicht-nullwertiger Wert (wahr) wenn `c` ein Großbuchstabe ist, andernfalls 0 (falsch).

### Verwendung
`isupper` wird häufig verwendet, um Eingaben zu validieren oder um Textverarbeitungsaufgaben durchzuführen, bei denen die Unterscheidung zwischen Groß- und Kleinbuchstaben erforderlich ist.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `isupper`:

### Beispiel 1: Überprüfung eines einzelnen Zeichens
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'A';
    if (isupper(ch)) {
        printf("%c ist ein Großbuchstabe.\n", ch);
    } else {
        printf("%c ist kein Großbuchstabe.\n", ch);
    }
    return 0;
}
```

### Beispiel 2: Überprüfung einer Zeichenkette
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[] = "Hallo Welt!";
    for (int i = 0; str[i] != '\0'; i++) {
        if (isupper(str[i])) {
            printf("%c ist ein Großbuchstabe.\n", str[i]);
        }
    }
    return 0;
}
```

## Erklärung
Ein häufiges Missverständnis ist, dass `isupper` nur für Zeichen im ASCII-Bereich gilt. Zeichen, die nicht im ASCII-Bereich liegen, können unerwartete Ergebnisse liefern. Zudem sollte beachtet werden, dass `isupper` als `int` deklariert ist, um negative Werte zu behandeln, die in C für das Ende einer Zeichenfolge wichtig sind. Ein weiterer Punkt ist, dass die Funktion keine Unicode-Zeichen unterstützt, da sie nur ASCII-Zeichen korrekt verarbeitet.

Ein typischer Fehler ist, `isupper` auf einen Wert jenseits des ASCII-Bereichs anzuwenden, was zu undefiniertem Verhalten führen kann. Stellen Sie außerdem sicher, dass Sie das Zeichen korrekt in einen `int`-Wert umwandeln, falls Sie mit unterschiedlichen Datentypen arbeiten.

## Einzeiliger Zusammenfassung
Die Funktion `isupper` in C prüft, ob ein Zeichen ein Großbuchstabe ist und gibt einen entsprechenden Wahrheitswert zurück.