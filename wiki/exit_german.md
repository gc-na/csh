<!--
Meta Description: # exit in C: Verwendung und Bedeutung ## Synopsis Der `exit` Befehl in C ist eine Funktion, die das Programm sofort beendet und einen Statuscode an da...
Meta Keywords: exit, der, die, funktion, programm
-->

# exit in C: Verwendung und Bedeutung

## Synopsis
Der `exit` Befehl in C ist eine Funktion, die das Programm sofort beendet und einen Statuscode an das Betriebssystem zurückgibt. Diese Funktion wird häufig verwendet, um den Programmfluss zu steuern und sicherzustellen, dass Ressourcen ordnungsgemäß freigegeben werden.

## Dokumentation
Die `exit` Funktion ist Teil der Standard-C-Bibliothek und wird in der Header-Datei `<stdlib.h>` deklariert. Sie hat die folgende Signatur:

```c
void exit(int status);
```

### Zweck
Die Hauptfunktion von `exit` besteht darin, ein Programm zu beenden. Sie ermöglicht es dem Programm, einen Statuscode zurückzugeben, der angibt, ob das Programm erfolgreich ausgeführt wurde oder nicht. Ein Statuscode von `0` signalisiert in der Regel einen erfolgreichen Abschluss, während ein Wert ungleich `0` auf einen Fehler oder eine unerwartete Situation hinweist.

### Verwendung
Um die `exit` Funktion zu verwenden, muss der Header `<stdlib.h>` eingebunden werden. Der Aufruf der Funktion wird normalerweise in Situationen verwendet, in denen das Programm aufgrund eines Fehlers oder einer speziellen Bedingung vorzeitig beendet werden muss.

```c
#include <stdlib.h>

int main() {
    // Erfolgreicher Programmabschluss
    exit(0);
}
```

## Beispiele
### Beispiel 1: Erfolgreiches Beenden
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("Programm erfolgreich gestartet.\n");
    exit(0); // Programm erfolgreich beenden
}
```

### Beispiel 2: Beenden bei Fehler
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int zahl = -1;

    if (zahl < 0) {
        printf("Fehler: Zahl darf nicht negativ sein.\n");
        exit(1); // Programm mit Fehlerstatus beenden
    }

    printf("Zahl ist %d\n", zahl);
    exit(0);
}
```

### Beispiel 3: Ressourcenfreigabe
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *datei = fopen("beispiel.txt", "r");
    if (datei == NULL) {
        printf("Fehler beim Öffnen der Datei.\n");
        exit(1); // Beenden bei Fehler
    }

    // Dateioperationen...

    fclose(datei);
    exit(0); // Erfolgreiches Beenden
}
```

## Erklärung
Ein häufiges Problem beim Einsatz von `exit` ist, dass es alle laufenden Funktionen sofort beendet, ohne die Ausführung von `atexit` registrierten Funktionen abzuwarten. Dies kann zu unerwartetem Verhalten führen, insbesondere wenn Ressourcen oder Speicher nicht ordnungsgemäß freigegeben werden.

Ein weiterer Punkt ist, dass `exit` nicht nur die aktuelle Funktion, sondern das gesamte Programm beendet. Um nur die aktuelle Funktion zu verlassen, sollte `return` verwendet werden. 

Es ist auch wichtig zu beachten, dass `exit` nicht nur in der `main` Funktion verwendet werden kann, sondern in jeder Funktion, die eine Rückgabe an das Betriebssystem erfordert. Bei der Verwendung von `exit` ist es ratsam, die Ausgabe- und Fehlerbehandlungsroutinen vorher abzuschließen, um einen ordnungsgemäßen Programmfluss zu gewährleisten.

## Einzeilensummary
Die `exit` Funktion in C beendet das Programm sofort und gibt einen Statuscode an das Betriebssystem zurück.