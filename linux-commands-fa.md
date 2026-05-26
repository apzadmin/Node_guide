# راهنمای دستورات لینوکس

دستورات پایه لینوکس که معمولاً برای سرورهای VPS و راه‌اندازی نودهای کریپتویی استفاده می‌شوند.

---

# ls — نمایش فایل‌ها و پوشه‌ها

نمایش فایل‌ها و پوشه‌های موجود.

## نمایش پوشه‌ها

```bash
ls
```

## نمایش همه فایل‌ها و فایل‌های مخفی

```bash
ls -a
```

---

# mkdir — ساخت پوشه

ایجاد پوشه جدید.

## ساخت یک پوشه

```bash
mkdir <folder-name>
```

## ساخت چند پوشه

```bash
mkdir <folder-name> <folder-name2>
```

## مثال

```bash
mkdir shahin
```

---

# cd — جابه‌جایی بین پوشه‌ها

حرکت بین دایرکتوری‌ها.

## رفتن به پوشه Home

```bash
cd
```

## رفتن به مسیر دلخواه

```bash
cd <directory-path>
```

## مثال

```bash
cd shahin
```

## برگشت به پوشه قبلی

```bash
cd ..
```

---

# mv — جابه‌جایی فایل‌ها و پوشه‌ها

انتقال یا تغییر نام فایل‌ها و پوشه‌ها.

## ساختار دستور

```bash
mv <source> <destination>
```

---

# rm — حذف فایل‌ها

حذف فایل‌ها و پوشه‌ها.

## حذف فایل

```bash
rm -rf <file>
```

## حذف فایل داخل پوشه

```bash
rm -rf <directory/file>
```

---

# nano — ویرایشگر فایل

باز کردن و ویرایش فایل‌ها داخل ترمینال.

## باز کردن یا ساخت فایل

```bash
nano <file>
```

## ذخیره و خروج

```text
CTRL + X → Y → ENTER
```

---

# git — دانلود پروژه‌های GitHub

انتقال پروژه‌های GitHub به سرور لینوکسی.

## دانلود Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY
```

## مثال

```bash
git clone https://github.com/shahin/linux-node-guide
```

---

# screen — اجرای پردازش در پس‌زمینه

Screen اجازه می‌دهد پردازش‌ها بعد از بستن ترمینال همچنان اجرا شوند.

مناسب برای ران کردن نودهای کریپتویی.

---

## نصب Screen

```bash
sudo apt install screen
```

## ساخت Screen جدید

```bash
screen -S <screen-name>
```

## خروج از Screen بدون توقف پردازش

```text
CTRL + A + D
```

## مشاهده Screenهای فعال

```bash
screen -ls
```

## بازگشت به Screen
# منابع مفید برای دستورات لینوکس

- [کتاب متن‌باز ۱۰۱ دستور لینوکس](https://github.com/bobbyiliev/101-linux-commands#basics)

- [مخزن دستورات Bash لینوکس](https://github.com/trinib/Linux-Bash-Commands)

- [راهنمای دستورات مهم لینوکس](https://www.digitalocean.com/community/tutorials/linux-commands#the-wget-command-in-linux)
```bash
screen -r <screen-name>
```
