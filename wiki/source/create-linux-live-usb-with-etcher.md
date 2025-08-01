# چگونه یک لایو USB لینوکس با ابزار BalenaEtcher بسازیم؟

## مقدمه

یکی از رایج‌ترین روش‌های نصب یا اجرای سیستم‌عامل لینوکس بدون تغییر در هارد دیسک، استفاده از **لایو USB** است. برای ساخت چنین فلش‌ درایوی، ابزارهای مختلفی وجود دارد که یکی از ساده‌ترین و پرطرفدارترین آن‌ها **BalenaEtcher** است. این ابزار، رایگان، متن‌باز و چندسکویی (Windows, macOS, Linux) بوده و روند ساخت لایو USB را بسیار ساده می‌کند. در این مقاله، مراحل ساخت لایو USB لینوکس با Etcher به‌صورت گام‌به‌گام توضیح داده می‌شود.

---

## پیش‌نیازها

- یک فلش USB با حداقل **4 گیگابایت فضای خالی** (8 گیگابایت یا بیشتر پیشنهاد می‌شود)
- فایل **ISO** از توزیع لینوکس مورد نظر (مثل Ubuntu، Fedora یا Debian)
- نرم‌افزار **BalenaEtcher** (قابل دریافت از [balena.io/etcher](https://www.balena.io/etcher/))

---

## مراحل ساخت لایو USB لینوکس با Etcher

### 1. دریافت و نصب BalenaEtcher

- به وب‌سایت رسمی Etcher بروید:  
  [https://www.balena.io/etcher/](https://www.balena.io/etcher/)
- نسخه مناسب سیستم‌عامل خود را دانلود کنید:
  - Windows: فایل نصب با پسوند `.exe`
  - macOS: فایل `.dmg`
  - Linux: فایل `.AppImage`
- فایل دانلودشده را اجرا کرده و برنامه را نصب یا مستقیماً اجرا کنید (در Linux، لازم است به فایل AppImage مجوز اجرا داده شود).

---

### 2. اجرای Etcher و اتصال فلش

- فلش USB را به رایانه متصل کنید.
- Etcher را اجرا نمایید. رابط کاربری Etcher بسیار ساده و شامل سه مرحله اصلی است:

---

### 3. انتخاب فایل ISO لینوکس

- در مرحله اول، روی **"Flash from file"** کلیک کنید.
- فایل ISO توزیع لینوکس مورد نظر را انتخاب کنید (مثلاً `ubuntu-22.04-desktop-amd64.iso`).

---

### 4. انتخاب درایو فلش

- Etcher به‌طور خودکار درایو USB متصل را شناسایی می‌کند.
- اگر بیش از یک دستگاه USB دارید، روی **"Change"** کلیک کرده و درایو صحیح را انتخاب کنید.
> ⚠️ هشدار: همه داده‌های موجود در فلش پاک خواهد شد.

---

### 5. آغاز فرایند نوشتن (Flash)

- روی دکمه **"Flash!"** کلیک کنید.
- Etcher اکنون فایل ISO را روی USB می‌نویسد و در پایان، اعتبارسنجی (Verify) انجام می‌دهد تا مطمئن شود عملیات با موفقیت انجام شده است.

---

### 6. پایان و استفاده از لایو USB

- پس از پایان عملیات، پیام "Flash Complete" نمایش داده می‌شود.
- اکنون می‌توانید سیستم را ریستارت کرده و از طریق BIOS/UEFI، بوت از USB را انتخاب کنید تا سیستم‌عامل لینوکس به‌صورت لایو اجرا شود.

---

## نکات مهم

- اگر فلش درایو شناسایی نشد، مطمئن شوید که به‌درستی متصل است یا آن را مجدداً وارد کنید.
- فایل ISO باید از منابع رسمی توزیع لینوکس دریافت شود تا از صحت و امنیت آن اطمینان حاصل شود.
- اگر بوت از USB انجام نمی‌شود، باید اولویت بوت را در تنظیمات BIOS/UEFI تغییر دهید.

---

## نتیجه‌گیری

ساخت یک لایو USB لینوکس با استفاده از BalenaEtcher فرآیندی سریع، ساده و قابل‌اعتماد است. این ابزار برای کاربران مبتدی تا حرفه‌ای طراحی شده و به شما امکان می‌دهد به‌آسانی توزیع دلخواه لینوکس را امتحان، نصب یا استفاده اضطراری انجام دهید. یک فلش‌ درایو لایو می‌تواند ابزاری مفید در آموزش، تست و تعمیر سیستم‌ها باشد.

---
