<!--
Meta Description: # Die Funktion `getchar` in C: Eingabe von Zeichen aus der Standardeingabe ## Synopsis Die Funktion `getchar` in C ermöglicht es, ein einzelnes Zeiche...
Meta Keywords: getchar, zeichen, der, von, die
-->

# Die Funktion `getchar` in C: Eingabe von Zeichen aus der Standardeingabe

## Synopsis
Die Funktion `getchar` in C ermöglicht es, ein einzelnes Zeichen von der Standardeingabe (normalerweise der Tastatur) zu lesen. Sie ist Teil der Standardbibliothek und wird häufig verwendet, um Benutzereingaben zu verarbeiten.

## Dokumentation
### Zweck
`getchar` ist eine einfache Funktion, die ein Zeichen von der Standardeingabe liest und als `int` zurückgibt. Sie wird oft in Programmen verwendet, bei denen die Eingabe von Zeichen erforderlich ist, wie z.B. bei der Verarbeitung von Benutzereingaben oder beim Erstellen von Textanwendungen.

### Verwendung
Die Funktion wird wie folgt verwendet:

```c
#include <stdio.h>

int getchar(void);
```

**Rückgabewert:**
- Bei erfolgreichem Lesen gibt `getchar` das gelesene Zeichen als `int` zurück.
- Bei Fehlern oder EOF (Ende der Datei) gibt sie `EOF` zurück, das durch die Konstante `EOF` definiert ist.

### Details
- `getchar` entfernt das gelesene Zeichen aus dem Eingabepuffer und wartet auf die nächste Eingabe vom Benutzer.
- Es ist wichtig, den Rückgabewert zu überprüfen, um Fehler oder das Ende der Datei zu erkennen.
- Da die Funktion ein `int` zurückgibt, kann sie auch `EOF` (normalerweise -1) zurückgeben, wodurch die Unterscheidung zwischen gültigen Zeichen und Fehlern ermöglicht wird.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `getchar`:

### Beispiel 1: Einfaches Zeichenecho
```c
#include <stdio.h>

int main() {
    int c;

    printf("Geben Sie ein Zeichen ein: ");
    c = getchar();
    printf("Sie haben eingegeben: %c\n", c);

    return 0;
}
```

### Beispiel 2: Zeichen lesen, bis EOF erreicht wird
```c
#include <stdio.h>

int main() {
    int c;

    printf("Geben Sie Zeichen ein (Strg+D zum Beenden):\n");
    while ((c = getchar()) != EOF) {
        putchar(c);  // Gibt das Zeichen sofort wieder aus
    }

    return 0;
}
```

## Erklärung
Bei der Verwendung von `getchar` sollten einige häufige Fallstricke beachtet werden:

1. **Eingabepuffer**: `getchar` liest nur ein Zeichen auf einmal. Wenn mehrere Zeichen eingegeben werden, bleibt der Rest im Eingabepuffer und wird beim nächsten Aufruf von `getchar` gelesen.
2. **EOF behandeln**: Es ist wichtig, den Rückgabewert von `getchar` zu überprüfen, um festzustellen, ob ein Fehler aufgetreten ist oder das Ende der Datei erreicht wurde. Ignorieren Sie dies, könnte zu unerwartetem Verhalten führen.
3. **Zeichenkodierung**: `getchar` arbeitet mit der Standardzeichencodierung (normalerweise ASCII), stellen Sie sicher, dass Ihre Anwendung dies berücksichtigt.

## Zusammenfassung in einem Satz
Die Funktion `getchar` in C ermöglicht das einfache Lesen eines einzelnen Zeichens von der Standardeingabe und ist ein nützliches Werkzeug für die Verarbeitung von Benutzereingaben.