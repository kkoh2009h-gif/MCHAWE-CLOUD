# MCHAWE CLOUD

مشروع MCHAWE CLOUD هدفه تقديم تجربة Xbox Cloud Gaming على PS4 بشكل يحمل اسم وهوية MCHAWE، بالاعتماد على محرك PSBox Cloud Gaming الأصلي بدلاً من واجهة ويب تجريبية.

## الوضع الحالي (بصراحة)
- الواجهة الحالية في `index.html` مجرد prototype / mockup وليست تطبيق بث.
- لا يوجد تسجيل Microsoft أو بث ألعاب أو PS4 PKG جاهز في هذا المستودع حالياً.
- ملف `ps4/` السابق يحتوي scaffold بسيط فقط، وليس محرك بث.
- الخطوة التقنية المطلوبة هي دمج/إعادة بناء المشروع على أساس upstream PSBox مع الحفاظ على متطلبات ترخيص GPL-3.0-or-later، وإضافة هوية MCHAWE وإعدادات/واجهة مناسبة.

## محرك المشروع الأساسي
- **PSBox Cloud Gaming**: https://github.com/RafaelNGP/psbox-cloud-gaming
- **الإصدارات الرسمية**: https://github.com/RafaelNGP/psbox-cloud-gaming/releases/latest
- **ترخيص upstream**: GPL-3.0-or-later (يجب الحفاظ على إشعارات الترخيص وحقوق المؤلف وشروط إعادة التوزيع عند الاشتقاق).

PSBox يوفّر محركاً أصلياً يتضمن كتالوج Xbox Cloud Gaming، تسجيل الدخول عبر Microsoft، streaming، ودعم PS4 مع GoldHEN بحسب توثيق upstream. يتطلب حساب Microsoft وخطة اشتراك/خدمة مؤهلة؛ المشروع لا يتجاوز متطلبات الاشتراك أو القيود الإقليمية.

## خارطة طريق الدمج
1. مراجعة بنية upstream والترخيص والاعتماديات.
2. إنشاء fork أو نسخة مشتقة مع الحفاظ على ملفات GPL والـ notices.
3. تخصيص branding وواجهة MCHAWE، دون تعطيل تسجيل الدخول أو البث أو التحديثات الأساسية.
4. بناء PS4 PKG باستخدام OpenOrbis toolchain.
5. اختبار PKG فعلياً على PS4 وGoldHEN قبل إعلان جاهزيته.

## الواجهة التجريبية الحالية
فتح `index.html` يعرض نموذج واجهة فقط؛ لا يُعد تشغيل الألعاب أو بثها.

## Disclaimer
MCHAWE CLOUD مشروع غير رسمي، وغير تابع أو مدعوم من Microsoft أو Sony أو Xbox. أسماء العلامات التجارية تخص أصحابها.
