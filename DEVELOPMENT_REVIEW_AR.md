# مراجعة وتطوير صفحة الأعمال

الحالة قبل العمل: `index.html` وملف CV فقط؛ بطاقات المشروعات ديناميكية. عيوب مثبتة: أقسام `.reveal` مخفية افتراضيًا عند فشل JavaScript/IntersectionObserver؛ dialog بلا اسم قابل للإتاحة؛ أزرار دراسات الحالة لا تميز المشروع؛ بطاقة Railway تصف Flutter بينما المستودع المرتبط TypeScript.

الخطة المنفذة: ظهور المحتوى كحالة افتراضية وإضافة التحريك عند توافره؛ روابط للمشروعات عند تعطيل JavaScript؛ skip link ومؤشر تركيز؛ اسم ووصف للنافذة وإغلاق بالزر/Escape والنقر خارج حدودها فقط؛ احترام الحركة المخففة في تمرير البطاقات؛ تصحيح هوية المستودع المرتبط وإضافة تعليمات التشغيل. لا تغيير لسجل الخبرات الشخصي.

المصادر: [MDN dialog](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/dialog)، [IntersectionObserver](https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver)، [prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion). الاستنتاج: HTML المرئي أساس، والتحريك تحسين تدريجي؛ الاسم مرتبط بعنوان المحتوى.

التحقق: Playwright عبر Edge حقيقي ورابط HTTP محلي: 5 بطاقات؛ اسم dialog؛ إغلاق/عودة التركيز/Escape؛ بقاء النافذة عند النقر داخلها وإغلاق خارجها؛ theme بعد إعادة التحميل؛ HTTP 200 وPDF صحيح؛ عرض هاتف390px بلا تجاوز؛ غياب observer؛ reduced motion؛ تعطيل JavaScript؛ صفر أخطاء JavaScript. اللقطات وسكربت التحقق محفوظة في evidence خارج مستودع التطبيق. `git diff --check` نجح.

التكامل: GET الصفحة -> JavaScript المسجل داخل الصفحة -> بطاقات يفتحها المستخدم -> نافذة مسماة وإغلاق يعود للزر؛ CSS/HTML -> ظهور المحتوى بدون JavaScript. أزيل onclick النصي القديم؛ callback واحد للإغلاق؛ لا تبعيات جديدة. GitHub Pages في الفرع الافتراضي لم ينشر هذه التغييرات بعد حتى دمج الفرع. مراجعة جميع الوظائف الشخصية/ادعاءات الإنتاج خارج نطاق هذه الأدلة.
