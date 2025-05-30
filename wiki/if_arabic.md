# [نظام التشغيل] C Shell (csh) if: تنفيذ الشروط

## Overview
يستخدم أمر `if` في C Shell (csh) لتقييم الشروط وتنفيذ الأوامر بناءً على نتيجة هذا التقييم. يسمح لك هذا الأمر بتنفيذ كود معين فقط إذا كانت الشروط المحددة صحيحة.

## Usage
تكون الصيغة الأساسية لأمر `if` كما يلي:

```
if (condition) then
    command
endif
```

## Common Options
- `then`: يستخدم لتحديد بداية الكود الذي سيتم تنفيذه إذا كانت الشرط صحيحًا.
- `endif`: يستخدم لإنهاء جملة الشرط.

## Common Examples
- **مثال 1: التحقق من وجود ملف**
```csh
if (-e filename.txt) then
    echo "الملف موجود"
endif
```

- **مثال 2: التحقق من قيمة متغير**
```csh
set var = 10
if ($var > 5) then
    echo "القيمة أكبر من 5"
endif
```

- **مثال 3: استخدام شرط مركب**
```csh
if (-e filename.txt && -r filename.txt) then
    echo "الملف موجود وقابل للقراءة"
endif
```

## Tips
- تأكد من استخدام الأقواس بشكل صحيح حول الشروط.
- استخدم التعليقات لتوضيح الشروط المعقدة.
- اختبر الشروط البسيطة أولاً قبل الانتقال إلى الشروط الأكثر تعقيدًا.