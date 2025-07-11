[→ سناریو ۴: سوالات](./scenario-04-questions.md) | [بازگشت به آزمون جامع نهایی](./index.md)

# پاسخنامه سناریو ۴: ارزیابی مدل تشخیص پزشکی از روی تصاویر

در این بخش، پاسخ‌های تشریحی و کامل تمام سوالات سناریو ۴ ارائه می‌شود. هدف، نمایش گام‌به‌گام روش رسیدن به پاسخ صحیح با تحلیل دقیق مسئله، محاسبات لازم، و ارجاع به مفاهیم کلیدی کتاب است.

---

### **سوال ۱۶**

**پاسخ صحیح: ب) `Variety`، زیرا تفاوت در منبع داده‌ها (مانند اسکنرهای مختلف) می‌تواند باعث شود مدل الگوهای وابسته به منبع (Source-specific patterns) را به جای ویژگی‌های بیولوژیکی واقعی یاد بگیرد.**

**مفاهیم کلیدی:** کلان‌داده (Big Data)، تعمیم (Generalization)، Domain Shift (فصل ۱ و ۶)

**تحلیل:**

- **تعمیم (Generalization)** به توانایی مدل برای عملکرد خوب بر روی داده‌های جدید و دیده‌نشده اشاره دارد.
- افزایش **`Volume` (حجم)** اگر داده‌ها متنوع و باکیفیت باشند، معمولاً به تعمیم بهتر کمک می‌کند، نه اینکه به آن آسیب بزند. چالش اصلی حجم، منابع محاسباتی است، نه خود تعمیم.
- چالش اصلی در اینجا **`Variety` (تنوع)** ناشی از منابع مختلف است. وقتی اسکنرها متفاوت هستند، ممکن است مدل به جای یادگیری ویژگی‌های سلول‌های سرطانی (سیگنال بیولوژیکی)، یاد بگیرد که چگونه تفاوت‌های جزئی در کنتراست، رنگ یا نویز ناشی از هر دستگاه را تشخیص دهد (سیگنال مصنوعی). این پدیده که به آن **تغییر دامنه (Domain Shift)** می‌گویند، یک تهدید جدی برای تعمیم است، زیرا مدل بر روی داده‌های یک اسکنر جدید که در آموزش ندیده، عملکرد ضعیفی خواهد داشت.

---

### **سوال ۱۷**

**پاسخ صحیح: ب) زیرا انکودر کانولوشنی می‌تواند **وابستگی‌های مکانی و الگوهای محلی (spatial dependencies and local patterns)** در تصویر را یاد بگیرد، در حالی که PCA با مسطح‌سازی، تمام این اطلاعات ساختاری را از بین می‌برد.**

**مفاهیم کلیدی:** کاهش ابعاد، PCA، شبکه‌های عصبی کانولوشنی (CNN)، انکودر خودکار (Autoencoder) (فصل ۵ و ۶)

**تحلیل:**

- تصاویر داده‌های ساختاریافته هستند. موقعیت یک پیکسل نسبت به پیکسل‌های همسایه‌اش حاوی اطلاعات حیاتی است (مثلاً برای تشکیل یک لبه، یک بافت یا شکل یک هسته سلولی).
- **رویکرد PCA:** با مسطح کردن تصویر (تبدیل یک ماتریس 1000x1000 به یک بردار 1,000,000)، تمام این اطلاعات مکانی و ساختاری از بین می‌رود. PCA تنها واریانس را در طول این بردار طولانی در نظر می‌گیرد و مفهوم همسایگی پیکسل‌ها را درک نمی‌کند.
- **رویکرد انکودر کانولوشنی:** این معماری ذاتاً برای کار با داده‌های شبکه‌ای (grid-like) مانند تصاویر طراحی شده است. فیلترهای کانولوشنی الگوهای محلی (مانند لبه‌ها و بافت‌ها) را در لایه‌های اولیه تشخیص می‌دهند و در لایه‌های عمیق‌تر این الگوها را برای شناسایی ساختارهای پیچیده‌تر ترکیب می‌کنند. بنابراین، نمایش نهفته (latent representation) تولید شده توسط آن، ویژگی‌های ساختاری و مکانی مهم تصویر را حفظ می‌کند که برای تشخیص بسیار حیاتی است.

---

### **سوال ۱۸**

**پاسخ صحیح: الف) Recall = 0.65, Specificity = 0.98**

**مفاهیم کلیدی:** ماتریس درهم‌ریختگی، Recall، Specificity (فصل ۵)

**مراحل حل:**

