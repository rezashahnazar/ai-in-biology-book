[→ سناریو ۳: سوالات](./scenario-03-questions.md) | [بازگشت به آزمون فصل ششم](./index.md) | [پاسخنامه سناریو ۴](./scenario-04-answers.md)

# سناریو ۴: تحلیل سوگیری (Bias) در یک مدل هوش مصنوعی در حوزه سلامت

---

### شرح سناریو

یک شرکت بزرگ بیمه سلامت، برای بهبود تخصیص منابع و ارائه خدمات پیشگیرانه، یک مدل هوش مصنوعی طراحی کرده است. هدف این مدل، شناسایی بیمارانی است که در آینده به بیشترین مراقبت‌های پزشکی نیاز خواهند داشت تا بتوان برای آن‌ها برنامه‌های حمایتی ویژه‌ای در نظر گرفت.

از آنجایی که "نیاز واقعی به مراقبت‌های پزشکی در آینده" یک متغیر پیچیده و غیرقابل اندازه‌گیری مستقیم است، تیم علم داده تصمیم می‌گیرد از یک **متغیر جایگزین (Proxy Variable)** برای آموزش مدل استفاده کند: **"مجموع هزینه‌های پزشکی فرد در سال گذشته"**. استدلال تیم این است که افرادی که در گذشته هزینه‌های درمانی بیشتری داشته‌اند، احتمالاً بیمارتر بوده و در آینده نیز به مراقبت بیشتری نیاز خواهند داشت.

پس از پیاده‌سازی مدل، نتایج نشان می‌دهد که مدل به طور سیستماتیک، بیمارانی که در مناطق کم‌برخوردار و با دسترسی محدودتر به خدمات درمانی زندگی می‌کنند را در اولویت پایین‌تری برای دریافت خدمات حمایتی قرار می‌دهد، حتی اگر وضعیت سلامتی آن‌ها مشابه یا وخیم‌تر از بیماران مناطق برخوردار باشد. بررسی‌های بیشتر نشان می‌دهد که افراد در مناطق کم‌برخوردار، به دلیل مشکلات حمل و نقل، هزینه و عدم اعتماد به سیستم درمانی، حتی در صورت بیماری شدید، کمتر به پزشک مراجعه کرده و در نتیجه، هزینه‌های درمانی ثبت‌شده کمتری در سال گذشته داشته‌اند.

### سوالات

**سوال ۱:**
استفاده از "هزینه‌های پزشکی گذشته" به عنوان جایگزینی برای "نیاز واقعی به مراقبت" در این مدل، منجر به کدام نوع از سوگیری (Bias) شده است؟

الف) **سوگیری نمونه‌گیری (Sampling Bias):** داده‌های آموزشی به درستی نماینده کل جمعیت بیماران نیستند.
ب) **سوگیری برچسب‌زنی (Labeling Bias / Proxy Discrimination):** برچسب‌ها (Labels) یا متغیر هدف (Target Variable) به درستی ماهیت واقعی پدیده‌ای که قصد پیش‌بینی آن را داریم، منعکس نمی‌کنند و خود تحت تأثیر سوگیری‌های اجتماعی موجود هستند.
ج) **سوگیری حذف (Exclusion Bias):** برخی از ویژگی‌های مهم به طور نامناسب از داده‌ها حذف شده‌اند.
د) **سوگیری بیش‌برازش (Overfitting Bias):** مدل بیش از حد به داده‌های آموزشی وابسته شده و قادر به تعمیم نیست.

**سوال ۲:**
کدام یک از گزاره‌های زیر، **ریشه اصلی مشکل** در این سناریو را به بهترین شکل توضیح می‌دهد؟

الف) الگوریتم هوش مصنوعی ذاتاً تبعیض‌آمیز است.
ب) داده‌های مربوط به هزینه‌ها، نویز زیادی داشته و بی‌کیفیت بوده‌اند.
ج) مدل به درستی کار می‌کند؛ این مدل دقیقاً همان چیزی را که از آن خواسته شده (پیش‌بینی هزینه‌ها) به خوبی انجام می‌دهد، اما هدف تعریف‌شده (پیش‌بینی هزینه‌ها) با هدف واقعی (پیش‌بینی نیاز به درمان) هم‌راستا نیست.
د) شرکت بیمه باید از یک مدل پیچیده‌تر مانند شبکه‌های عصبی عمیق استفاده می‌کرد.

**سوال ۳:**
برای کاهش این نوع سوگیری، کدام یک از اقدامات زیر **مؤثرترین** گام اولیه خواهد بود؟

الف) جمع‌آوری داده‌های بیشتر از همان نوع (هزینه‌های پزشکی) برای بازآموزی مدل.
ب) تلاش برای یافتن یا ایجاد یک متغیر هدف (برچسب) بهتر که به "نیاز واقعی پزشکی" نزدیک‌تر باشد، مانند استفاده از نتایج آزمایش‌ها، تشخیص‌های پزشکی ثبت‌شده یا ارزیابی‌های مستقیم سلامت.
ج) حذف اطلاعات مربوط به محل زندگی بیماران از داده‌های آموزشی برای "کور کردن" مدل نسبت به این ویژگی.
د) تنظیم دقیق‌تر هایپرپارامترهای مدل برای افزایش دقت پیش‌بینی هزینه‌ها.
