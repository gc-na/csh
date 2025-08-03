<!--
Meta Description: # rand: Generierung von Zufallszahlen in C ## Synopsis Die Funktion `rand` in C wird verwendet, um Pseudozufallszahlen zu generieren. Diese Funktion i...
Meta Keywords: die, rand, zufallszahlen, include, zufallszahl
-->

# rand: Generierung von Zufallszahlen in C

## Synopsis
Die Funktion `rand` in C wird verwendet, um Pseudozufallszahlen zu generieren. Diese Funktion ist Teil der Standardbibliothek und ermöglicht es Programmierern, zufällige Werte für verschiedene Anwendungen zu erzeugen.

## Dokumentation
### Zweck
Die Funktion `rand` gibt eine Pseudozufallszahl zurück, die in einem Bereich von 0 bis RAND_MAX liegt, wobei RAND_MAX eine Konstante ist, die in `<stdlib.h>` definiert ist. Diese Funktion ist nützlich in Anwendungen, die Zufallszahlen benötigen, wie z.B. Spiele, Simulationen oder statistische Analysen.

### Verwendung
Um die Funktion `rand` zu verwenden, müssen Sie die Header-Datei `<stdlib.h>` einfügen. Der grundlegende Aufruf der Funktion ist sehr einfach:

```c
#include <stdlib.h>
#include <stdio.h>

int main() {
    int zufallszahl = rand();
    printf("Zufallszahl: %d\n", zufallszahl);
    return 0;
}
```

### Details
- **Initialisierung:** Um eine variierende Sequenz von Zufallszahlen zu erzeugen, sollten Sie die Funktion `srand` verwenden, um den Zufallszahlengenerator mit einem Startwert (Seed) zu initialisieren. Ein häufig verwendeter Wert ist die aktuelle Zeit, die mit `time(NULL)` abgerufen wird.
  
  Beispiel:
  ```c
  #include <stdlib.h>
  #include <stdio.h>
  #include <time.h>

  int main() {
      srand(time(NULL)); // Initialisierung des Zufallszahlengenerators
      int zufallszahl = rand();
      printf("Zufallszahl: %d\n", zufallszahl);
      return 0;
  }
  ```

- **Bereich der Zufallszahlen:** Um Zufallszahlen in einem bestimmten Bereich zu erhalten, können Sie die folgende Formel verwenden:
  ```c
  int zufallszahl_im_bereich = (rand() % (obergrenze - untergrenze + 1)) + untergrenze;
  ```

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `rand`:

1. **Einfaches Erzeugen einer Zufallszahl:**
   ```c
   #include <stdlib.h>
   #include <stdio.h>

   int main() {
       printf("Zufallszahl: %d\n", rand());
       return 0;
   }
   ```

2. **Zufallszahlen zwischen 1 und 10:**
   ```c
   #include <stdlib.h>
   #include <stdio.h>
   #include <time.h>

   int main() {
       srand(time(NULL));
       for (int i = 0; i < 5; i++) {
           printf("Zufallszahl zwischen 1 und 10: %d\n", (rand() % 10) + 1);
       }
       return 0;
   }
   ```

## Erklärung
Ein häufiges Missverständnis ist, dass `rand` echte Zufallszahlen erzeugt. Tatsächlich generiert `rand` Pseudozufallszahlen, die deterministisch sind, basierend auf einem Startwert (Seed). Wenn `srand` nicht aufgerufen wird, wird der Zufallszahlengenerator standardmäßig mit dem Wert 1 initialisiert, was bedeutet, dass jedes Programm, das `rand` ohne vorherige Initialisierung aufruft, die gleiche Sequenz von Zufallszahlen erzeugt.

Ein weiterer Punkt ist, dass die Qualität der Zufallszahlen von der Implementierung abhängt, und für kryptographische Anwendungen sollten andere Bibliotheken verwendet werden, die sicherere Zufallszahlen erzeugen.

## Einzeilige Zusammenfassung
Die Funktion `rand` in C generiert Pseudozufallszahlen und sollte zusammen mit `srand` zur Initialisierung verwendet werden, um variierende Ergebnisse zu erzielen.