1.  **داده‌ها از ماتریس:**

    - TP = 65 (سرطانی‌هایی که به درستی سرطانی تشخیص داده شده‌اند)
    - FN = 35 (سرطانی‌هایی که به اشتباه نرمال تشخیص داده شده‌اند)
    - TN = 882 (نرمال‌هایی که به درستی نرمال تشخیص داده شده‌اند)
    - FP = 18 (نرمال‌هایی که به اشتباه سرطانی تشخیص داده شده‌اند)
    - کل موارد سرطانی واقعی (Actual Positives) = TP + FN = 65 + 35 = 100
    - کل موارد نرمال واقعی (Actual Negatives) = TN + FP = 882 + 18 = 900

2.  **محاسبه Recall (نرخ بازیابی یا حساسیت):**

    - این معیار نشان می‌دهد که مدل چه کسری از موارد سرطانی واقعی را پیدا کرده است.
    - `Recall = TP / (TP + FN) = 65 / 100 = 0.65`

3.  **محاسبه Specificity (ویژگی):**
    - این معیار نشان می‌دهد که مدل چه کسری از موارد نرمال واقعی را به درستی شناسایی کرده است.
    - `Specificity = TN / (TN + FP) = 882 / 900 = 0.98`

نتایج محاسبه شده با گزینه **الف** مطابقت دارد.

---

### **سوال ۱۹**

**پاسخ صحیح: ب) خطای **FN** خطرناک‌تر است؛ اولویت با **Recall (Sensitivity)** است.**

**مفاهیم کلیدی:** انتخاب معیار ارزیابی، پیامدهای بالینی خطا (فصل ۵)

**تحلیل:**

- **False Negative (FN):** یک بیمار مبتلا به سرطان به اشتباه سالم تشخیص داده می‌شود. پیامد این خطا بسیار خطرناک است، زیرا بیمار درمان لازم را دریافت نمی‌کند و بیماری پیشرفت می‌کند که می‌تواند منجر به مرگ شود.
- **False Positive (FP):** یک فرد سالم به اشتباه مشکوک به سرطان تشخیص داده می‌شود. پیامد این خطا استرس روانی برای بیمار و نیاز به آزمایش‌های تکمیلی (مانند بیوپسی) است. گرچه این پیامدها نامطلوب و پرهزینه هستند، اما به اندازه از دست دادن جان یک بیمار خطرناک نیستند.
- **اولویت‌بندی:** در غربالگری پزشکی برای بیماری‌های کشنده، به حداقل رساندن FNها بالاترین اولویت را دارد. معیاری که مستقیماً با تعداد FNها در مخرج خود سروکار دارد و برای به حداقل رساندن آن‌ها تلاش می‌کند، **Recall** است. بنابراین، باید مدلی با بالاترین Recall ممکن را انتخاب کرد.

---

### **سوال ۲۰**

**پاسخ صحیح: ج) چالش: **سوگیری الگوریتمی ناشی از تغییر دامنه (Domain Shift Bias)**. راهکار: افزودن داده‌های متنوع از Scanner-A به مجموعه آموزشی و آموزش مجدد مدل (Fine-tuning).**

**مفاهیم کلیدی:** اخلاق در هوش مصنوعی، سوگیری الگوریتمی، تغییر دامنه (فصل ۶)

**تحلیل:**

- **تشخیص مشکل:** عملکرد متفاوت مدل بر روی داده‌های حاصل از دستگاه‌های مختلف یک نمونه کلاسیک از **تغییر دامنه (Domain Shift)** است. این یک نوع **سوگیری الگوریتمی (Algorithmic Bias)** است، زیرا مدل به جای یادگیری ویژگی‌های بیولوژیکی جهان‌شمول، ویژگی‌های خاص یک "دامنه" (یعنی تصاویر Scanner-B) را یاد گرفته است. این باعث می‌شود که مدل نسبت به جمعیت‌هایی که به دستگاه‌های متفاوتی دسترسی دارند (مانند مناطق روستایی)، ناعادلانه و ناکارآمد عمل کند.
- **راهکار موثر:** موثرترین راهکار فنی برای این مشکل، کاهش این شکاف دامنه است. با افزودن داده‌های کافی و متنوع از دامنه هدف (Scanner-A) به مجموعه داده آموزشی و سپس آموزش مجدد یا **تنظیم دقیق (Fine-tuning)** مدل، ما به مدل اجازه می‌دهیم تا ویژگی‌هایی را یاد بگیرد که در هر دو دامنه مشترک هستند و نسبت به تفاوت‌های ناشی از دستگاه، مقاوم (robust) شود.
- گزینه‌های دیگر به مسائل مهمی اشاره دارند اما مشکل اصلی را در این سناریو هدف قرار نمی‌دهند.
