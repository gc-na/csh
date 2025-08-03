<!--
Meta Description: # mktime in C: Zeitstempel aus strukturierten Zeitdaten erstellen ## Synopsis Die Funktion `mktime` in der Programmiersprache C wird verwendet, um ein...
Meta Keywords: die, der, timeinfo, mktime, struct
-->

# mktime in C: Zeitstempel aus strukturierten Zeitdaten erstellen

## Synopsis
Die Funktion `mktime` in der Programmiersprache C wird verwendet, um einen Zeitstempel (epoch time) aus einer strukturierten Zeitdarstellung zu erzeugen. Sie konvertiert eine `struct tm`-Struktur in einen `time_t`-Wert, der die Anzahl der Sekunden seit dem 1. Januar 1970 (UTC) darstellt.

## Documentation
Die Funktion `mktime` ist Teil der C-Standardbibliothek und wird in `<time.h>` definiert. Sie hat die folgende Signatur:

```c
time_t mktime(struct tm *timeptr);
```

### Zweck
`mktime` wandelt eine lokale Zeit, die in der `struct tm` gespeichert ist, in einen Zeitstempel um. Diese Funktion korrigiert automatisch die Werte in der `struct tm`, falls diese ungültig sind (z.B. wenn der Monat 13 oder der Tag 32 angegeben wird).

### Verwendung
Um die Funktion `mktime` zu verwenden, müssen Sie die Zeit in einer `struct tm`-Struktur definieren. Die Struktur enthält Felder für Jahr, Monat, Tag, Stunde, Minute und Sekunde. Nach der Aufruf von `mktime` erhalten Sie den entsprechenden Zeitstempel.

### Details
- **Rückgabewert**: `mktime` gibt einen `time_t`-Wert zurück. Bei einem Fehler wird `-1` zurückgegeben.
- **Änderungen an der Struktur**: Die Funktion kann die `tm`-Struktur, die übergeben wird, modifizieren, um die korrekten Werte zu reflektieren.
- **Zeitzonen**: `mktime` berücksichtigt die lokale Zeitzone des Systems, auf dem das Programm läuft.

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung von `mktime` in C:

### Beispiel 1: Einfache Umwandlung
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo = {0};
    timeinfo.tm_year = 2023 - 1900; // Jahr seit 1900
    timeinfo.tm_mon = 10 - 1;        // Monat von 0 bis 11
    timeinfo.tm_mday = 15;           // Tag des Monats
    timeinfo.tm_hour = 12;           // Stunde
    timeinfo.tm_min = 0;             // Minute
    timeinfo.tm_sec = 0;             // Sekunde

    time_t timestamp = mktime(&timeinfo);
    printf("Zeitstempel: %ld\n", (long)timestamp);
    return 0;
}
```

### Beispiel 2: Automatische Korrektur
```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm timeinfo = {0};
    timeinfo.tm_year = 2023 - 1900;
    timeinfo.tm_mon = 2; // März
    timeinfo.tm_mday = 32; // Ungültiger Tag, wird korrigiert
    timeinfo.tm_hour = 12;
    timeinfo.tm_min = 0;
    timeinfo.tm_sec = 0;

    time_t timestamp = mktime(&timeinfo);
    printf("Korrigierter Zeitstempel: %ld\n", (long)timestamp);
    return 0;
}
```

## Explanation
Ein häufiger Fehler bei der Verwendung von `mktime` ist das Missverständnis der Monate. Beachten Sie, dass Monate in der `struct tm` von 0 bis 11 gezählt werden (0 = Januar, 11 = Dezember). Ein weiterer Punkt ist, dass die `tm_year`-Angabe die Anzahl der Jahre seit 1900 darstellt. Daher müssen Sie 1900 von dem aktuellen Jahr abziehen.

Zusätzlich kann es bei der Umwandlung von Zeiten, die in der Sommerzeit liegen, zu unerwarteten Ergebnissen kommen. Es ist wichtig, die lokale Zeitzone und die Sommerzeit zu berücksichtigen, wenn Sie `mktime` verwenden.

## One Line Summary
Die Funktion `mktime` in C konvertiert eine `struct tm` in einen Zeitstempel und berücksichtigt dabei lokale Zeitzonen und automatische Korrekturen.