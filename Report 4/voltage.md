
# نام آزمایش :
 کاعش و افزایش ولتاژ با چرخاندن پتانسیومتر

## هدف :
هدف از این آزمایش، آشنایی با نحوه خواندن مقادیر آنالوگ از یک پین آنالوگ آردوینو و تبدیل آن به ولتاژ واقعی است. همچنین، نمایش این مقدار بر روی مانیتور سریال به منظور بررسی و عیب‌یابی مدارها کاربرد دارد.

## وسایل مورد نیاز :
* 1 بورد اردینو
* 2 برد بورد
* 3 کابل  USB  برای اتصال بورد اردینو به کامپیوتر
* 4 پتانسیومتر 


  ## شرح آزمایش :
 در این آزمایش، یک پتانسیومتر به یک پین آنالوگ آردوینو متصل می‌شود. 
 با تغییر مقاومت پتانسیومتر، ولتاژ ورودی به پین آنالوگ تغییر می‌کند.
 آردوینو این ولتاژ را خوانده و به یک عدد دیجیتال تبدیل می‌کند. 
 سپس این عدد دیجیتال به ولتاژ واقعی تبدیل شده و بر روی مانیتور سریال نمایش داده می‌شود.

 

    ## تفسیر کد:
       * تعریف پایه‌ها و متغیرها: پین ۹ به عنوان خروجی (برای LED) و A0 به عنوان ورودی آنالوگ تعریف می‌شود. متغیر val برای ذخیره مقدار خوانده شده از پین آنالوگ استفاده می‌شود.
       * خواندن مقدار آنالوگ: تابع analogRead(A0) مقدار آنالوگ را از پین A0 می‌خواند و در متغیر val ذخیره می‌کند.
       * تبدیل به ولتاژ: با ضرب مقدار خوانده شده در 5.0/1023، مقدار آنالوگ به ولتاژ تبدیل می‌شود (با فرض ولتاژ تغذیه 5 ولت).
       * نمایش بر روی سریال: مقدار ولتاژ محاسبه شده بر روی مانیتور سریال نمایش داده می‌شود.



 
  ## کد آزمایش :
void setup() {

Serial.begin(9600);

}

void loop() {

int raw = analogRead(A0);

float voltage = raw * ( 5.0 / 1023.0 );


Serial.println("voltage:  ");

Serial.println(voltage);

delay(2000);

}


 ## شماتیک مدار:
![توضیح تصویر](https://github.com/Rahel12384/Microprocessor-4/blob/main/Report%204/333.jpg)



## خروجی آزمایش:
![alt text](https://github.com/Rahel12384/Microprocessor-4/blob/main/Report%204/1736186096061.mp4)

  
## نتیجه گیری:
در این آزمایش، با موفقیت توانستیم ولتاژ آنالوگ ورودی به آردوینو را اندازه‌گیری کرده و بر روی مانیتور سریال نمایش دهیم.
این آزمایش پایه برای بسیاری از پروژه‌های آردوینو است که به خواندن مقادیر آنالوگ از سنسورها نیاز دارند.
