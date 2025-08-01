# بررسی تخصصی آرچ لینوکس، ساخت توزیع‌های لینوکسی، و نقش لینوس توروالدز در پیدایش لینوکس

در این مقاله، به صورت علمی و دقیق بررسی می‌کنیم:

* آرچ لینوکس دقیقاً شامل چه مؤلفه‌هایی است؛
* ساخت آن از ابتدا چقدر پیچیده است؛
* فرآیند ایجاد یک توزیع لینوکسی چیست؛
* لینوس توروالدز دقیقاً چه چیزی ساخت و آن را چگونه منتشر کرد.

---

## 🔍 آرچ لینوکس چیست و شامل چه چیزی است؟

**آرچ لینوکس (Arch Linux)** یک توزیع لینوکس **مینیمالیستی و رولینگ (Rolling Release)** است که بر اساس اصل **KISS (Keep It Simple, Stupid)** ساخته شده. این توزیع برای کاربران حرفه‌ای طراحی شده که می‌خواهند سیستم‌عامل خود را از پایین‌ترین سطح کنترل کنند.

### 🎯 ویژگی‌های کلیدی آرچ:

| ویژگی                               | توضیح                                                              |
| ----------------------------------- | ------------------------------------------------------------------ |
| **مینیمالیستی**                     | بدون برنامه‌های اضافی نصب‌شده – شما تصمیم می‌گیرید چه چیزی نصب شود |
| **رولینگ ریلیز**                    | به‌جای انتشار نسخه‌های جدید، همیشه به‌روز می‌ماند                  |
| **Pacman**                          | مدیر پکیج اختصاصی برای نصب، به‌روزرسانی، و مدیریت نرم‌افزارها      |
| **AUR (Arch User Repository)**      | مخزن پکیج‌های ساخته‌شده توسط کاربران با امکان ساخت از سورس         |
| **سیستم‌عامل خالص لینوکس**          | بدون سفارشی‌سازی زیاد؛ نزدیک به کرنل اصلی                          |
| **عدم استفاده از GUI در نصب اولیه** | تمام فرآیند نصب از طریق CLI (ترمینال) انجام می‌شود                 |

### 📦 اجزای کلیدی که در نصب اولیه Arch وجود دارند:

* **Bootloader (معمولاً GRUB)**
* **Systemd (سیستم مدیریت سرویس‌ها)**
* **Kernel (معمولاً آخرین نسخه stable لینوکس)**
* **Pacman (Package Manager)**
* **Bash یا Zsh (Shell)**
* **Networking Tools (iproute2, dhcpcd یا systemd-networkd)**
* هیچ محیط دسکتاپی یا ابزار گرافیکی به صورت پیش‌فرض وجود ندارد.

---

## 🛠 ساخت آرچ لینوکس از ابتدا چقدر سخت است؟

نصب و پیکربندی آرچ برای تازه‌کاران می‌تواند **چالش‌برانگیز** باشد، زیرا:

* تمام مراحل باید **دستی** انجام شوند: پارتیشن‌بندی، mount، نصب سیستم پایه، تنظیم bootloader، تنظیم locale و شبکه.
* هیچ Installer گرافیکی رسمی ندارد (بر خلاف Ubuntu یا Fedora).
* نیاز به دانش پایه از ساختار لینوکس، مدیریت پکیج، boot process و فایل‌سیستم‌ها دارد.

> با این حال، مستندات رسمی Arch Wiki بسیار کامل و شفاف است. یک کاربر متوسط لینوکس با **صرف چند ساعت مطالعه و تمرین** می‌تواند آن را نصب کند.

---

## 🧱 چگونه یک توزیع لینوکس از صفر ساخته می‌شود؟

اگر کسی بخواهد **توزیع لینوکس شخصی خود** را بسازد، چند مسیر ممکن دارد:

### مسیر ۱: استفاده از توزیع‌های پایه

