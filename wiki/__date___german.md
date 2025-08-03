<!--
Meta Description: # __DATE__: Verwendung des Datums in C-Programmen ## Synopsis `__DATE__` ist ein vordefiniertes Makro in der Programmiersprache C, das das Datum enthä...
Meta Keywords: das, __date__, der, datum, ist
-->

# __DATE__: Verwendung des Datums in C-Programmen

## Synopsis
`__DATE__` ist ein vordefiniertes Makro in der Programmiersprache C, das das Datum enthält, an dem der Quellcode kompiliert wurde. Dieses Makro ermöglicht Entwicklern, Informationen über den Build-Zeitpunkt direkt im Code zu verwenden.

## Dokumentation
`__DATE__` ist ein vordefiniertes Makro, das von der C-Compiler-Umgebung bereitgestellt wird. Es gibt das aktuelle Datum im Format "Mmm dd yyyy" zurück, wobei "Mmm" der abgekürzte Monat (z.B. Jan, Feb) ist. Es wird häufig verwendet, um Versionsinformationen oder das Erstellungsdatum eines Programms in den Ausgaben oder in der Dokumentation anzuzeigen.

### Verwendung
Das Makro kann in jedem C-Programm ohne zusätzliche Deklarationen verwendet werden:

```c
#include <stdio.h>

int main() {
    printf("Build-Datum: %s\n", __DATE__);
    return 0;
}
```

Wenn das obige Programm kompiliert wird, gibt es das Datum aus, an dem es kompiliert wurde. 

### Details
- **Datentyp**: `__DATE__` ist vom Typ `const char[]`.
- **Format**: "Mmm dd yyyy", wobei:
  - `Mmm` den abgekürzten Monatsnamen darstellt,
  - `dd` den Tag des Monats,
  - `yyyy` das Jahr.
- **Kompilierungszeitpunkt**: Das Datum wird zur Kompilierungszeit festgelegt und ändert sich nicht, solange der Code nicht neu kompiliert wird.

## Beispiele
### Einfaches Beispiel
Hier ist ein einfaches C-Programm, das das Kompilierungsdatum anzeigt:

```c
#include <stdio.h>

int main() {
    printf("Das Programm wurde am %s kompiliert.\n", __DATE__);
    return 0;
}
```

### Verwendung in einer Versionierungsinformation
Sie können `__DATE__` auch nutzen, um die Version Ihres Programms zu dokumentieren:

```c
#include <stdio.h>

#define VERSION "1.0.0"

int main() {
    printf("Version: %s, kompiliert am: %s\n", VERSION, __DATE__);
    return 0;
}
```

## Erklärung
Ein häufiger Stolperstein beim Arbeiten mit `__DATE__` ist, dass es sich um eine Konstante handelt und nicht verändert werden kann. Es wird immer das Datum der letzten Kompilierung angezeigt, nicht das aktuelle Datum. Bei der Verwendung in verschiedenen Umgebungen (z.B. in verschiedenen Zeitzonen) sollte man darauf achten, dass das Datum im Systemstandardformat angezeigt wird.

Zusätzlich ist zu beachten, dass `__DATE__` sich nicht automatisch aktualisiert, wenn der Code nicht neu kompiliert wird. Dies kann zu Verwirrung führen, wenn ein Entwickler nicht erkennt, dass das angezeigte Datum möglicherweise veraltet ist.

## Ein-Satz-Zusammenfassung
`__DATE__` ist ein vordefiniertes Makro in C, das das Datum der letzten Kompilierung im Format "Mmm dd yyyy" zurückgibt und häufig für Versionsinformationen verwendet wird.