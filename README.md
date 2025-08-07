# MatrixUploader

A secure and lightweight file uploader with admin panel, file-type filtering, upload progress, and animated Matrix-style background — fully RTL and Farsi-supported.

---

سیستم آپلود فایل امن و سبک با داشبورد مدیریت، فیلتر نوع فایل، نمایش پیشرفت آپلود و پس‌زمینه متحرک ماتریکس — کاملاً راست‌چین و فارسی‌ساز.

## ویژگی‌ها

- آپلود فایل با نوار پیشرفت زنده (Progress bar)
- فیلتر فایل‌های خطرناک (مثل php و html)
- جلوه پس‌زمینه ماتریکس با canvas
- رابط کاربری کاملاً فارسی و راست‌چین
- پنل ادمین با ورود (login) امن و حذف فایل‌ها
- ذخیره فایل‌ها در پوشه امن (uploads/)
- محافظت از اجرای فایل‌های اسکریپت در پوشه آپلود

## ساختار فایل‌ها

```
MatrixUpload/
├── index.html              # رابط آپلود فایل برای کاربران
├── upload.php              # دریافت فایل‌ها از کاربران
├── admin.php               # پنل مدیریت ادمین (ورود + لیست فایل‌ها + حذف)
├── logout.php              # خروج از پنل ادمین
├── uploads/                # محل ذخیره فایل‌های آپلودشده
│   └── .htaccess           # جلوگیری از اجرای فایل‌های اسکریپت
├── README.md               # فایل راهنما (همین فایل)
```

## امنیت

- فایل‌های `.php` و `.html` قابل آپلود نیستند
- بررسی نوع MIME فایل‌ها برای جلوگیری از آپلود مخفیانه فایل اسکریپت
- استفاده از `uniqid()` برای نام‌گذاری امن فایل‌ها
- مسدود کردن اجرای کد در `uploads/` با `.htaccess`

محتوای `.htaccess`:
```
php_flag engine off
RemoveHandler .php .phtml .php3 .php4 .php5 .php7
```

## نحوه اجرا

1. این پروژه را کلون یا دانلود کنید:
   ```bash
   git clone https://github.com/USERNAME/MatrixUpload.git
   ```
2. پروژه را روی یک سرور PHP (مثل XAMPP یا هاست واقعی) قرار دهید.
3. مطمئن شوید پوشه `uploads/` وجود دارد و قابل نوشتن است (CHMOD 0777 اگر لوکال هستید).
4. به `index.html` بروید و آپلود فایل را تست کنید.
5. برای ورود به پنل مدیریت، به `admin.php` بروید:
   - نام کاربری: `admin`
   - رمز عبور: `admin123`

> می‌توانید رمز عبور را از قبل هش‌شده جایگزین کنید یا از دیتابیس استفاده نمایید.

## TODO (برای آینده)

- افزودن CAPTCHA
- احراز هویت با توکن JWT یا session دقیق‌تر
- شمارشگر دانلود
- زمان انقضا برای فایل‌ها

---

🛡️ Developed By [Matin](http://matin-technology.ir/)


