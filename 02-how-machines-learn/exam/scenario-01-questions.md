[→ آزمون فصل دوم](./index.md) | [سناریو ۲: سوالات ←](./scenario-02-questions.md) | [پاسخنامه سناریو ۱](./scenario-01-answers.md)

## سناریوی ۱: پیش‌بینی جایگاه پروتئین‌ها در سلول

**مقدمه سناریو:**

شما به عنوان یک محقق بیوانفورماتیک در یک لابراتوار زیست‌شناسی سلولی مشغول به کار هستید. تیم شما در حال مطالعه روی عملکرد پروتئین‌ها در سلول‌های مخمر (_Saccharomyces cerevisiae_) است. یکی از چالش‌های اصلی، شناسایی سریع و دقیق جایگاه عملکردی (Localization) پروتئین‌ها در بخش‌های مختلف سلول (مانند سیتوپلاسم، میتوکندری، هسته و غیره) است. تعیین این جایگاه‌ها به روش‌های آزمایشگاهی بسیار زمان‌بر و پرهزینه است. شما ماموریت یافته‌اید تا یک مدل هوش مصنوعی مبتنی بر شبکه عصبی طراحی کنید که بتواند با استفاده از ویژگی‌های بیوشیمیایی یک پروتئین، جایگاه نهایی آن در سلول را پیش‌بینی کند. این مدل می‌تواند فرآیندهای تحقیقاتی را به شدت تسریع کند.

شما به یک مجموعه داده استاندارد (برگرفته از مجموعه داده Yeast از UCI Machine Learning Repository) دسترسی پیدا کرده‌اید. این مجموعه داده شامل ۸ ویژگی بیوشیمیایی محاسبه‌شده از توالی آمینو اسیدی پروتئین‌ها و همچنین برچسب جایگاه سلولی آن‌ها است که به صورت آزمایشگاهی تایید شده است.

**داده‌ها:**

جدول زیر، نمونه‌ای کوچک از داده‌هایی است که در اختیار دارید. این داده‌ها شامل ویژگی‌های عددی و یک ستون هدف (کلاس) است.

| نام پروتئین | mcg  | gvh  | alm  | mit  | erl | pox | vac  | nuc  | کلاس (جایگاه)       |
| :---------- | :--- | :--- | :--- | :--- | :-- | :-- | :--- | :--- | :------------------ |
| ADH1        | 0.58 | 0.61 | 0.47 | 0.13 | 0.5 | 0.0 | 0.48 | 0.22 | **CYT** (سیتوپلاسم) |
| NUD1        | 0.43 | 0.67 | 0.48 | 0.27 | 0.5 | 0.0 | 0.53 | 0.22 | **CYT** (سیتوپلاسم) |
| TYS1        | 0.64 | 0.62 | 0.49 | 0.15 | 0.5 | 0.0 | 0.53 | 0.22 | **CYT** (سیتوپلاسم) |
| QCR2        | 0.58 | 0.44 | 0.57 | 0.58 | 0.5 | 0.0 | 0.54 | 0.22 | **MIT** (میتوکندری) |
| MIH1        | 0.42 | 0.40 | 0.60 | 0.18 | 0.5 | 0.0 | 0.58 | 0.30 | **NUC** (هسته)      |
| NUP49       | 0.51 | 0.40 | 0.56 | 0.17 | 0.5 | 0.0 | 0.49 | 0.22 | **NUC** (هسته)      |
| ...         | ...  | ...  | ...  | ...  | ... | ... | ...  | ...  | ...                 |

**توضیحات ویژگی‌ها:**

- **mcg, gvh, alm, mit, vac, nuc:** امتیازات به دست آمده از الگوریتم‌های مختلف برای پیش‌بینی سیگنال‌های هدف‌گیری پروتئین.
- **erl:** یک ویژگی باینری (دودویی) برای حضور یک سیگنال خاص.
- **کلاس:** جایگاه نهایی پروتئین (مثلاً CYT, MIT, NUC, ME3, ME2, ME1, EXC, VAC, POX, ERL).

---

### سوالات آزمون

**سوال ۱ (چند گزینه‌ای):**

با توجه به ماهیت مسئله (پیش‌بینی جایگاه پروتئین از روی ویژگی‌های آن) و داده‌های ارائه‌شده، کدام‌یک از پارادایم‌های یادگیری ماشین و کدام نوع وظیفه (Task) برای حل این مسئله مناسب‌تر است؟

الف) یادگیری بدون نظارت - خوشه‌بندی (Clustering)
ب) یادگیری با نظارت - رگرسیون (Regression)
ج) یادگیری با نظارت - طبقه‌بندی (Classification)
د) یادگیری تقویتی - بهینه‌سازی سیاست (Policy Optimization)

**سوال ۲ (صحیح/غلط):**

برای آماده‌سازی داده‌های ورودی (ویژگی‌های `mcg` تا `nuc`) برای یک شبکه عصبی پرسپترون چندلایه (MLP)، بهتر است ابتدا مقادیر آن‌ها را به دامنه‌ی مشترکی مانند \[0, 1] یا میانگین 0 و انحراف معیار 1 مقیاس‌بندی (Scale) کنیم. این کار به همگرایی سریع‌تر و پایدارتر مدل در حین آموزش کمک می‌کند.

الف) صحیح
ب) غلط

**سوال ۳ (چند گزینه‌ای):**

شما در حال طراحی معماری یک شبکه عصبی برای این مسئله هستید. با فرض اینکه مجموعه داده کامل شامل ۱۰ کلاس (جایگاه) مختلف است، لایه ورودی و لایه خروجی این شبکه باید به ترتیب چند نورون داشته باشند؟

الف) ورودی: ۹ نورون، خروجی: ۱۰ نورون
ب) ورودی: ۸ نورون، خروجی: ۱ نورون
ج) ورودی: ۸ نورون، خروجی: ۱۰ نورون
د) ورودی: ۱۰ نورون، خروجی: ۸ نورون

**سوال ۴ (چند گزینه‌ای):**

کدام ترکیب از **تابع فعال‌سازی لایه خروجی (Output Layer Activation)** و **تابع هزینه (Loss Function)** برای آموزش این شبکه عصبی طبقه‌بندی چندکلاسه مناسب‌تر است؟

الف) تابع فعال‌سازی: Sigmoid، تابع هزینه: Mean Squared Error (MSE)
ب) تابع فعال‌سازی: ReLU، تابع هزینه: Mean Absolute Error (MAE)
ج) تابع فعال‌سازی: Softmax، تابع هزینه: Categorical Cross-Entropy
د) تابع فعال‌سازی: Tanh، تابع هزینه: Binary Cross-Entropy
