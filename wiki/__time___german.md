<!--
Meta Description: # __TIME__ in C: Das eingebaute Makro für Zeitstempel ## Synopsis Das Makro `__TIME__` in der Programmiersprache C ermöglicht es Programmierern, den Z...
Meta Keywords: der, __time__, das, ist, makro
-->

# __TIME__ in C: Das eingebaute Makro für Zeitstempel

## Synopsis
Das Makro `__TIME__` in der Programmiersprache C ermöglicht es Programmierern, den Zeitpunkt der Kompilierung ihres Programms als String im Format "hh:mm:ss" zu erhalten.

## Dokumentation
### Zweck
`__TIME__` ist ein vordefiniertes Makro in C, das den Zeitpunkt der Kompilierung des Quellcodes zurückgibt. Es ist nützlich, um Informationen zur Versionskontrolle oder zur Protokollierung in Programmen zu integrieren.

### Verwendung
Um `__TIME__` zu verwenden, müssen Sie es einfach in Ihrem Code an einer geeigneten Stelle einfügen. Es gibt keine speziellen Anforderungen oder Header-Dateien, die eingebunden werden müssen. Das Makro gibt immer einen String zurück, der die aktuelle Uhrzeit im Kompilierungszeitpunkt darstellt.

### Details
- Format: Der Wert von `__TIME__` hat das Format "hh:mm:ss".
- Typ: Es handelt sich um einen String, der zur Kompilierungszeit festgelegt wird.
- Beispielwert: Ein typischer Wert könnte "14:30:15" sein, was 14 Uhr, 30 Minuten und 15 Sekunden entspricht.

## Beispiele
### Beispiel 1: Einfaches Programm zur Anzeige der Kompilierungszeit
```c
#include <stdio.h>

int main() {
    printf("Dieses Programm wurde kompiliert um: %s\n", __TIME__);
    return 0;
}
```
In diesem Beispiel wird die Uhrzeit, zu der das Programm kompiliert wurde, auf der Konsole ausgegeben.

### Beispiel 2: Verwendung in einem Header für Versionsinformationen
```c
#include <stdio.h>

#define VERSION "1.0.0"
#define COMPILE_TIME __TIME__

void printInfo() {
    printf("Version: %s, kompiliert um: %s\n", VERSION, COMPILE_TIME);
}
```
Hier wird die Kompilierungszeit zusammen mit einer Versionsnummer ausgegeben, was hilfreich für die Nachverfolgbarkeit ist.

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `__TIME__` ist, dass es nicht zur Laufzeit des Programms aktualisiert wird. Es gibt den Zeitpunkt der Kompilierung an, nicht den Zeitpunkt der Ausführung. Daher ist es wichtig zu beachten, dass Änderungen am Code und anschließende Kompilierungen zu unterschiedlichen Zeitstempeln führen können. 

Ein weiterer Punkt ist, dass `__TIME__` nicht in allen Kompilierumgebungen oder bei allen Compilern gleich behandelt wird. Daher sollte stets die Dokumentation des verwendeten Compilers konsultiert werden, um sicherzustellen, dass das Makro korrekt unterstützt wird.

## Einzeiler Zusammenfassung
`__TIME__` ist ein vordefiniertes Makro in C, das den Zeitpunkt der Kompilierung als String im Format "hh:mm:ss" zurückgibt.