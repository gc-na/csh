<!--
Meta Description: # scanf in C: Eingaben effizient verarbeiten ## Synopsis `scanf` ist eine Standardbibliotheksfunktion in der Programmiersprache C, die verwendet wird,...
Meta Keywords: der, die, scanf, von, eingaben
-->

# scanf in C: Eingaben effizient verarbeiten

## Synopsis
`scanf` ist eine Standardbibliotheksfunktion in der Programmiersprache C, die verwendet wird, um Eingaben von der Standard-Eingabe (normalerweise der Tastatur) zu lesen und sie in Variablen zu speichern.

## Dokumentation
Die `scanf`-Funktion gehört zur `<stdio.h>`-Bibliothek und ermöglicht es Programmierern, formatierte Eingaben zu lesen. Sie wird häufig verwendet, um verschiedene Datentypen wie Ganzzahlen, Fließkommazahlen und Strings zu erfassen.

### Zweck
Der Hauptzweck von `scanf` ist es, Benutzereingaben zu verarbeiten und sie in Variablen zu speichern, die im Programm weiterverwendet werden können.

### Verwendung
Die allgemeine Syntax der `scanf`-Funktion lautet:

```c
int scanf(const char *format, ...);
```

- `format`: Ein Format-String, der die Art der erwarteten Eingaben beschreibt (z.B. `%d` für Ganzzahlen, `%f` für Fließkommazahlen, `%s` für Strings).
- `...`: Eine Liste von Zeigern auf die Variablen, in die die Eingaben gespeichert werden sollen.

### Rückgabewert
`scanf` gibt die Anzahl der erfolgreich gelesenen Elemente zurück oder EOF (End of File), wenn ein Fehler auftritt oder das Ende der Eingabe erreicht wird.

## Beispiele
### Beispiel 1: Lesen einer Ganzzahl
```c
#include <stdio.h>

int main() {
    int zahl;
    printf("Bitte geben Sie eine Ganzzahl ein: ");
    scanf("%d", &zahl);
    printf("Sie haben die Zahl %d eingegeben.\n", zahl);
    return 0;
}
```

### Beispiel 2: Lesen eines Strings
```c
#include <stdio.h>

int main() {
    char name[50];
    printf("Bitte geben Sie Ihren Namen ein: ");
    scanf("%s", name);
    printf("Hallo, %s!\n", name);
    return 0;
}
```

### Beispiel 3: Lesen einer Fließkommazahl
```c
#include <stdio.h>

int main() {
    float pi;
    printf("Bitte geben Sie einen Wert für Pi ein: ");
    scanf("%f", &pi);
    printf("Der eingegebene Wert für Pi ist: %.2f\n", pi);
    return 0;
}
```

## Erklärung
### Häufige Probleme und Hinweise
- **Pufferüberlauf**: Bei der Verwendung von `%s` wird der eingegebene String nicht auf die maximale Länge überprüft, was zu einem Pufferüberlauf führen kann. Es ist ratsam, die maximale Länge anzugeben, z.B. `%49s` für einen Puffer von 50 Zeichen.
- **Eingabe von mehreren Werten**: Wenn mehrere Werte eingelesen werden, müssen die entsprechenden Variablen als Argumente in der gleichen Reihenfolge wie die Formatzeichenfolgen übergeben werden.
- **Unzureichende Eingaben**: Wenn der Benutzer nicht die erwartete Eingabe liefert, kann `scanf` fehlschlagen und das Programm in einen unerwarteten Zustand versetzen.
- **Whitespace**: `scanf` ignoriert führende Whitespaces (Leerzeichen, Tabs, Zeilenumbrüche) bei der Verarbeitung von Eingaben. 

## Einzeiliger Zusammenfassung
`scanf` ist eine Funktion in C, die es ermöglicht, formatierte Benutzereingaben von der Standard-Eingabe zu lesen und in Variablen zu speichern.