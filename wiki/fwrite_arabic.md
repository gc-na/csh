<!--
Meta Description: # fwrite في لغة C: كيفية استخدامه لتخزين البيانات في الملفات ## ملخص تُستخدم دالة `fwrite` في لغة C لكتابة البيانات إلى ملف. توفر هذه الدالة وسيلة فعا...
Meta Keywords: file, البيانات, fwrite, إلى, elements_written
-->

# fwrite في لغة C: كيفية استخدامه لتخزين البيانات في الملفات

## ملخص
تُستخدم دالة `fwrite` في لغة C لكتابة البيانات إلى ملف. توفر هذه الدالة وسيلة فعالة لتخزين كميات كبيرة من البيانات بشكلٍ متسلسل، مما يجعلها مفيدة في معالجة الملفات الثنائية.

## الوثائق
### الغرض
تعمل دالة `fwrite` على كتابة محتوى مصفوفة من البيانات إلى ملف معين، مما يسهل تخزين البيانات في شكل ثنائي.

### الاستخدام
تكون صيغتها الأساسية كالتالي:
```c
size_t fwrite(const void *ptr, size_t size, size_t count, FILE *stream);
```

### المعاملات
- `ptr`: مؤشر إلى البيانات التي ترغب في كتابتها.
- `size`: حجم كل عنصر (بالبايت).
- `count`: عدد العناصر التي ترغب في كتابتها.
- `stream`: مؤشر إلى كائن الملف الذي سيتم الكتابة إليه.

### القيمة المرجعة
ترجع الدالة `fwrite` عدد العناصر التي تم كتابتها بنجاح. إذا كان هذا العدد أقل من `count`، فقد يشير ذلك إلى حدوث خطأ.

## أمثلة
### مثال بسيط
```c
#include <stdio.h>

int main() {
    FILE *file;
    int numbers[] = {1, 2, 3, 4, 5};
    size_t elements_written;

    file = fopen("data.bin", "wb");
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }

    elements_written = fwrite(numbers, sizeof(int), 5, file);
    if (elements_written < 5) {
        perror("Error writing to file");
    }

    fclose(file);
    return 0;
}
```

### مثال مع معالجة الأخطاء
```c
#include <stdio.h>

int main() {
    FILE *file;
    float values[] = {3.14, 1.59, 2.65};
    size_t elements_written;

    file = fopen("values.bin", "wb");
    if (file == NULL) {
        perror("Unable to open file");
        return 1;
    }

    elements_written = fwrite(values, sizeof(float), 3, file);
    if (elements_written != 3) {
        perror("Failed to write all data");
    }

    fclose(file);
    return 0;
}
```

## الشرح
### الأخطاء الشائعة
- **عدم فتح الملف بشكل صحيح**: تأكد دائمًا من أن الملف قد تم فتحه بنجاح قبل محاولة الكتابة.
- **عدم استخدام الصيغة الصحيحة**: تأكد من أن حجم البيانات وعددها يتطابق مع ما تريد كتابته.
- **فشل الكتابة**: قد يحدث فشل في الكتابة إذا كان هناك مشكلة في القرص أو إذا كانت الذاكرة ممتلئة.

### ملاحظات إضافية
- عند كتابة البيانات، تأكد من أن تنسيق البيانات متوافق مع التطبيق الذي سيقوم بقراءة هذه البيانات لاحقًا.
- استخدام `fwrite` لكتابة الملفات الثنائية يمكن أن يكون أسرع من استخدام `fprintf` للملفات النصية.

## ملخص جملة واحدة
`fwrite` هي دالة في لغة C تُستخدم لكتابة كميات كبيرة من البيانات إلى ملف بشكلٍ فعال.