# السبحة الذكية: تحويل المشروع إلى APK

المجلد `www/index.html` هو التطبيق كاملًا (صفحة واحدة). الملفات الأخرى تجهّزه للتحويل إلى تطبيق أندرويد عبر Capacitor.

## المتطلبات
- Node.js 18 أو أحدث
- Android Studio (يتضمن Android SDK و JDK)

## الخطوات
1. افتح الطرفية داخل هذا المجلد ونفّذ:

   npm install
   npx cap add android
   npx cap sync android
   npx cap open android

2. في Android Studio: من القائمة اختر Build ثم Build Bundle(s) / APK(s) ثم Build APK(s).
3. يظهر ملف الـ APK في المسار:

   android/app/build/outputs/apk/debug/app-debug.apk

لنسخة رسمية للنشر في متجر Google Play اختر Build ثم Generate Signed Bundle / APK ووقّعها بمفتاحك.

## ملاحظات
- الخطوط (Cairo و Orbitron و Reem Kufi) تُحمَّل من الإنترنت. بدون اتصال يستخدم التطبيق خطوط الجهاز البديلة وتبقى كل الوظائف تعمل. لجعل الخطوط محلية نزّلها وضعها داخل www واربطها بـ @font-face.
- عند تعديل `www/index.html` نفّذ `npx cap sync android` ثم أعد بناء الـ APK.
- بديل أسهل بلا Android Studio: خدمات التحويل عبر الإنترنت التي تقبل ملف HTML أو رابط موقع.

## البناء عبر GitHub (بدون Android Studio)
1. أنشئ مستودعًا جديدًا على GitHub وارفع إليه كل محتويات هذا المجلد، ومنها المجلد المخفي `.github`.
2. افتح تبويب Actions في المستودع. يبدأ البناء تلقائيًا عند الرفع، أو شغّل Build APK يدويًا بزر Run workflow.
3. بعد اكتمال البناء (نحو 3 إلى 5 دقائق) افتح التشغيل الناجح ونزّل `smart-tasbih-apk` من قسم Artifacts، وبداخله ملف `app-debug.apk`.
