<!--
Meta Description: # fscanf: Eingaben aus Dateien in C lesen ## Synopsis `fscanf` ist eine Funktion in C, die es ermöglicht, formatierte Eingaben aus Dateien zu lesen. S...
Meta Keywords: datei, die, fscanf, der, sie
-->

# fscanf: Eingaben aus Dateien in C lesen

## Synopsis
`fscanf` ist eine Funktion in C, die es ermöglicht, formatierte Eingaben aus Dateien zu lesen. Sie ist besonders nützlich, um Daten effizient aus strukturierten Textdateien zu extrahieren.

## Documentation
Die Funktion `fscanf` ist Teil der Standardbibliothek in C und wird durch die Header-Datei `<stdio.h>` bereitgestellt. Sie wird verwendet, um Daten aus einer Datei in Variablen zu lesen, basierend auf einem angegebenen Format.

### Syntax
```c
int fscanf(FILE *stream, const char *format, ...);
```

### Parameter
- `stream`: Ein Zeiger auf das `FILE`-Objekt, das die zu lesende Datei repräsentiert.
- `format`: Ein Format-String, der angibt, wie die Daten interpretiert werden sollen (ähnlich wie bei `printf`).
- `...`: Eine variable Anzahl von Argumenten, die Zeiger auf die Variablen sind, in die die gelesenen Daten gespeichert werden.

### Rückgabewert
`fscanf` gibt die Anzahl der erfolgreich gelesenen und zugewiesenen Werte zurück. Bei einem Fehler oder am Ende der Datei wird ein Wert kleiner als die angegebene Anzahl zurückgegeben.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `fscanf`:

### Beispiel 1: Ganzzahl und Fließkommazahl lesen
```c
#include <stdio.h>

int main() {
    FILE *datei = fopen("daten.txt", "r");
    int zahl;
    float kommazahl;

    if (datei != NULL) {
        fscanf(datei, "%d %f", &zahl, &kommazahl);
        printf("Gelesene Zahl: %d, Gelesene Kommazahl: %.2f\n", zahl, kommazahl);
        fclose(datei);
    } else {
        printf("Fehler beim Öffnen der Datei.\n");
    }
    return 0;
}
```

### Beispiel 2: Zeichenkette lesen
```c
#include <stdio.h>

int main() {
    FILE *datei = fopen("text.txt", "r");
    char text[100];

    if (datei != NULL) {
        fscanf(datei, "%s", text);
        printf("Gelesener Text: %s\n", text);
        fclose(datei);
    } else {
        printf("Fehler beim Öffnen der Datei.\n");
    }
    return 0;
}
```

## Explanation
Bei der Verwendung von `fscanf` sind einige häufige Fallstricke zu beachten:

1. **Formatübereinstimmung**: Stellen Sie sicher, dass das Format in `fscanf` mit dem tatsächlichen Inhalt der Datei übereinstimmt. Andernfalls kann es zu unerwarteten Ergebnissen oder Fehlern kommen.

2. **Datei öffnen**: Vergewissern Sie sich, dass die Datei erfolgreich geöffnet wurde, bevor Sie versuchen, Daten zu lesen. Ein NULL-Zeiger auf das `FILE`-Objekt bedeutet, dass die Datei nicht geöffnet werden konnte.

3. **Pufferüberlauf**: Bei der Eingabe von Zeichenfolgen sollten Sie sicherstellen, dass der Puffer groß genug ist, um die Eingabe aufzunehmen, um Pufferüberläufe zu vermeiden.

4. **Rückgabewert**: Überprüfen Sie den Rückgabewert von `fscanf`, um sicherzustellen, dass die erwartete Anzahl von Werten erfolgreich gelesen wurde.

## One Line Summary
`fscanf` ist eine C-Funktion zum strukturierten Einlesen von Daten aus Dateien, die eine präzise Formatierung erfordert.