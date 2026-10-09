# حاضریاد | اپلیکیشن حضور و غیاب تکنویاد

این پوشه نسخهٔ آمادهٔ GitHub برای ساخت APK برنامهٔ **حاضریاد** است. برنامهٔ اصلی داخل `www/index.html` قرار دارد و بعد از نصب APK به‌صورت آفلاین اجرا می‌شود.

## ساخت APK با GitHub Actions

۱. تمام فایل‌های این پوشه را در یک مخزن جدید GitHub آپلود کنید.

۲. از بخش **Actions**، Workflow با نام **Build Hazeryad APK** را باز کنید و گزینهٔ **Run workflow** را بزنید.

۳. بعد از پایان موفق، در همان اجرای Workflow از بخش **Artifacts** فایل `hazeryad-debug-apk` را دانلود کنید. داخل فایل فشرده، `app-debug.apk` قرار دارد.

Workflow هر بار که روی شاخهٔ `main` یا `master` کدی Push شود نیز اجرا می‌شود.

## ساخت روی رایانه

نیازمندی‌ها: Node.js 22 یا جدیدتر، Java 21 و Android SDK.

```bash
npm ci
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

فایل خروجی در این مسیر ساخته می‌شود:

```text
android/app/build/outputs/apk/debug/app-debug.apk
```

## نام و شناسهٔ برنامه

- نام برنامه: حاضریاد
- شناسهٔ اندروید: `ir.technoyaad.hazeryad`
- سازنده: گروه آموزشی تکنویاد (میلاد حیرانی)
- اینستاگرام: `@technoyaad`

برای تغییر محتوای برنامه، فایل `www/index.html` را ویرایش کنید و دوباره Workflow را اجرا کنید.
