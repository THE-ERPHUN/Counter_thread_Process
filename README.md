# Counter_thread_Process

یک اسکریپت ساده پایتون برای مشاهده وضعیت پردازنده (CPU)، فرایندها (Process) و نخ‌ها (Thread) در سیستم.

## امکانات

- نمایش اطلاعات کلی سیستم: سیستم‌عامل، نسخه، نام پردازنده و شناسه فرایند برنامه (PID)
- نمایش تعداد هسته‌های فیزیکی و منطقی CPU
- اندازه‌گیری درصد استفاده کلی از CPU (در بازه یک ثانیه)
- نمایش میزان استفاده از هر هسته منطقی به‌صورت جداگانه
- شمارش تمام فرایندهای در حال اجرا و مجموع نخ‌های آن‌ها
- دسته‌بندی فرایندها بر اساس وضعیت: `Running`، `Sleeping` و سایر وضعیت‌ها
- نمایش ۱۰ فرایندی که بیشترین تعداد نخ را دارند
- چاپ زمان تولید گزارش

## پیش‌نیازها

- Python 3.6 یا بالاتر
- کتابخانه [psutil](https://pypi.org/project/psutil/)

```bash
pip install psutil
```

## نحوه اجرا

```bash
python Counter_thread_Process.py
```

## نمونه خروجی

```
============================================================
Gozaresh vaziyate pardazande va farayandhaye system
============================================================
System عامل: Linux 6.5.0
Name pardazande: x86_64
Shenase farayande barnameye fa'ali: 12345

--- Etelaate CPU ---
Tedade hastehaye fiziki: 4
Tedade hastehaye manteghi: 8

Darsade estefade kolli az CPU: 12.5%

--- Amare farayandha va thread-ha ---
Tedade farayandhaye moshahede-shode: 245
Majmooe threadhaye farayandha: 1320
...

--- 10 farayand ba bishtarin tedade thread ---
PID       Threads   Status         Name
------------------------------------------------------------
...
```

## نکات

- برخی فرایندهای سیستمی ممکن است به دلیل محدودیت دسترسی (`AccessDenied`) شمارش نشوند. برای نتیجه کامل‌تر، اسکریپت را با دسترسی مدیر (Administrator / root) اجرا کنید.
- فرایندهایی که هنگام شمارش بسته شوند به‌طور خودکار نادیده گرفته می‌شوند.
- مقدار `cpu_percent` برای هر فرایند در اولین فراخوانی معمولاً `0.0` است؛ بنابراین در این اسکریپت فقط برای مرتب‌سازی بر اساس تعداد نخ استفاده می‌شود، نه درصد CPU.
- اسکریپت روی ویندوز، لینوکس و macOS اجرا می‌شود (وابسته به پشتیبانی psutil).

## ساختار پروژه

```
.
├── Counter_thread_Process.py
└── README.md
```


<img width="537" height="847" alt="Screenshot 2026-10-28 164452" src="https://github.com/user-attachments/assets/3a836b25-52af-4e4f-8e5c-5eb37eaad415" />
