[→ سناریو ۲: سوالات](./scenario-02-questions.md) | [سناریو ۴: سوالات ←](./scenario-04-questions.md) | [پاسخنامه سناریو ۳](./scenario-03-answers.md)

# سناریو ۳: ارزیابی مولکول‌های دارویی تولید‌شده توسط هوش مصنوعی مولد

---

### شرح سناریو

یک شرکت داروسازی از یک مدل **هوش مصنوعی مولد (Generative AI)** برای طراحی مولکول‌های جدیدی استفاده کرده است که به طور بالقوه می‌توانند یک پروتئین کلیدی در یک بیماری را مهار کنند. هدف، یافتن یک مولکول کاندیدا برای شروع فرآیند آزمایش‌های پیش‌بالینی است. برای موفقیت یک دارو، سه ویژگی اصلی باید به طور همزمان بهینه شوند:
۱. **قدرت اتصال (Binding Affinity):** توانایی مولکول در اتصال محکم به پروتئین هدف. این مقدار با **Ki (ثابت مهار)** اندازه‌گیری می‌شود. **مقدار Ki کمتر، به معنای اتصال قوی‌تر و داروی بهتر است.**
۲. **حلالیت در آب (Aqueous Solubility):** برای اینکه دارو بتواند در بدن جذب شود، باید به میزان کافی در آب محلول باشد. **حلالیت بالاتر، بهتر است.**
۳. **سمیت پیش‌بینی‌شده (Predicted Toxicity):** احتمال اینکه مولکول اثرات سمی بر سلول‌های سالم داشته باشد. این مقدار با یک امتیاز بین ۰ تا ۱ بیان می‌شود. **امتیاز سمیت کمتر، بهتر است.**

مدل هوش مصنوعی چهار مولکول کاندیدای امیدوارکننده (با نام‌های A, B, C, D) را تولید کرده است. ویژگی‌های پیش‌بینی‌شده برای این چهار مولکول در جدول زیر آمده است:

| مولکول کاندیدا | Ki (نانومولار - nM) | حلالیت (میکروگرم بر میلی‌لیتر - µg/mL) | امتیاز سمیت پیش‌بینی‌شده |
| :------------- | :------------------ | :------------------------------------- | :----------------------- |
| **Molecule A** | **0.5**             | 5                                      | 0.85                     |
| **Molecule B** | 25.0                | **350**                                | 0.15                     |
| **Molecule C** | 5.0                 | 150                                    | **0.05**                 |
| **Molecule D** | 15.0                | 20                                     | 0.60                     |

### سوالات

**سوال ۱:**
کدام مولکول بهترین **قدرت اتصال (Binding Affinity)** به پروتئین هدف را نشان می‌دهد؟

الف) Molecule A
ب) Molecule B
ج) Molecule C
د) Molecule D

**سوال ۲:**
کدام مولکول از نظر **ایمنی (Safety)**، یعنی کمترین احتمال ایجاد اثرات سمی، بهترین گزینه به نظر می‌رسد؟

الف) Molecule A
ب) Molecule B
ج) Molecule C
د) Molecule D

**سوال ۳:**
با در نظر گرفتن **توازن (Trade-off)** بین هر سه ویژگی کلیدی (قدرت اتصال قوی، حلالیت مناسب و سمیت پایین)، کدام مولکول به عنوان **بهترین کاندیدا برای ورود به مرحله تحقیقات پیش‌بالینی** انتخاب می‌شود؟

الف) Molecule A، زیرا قدرت اتصال فوق‌العاده بالایی دارد و می‌توان مشکل حلالیت و سمیت آن را بعداً حل کرد.
ب) Molecule B، زیرا حلالیت بسیار بالایی دارد و سمیت آن نیز نسبتاً پایین است، حتی اگر قدرت اتصال آن بهترین نباشد.
ج) Molecule C، زیرا یک توازن منطقی بین هر سه معیار ارائه می‌دهد: قدرت اتصال خوب، حلالیت کافی و سمیت بسیار پایین.
د) Molecule D، زیرا هیچ ویژگی خیلی ضعیفی ندارد و یک گزینه متوسط و بدون ریسک است.
