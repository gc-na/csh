<!--
Meta Description: # tan in C: Die Berechnung der Tangensfunktion ## Synopsis Die Funktion `tan` in C ist Teil der mathematischen Bibliothek und wird verwendet, um den T...
Meta Keywords: tan, der, die, bogenmaß, grad
-->

# tan in C: Die Berechnung der Tangensfunktion

## Synopsis
Die Funktion `tan` in C ist Teil der mathematischen Bibliothek und wird verwendet, um den Tangens eines gegebenen Winkels in Bogenmaß zu berechnen.

## Dokumentation
Die `tan`-Funktion gehört zur C-Standardbibliothek und ist in der Header-Datei `<math.h>` definiert. Sie nimmt einen einzelnen Parameter, der den Winkel in Bogenmaß darstellt, und gibt den Tangenswert dieses Winkels zurück. 

### Zweck
Die Hauptfunktion von `tan` besteht darin, den Tangens eines Winkels zu berechnen, was in vielen mathematischen und physikalischen Anwendungen nützlich ist. Der Tangens ist definiert als das Verhältnis von der Gegenkathete zur Ankathete in einem rechtwinkligen Dreieck.

### Verwendung
Um die `tan`-Funktion zu verwenden, müssen Sie sicherstellen, dass Sie die mathematische Bibliothek einbinden. Hier ist die allgemeine Syntax:

```c
#include <math.h>

double tan(double x);
```

- **Parameter**: 
  - `x`: der Winkel in Bogenmaß.
  
- **Rückgabewert**: 
  - Der Tangenswert des angegebenen Winkels.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung der `tan`-Funktion:

### Beispiel 1: Berechnung des Tangens von 45 Grad

```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 4; // 45 Grad in Bogenmaß
    double result = tan(angle);
    printf("tan(45 Grad) = %f\n", result); // Erwarteter Wert: 1.000000
    return 0;
}
```

### Beispiel 2: Berechnung des Tangens von 90 Grad

```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 2; // 90 Grad in Bogenmaß
    double result = tan(angle);
    printf("tan(90 Grad) = %f\n", result); // Erwarteter Wert: unendlich (Fehler)
    return 0;
}
```

## Erklärung
Bei der Verwendung der `tan`-Funktion sollten einige häufige Fallstricke beachtet werden:

- **Eingabewerte**: Der Eingabewinkel muss in Bogenmaß angegeben werden. Um von Grad in Bogenmaß zu konvertieren, verwenden Sie die Formel: \( \text{Bogenmaß} = \text{Grad} \times \frac{\pi}{180} \).
  
- **Grenzfälle**: Der Tangens ist nicht definiert für Winkel, die \( \frac{\pi}{2} + k\pi \) für ganze Zahlen \( k \) entsprechen, was zu einer Division durch Null führen kann. In solchen Fällen kann das Programm abstürzen oder unvorhersehbare Ergebnisse liefern.

## Zusammenfassung in einem Satz
Die `tan`-Funktion in C berechnet den Tangens eines Winkels in Bogenmaß und ist ein essentielles Werkzeug in mathematischen und physikalischen Berechnungen.