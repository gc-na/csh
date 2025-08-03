<!--
Meta Description: # calloc in C: Dynamische Speicherzuweisung für Arrays ## Synopsis `calloc` ist eine Funktion in C, die verwendet wird, um dynamischen Speicher für Ar...
Meta Keywords: calloc, die, der, int, speicher
-->

# calloc in C: Dynamische Speicherzuweisung für Arrays

## Synopsis
`calloc` ist eine Funktion in C, die verwendet wird, um dynamischen Speicher für Arrays zuzuweisen und diesen Speicher gleichzeitig zu initialisieren. Sie ist Teil der Standardbibliothek und ermöglicht eine sichere und effiziente Speicherverwaltung.

## Documentation
Die Funktion `calloc` wird in der `<stdlib.h>`-Bibliothek definiert und hat die folgende Syntax:

```c
void* calloc(size_t nitems, size_t size);
```

### Zweck
`calloc` wird verwendet, um Speicher für ein Array von `nitems` Elementen, wobei jedes Element `size` Bytes groß ist, zu reservieren. Im Gegensatz zu `malloc` initialisiert `calloc` den zugewiesenen Speicher mit Nullwerten.

### Verwendung
Um `calloc` zu verwenden, müssen Sie die Anzahl der Elemente und die Größe der einzelnen Elemente angeben. Der Rückgabewert ist ein Zeiger auf den zugewiesenen Speicherblock oder `NULL`, wenn die Zuweisung fehlschlägt.

### Details
- **Parameter**:
  - `nitems`: Anzahl der Elemente, die zugewiesen werden sollen.
  - `size`: Größe eines einzelnen Elements in Bytes.
  
- **Rückgabewert**: Ein Zeiger auf den Anfang des zugewiesenen Speicherbereichs oder `NULL`, wenn der Speicher nicht zugewiesen werden konnte.

- **Speicherfreigabe**: Der mit `calloc` zugewiesene Speicher sollte mit `free()` freigegeben werden, um Speicherlecks zu vermeiden.

## Examples
Hier sind einige grundlegende Beispiele für die Verwendung von `calloc`:

### Beispiel 1: Zuweisung eines Arrays von Ganzzahlen

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n = 5;
    int *array = (int*) calloc(n, sizeof(int));

    if (array == NULL) {
        printf("Speicherzuweisung fehlgeschlagen\n");
        return 1;
    }

    for (int i = 0; i < n; i++) {
        printf("array[%d] = %d\n", i, array[i]); // Alle Werte sind 0
    }

    free(array);
    return 0;
}
```

### Beispiel 2: Zuweisung eines Arrays von Strukturen

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int id;
    char name[20];
} Student;

int main() {
    int n = 3;
    Student *students = (Student*) calloc(n, sizeof(Student));

    if (students == NULL) {
        printf("Speicherzuweisung fehlgeschlagen\n");
        return 1;
    }

    for (int i = 0; i < n; i++) {
        students[i].id = i + 1; // Initialisierung der IDs
        snprintf(students[i].name, sizeof(students[i].name), "Student %d", i + 1);
    }

    for (int i = 0; i < n; i++) {
        printf("Student ID: %d, Name: %s\n", students[i].id, students[i].name);
    }

    free(students);
    return 0;
}
```

## Explanation
- **Gemeinsame Fallstricke**: 
  - Achten Sie darauf, den Rückgabewert von `calloc` zu überprüfen, um sicherzustellen, dass die Speicherzuweisung erfolgreich war.
  - Die Verwendung von `calloc` kann in einigen Fällen langsamer sein als `malloc`, da der Speicher initialisiert wird.
  
- **Zusätzliche Hinweise**: 
  - `calloc` kann nützlich sein, wenn Sie sicherstellen möchten, dass alle Werte im zugewiesenen Speicher auf Null gesetzt sind, z.B. bei der Initialisierung von Arrays.
  - Es ist wichtig, den zugewiesenen Speicher mit `free()` zu deallokieren, um Speicherlecks zu vermeiden, insbesondere in größeren Programmen.

## One Line Summary
`calloc` ist eine Funktion in C zur dynamischen Zuweisung und Initialisierung von Speicher für Arrays, die sicherstellt, dass alle Werte auf Null gesetzt sind.