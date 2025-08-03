<!--
Meta Description: # ldiv: Ganzzahlige Division in C ## Synopsis Die Funktion `ldiv` in C dient zur Durchführung der ganzzahligen Division von zwei `long`-Werten und lie...
Meta Keywords: der, ldiv, division, die, rest
-->

# ldiv: Ganzzahlige Division in C

## Synopsis
Die Funktion `ldiv` in C dient zur Durchführung der ganzzahligen Division von zwei `long`-Werten und liefert sowohl das Ergebnis der Division als auch den Rest zurück. Dies ist besonders nützlich, wenn sowohl Quotient als auch Rest benötigt werden.

## Dokumentation
Die Funktion `ldiv` ist Teil der Standardbibliothek `<stdlib.h>` und hat die folgende Signatur:

```c
ldiv_t ldiv(long numer, long denom);
```

### Zweck
`ldiv` wird verwendet, um die ganzzahlige Division von zwei `long`-Werten durchzuführen. Sie gibt ein `ldiv_t`-Struktur zurück, die den Quotienten und den Rest der Division enthält.

### Nutzung
Um `ldiv` zu verwenden, müssen Sie die Header-Datei `<stdlib.h>` einbinden. Hier ist die grundlegende Syntax:

1. **Inkludieren der Header-Datei:**
   ```c
   #include <stdlib.h>
   ```

2. **Verwendung der Funktion:**
   ```c
   ldiv_t result = ldiv(numer, denom);
   ```

   Hierbei ist `numer` der Zähler (Dividend) und `denom` der Nenner (Divisor).

### Rückgabewert
Die Funktion gibt eine `ldiv_t`-Struktur zurück, die zwei Mitglieder enthält:
- `quot`: Der Quotient der Division (`numer / denom`).
- `rem`: Der Rest der Division (`numer % denom`).

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `ldiv`:

### Beispiel 1: Einfache Division
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    long a = 10;
    long b = 3;

    ldiv_t result = ldiv(a, b);
    printf("Quotient: %ld, Rest: %ld\n", result.quot, result.rem);
    return 0;
}
```
**Ausgabe:**
```
Quotient: 3, Rest: 1
```

### Beispiel 2: Negative Zahlen
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    long a = -10;
    long b = 3;

    ldiv_t result = ldiv(a, b);
    printf("Quotient: %ld, Rest: %ld\n", result.quot, result.rem);
    return 0;
}
```
**Ausgabe:**
```
Quotient: -3, Rest: -1
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `ldiv` ist das Verständnis des Verhaltens mit negativen Zahlen. Bei der Division von negativen und positiven Zahlen kann der Rest negativ sein, was von den mathematischen Regeln der ganzzahligen Division abhängt.

### Zusätzliche Hinweise
- `ldiv` sollte nicht mit der normalen Division (z.B. `/`) verwechselt werden, die nur den Quotienten zurückgibt.
- Achten Sie darauf, dass der Nenner `denom` nicht null ist, da dies zu einem Laufzeitfehler führen würde.

## Zusammenfassung in einer Zeile
`ldiv` ist eine Funktion in C, die eine ganzzahlige Division von zwei `long`-Werten durchführt und sowohl den Quotienten als auch den Rest zurückgibt.