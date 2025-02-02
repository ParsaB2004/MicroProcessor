## گزارش کار پروژه نمایش اعداد و حروف بر روی نمایشگر هفت قسمتی (Seven-Segment Display)

**مقدمه:**

این گزارش، مستندات مربوط به پروژه نمایش اعداد 0 تا 9 و حروف A تا F بر روی یک نمایشگر هفت قسمتی (Seven-Segment Display) با استفاده از برد آردوینو را ارائه می‌دهد. هدف این پروژه، آشنایی با نحوه کنترل نمایشگرهای هفت قسمتی و پیاده‌سازی یک سیستم نمایش ساده با استفاده از کدنویسی آردوینو است.

**شرح پروژه:**

در این پروژه، از یک آرایه دو بعدی به نام `Seguence` برای ذخیره الگوهای روشن و خاموش شدن هر قسمت از نمایشگر برای نمایش اعداد و حروف مورد نظر استفاده شده است. هر سطر از این آرایه، نمایانگر یک عدد یا حرف است و هر ستون آن، وضعیت یکی از هفت قسمت نمایشگر (a تا g) را مشخص می‌کند. مقدار 1 به معنای روشن بودن و مقدار 0 به معنای خاموش بودن قسمت مربوطه است.

**کد برنامه:**

کد برنامه به زبان C++ برای آردوینو به شرح زیر است:

```cpp
int Seguence[][7]={
  {1,1,1,1,1,1,0}, //0
  {0,1,1,0,0,0,0}, //1
  {1,1,0,1,1,0,1}, //2
  {1,1,1,1,0,0,1}, //3
  {0,1,1,0,0,1,1}, //4
  {1,0,1,1,0,1,1}, //5
  {1,0,1,1,1,1,1}, //6
  {1,1,1,0,0,0,0}, //7
  {1,1,1,1,1,1,1}, //8
  {1,1,1,1,0,1,1}, //9
  {1,1,1,0,1,1,1}, //A
  {0,0,1,1,1,1,1}, //b
  {1,0,0,1,1,1,0}, //c
  {0,1,1,1,1,0,1}, //d
  {1,0,0,1,1,1,1}, //E
  {1,0,0,0,1,1,1}  //F
};

void set1(int number){
  for(int i = 0 ; i<7 ; i++){
    digitalWrite(1+i , Seguence[number][i]);
  }
}

void setup() {
  for(int i = 1 ; i<8; i++){
    pinMode(i , OUTPUT);
  }
}

void loop() {
  for(int i = 0 ; i <16 ; i++){
    set1(i);
    delay(1000);
  }
}
```

**توضیح کد:**

*   **آرایه `Seguence`:** این آرایه الگوهای نمایش اعداد و حروف را ذخیره می‌کند.
*   **تابع `set1(int number)`:** این تابع با دریافت شماره عدد یا حرف مورد نظر، وضعیت پین‌های خروجی آردوینو را بر اساس الگوی ذخیره شده در آرایه `Seguence` تنظیم می‌کند.
*   **تابع `setup()`:** این تابع در ابتدای اجرای برنامه فراخوانی می‌شود و پین‌های 1 تا 7 آردوینو را به عنوان خروجی تعریف می‌کند.
*   **تابع `loop()`:** این تابع به صورت مداوم اجرا می‌شود و با استفاده از یک حلقه `for`، اعداد 0 تا 15 (معادل 0 تا 9 و A تا F) را به ترتیب نمایش می‌دهد و سپس یک ثانیه مکث می‌کند.

**اتصالات سخت افزاری:**

اتصالات سخت افزاری به صورت زیر است:

*   هر یک از هفت قسمت نمایشگر (a تا g) به یک پین دیجیتال آردوینو (به ترتیب از پین 1 تا 7) متصل می‌شود.
*   پین‌های نمایشگر باید از طریق یک مقاومت محدود کننده جریان (معمولا 220 اهم) به پین‌های آردوینو متصل شوند تا از آسیب دیدن نمایشگر و آردوینو جلوگیری شود. (این در کد ذکر نشده اما بسیار مهم است)
*   پین مشترک نمایشگر (Common Cathode یا Common Anode) به زمین (GND) یا منبع تغذیه (VCC) متصل می‌شود، بسته به نوع نمایشگر. (در کد نوع نمایشگر مشخص نشده و باید در عمل مشخص باشد)

**نتایج:**

با اجرای این برنامه، اعداد 0 تا 9 و حروف A تا F به ترتیب و با فاصله یک ثانیه بر روی نمایشگر هفت قسمتی نمایش داده می‌شوند.

**تصاویر:**
![](https://github.com/vahidseyyedi/microProcessor/blob/main/06%20Laboratory/L_Report_01/src/Untitled%20Sketch_bb.jpg)
![](https://github.com/vahidseyyedi/microProcessor/blob/main/06%20Laboratory/L_Report_01/src/photo_2024-11-10_23-00-07.jpg)

**نتیجه گیری:**

این پروژه نشان داد که چگونه می‌توان با استفاده از آردوینو و یک آرایه ساده، نمایشگر هفت قسمتی را برای نمایش اعداد و حروف کنترل کرد. این روش، پایه‌ای برای پروژه‌های پیچیده‌تر با استفاده از نمایشگرهای هفت قسمتی است.
