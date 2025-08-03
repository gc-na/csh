<!--
Meta Description: # Die Funktion srand in C: Zufallszahlengenerierung ## Synopsis Die Funktion `srand` in C wird verwendet, um den Startwert (Seed) für die Zufallszahle...
Meta Keywords: die, srand, seed, rand, von
-->

# Die Funktion srand in C: Zufallszahlengenerierung

## Synopsis
Die Funktion `srand` in C wird verwendet, um den Startwert (Seed) für die Zufallszahlengenerierung festzulegen. Sie ist Teil der Standardbibliothek `<stdlib.h>` und ermöglicht es, die von der Funktion `rand` generierten Zufallszahlen zu steuern.

## Dokumentation
### Zweck
`srand` steht für "seed random" und legt den Startwert für die Zufallszahlengenerierung fest. Ohne diesen Seed generiert die Funktion `rand` jedes Mal die gleiche Sequenz von Zufallszahlen, was in vielen Anwendungsfällen unerwünscht ist.

### Verwendung
Die Funktion hat die folgende Syntax:

```c
void srand(unsigned int seed);
```

- **Parameter**: 
  - `seed`: Ein unsigned int, der als Startwert für die Zufallszahlengenerierung dient.
  
### Details
- `srand` sollte einmal zu Beginn des Programms aufgerufen werden, bevor `rand` verwendet wird.
- Um echte Zufallszahlen zu erhalten, wird häufig der aktuelle Zeitstempel (z. B. von `time(NULL)`) als Seed verwendet.
- `rand` gibt eine Pseudo-Zufallszahl zwischen 0 und `RAND_MAX` zurück, wobei `RAND_MAX` in `<stdlib.h>` definiert ist und den maximalen Rückgabewert von `rand` angibt.

## Beispiele
### Beispiel 1: Verwendung von srand
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    // Seed mit der aktuellen Zeit setzen
    srand(time(NULL));

    // Zufallszahlen generieren
    for (int i = 0; i < 5; i++) {
        printf("%d\n", rand());
    }
    return 0;
}
```

### Beispiel 2: Wiederholbare Zufallszahlensequenzen
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Seed auf einen festen Wert setzen
    srand(42);

    // Zufallszahlen generieren
    for (int i = 0; i < 5; i++) {
        printf("%d\n", rand());
    }
    return 0;
}
```

## Erklärung
- **Häufige Stolpersteine**: Eine häufige Falle besteht darin, `srand` nicht zu verwenden oder mehrmals mit demselben Seed aufzurufen, was zu identischen Zufallszahlen führt. Um unterschiedliche Sequenzen zu erhalten, sollte `srand` nur einmal zu Beginn des Programms aufgerufen werden.
- **Zusätzliche Hinweise**: Es ist wichtig zu beachten, dass die von `rand` generierten Zahlen nicht wirklich zufällig sind, sondern pseudozufällig, was bedeutet, dass sie deterministisch sind, basierend auf dem Seed. Für Anwendungen, die echte Zufälligkeit erfordern, sollte auf andere Methoden oder Bibliotheken zurückgegriffen werden.

## Ein-Satz-Zusammenfassung
Die Funktion `srand` in C setzt den Startwert für die Pseudo-Zufallszahlengenerierung und ermöglicht die Kontrolle über die von `rand` erzeugten Zufallszahlen.