* **با استفاده از Debian یا Arch یا Gentoo** می‌توان یک توزیع سفارشی ایجاد کرد.
* مثلاً Ubuntu، یک fork از Debian است. Manjaro از Arch منشعب شده.

### مسیر ۲: ساخت توزیع از صفر (Linux From Scratch - LFS)

* با استفاده از پروژه [Linux From Scratch](https://www.linuxfromscratch.org)، می‌توان سیستم‌عامل کامل را فقط با کدنویسی و کامپایل دستی ساخت.
* مراحل:

  1. دانلود و نصب کرنل لینوکس (Linux Kernel)
  2. ساخت کتابخانه libc و ابزارهای پایه (GCC, Bash, Coreutils)
  3. تنظیم فایل‌سیستم و بوت
  4. طراحی ساختار پکیج و نصب ابزارها
  5. تعریف نصب‌کننده یا اسکریپت‌ها

### پیش‌نیازها:

* دانش C و Shell
* درک boot process لینوکس
* تسلط بر cross-compilation و مدیریت وابستگی‌ها

---

## 👨‍🔬 لینوس توروالدز دقیقاً چه چیزی ساخت؟

### ❗ نکته مهم:

**لینوس توروالدز سیستم‌عامل کامل نساخت. او فقط کرنل لینوکس را نوشت.**

در سال 1991، لینوس نسخه اولیه‌ی کرنل را با یک پست معروف در گروه خبری comp.os.minix معرفی کرد:

> *"Hello everybody out there using minix – I’m doing a (free) operating system (just a hobby, won’t be big and professional like gnu)..."*

### 📦 چه چیزی ساخته شد؟

* یک **کرنل ماژولار و قابل حمل** برای سیستم‌های x86
* در ابتدا ساده بود ولی به‌مرور رشد کرد

### 🧩 سیستم‌عامل کامل چطور ساخته شد؟

* کرنل لینوکس به تنهایی کافی نبود.
* **GNU Project** (ریچارد استالمن) ابزارهای زیادی مانند GCC، libc، Bash و ... فراهم کرده بود.
* با ترکیب کرنل لینوکس و ابزارهای GNU، سیستم‌عامل کاملی ساخته شد.

> به همین دلیل برخی (مثل FSF) ترجیح می‌دهند به آن **GNU/Linux** بگویند.

---

## 📥 آیا کرنل لینوکس به اشتراک گذاشته شد؟ نام خاصی داشت؟

بله، کرنل لینوکس:

* از ابتدا به صورت **متن‌باز و رایگان** با مجوز GPLv2 منتشر شد.
* اولین نسخه: 0.01 در سال 1991
* فایل‌های اولیه از طریق FTP در دانشگاه هلسینکی منتشر شدند.
* از ابتدا به‌صورت **Linux Kernel** شناخته می‌شد، و به‌تدریج جامعه‌ی توسعه‌دهنده بزرگی دور آن شکل گرفت.

---

## 🧠 جمع‌بندی نهایی

| سؤال                                  | پاسخ خلاصه                                                    |
| ------------------------------------- | ------------------------------------------------------------- |
| آرچ لینوکس شامل چیست؟                 | سیستم‌عامل مینیمالیستی، با کرنل، سیستم پایه، pacman           |
| نصب آرچ سخت است؟                      | بله، برای تازه‌کارها چالش‌برانگیز است                         |
| ساخت توزیع لینوکس از کجا شروع می‌شود؟ | یا از یک توزیع موجود، یا با Linux From Scratch                |
| لینوس توروالدز چه چیزی ساخت؟          | فقط کرنل لینوکس، نه سیستم‌عامل کامل                           |
| آیا آن را منتشر کرد؟                  | بله، با مجوز GPL از سال 1991 به اشتراک گذاشته شد              |
| نام خاصی داشت؟                        | فقط "Linux Kernel" – سیستم‌عامل کامل با ابزارهای GNU ساخته شد |

---
