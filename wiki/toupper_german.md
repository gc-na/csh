<!--
Meta Description: # toupper: Großbuchstaben in C umwandeln ## Synopsis Die Funktion `toupper` in C wird verwendet, um ein einzelnes Zeichen in seinen entsprechenden Gro...
Meta Keywords: die, zeichen, toupper, int, funktion
-->

# toupper: Großbuchstaben in C umwandeln

## Synopsis
Die Funktion `toupper` in C wird verwendet, um ein einzelnes Zeichen in seinen entsprechenden Großbuchstaben umzuwandeln, falls es sich um einen Kleinbuchstaben handelt.

## Dokumentation

### Zweck
Die Funktion `toupper` gehört zur Standardbibliothek `<ctype.h>` und wird verwendet, um die Lesbarkeit von Text zu verbessern, indem Kleinbuchstaben in Großbuchstaben umgewandelt werden. Dies ist nützlich in Anwendungen, in denen die Großschreibung von Zeichen eine Rolle spielt, wie z.B. beim Vergleich von Zeichen oder bei der Ausgabe von Text.

### Verwendung
Die Funktion hat die folgende Prototyp-Deklaration:

```c
int toupper(int c);
```

#### Parameter
- `c`: Das Zeichen, das umgewandelt werden soll, übergeben als `int`. Normalerweise wird ein `char`-Wert übergeben, der in einen `int`-Wert umgewandelt wird.

#### Rückgabewert
- Gibt das umgewandelte Zeichen als `int` zurück. Wenn `c` kein Kleinbuchstabe ist, wird `c` unverändert zurückgegeben.

### Header-Datei
Um die `toupper`-Funktion nutzen zu können, muss die Header-Datei `<ctype.h>` eingebunden werden:

```c
#include <ctype.h>
```

## Beispiele

### Beispiel 1: Einfache Umwandlung
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char lowercase = 'a';
    char uppercase = toupper(lowercase);
    printf("Ursprüngliches Zeichen: %c, Umgewandeltes Zeichen: %c\n", lowercase, uppercase);
    return 0;
}
```

### Beispiel 2: Umwandlung mehrerer Zeichen
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[] = "hallo welt!";
    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = toupper(str[i]);
    }
    printf("Umgewandelter String: %s\n", str);
    return 0;
}
```

## Erklärung
- **Kleinbuchstaben**: `toupper` wandelt nur Kleinbuchstaben ('a' bis 'z') in ihre entsprechenden Großbuchstaben ('A' bis 'Z') um. Zeichen, die nicht im Bereich der Kleinbuchstaben liegen, bleiben unverändert. 
- **Nicht-Alphabetische Zeichen**: Zahlen, Leerzeichen und Sonderzeichen werden nicht beeinflusst.
- **Rückgabewert**: Es ist wichtig, den Rückgabewert der Funktion zu beachten, da dieser nicht nur das umgewandelte Zeichen, sondern auch den unveränderten Wert zurückgeben kann.

### Häufige Fallstricke
- **Typkonvertierung**: Stellen Sie sicher, dass der übergebene Parameter ein `int` ist, insbesondere wenn Sie diese Funktion innerhalb einer Schleife oder mit ASCII-Werten verwenden.
- **Nicht definierte Verhalten**: Die Funktion könnte undefiniertes Verhalten zeigen, wenn ein Wert übergeben wird, der nicht im Bereich von `unsigned char` oder `EOF` liegt.

## Zusammenfassung
Die `toupper`-Funktion in C ist eine nützliche Methode zur Umwandlung von Kleinbuchstaben in Großbuchstaben, die eine bessere Handhabung und Lesbarkeit von Text in verschiedenen Anwendungen ermöglicht.