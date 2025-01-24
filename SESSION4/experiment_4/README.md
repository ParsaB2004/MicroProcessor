## آزمایش شماره چهار 💡

### گزارش کار و مراحل 📝

در این آزمایش با استفاده از ماژول LCD یک پیام را بر روی صفحه آن چاپ می کنیم.

---

### توصیف کد های برنامه 💻

```cpp
#include <LiquidCrystal.h>  // وارد کردن کتابخانه مخصوص

const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);  // تعیین کردن شماره پین های متصل شده به آردوینو

void setup() {
  lcd.begin(16, 2);     // تعیین کردن تعداد سطر و ستون LCD
}

void loop() {
  lcd.print("Hello World :)");  // چاپ پیام بر روی صفحه
  lcd.setCursor(0, 1);  // حرکت دادن نشانگر بر روی ابتدای خط بعدی
  lcd.print("You are the best");    // چاپ دومین پیام (در خط بعدی)
}
```

---

### تصویر خروجی صفحه نمایش LCD

<br>

<div align="center">
<img src="/media/microprocessor_10.jpg">
</div>

---

### شماتیک مدار 🗺️

<br>

<div align="center">
<img src="/media/schematic_9.jpg" width="600px" height="400px">
</div>
