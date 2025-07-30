# 📦 همه چیز درباره‌ی پکیج منیجرهای لینوکس، دستورها و سازندگانشان

---

## 🧠 پکیج منیجر چیست؟

پکیج منیجر (Package Manager) ابزار یا مجموعه‌ای از ابزارها است که برای **نصب، حذف، بروزرسانی و مدیریت وابستگی‌های نرم‌افزاری** در سیستم‌عامل استفاده می‌شود. هر توزیع لینوکس معمولاً از یک یا چند پکیج منیجر مشخص استفاده می‌کند.

---

## 🧾 فهرست کامل پکیج منیجرهای مشهور در لینوکس

در جدول زیر پکیج منیجرهای اصلی، توزیع‌های مرتبط و توضیح مختصر آورده شده‌اند:

| نام پکیج منیجر | توزیع/سیستم مرتبط  | زبان توسعه  | توسعه‌دهنده                       | سال معرفی | نوع                  |
| -------------- | ------------------ | ----------- | --------------------------------- | --------- | -------------------- |
| `dpkg`         | Debian, Ubuntu     | C           | Ian Murdock (Debian founder)      | 1994      | پایه‌ای              |
| `apt`          | Debian, Ubuntu     | C++         | Debian Project                    | \~1998    | رابط dpkg            |
| `aptitude`     | Debian             | C++         | Daniel Burrows                    | \~2000    | رابط گرافیکی‌تر apt  |
| `yum`          | Fedora (قدیمی)     | Python      | Duke University                   | 2003      | جایگزین rpm frontend |
| `dnf`          | Fedora             | Python/C    | Red Hat, Fedora Project           | 2015      | جایگزین yum          |
| `rpm`          | RHEL, Fedora, SUSE | C           | Red Hat (Erik Troan و Marc Ewing) | 1997      | پایه‌ای              |
| `zypper`       | openSUSE           | C++         | SUSE Linux GmbH                   | \~2007    | رابط rpm             |
| `pacman`       | Arch Linux         | C           | Judd Vinet (بنیان‌گذار Arch)      | 2002      | پایه‌ای و مستقل      |
| `eopkg`        | Solus              | Python      | Ikey Doherty                      | \~2015    | مستقل                |
| `xbps`         | Void Linux         | C           | Juan RP                           | 2008      | مستقل                |
| `emerge`       | Gentoo             | Python/Bash | Gentoo Foundation                 | 2002      | سیستم سورسی          |
| `nix`          | NixOS              | Haskell     | Eelco Dolstra                     | 2003      | غیرمتعارف            |
| `guix`         | Guix System        | Scheme      | Ludovic Courtès                   | 2012      | مبتنی بر Nix         |
| `flatpak`      | توزیع‌های مدرن     | C           | Alexander Larsson (Red Hat)       | 2015      | universal sandbox    |
| `snap`         | Ubuntu             | Go          | Canonical Ltd                     | 2016      | universal sandbox    |
| `brew`         | macOS/Linux        | Ruby        | Max Howell (در اصل)               | 2009      | ported to Linux      |
| `conda`        | علمی، Python       | Python      | Continuum Analytics               | 2012      | برای محیط‌های علمی   |

---

## 📘 دستورهای پرکاربرد برخی پکیج منیجرها

### 🔸 `apt` (Debian/Ubuntu)

```bash
sudo apt update          # بروزرسانی لیست بسته‌ها
sudo apt upgrade         # بروزرسانی بسته‌های نصب‌شده
sudo apt install <pkg>   # نصب بسته
sudo apt remove <pkg>    # حذف بسته
sudo apt search <term>   # جستجو
```

### 🔸 `pacman` (Arch)

```bash
sudo pacman -Syu         # بروزرسانی سیستم
sudo pacman -S <pkg>     # نصب بسته
sudo pacman -R <pkg>     # حذف بسته
pacman -Ss <term>        # جستجو
```

### 🔸 `dnf` (Fedora)

```bash
sudo dnf check-update
sudo dnf install <pkg>
sudo dnf remove <pkg>
sudo dnf search <term>
```

### 🔸 `zypper` (openSUSE)

```bash
sudo zypper refresh
sudo zypper install <pkg>
sudo zypper remove <pkg>
sudo zypper search <term>
```

### 🔸 `emerge` (Gentoo)

```bash
emerge --sync
emerge <pkg>               # نصب
emerge -C <pkg>            # حذف
emerge --update --deep @world
```

### 🔸 `flatpak` (همه توزیع‌ها)

```bash
flatpak install flathub <app>
flatpak run <app>
flatpak uninstall <app>
```

### 🔸 `snap` (Ubuntu و دیگران)

```bash
sudo snap install <pkg>
sudo snap remove <pkg>
snap list
```

### 🔸 `xbps-install` (Void)

```bash
sudo xbps-install -S        # بروزرسانی لیست
sudo xbps-install <pkg>
sudo xbps-remove <pkg>
```

---

## 👤 چه کسانی این پکیج منیجرها را ساخته‌اند؟

### 🔹 `pacman` و Arch

* **نویسنده اصلی:** Judd Vinet
* **سازمان:** Arch Linux
* **ویژگی:** ساده، سریع، بدون نیاز به ابزارهای اضافی مثل yum یا apt.

### 🔹 `apt`

* **نویسنده‌ها:** Jason Gunthorpe و تیم Debian
* **سال:** حدود 1998 برای ساده‌تر کردن کار با `dpkg`

### 🔹 `rpm`

* **سازنده:** Red Hat
* **افراد کلیدی:** Erik Troan، Marc Ewing
* **RPM مخفف:** Red Hat Package Manager

### 🔹 `dnf`

* **سازنده:** Fedora Project
* **نویسنده اصلی:** Aleš Kozumplík، با همکاری تیم Fedora

### 🔹 `flatpak`

* **سازنده:** Alexander Larsson از Red Hat
* هدف: جدا کردن برنامه‌ها از سیستم اصلی برای افزایش امنیت و سازگاری

### 🔹 `snap`

* **سازنده:** شرکت Canonical (سازنده Ubuntu)
* **هدف:** پکیج جهانی و ایزوله

### 🔹 `nix`

* **نویسنده:** Eelco Dolstra (پروژه دانشگاهی)
* **ویژگی:** مدیریت بسته با atomicity و reproducibility

### 🔹 `xbps`

* **سازنده:** Juan Romero Pardines (Void Linux)
* **ویژگی:** سبک، مستقل، بدون systemd

---

## 🔬 تحلیل نهایی

* بیشتر پکیج منیجرها توسط گروه‌هایی مانند **Debian Project، Red Hat، Canonical** توسعه یافته‌اند.
* ولی بعضی‌ها مانند **Arch (pacman)** و **Void (xbps)** توسط افراد مستقل و علاقه‌مند آغاز شده‌اند.
* پکیج منیجرهایی مثل `nix` و `guix` نمونه‌هایی از آینده‌نگری در حوزه‌ی بسته‌بندی نرم‌افزار هستند.
* انتخاب بین آن‌ها بسته به **نیاز، سطح دانش، و نوع سیستم** شما متفاوت است.

---
