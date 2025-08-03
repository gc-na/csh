<!--
Meta Description: # fprintf in C: Formatierte Ausgabe in Dateien ## Synopsis Die Funktion `fprintf` in C ermöglicht es, formatierte Ausgaben in Dateien zu schreiben. Si...
Meta Keywords: die, file, fprintf, sie, eine
-->

# fprintf in C: Formatierte Ausgabe in Dateien

## Synopsis
Die Funktion `fprintf` in C ermöglicht es, formatierte Ausgaben in Dateien zu schreiben. Sie ist Teil der Standardbibliothek und bietet eine flexible Möglichkeit, Daten in verschiedenen Formaten zu speichern.

## Documentation
Die Funktion `fprintf` wird im Header `<stdio.h>` deklariert und hat die folgende Syntax:

```c
int fprintf(FILE *stream, const char *format, ...);
```

### Zweck
`fprintf` wird verwendet, um formatierte Textausgaben in eine Datei oder einen anderen Ausgabestrom zu schreiben. Sie ist besonders nützlich, wenn Daten in einem bestimmten Format gespeichert werden sollen, wie z.B. Zahlen mit einer bestimmten Anzahl von Dezimalstellen oder Strings mit spezifischen Abständen.

### Parameter
- `FILE *stream`: Ein Zeiger auf ein `FILE`-Objekt, das den Ausgabestrom repräsentiert. Dies kann eine Datei oder ein anderer Ausgabestrom, wie `stdout`, sein.
- `const char *format`: Ein Format-String, der Platzhalter für die Werte enthält, die ausgegeben werden sollen. Platzhalter beginnen mit `%` und können durch Typ-Spezifizierer ergänzt werden (z.B. `%d` für Ganzzahlen, `%f` für Fließkommazahlen).
- `...`: Eine variable Anzahl von Argumenten, die in den Format-String eingesetzt werden.

### Rückgabewert
`fprintf` gibt die Anzahl der erfolgreich geschriebenen Zeichen zurück. Bei einem Fehler wird ein negativer Wert zurückgegeben.

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung von `fprintf`:

### Beispiel 1: Schreiben in eine Datei
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w");
    if (file != NULL) {
        fprintf(file, "Hallo, Welt!\n");
        fclose(file);
    }
    return 0;
}
```

### Beispiel 2: Formatierte Ausgabe
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("output.txt", "w");
    if (file != NULL) {
        int alter = 25;
        float gehalt = 2500.50;
        fprintf(file, "Alter: %d Jahre\nGehalt: %.2f Euro\n", alter, gehalt);
        fclose(file);
    }
    return 0;
}
```

## Explanation
### Häufige Fallstricke
- **Dateizugriffsfehler**: Stellen Sie sicher, dass die Datei erfolgreich geöffnet wurde, bevor Sie `fprintf` verwenden. Andernfalls kann ein Fehler auftreten.
- **Format-Strings**: Achten Sie darauf, die richtigen Format-Spezifizierer zu verwenden, um Typfehler zu vermeiden, die zu Laufzeitfehlern führen können.
- **Pufferung**: Ausgaben werden möglicherweise nicht sofort in die Datei geschrieben, da `fprintf` durch Pufferung optimiert ist. Verwenden Sie `fflush(file)`, um den Puffer manuell zu leeren, falls erforderlich.

### Zusätzliche Hinweise
- `fprintf` kann auch verwendet werden, um Ausgaben auf den Standardausgabestrom (`stdout`) zu schreiben, indem Sie `stdout` als den `stream`-Parameter übergeben.
- Achten Sie darauf, die Datei nach dem Schreiben mit `fclose` zu schließen, um Datenverlust zu vermeiden.

## One Line Summary
`fprintf` in C ist eine Funktion, die formatierte Ausgaben in Dateien oder Ausgabeströme ermöglicht und dabei eine flexible Handhabung von verschiedenen Datentypen bietet.