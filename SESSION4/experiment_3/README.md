## آزمایش شماره سه 💡

### گزارش کار و مراحل 📝

در این جا می خواهیم حالتی را پیاده کنیم که هر بار با فشار دادن کلید، یکی از لامپ های LED به طور تصادفی روشن شود. بنابراین باید از ساز و کار های تولید عدد رندوم استفاده کنیم.

---

### توصیف کد های برنامه 💻

```cpp
#define key1 digitalRead(A0)
int btn = A0;

void setup() {
  Serial.begin(9600);
  pinMode(A0, INPUT);   // مشخص کردن پین های خروجی برای 6 عدد LED
  for (int i = 8; i < 14; i++) {
    pinMode(i, OUTPUT);
  }
  randomSeed(analogRead(btn));  // افزایش ضریب اطمینان پذیری اعداد رندوم
}

void loop() {
  if (key1 == 0) {
    for (int i = 8; i < 14; i++) {
      digitalWrite(i, LOW);     // هر بار کلید فشار داده شد ابتدا یکبار تمام LED ها را خاموش می کنیم
    }
    int randomNum = random(8, 14);  // تولید یک عدد رندوم بر اساس شماره پایه LED ها
    digitalWrite(randomNum, HIGH);
    Serial.println(randomNum-7);
    delay(500);
  }
}
```

---

### شرح کارکرد مدار به صورت ویدیویی 🖼️

<br>

<div align="center">
<img src="/media/microprocessor_9.gif">
</div>

---

### شماتیک مدار 🗺️

<br>

<div align="center">
<img src="/media/schematic_8.jpg" width="600px" height="300px">
</div>
