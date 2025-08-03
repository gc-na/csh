<!--
Meta Description: # atexit in C: Funktionen zur Registrierung von Aufräumfunktionen ## Synopsis Die Funktion `atexit` in C ermöglicht es Programmierern, Funktionen zu r...
Meta Keywords: atexit, die, werden, von, das
-->

# atexit in C: Funktionen zur Registrierung von Aufräumfunktionen

## Synopsis
Die Funktion `atexit` in C ermöglicht es Programmierern, Funktionen zu registrieren, die beim normalen Beenden eines Programms aufgerufen werden. Dies ist besonders nützlich für das Aufräumen von Ressourcen oder das Speichern von Zuständen.

## Dokumentation
Die `atexit` Funktion ist Teil der Standardbibliothek in C und wird in der Header-Datei `<stdlib.h>` deklariert. Sie hat die folgende Signatur:

```c
int atexit(void (*func)(void));
```

### Zweck
Der Hauptzweck von `atexit` ist es, eine oder mehrere Funktionen zu registrieren, die automatisch ausgeführt werden, wenn das Programm mit `exit()` oder durch das Erreichen des Endes der `main()`-Funktion beendet wird. Dies bietet eine Möglichkeit, sicherzustellen, dass alle notwendigen Aufräumarbeiten durchgeführt werden, bevor das Programm beendet wird.

### Verwendung
Um `atexit` zu verwenden, müssen Sie eine Funktion definieren, die keine Argumente akzeptiert und keinen Rückgabewert hat. Diese Funktion kann dann mit `atexit` registriert werden. Bis zu 32 Funktionen können registriert werden. Die registrierten Funktionen werden in umgekehrter Reihenfolge aufgerufen, wenn das Programm beendet wird.

### Rückgabewert
`atexit` gibt 0 zurück, wenn die Funktion erfolgreich registriert wurde, und einen Wert ungleich 0, wenn ein Fehler aufgetreten ist.

## Beispiele

### Beispiel 1: Einfache Verwendung von atexit
```c
#include <stdio.h>
#include <stdlib.h>

void cleanup() {
    printf("Ressourcen werden freigegeben.\n");
}

int main() {
    if (atexit(cleanup) != 0) {
        perror("Fehler beim Registrieren der Funktion");
        return EXIT_FAILURE;
    }
    printf("Programm läuft.\n");
    return EXIT_SUCCESS;
}
```

### Beispiel 2: Mehrere Funktionen registrieren
```c
#include <stdio.h>
#include <stdlib.h>

void cleanup1() {
    printf("Aufräumfunktion 1 aufgerufen.\n");
}

void cleanup2() {
    printf("Aufräumfunktion 2 aufgerufen.\n");
}

int main() {
    atexit(cleanup1);
    atexit(cleanup2);
    
    printf("Programm läuft.\n");
    return EXIT_SUCCESS;
}
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von `atexit` ist, dass die registrierten Funktionen nicht aufgerufen werden, wenn das Programm durch einen unerwarteten Fehler oder durch einen Aufruf von `exit()` mit einem bestimmten Statuscode beendet wird. Auch das Freigeben von Ressourcen in einem `fork()`-Szenario kann zu unbeabsichtigten Ergebnissen führen, da die Kindprozesse ihre eigenen Aufräumfunktionen benötigen.

Ein weiterer wichtiger Punkt ist, dass Funktionen, die mit `atexit` registriert wurden, nicht aufgerufen werden, wenn das Programm durch einen `abort()`-Aufruf beendet wird.

## Ein-Satz-Zusammenfassung
Die `atexit` Funktion in C ermöglicht die Registrierung von Aufräumfunktionen, die beim regulären Beenden des Programms automatisch aufgerufen werden.