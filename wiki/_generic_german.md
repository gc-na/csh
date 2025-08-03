<!--
Meta Description: # _Generic in C: Der Schlüssel zur Typunabhängigkeit ## Synopsis Der _Generic Operator in C ermöglicht eine typunabhängige Programmierung, indem er ei...
Meta Keywords: der, _generic, ist, typ, die
-->

# _Generic in C: Der Schlüssel zur Typunabhängigkeit

## Synopsis
Der _Generic Operator in C ermöglicht eine typunabhängige Programmierung, indem er eine Funktion oder einen Ausdruck basierend auf dem Datentyp seiner Argumente auswählt. Dies führt zu flexiblerem und wartbarem Code.

## Dokumentation

### Zweck
Der _Generic Operator ist ein Teil des C11 Standards und dient dazu, eine Auswahl von verschiedenen Ausdrücken basierend auf dem Typ eines gegebenen Arguments zu ermöglichen. Er ist besonders nützlich in Situationen, in denen Sie eine Funktion generisch gestalten möchten, sodass sie mit verschiedenen Datentypen arbeiten kann.

### Verwendung
Die allgemeine Syntax von _Generic ist wie folgt:

```c
_Generic(expression, type1: result1, type2: result2, ..., default: default_result)
```

- **expression**: Der Ausdruck, dessen Typ bestimmt werden soll.
- **type1, type2, ...**: Die Datentypen, die überprüft werden.
- **result1, result2, ...**: Die Ergebnisse, die zurückgegeben werden, wenn der entsprechende Typ gefunden wird.
- **default**: Ein optionaler Standardwert, der zurückgegeben wird, wenn kein Typ übereinstimmt.

### Details
- Der _Generic Operator wird zur Compile-Zeit ausgewertet, was bedeutet, dass der Compiler den Typ des Arguments zur Compile-Zeit bestimmen muss.
- Ein _Generic Ausdruck muss in einem Kontext verwendet werden, der einen Wert erwartet (z. B. bei der Zuweisung oder Rückgabe).

## Beispiele

### Beispiel 1: Einfache Typauswahl
```c
#include <stdio.h>

#define get_type(x) _Generic((x), \
    int: "Integer", \
    float: "Float", \
    double: "Double", \
    default: "Unbekannt")

int main() {
    printf("Der Typ von 5 ist: %s\n", get_type(5));         // Ausgabe: Integer
    printf("Der Typ von 5.0 ist: %s\n", get_type(5.0));     // Ausgabe: Double
    printf("Der Typ von 5.0f ist: %s\n", get_type(5.0f));   // Ausgabe: Float
    return 0;
}
```

### Beispiel 2: Verwendung in einer Funktion
```c
#include <stdio.h>

void print_value(void *value, int type) {
    switch(type) {
        case 0: // int
            printf("Wert: %d\n", *(int*)value);
            break;
        case 1: // float
            printf("Wert: %f\n", *(float*)value);
            break;
        case 2: // double
            printf("Wert: %lf\n", *(double*)value);
            break;
        default:
            printf("Unbekannter Typ\n");
            break;
    }
}

#define print(value) _Generic((value), \
    int*: print_value(value, 0), \
    float*: print_value(value, 1), \
    double*: print_value(value, 2), \
    default: printf("Unbekannter Typ\n"))

int main() {
    int a = 10;
    float b = 5.5f;
    double c = 3.14;

    print(&a);
    print(&b);
    print(&c);
    return 0;
}
```

## Erklärung
Ein häufiger Stolperstein beim Einsatz von _Generic ist die korrekte Verwendung der Typen. Es ist essenziell, dass die Typen exakt angegeben werden, da _Generic typgenau ist. Falsche Typen führen zu Compiler-Fehlern. Außerdem sollte darauf geachtet werden, dass _Generic nicht in jedem Kontext anwendbar ist; er funktioniert nur in Ausdrücken, die einen Wert zurückgeben.

## Ein-Satz-Zusammenfassung
Der _Generic Operator in C ermöglicht die Auswahl von Ausdrücken basierend auf Datentypen zur Unterstützung generischer Programmierung.