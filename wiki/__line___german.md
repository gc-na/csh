<!--
Meta Description: # __LINE__ in C: Eine detaillierte Übersicht über das vorverarbeitende Makro ## Synopsis Das vorverarbeitende Makro `__LINE__` in C gibt die aktuelle ...
Meta Keywords: der, __line__, zeilennummer, die, ist
-->

# __LINE__ in C: Eine detaillierte Übersicht über das vorverarbeitende Makro

## Synopsis
Das vorverarbeitende Makro `__LINE__` in C gibt die aktuelle Zeilennummer des Codes in der Quelldatei zurück und ist nützlich für Debugging und Protokollierung.

## Documentation
Das Makro `__LINE__` ist ein integriertes, vorverarbeitetes Makro in der C-Programmiersprache, das die Zeilennummer der Zeile liefert, in der es verwendet wird. Es wird automatisch vom C-Compiler definiert und benötigt keine spezielle Deklaration.

### Zweck
`__LINE__` wird häufig verwendet, um Informationen über die Position des Codes bereitzustellen, was besonders hilfreich beim Debugging, Logging oder beim Erstellen von Fehlermeldungen ist.

### Verwendung
Um `__LINE__` zu verwenden, können Sie es einfach in Ihrem Code an der gewünschten Stelle einfügen. Es gibt den Wert als Ganzzahl zurück, der die aktuelle Zeilennummer darstellt.

### Details
- **Typ**: `int`
- **Gültigkeitsbereich**: Gilt für die gesamte Datei, in der es definiert ist.
- **Automatische Ersetzung**: Es wird automatisch durch die aktuelle Zeilennummer ersetzt, wenn der Code kompiliert wird.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `__LINE__`:

### Beispiel 1: Einfache Ausgabe der Zeilennummer
```c
#include <stdio.h>

int main() {
    printf("Die aktuelle Zeilennummer ist: %d\n", __LINE__);
    return 0;
}
```
*Ausgabe*: `Die aktuelle Zeilennummer ist: 5` (abhängig von der Zeilennummer im Code)

### Beispiel 2: Verwendung in einer Fehlermeldung
```c
#include <stdio.h>

void Fehler() {
    printf("Fehler in Zeile %d aufgetreten!\n", __LINE__);
}

int main() {
    Fehler();
    return 0;
}
```
*Ausgabe*: `Fehler in Zeile 5 aufgetreten!` (abhängig von der Zeilennummer im Code)

### Beispiel 3: Kombination mit anderen Makros
```c
#include <stdio.h>

#define DEBUG_MSG(msg) printf("DEBUG: %s, Zeile: %d\n", msg, __LINE__)

int main() {
    DEBUG_MSG("Das Programm hat gestartet.");
    return 0;
}
```
*Ausgabe*: `DEBUG: Das Programm hat gestartet., Zeile: 6` (abhängig von der Zeilennummer im Code)

## Erklärung
Ein häufiger Fehler beim Umgang mit `__LINE__` ist, diese Zeilennummer in der Annahme zu verwenden, dass sie sich nicht ändert, wenn der Code bearbeitet wird. Da `__LINE__` immer die aktuelle Zeilennummer zurückgibt, kann es zu Verwirrung führen, wenn Zeilen hinzugefügt oder entfernt werden. Ein weiterer Punkt ist, dass `__LINE__` nur den Wert zur Kompilierzeit liefert, was bedeutet, dass es zur Laufzeit nicht verändert werden kann.

## One Line Summary
Das Makro `__LINE__` in C gibt die aktuelle Zeilennummer des Quellcodes zurück und ist ein wertvolles Werkzeug für Debugging und Protokollierung.