<!--
Meta Description: # Der Datentyp "int" in C: Grundlagen und Anwendung ## Synopsis Der Datentyp `int` in der Programmiersprache C ist der grundlegende Ganzzahltyp, der z...
Meta Keywords: int, der, ist, sie, und
-->

# Der Datentyp "int" in C: Grundlagen und Anwendung

## Synopsis
Der Datentyp `int` in der Programmiersprache C ist der grundlegende Ganzzahltyp, der zur Speicherung und Manipulation von ganzzahligen Werten verwendet wird.

## Dokumentation
Der `int`-Datentyp ist einer der am häufigsten verwendeten Datentypen in C. Er repräsentiert eine Ganzzahl und kann sowohl positive als auch negative Werte speichern. Standardmäßig hat ein `int`-Wert in C je nach Plattform (32-Bit oder 64-Bit) eine Größe von 2 oder 4 Byte, was bedeutet, dass er typischerweise Werte im Bereich von -32.768 bis 32.767 (bei 16-Bit) oder -2.147.483.648 bis 2.147.483.647 (bei 32-Bit) darstellen kann.

### Verwendung
Um eine Variable vom Typ `int` zu deklarieren, verwenden Sie die folgende Syntax:
```c
int variable_name;
```
Sie können der Variable auch einen Wert zuweisen:
```c
int a = 10;
```
Es ist auch möglich, mehrere Variablen in einer Zeile zu deklarieren:
```c
int x = 5, y = 10, z = 15;
```

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung des `int`-Datentyps:

1. **Einfache Deklaration und Initialisierung**:
   ```c
   #include <stdio.h>

   int main() {
       int zahl = 25;
       printf("Die Zahl ist: %d\n", zahl);
       return 0;
   }
   ```

2. **Arithmetische Operationen**:
   ```c
   #include <stdio.h>

   int main() {
       int a = 10;
       int b = 5;
       int summe = a + b;
       printf("Die Summe ist: %d\n", summe);
       return 0;
   }
   ```

3. **Benutzerinteraktion**:
   ```c
   #include <stdio.h>

   int main() {
       int eingabe;
       printf("Bitte geben Sie eine ganze Zahl ein: ");
       scanf("%d", &eingabe);
       printf("Sie haben %d eingegeben.\n", eingabe);
       return 0;
   }
   ```

## Erklärung
Ein häufiges Problem bei der Verwendung von `int` ist der Überlauf. Wenn Sie versuchen, einen Wert zu speichern, der außerhalb des zulässigen Bereichs für `int` liegt, kann es zu unerwarteten Ergebnissen kommen. Außerdem sollten Sie sich der Unterschiede zwischen `int`, `short`, `long` und `long long` bewusst sein, da diese unterschiedliche Speichergrößen und Wertebereiche haben können.

Ein weiteres wichtiges Konzept ist die Verwendung von Vorzeichen. Ein `int` ist standardmäßig vorzeichenbehaftet, was bedeutet, dass er sowohl positive als auch negative Werte speichern kann. Wenn Sie nur nicht-negative Werte speichern möchten, können Sie `unsigned int` verwenden, um den Wertebereich zu erweitern.

## Zusammenfassung in einem Satz
Der `int`-Datentyp in C ist ein grundlegender, vorzeichenbehafteter Ganzzahltyp, der für die Speicherung und Durchführung von Berechnungen mit ganzzahligen Werten verwendet wird.