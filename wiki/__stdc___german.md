<!--
Meta Description: # __STDC__: Der Standard-Definition für die C-Programmiersprache ## Synopsis `__STDC__` ist ein vordefiniertes Makro in der C-Programmiersprache, das ...
Meta Keywords: der, __stdc__, ist, compiler, unterstützt
-->

# __STDC__: Der Standard-Definition für die C-Programmiersprache

## Synopsis
`__STDC__` ist ein vordefiniertes Makro in der C-Programmiersprache, das angibt, ob der Compiler den ANSI C Standard unterstützt.

## Dokumentation
Das Makro `__STDC__` ist ein zentraler Bestandteil der C-Programmierung, das zur Identifikation der Konformität eines Compilers mit dem ANSI C Standard verwendet wird. Es wird automatisch vom Compiler definiert, wenn er den Standard C (auch bekannt als C89 oder C90) unterstützt. 

### Zweck
Der Hauptzweck von `__STDC__` besteht darin, Programmierern zu ermöglichen, ihren Code so zu gestalten, dass er portabel bleibt und die Standardkonformität sichergestellt ist. 

### Verwendung
Um die Konformität eines Compilers zu überprüfen, kann das Makro in bedingten Kompilierungsanweisungen verwendet werden. Beispielsweise kann man Code schreiben, der nur dann kompiliert wird, wenn der Compiler den Standard unterstützt. 

### Details
- Der Wert von `__STDC__` ist immer eine positive Ganzzahl, typischerweise `1`, wenn der Standard unterstützt wird.
- Wenn der Compiler eine erweiterte Version von C unterstützt, kann der Wert von `__STDC__` ebenfalls vorhanden sein, aber es sind zusätzliche Makros erforderlich, um spezifische Erweiterungen zu identifizieren.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `__STDC__`:

```c
#include <stdio.h>

int main() {
    #ifdef __STDC__
        printf("Dieser Compiler unterstützt ANSI C.\n");
    #else
        printf("Dieser Compiler unterstützt kein ANSI C.\n");
    #endif
    return 0;
}
```

In diesem Beispiel prüft der Code, ob das Makro `__STDC__` definiert ist und gibt eine entsprechende Nachricht aus.

## Erklärung
Ein häufiges Problem bei der Verwendung von `__STDC__` ist das Fehlen des Makros in nicht-standardmäßigen Compilern oder bei veralteten C-Compilern. Dies kann zu Missverständnissen führen, da Programmierer möglicherweise fälschlicherweise annehmen, dass ihr Compiler ANSI C unterstützt, nur weil der Code nicht kompiliert wird.

Ein weiterer Punkt ist, dass einige Compiler spezifische Erweiterungen unterstützen, die nicht Teil des ANSI C Standards sind. In solchen Fällen ist es wichtig, zusätzliche Makros wie `__STDC_NO_VLA__` oder `__STDC_NO_COMPLEX__` zu verwenden, um die Unterstützung von bestimmten C-Funktionen zu überprüfen.

## Einzeilensummary
`__STDC__` ist ein vordefiniertes Makro in C, das die Konformität eines Compilers mit dem ANSI C Standard angibt.