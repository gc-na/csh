<!--
Meta Description: # Die while-Schleife in C: Grundlagen, Verwendung und Beispiele ## Synopsis Die `while`-Schleife in C ist eine Kontrollstruktur, die es ermöglicht, ei...
Meta Keywords: die, schleife, bedingung, ist, der
-->

# Die while-Schleife in C: Grundlagen, Verwendung und Beispiele

## Synopsis
Die `while`-Schleife in C ist eine Kontrollstruktur, die es ermöglicht, einen Block von Anweisungen wiederholt auszuführen, solange eine bestimmte Bedingung wahr ist. Sie ist eine fundamentale Komponente der Programmiersprache C und wird häufig zur Implementierung von Iterationen verwendet.

## Dokumentation
Die `while`-Schleife hat die folgende allgemeine Syntax:

```c
while (Bedingung) {
    // Anweisungen
}
```

### Zweck
Die Hauptfunktion der `while`-Schleife besteht darin, eine wiederholte Ausführung eines Anweisungsblocks zu ermöglichen, solange die angegebene Bedingung wahr (`true`) ist. Dies ist besonders nützlich in Situationen, in denen die Anzahl der durchzuführenden Iterationen im Voraus nicht bekannt ist.

### Verwendung
Um eine `while`-Schleife zu verwenden, definiert man zunächst eine Bedingung. Solange diese Bedingung erfüllt ist, werden die Anweisungen innerhalb des Schleifenblocks ausgeführt. Es ist wichtig, sicherzustellen, dass die Bedingung irgendwann falsch wird, um eine unendliche Schleife zu vermeiden.

### Details
- Die Bedingung wird vor jedem Durchlauf der Schleife evaluiert.
- Es ist möglich, die Schleife ohne Ausführung des Blocks zu betreten, wenn die Bedingung von Anfang an falsch ist.
- Der Code innerhalb der Schleife sollte in der Regel dazu beitragen, die Bedingung irgendwann zu verändern, um die Schleife zu beenden.

## Beispiele

### Beispiel 1: Zähler
```c
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 5) {
        printf("%d\n", i);
        i++;
    }
    return 0;
}
```
In diesem Beispiel wird die Zahl `i` von `0` bis `4` ausgegeben.

### Beispiel 2: Benutzerinteraktion
```c
#include <stdio.h>

int main() {
    char eingabe;
    printf("Geben Sie 'q' ein, um zu beenden: ");
    while ((eingabe = getchar()) != 'q') {
        printf("Sie haben '%c' eingegeben.\n", eingabe);
    }
    return 0;
}
```
Hier wird der Benutzer aufgefordert, Zeichen einzugeben, bis er `q` eingibt.

## Erklärung
Ein häufiges Problem bei der Verwendung der `while`-Schleife sind unendliche Schleifen, die entstehen, wenn die Bedingung niemals falsch wird. Um dies zu vermeiden, sollten Sie sicherstellen, dass innerhalb des Schleifenblocks eine Anweisung zur Änderung der Bedingung vorhanden ist. Ein weiteres häufiges Missverständnis besteht darin, dass die Schleife bei einer falschen Bedingung sofort übersprungen wird, was möglicherweise nicht dem gewünschten Verhalten entspricht.

## Einzeilenzusammenfassung
Die `while`-Schleife in C ermöglicht die wiederholte Ausführung eines Anweisungsblocks, solange eine angegebene Bedingung wahr ist.