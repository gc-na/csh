<!--
Meta Description: # iscntrl - Überprüfung von Steuerzeichen in C ## Synopsis Die Funktion `iscntrl` in C dient dazu, zu überprüfen, ob ein gegebenes Zeichen ein Steuerz...
Meta Keywords: die, zeichen, ist, iscntrl, steuerzeichen
-->

# iscntrl - Überprüfung von Steuerzeichen in C

## Synopsis
Die Funktion `iscntrl` in C dient dazu, zu überprüfen, ob ein gegebenes Zeichen ein Steuerzeichen ist. Steuerzeichen sind Zeichen, die keine druckbaren Symbole darstellen und typischerweise Steuerfunktionen in der Textverarbeitung durchführen.

## Documentation
Die Funktion `iscntrl` ist Teil der C-Standardbibliothek und wird in `<ctype.h>` deklariert. Der Hauptzweck dieser Funktion besteht darin, festzustellen, ob das übergebene Zeichen ein Steuerzeichen ist. Steuerzeichen umfassen Zeichen wie Zeilenumbruch (LF), Wagenrücklauf (CR), Tabulator (TAB) und andere nicht druckbare Zeichen.

### Verwendung
Die allgemeine Syntax der Funktion lautet:

```c
#include <ctype.h>

int iscntrl(int c);
```

**Parameter:**
- `c`: Das Zeichen, das überprüft werden soll, typischerweise als Ganzzahl (int) übergeben, was dem ASCII-Wert des Zeichens entspricht.

**Rückgabewert:**
Die Funktion gibt einen Wert ungleich Null zurück, wenn das Zeichen ein Steuerzeichen ist. Andernfalls wird 0 zurückgegeben.

### Details
- `iscntrl` ist nützlich beim Verarbeiten von Text, da es hilft, nicht druckbare Zeichen zu identifizieren, die möglicherweise in Eingabedaten verborgen sind.
- Die Funktion arbeitet mit den Werten von 0 bis 255, was sie zu einer praktischen Wahl für die Arbeit mit ASCII-Zeichen macht.

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung von `iscntrl`:

### Beispiel 1: Überprüfung eines Steuerzeichens
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = '\n'; // Zeilenumbruch
    if (iscntrl(ch)) {
        printf("Das Zeichen ist ein Steuerzeichen.\n");
    } else {
        printf("Das Zeichen ist kein Steuerzeichen.\n");
    }
    return 0;
}
```

### Beispiel 2: Überprüfung mehrerer Zeichen
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[] = "Hello\nWorld\t!";
    for (int i = 0; str[i] != '\0'; i++) {
        if (iscntrl(str[i])) {
            printf("Das Zeichen '%c' ist ein Steuerzeichen.\n", str[i]);
        }
    }
    return 0;
}
```

## Explanation
Ein häufiger Fehler bei der Verwendung von `iscntrl` besteht darin, die Funktion mit nicht-gültigen Werten aufzurufen, die außerhalb des Bereichs von 0 bis 255 liegen. Dies kann zu undefiniertem Verhalten führen. Es ist auch wichtig zu beachten, dass die Funktion nur für Zeichen funktioniert, die im ASCII-Zeichensatz definiert sind. 

Ein weiterer Punkt ist, dass `iscntrl` nur einen Wert zurückgibt, der ungleich Null ist, wenn das Zeichen ein Steuerzeichen ist. Der spezifische Rückgabewert ist nicht von Bedeutung. Die Benutzer sollten sich nicht auf bestimmte Rückgabewerte verlassen, um die Art des Steuerzeichens zu bestimmen.

## One Line Summary
Die Funktion `iscntrl` in C überprüft, ob ein Zeichen ein Steuerzeichen ist, und ist nützlich für die Verarbeitung von Textdaten.