# [سیستم‌عامل] C Shell (csh) who استفاده: [نمایش کاربران وارد شده]

## Overview
دستور `who` در C Shell (csh) برای نمایش لیست کاربرانی که در حال حاضر وارد سیستم شده‌اند، استفاده می‌شود. این دستور اطلاعاتی از جمله نام کاربر، زمان ورود و ترمینالی که کاربر از آن استفاده می‌کند را نمایش می‌دهد.

## Usage
سینتکس پایه دستور `who` به صورت زیر است:

```
who [options] [arguments]
```

## Common Options
- `-b`: زمان آخرین راه‌اندازی سیستم را نمایش می‌دهد.
- `-q`: فقط نام کاربران را نمایش می‌دهد و تعداد آنها را در انتها نشان می‌دهد.
- `-H`: هدرها را به خروجی اضافه می‌کند.

## Common Examples
- نمایش لیست کاربران وارد شده:
  ```csh
  who
  ```

- نمایش زمان آخرین راه‌اندازی سیستم:
  ```csh
  who -b
  ```

- نمایش فقط نام کاربران و تعداد آنها:
  ```csh
  who -q
  ```

- نمایش لیست کاربران با هدر:
  ```csh
  who -H
  ```

## Tips
- برای مشاهده اطلاعات دقیق‌تر در مورد هر کاربر، می‌توانید از دستور `finger` استفاده کنید.
- اگر به دنبال اطلاعات خاصی هستید، می‌توانید خروجی دستور `who` را با دیگر دستورات مانند `grep` ترکیب کنید.
- برای مشاهده تغییرات در لیست کاربران، می‌توانید دستور `watch` را به کار ببرید تا به‌طور مداوم خروجی `who` را مشاهده کنید.