<!--
Meta Description: # strftime in C: Datums- und Zeitformatierung leicht gemacht ## Synopsis Die Funktion `strftime` in C wird verwendet, um Datums- und Zeitinformationen...
Meta Keywords: die, strftime, buffer, und, format
-->

# strftime in C: Datums- und Zeitformatierung leicht gemacht

## Synopsis
Die Funktion `strftime` in C wird verwendet, um Datums- und Zeitinformationen in ein benutzerdefiniertes Format zu formatieren. Sie ermöglicht es Entwicklern, Datumsangaben in lesbare Strings zu konvertieren.

## Dokumentation
Die Funktion `strftime` gehört zur C Standardbibliothek und ist in der Header-Datei `<time.h>` definiert. Ihr Hauptzweck ist es, eine strukturierte Zeitangabe (vom Typ `struct tm`) in einen formatierten String umzuwandeln. 

### Syntax
```c
size_t strftime(char *str, size_t maxsize, const char *format, const struct tm *timeptr);
```

### Parameter
- **str**: Ein Zeiger auf den Puffer, in den das formatierte Datum geschrieben wird.
- **maxsize**: Die maximale Größe des Puffers.
- **format**: Ein Format-String, der angibt, wie das Datum formatiert werden soll.
- **timeptr**: Ein Zeiger auf eine `struct tm`, die die abzubildenden Zeitinformationen enthält.

### Rückgabewert
Die Funktion gibt die Anzahl der in den Puffer geschriebenen Zeichen (ohne das Null-Zeichen) zurück. Wenn die Größe des Puffers nicht ausreicht, um das formatierte Datum zu speichern, wird 0 zurückgegeben.

## Beispiele
### Einfaches Beispiel
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    
    char buffer[80];
    strftime(buffer, sizeof(buffer), "%Y-%m-%d %H:%M:%S", tm_info);
    
    printf("Aktuelles Datum und Uhrzeit: %s\n", buffer);
    return 0;
}
```

### Verwendung von benutzerdefinierten Formatierungen
```c
#include <stdio.h>
#include <time.h>

int main() {
    time_t t = time(NULL);
    struct tm *tm_info = localtime(&t);
    
    char buffer[100];
    strftime(buffer, sizeof(buffer), "Heute ist der %A, %d. %B %Y", tm_info);
    
    printf("%s\n", buffer);
    return 0;
}
```

## Erklärung
Bei der Verwendung von `strftime` sind einige häufige Fallstricke zu beachten:
- **Puffergröße**: Stellen Sie sicher, dass der Puffer groß genug ist, um das formatierte Datum zu speichern. Andernfalls wird die Funktion fehlschlagen, und es wird möglicherweise keine aussagekräftige Ausgabe generiert.
- **Format-Strings**: Verwenden Sie korrekte Format-Strings, um die gewünschten Datums- und Zeitangaben zu erhalten. Eine falsche Verwendung kann zu unerwarteten Ergebnissen führen.
- **Locales**: Das Format kann je nach eingestelltem Locale unterschiedlich sein. Achten Sie darauf, das passende Locale für die gewünschte Ausgabe zu setzen.

## Einzeilensummary
Die Funktion `strftime` in C formatiert Datums- und Zeitangaben in lesbare Strings gemäß benutzerdefinierten Formatvorgaben.