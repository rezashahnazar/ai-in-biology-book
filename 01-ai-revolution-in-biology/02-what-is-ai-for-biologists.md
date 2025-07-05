# فصل ۱: انقلاب جدید در زیست‌شناسی

## بخش ۱-۲: هوش مصنوعی چیست؟ یک تعریف ساده و کاربردی

در بخش قبل، دیدیم که چگونه علم زیست‌شناسی با یک "سونامی داده" روبرو شده و چرا به ابزارهای جدیدی برای تحلیل این داده‌ها نیاز داریم. آن ابزار جدید، هوش مصنوعی یا AI است. اما AI واقعاً چیست؟

وقتی اسم "هوش مصنوعی" را می‌شنوید، شاید یاد ربات‌های انسان‌نما در فیلم‌های علمی-تخیلی بیفتید. اما در واقعیت، هوش مصنوعی که ما امروز از آن استفاده می‌کنیم، بسیار کاربردی‌تر و ملموس‌تر است.

### 🎯 مسئله محوری این بخش:

فرض کنید می‌خواهید به یک کشاورز سنتی توضیح دهید که چگونه یک "مغز کامپیوتری" می‌تواند با دیدن عکس‌هایی که یک پهپاد از مزرعه گرفته، بیماری گیاهان را تشخیص دهد. آن کشاورز هیچ چیزی از کامپیوتر و الگوریتم نمی‌داند. هدف شما این نیست که جزئیات فنی را بگویید، بلکه می‌خواهید شهود و ایده اصلی پشت این جادو را منتقل کنید. از چه مثال یا استعاره‌ای استفاده می‌کنید؟

### 🤖 **یک تعریف ساده: هوش مصنوعی = تقلید از یادگیری انسان**

بیایید با یک مقایسه شروع کنیم. یک **پزشک متخصص پوست باتجربه** را در نظر بگیرید. او چگونه یک خال سرطانی را از یک خال خوش‌خیم تشخیص می‌دهد؟

1. **تجربه (آموزش):** او در طول سال‌ها، هزاران عکس از خال‌های مختلف دیده و به او گفته شده که کدام خوش‌خیم و کدام بدخیم بوده‌اند.
2. **یادگیری الگو:** مغز او به طور ناخودآگاه الگوهایی را یاد گرفته است. مثلاً "خال‌هایی با لبه‌های نامنظم" یا "خال‌هایی با رنگ غیریکنواخت" احتمالاً خطرناک هستند.
3. **تشخیص (پیش‌بینی):** وقتی یک خال جدید می‌بیند، مغزش آن را با الگوهای ذخیره شده در حافظه‌اش مقایسه می‌کند و یک تشخیص ارائه می‌دهد.
4. **یادگیری از اشتباه:** اگر تشخیص او اشتباه باشد (که توسط نمونه‌برداری تأیید می‌شود)، او این تجربه جدید را به حافظه‌اش اضافه می‌کند و در آینده دقیق‌تر عمل می‌کند.

**هوش مصنوعی دقیقاً همین فرآیند را تقلید می‌کند، اما در مقیاسی بسیار بزرگتر:**

- به جای هزاران عکس، به آن **میلیون‌ها عکس** نشان می‌دهیم.
- به جای مغز انسان، از **الگوریتم‌های ریاضی و قدرت محاسباتی** کامپیوترها استفاده می‌کند.
- به جای چند سال، در چند **ساعت یا چند روز** آموزش می‌بیند.
- **خسته نمی‌شود**، فراموش نمی‌کند و ۲۴ ساعته با دقت یکسان کار می‌کند.

> پس به زبان ساده، **هوش مصنوعی (در کاربرد امروزی) یعنی آموزش دادن به کامپیوترها برای تشخیص الگوها در داده‌ها، تا بتوانند بر اساس آن الگوها، پیش‌بینی یا تصمیم‌گیری کنند.**

### 🎯 **مثال عملی ۱: تشخیص سرطان پوست با AI**

#### **مسئله واقعی:**

یک متخصص پوست به طور متوسط روزانه ۳۰ بیمار را ویزیت می‌کند. دقت تشخیص اولیه او برای سرطان پوست (ملانوما) بر اساس نگاه کردن، حدود **۷۷-۸۶٪** است[1][2][3]. این یعنی از هر ۱۰۰ بیمار، ممکن است در تشخیص ۱۴ تا ۲۳ نفر اشتباه کند. این اشتباه می‌تواند کشنده باشد.

#### **راه‌حل با هوش مصنوعی:**

محققان دانشگاه استنفورد یک سیستم هوش مصنوعی را با **۱۲۹,۴۵۰ عکس** از خال‌های پوستی که تشخیص قطعی آن‌ها مشخص بود، "آموزش" دادند[4][5][6].

```mermaid
flowchart LR
    subgraph آموزش [مرحله آموزش]
        A[تصویر خال ۱] --> C{الگوریتم AI};
        B[برچسب: "خوش‌خیم"] --> C;
        D[تصویر خال ۲] --> C;
        E[برچسب: "بدخیم"] --> C;
        F[...] --> C;
    end

    subgraph تشخیص [مرحله تشخیص]
        G[تصویر خال جدید] --> H{مدل آموزش‌دیده AI};
        H --> I[خروجی: "۹۵٪ احتمال بدخیم بودن"];
    end

    آموزش -->|تولید مدل| تشخیص;
```

#### **نتایج شگفت‌انگیز:**

وقتی عملکرد این سیستم AI را با ۲۱ متخصص پوست مقایسه کردند، نتیجه خیره‌کننده بود: **دقت هوش مصنوعی در تشخیص، برابر یا حتی بهتر از متخصصان انسان بود (حدود ۹۱٪ یا بیشتر)**[4][7][8][6][9].

> **نکته بسیار مهم:** این AI قرار نیست جایگزین پزشک شود. بلکه یک **ابزار کمکی فوق‌العاده قدرتمند** برای پزشک است. پزشک می‌تواند از AI به عنوان "نظر دوم" استفاده کند تا دقت تشخیص خود را افزایش دهد و هیچ موردی را از دست ندهد. این یعنی همکاری انسان و ماشین برای رسیدن به بهترین نتیجه.

### 🔬 **مثال عملی ۲: کشف آنتی‌بیوتیک جدید با AI**

#### **مسئله سنتی:**

کشف یک داروی جدید به طور متوسط **۱۰ تا ۱۵ سال** زمان و بیش از **۲ میلیارد دلار** هزینه نیاز دارد[10][11][12][13]. یکی از دلایل این زمان طولانی، فرآیند غربالگری (Screening) است. دانشمندان باید هزاران یا میلیون‌ها ترکیب شیمیایی را در آزمایشگاه تست کنند تا شاید یکی از آن‌ها موثر باشد.

#### **انقلاب با هوش مصنوعی:**

در سال ۲۰۲۰، محققان MIT از هوش مصنوعی برای حل این مشکل استفاده کردند[14][15][16].

1. **آموزش:** آن‌ها یک مدل AI را با داده‌های ۲۵۰۰ ترکیب شیمیایی آموزش دادند تا یاد بگیرد کدام ساختارهای مولکولی می‌توانند باکتری _E. coli_ را از بین ببرند.
2. **غربالگری مجازی:** سپس از این مدل آموزش‌دیده خواستند که یک کتابخانه دیجیتال شامل **بیش از ۱۰۰ میلیون ترکیب شیمیایی** را بررسی کند[14][17][16]!
3. **کشف:** هوش مصنوعی در عرض تنها **۳ روز**، یک مولکول بسیار قدرتمند به نام **هالیسین (Halicin)** را به عنوان یک آنتی‌بیوتیک بالقوه جدید شناسایی کرد که ساختار آن با تمام آنتی‌بیوتیک‌های شناخته‌شده متفاوت بود[18][14][15][16].

آزمایش‌های بعدی در آزمایشگاه نشان داد که هالیسین نه تنها _E. coli_ بلکه بسیاری از باکتری‌های مقاوم به داروهای دیگر را نیز از بین می‌برد[19][20].

**مقایسه فرآیند:**

- **روش سنتی:** سال‌ها تحقیق و میلیون‌ها دلار هزینه.
- **روش AI:** سه روز پردازش کامپیوتری!

این یعنی AI می‌تواند فرآیند کشف دارو را به شدت تسریع کند و شانس ما را برای پیدا کردن درمان بیماری‌های جدید افزایش دهد[21][22][23][24].

### 📊 **انواع اصلی هوش مصنوعی در زیست‌شناسی**

کارهایی که از هوش مصنوعی در زیست‌شناسی می‌خواهیم، معمولا در یکی از این چهار دسته قرار می‌گیرند:

| نوع AI                                  | سوالی که پاسخ می‌دهد              | مثال در زیست‌شناسی                                              |
| :-------------------------------------- | :-------------------------------- | :-------------------------------------------------------------- |
| **۱. تشخیص الگو (Pattern Recognition)** | این داده شبیه کدام الگو است؟      | آیا این عکس بافت، الگوی سلول سرطانی را دارد؟                    |
| **۲. پیش‌بینی (Prediction)**            | در آینده چه اتفاقی می‌افتد؟       | آیا این بیمار به داروی X پاسخ مثبت خواهد داد؟                   |
| **۳. بهینه‌سازی (Optimization)**        | بهترین راه‌حل برای این مشکل چیست؟ | بهترین ساختار مولکولی برای اتصال به این پروتئین ویروسی چیست؟    |
| **۴. تولید (Generation)**               | یک نمونه جدید با این مشخصات بساز. | یک توالی پروتئین جدید طراحی کن که این عملکرد خاص را داشته باشد. |

در اکثر موارد، این دسته‌ها با هم ترکیب می‌شوند. مثلا برای طراحی یک داروی جدید (بهینه‌سازی)، ابتدا باید الگوهای اتصال را یاد بگیریم (تشخیص الگو).

### 🔬 تمرین تحلیلی: شما نقش AI را بازی کنید!

حالا نوبت شماست که مثل یک ماشین فکر کنید.

#### **سناریو: تشخیص عفونت ادراری**

شما یک مدل هوش مصنوعی هستید که باید بر اساس داده‌های اولیه، وجود یا عدم وجود عفونت ادراری را تشخیص دهید. این داده‌های آموزشی شما هستند:

**🗂️ داده‌های آموزشی (۱۰ بیمار):**

| بیمار | سن  | جنسیت | تب دارد؟ | سوزش ادرار دارد؟ | تعداد گلبول سفید (در میکرولیتر خون) | تشخیص نهایی: عفونت دارد؟ |
| :---- | :-- | :---- | :------- | :--------------- | :---------------------------------- | :----------------------- |
| ۱     | ۲۵  | زن    | بله      | بله              | ۱۵,۰۰۰                              | **دارد**                 |
| ۲     | ۴۰  | مرد   | خیر      | خیر              | ۶,۰۰۰                               | **ندارد**                |
| ۳     | ۳۰  | زن    | بله      | بله              | ۲۰,۰۰۰                              | **دارد**                 |
| ۴     | ۵۰  | مرد   | خیر      | خیر              | ۵,۰۰۰                               | **ندارد**                |
| ۵     | ۲۰  | زن    | بله      | بله              | ۱۸,۰۰۰                              | **دارد**                 |
| ۶     | ۶۰  | مرد   | خیر      | **بله**          | ۷,۰۰۰                               | **ندارد**                |
| ۷     | ۳۵  | زن    | بله      | بله              | ۱۶,۰۰۰                              | **دارد**                 |
| ۸     | ۴۵  | مرد   | خیر      | خیر              | ۵,۵۰۰                               | **ندارد**                |
| ۹     | ۲۸  | زن    | بله      | بله              | ۱۹,۰۰۰                              | **دارد**                 |
| ۱۰    | ۳۸  | مرد   | **بله**  | خیر              | ۶,۵۰۰                               | **ندارد**                |

**مرحله ۱: کشف الگو (آموزش)**
با دقت به جدول نگاه کنید. به عنوان یک AI، شما به دنبال "قوانین" و "الگوها" هستید. چه الگوهایی پیدا می‌کنید؟

- **الگوی ۱:** اگر جنسیت "زن" باشد، تب "بله" باشد و سوزش ادرار "بله" باشد، احتمال عفونت خیلی بالاست.
- **الگوی ۲:** اگر تعداد گلبول سفید خیلی بالا باشد (مثلا > ۱۰,۰۰۰)، احتمال عفونت زیاد است[25][26][27].
- **الگوی ۳:** اگر جنسیت "مرد" باشد و تب و سوزش "خیر" باشد، احتمال عفونت خیلی کم است.
- **الگوی پیچیده‌تر:** به نظر می‌رسد هیچ‌کدام از این ویژگی‌ها به تنهایی کافی نیست (بیمار ۱۰ تب دارد ولی عفونت ندارد، بیمار ۶ سوزش ادرار دارد ولی عفونت ندارد). **ترکیب ویژگی‌ها** مهم است.

**مرحله ۲: تست (تشخیص)**
حالا یک بیمار جدید با داده‌های زیر به شما مراجعه کرده است. شما باید تشخیص دهید.

- **بیمار جدید:** سن: ۳۲ سال، جنسیت: زن، تب: بله، سوزش ادرار: بله، تعداد گلبول سفید: ۱۷,۰۰۰

**سوال: به عنوان یک مدل AI که بر اساس ۱۰ نمونه قبلی آموزش دیده، تشخیص شما چیست؟ چرا؟**

**مرحله ۳: درک محدودیت‌ها**
چرا تشخیص شما ممکن است ۱۰۰٪ قطعی نباشد؟ چه اطلاعات اضافی می‌توانست به شما کمک کند تا مدل بهتری بسازید؟ (مثلا: سابقه بیماری، نتایج کشت ادرار و...)

### 🚫 **باورهای غلط رایج درباره AI**

- **❌ باور غلط ۱: AI مانند انسان "فکر" می‌کند.**
  **واقعیت:** AI فکر نمی‌کند، احساس ندارد و خلاقیت به معنای انسانی ندارد. AI یک ابزار بسیار قدرتمند برای **شناسایی الگوهای ریاضی** در داده‌هاست.

- **❌ باور غلط ۲: AI همیشه درست می‌گوید و هرگز اشتباه نمی‌کند.**
  **واقعیت:** دقت AI به شدت به **کیفیت و کمیت داده‌های آموزشی** آن بستگی دارد. اگر داده‌های آموزشی ناقص یا دارای سوگیری باشند، AI هم همان اشتباهات را تکرار خواهد کرد. (به این می‌گویند: "Garbage in, garbage out" یا "آشغال بدی، آشغال تحویل می‌گیری").

- **❌ باور غلط ۳: AI قرار است جایگزین پزشکان و دانشمندان شود.**
  **واقعیت:** خیر. موفق‌ترین کاربردهای AI در **همکاری انسان و ماشین** است. AI کارهای تکراری و تحلیلی را با سرعت بالا انجام می‌دهد و به انسان اجازه می‌دهد تا بر تفکر خلاق، تصمیم‌گیری نهایی و تعامل انسانی تمرکز کند.

### 💡 نکات کلیدی این بخش

- **AI تقلیدگر است:** هوش مصنوعی از فرآیند یادگیری انسان (تجربه -> الگو -> پیش‌بینی) تقلید می‌کند.
- **AI با داده کار می‌کند:** سوخت اصلی هوش مصنوعی، داده است. هرچه داده بیشتر و باکیفیت‌تر باشد، AI هوشمندتر می‌شود.
- **AI یک ابزار است:** AI جایگزین تفکر انسان نیست، بلکه ابزاری برای تقویت و افزایش توانایی‌های ماست.
- **کاربردهای اصلی:** مهم‌ترین کاربردهای AI در زیست‌شناسی شامل تشخیص الگو، پیش‌بینی، بهینه‌سازی و تولید داده‌های جدید است.

حالا که یک درک کلی از چیستی هوش مصنوعی پیدا کردیم، در بخش بعدی به سراغ اولین ماده اولیه و مهم‌ترین بخش این پازل می‌رویم: **داده!** بیایید ببینیم "انقلاب داده" در زیست‌شناسی دقیقاً به چه معناست.

[1] https://www.emjreviews.com/dermatology/news/experience-and-dermoscopy-improve-skin-cancer-diagnosis-accuracy/
[2] https://pubmed.ncbi.nlm.nih.gov/39535756/
[3] https://www.beckershospitalreview.com/oncology/skin-cancer-diagnosis-accuracy-varies-by-physician-4-study-notes/
[4] https://www.theverge.com/2017/1/26/14396500/ai-skin-cancer-detection-stanford-university
[5] https://cs.stanford.edu/people/esteva/nature/
[6] https://news.stanford.edu/stories/2017/01/artificial-intelligence-used-identify-skin-cancer
[7] https://www.wired.com/story/ai-detect-diagnosis-cancer-skin-breast/
[8] https://fortune.com/2017/01/26/stanford-ai-skin-cancer/
[9] https://www.cnn.com/2017/01/26/health/ai-system-detects-skin-cancer-study
[10] https://www.genengnews.com/gen-edge/the-unbearable-cost-of-drug-development-deloitte-report-shows-15-jump-in-rd-to-2-3-billion/
[11] https://www.fiercebiotech.com/biotech/drug-development-cost-pharma-22b-asset-2024-plus-how-glp-1s-impact-roi-deloitte
[12] https://www.upm-inc.com/drug-development-process
[13] https://www.ppd.com/what-is-a-cro/drug-discovery-and-development/
[14] https://www.technologyreview.com/2020/04/15/999303/ai-vs-bacteria/
[15] https://pubmed.ncbi.nlm.nih.gov/32084340/
[16] https://news.mit.edu/2020/artificial-intelligence-identifies-new-antibiotic-0220
[17] https://www.eurekalert.org/news-releases/1029354
[18] https://alj.com/en/news/j-clinic-discovers-powerful-new-antibiotic-using-ai-technology/
[19] https://pmc.ncbi.nlm.nih.gov/articles/PMC8698312/
[20] https://www.sciencedirect.com/science/article/pii/S0092867420301021
[21] https://itif.org/publications/2024/11/18/ai-can-transform-drug-development/
[22] https://www.drugpatentwatch.com/blog/how-ai-is-already-changing-drug-development/
[23] https://www.idtechex.com/th/research-article/ai-in-drug-discovery-cuts-timelines-from-5-years-to-months/24011
[24] https://www.carsongroup.com/insights/blog/ai-is-unraveling-the-structures-of-life-accelerating-drug-development/
[25] https://ada.com/white-blood-cell-count/
[26] https://www.healthline.com/health/wbc-count
[27] https://my.clevelandclinic.org/health/diseases/17704-high-white-blood-cell-count
[28] https://academic.oup.com/bjd/article/191/1/125/7564904
[29] https://pmc.ncbi.nlm.nih.gov/articles/PMC10571810/
[30] https://www.curemelanoma.org/blog/applying-ai-to-melanoma-detection
[31] https://med.stanford.edu/news/all-news/2024/04/ai-skin-diagnosis.html
[32] https://www.ajmc.com/view/ai-based-smartphone-app-proves-reliable-in-diagnosis-of-melanoma
[33] https://www.techtarget.com/healthtechanalytics/news/366590002/Artificial-intelligence-tools-improve-skin-cancer-diagnostic-accuracy
[34] https://www.nature.com/articles/s43856-024-00598-5
[35] https://dermnetnz.org/topics/artificial-intelligence
[36] https://www.curemelanoma.org/blog/ai-and-melanoma-innovation-for-the-future
[37] https://stanfordhealthcare.org/medical-clinics/skin-cancer-program.html
[38] https://arxiv.org/abs/2401.14193
[39] https://dermnetnz.org/topics/convolutional-neural-networks-in-dermatology
[40] https://pubmed.ncbi.nlm.nih.gov/38594408/
[41] https://www.nature.com/articles/s41467-025-59532-5
[42] https://wyss.harvard.edu/media-post/harnessing-the-power-of-artificial-intelligence-synthetic-biology-to-usher-in-a-new-age-of-drug-discovery-jim-collins/
[43] https://www.genengnews.com/topics/artificial-intelligence/explainable-ai-directs-small-molecule-structural-class-drug-discovery/
[44] https://erictopol.substack.com/p/jim-collins-discovery-of-the-first
[45] https://pmc.ncbi.nlm.nih.gov/articles/PMC10493153/
[46] https://www.ddw-online.com/ai-helps-find-first-new-antibiotic-in-60-years-27807-202401/
[47] https://news.mit.edu/2023/using-ai-mit-researchers-identify-antibiotic-candidates-1220
[48] https://www.collinslab.mit.edu
[49] https://www.sciencedirect.com/science/article/pii/S2095177925000656
[50] https://www.nad.com/news/new-anti-aging-drugs-artificial-intelligence-harvard-mit
[51] https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2820562
[52] https://www.drugdiscoverytrends.com/pharmas-top-20-rd-spenders-in-2020/
[53] https://intuitionlabs.ai/articles/drug-development-timeline-challenges
[54] https://biostock.se/en/2023/01/drug-development-the-four-phases/
[55] https://www.lshtm.ac.uk/newsevents/news/2020/average-cost-developing-new-drug-could-be-15-billion-less-pharmaceutical
[56] https://www.rdworldonline.com/how-much-does-the-pharma-industry-spend-on-rd-anyway-probably-more-than-you-thought/
[57] https://pubmed.ncbi.nlm.nih.gov/32125404/
[58] https://www.investopedia.com/ask/answers/060115/how-much-drug-companys-spending-allocated-research-and-development-average.asp
[59] https://matchtrial.health/en/how-long-does-it-take-to-develop-a-new-drug/
[60] https://en.wikipedia.org/wiki/Cost_of_drug_development
[61] https://www.statista.com/statistics/309466/global-r-and-d-expenditure-for-pharmaceuticals/
[62] https://pubs.acs.org/doi/10.1021/cn500298z
[63] https://pmc.ncbi.nlm.nih.gov/articles/PMC11214120/
[64] https://www.lindushealth.com/blog/understanding-the-pharmaceutical-development-timeline-key-stages-and-processes
[65] https://www.zeclinics.com/blog/drug-discovery-and-development-process/
[66] https://www.cbo.gov/publication/57126
[67] https://jamanetwork.com/journals/jamadermatology/fullarticle/2785614
[68] http://www.actasdermo.org/en-effectiveness-primary-care-physicians-dermatologists-articulo-S1578219011707521
[69] https://onlinelibrary.wiley.com/doi/10.1111/jdv.17129
[70] https://pmc.ncbi.nlm.nih.gov/articles/PMC10906670/
[71] https://dialnet.unirioja.es/servlet/articulo?codigo=6551808
[72] https://ecancer.org/en/news/23820-ai-software-shows-significant-improvement-in-skin-cancer-detection-new-study-shows
[73] https://www.jabfm.org/content/jabfp/34/5/984.full.pdf
[74] https://pubmed.ncbi.nlm.nih.gov/11903237/
[75] https://www.lubbockdermatology.com/files/midleveVSdermDX.pdf
[76] https://www.cancertherapyadvisor.com/news/in-person-exam-with-dermoscopy-yields-more-accurate-skin-cancer-diagnosis/
[77] https://www.actasdermo.org/es-melanoma-detection-patterns-their-association-articulo-S0001731025002789
[78] https://www.sciencedirect.com/science/article/pii/S0151963824000541
[79] https://pmc.ncbi.nlm.nih.gov/articles/PMC11460753/
[80] https://skin-analytics.com/ai-pathways/derm-performance/
[81] https://pmc.ncbi.nlm.nih.gov/articles/PMC9180451/
[82] https://www.sciencedirect.com/science/article/pii/S1578219011707521
[83] https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2021.637069/full
[84] https://www.vinmec.com/eng/blog/why-do-urine-tests-have-high-white-blood-cells-en
[85] https://www.medicalnewstoday.com/articles/can-uti-cause-fever
[86] https://www.nhs.uk/conditions/low-white-blood-cell-count/
[87] https://www.verywellhealth.com/leukocytes-in-urine-normal-range-8659879
[88] https://www.nhs.uk/conditions/urinary-tract-infections-utis/
[89] https://www.medicalnewstoday.com/articles/313751
[90] https://en.wikipedia.org/wiki/Urinary_tract_infection
[91] https://medlineplus.gov/lab-tests/white-blood-count-wbc/
[92] https://pmc.ncbi.nlm.nih.gov/articles/PMC6533974/
[93] https://www.hopkinsmedicine.org/health/conditions-and-diseases/urinary-tract-infections/is-that-burning-sensation-a-urinary-tract-infection
[94] https://www.medicalnewstoday.com/articles/315133
[95] https://www.webmd.com/a-to-z-guides/leukocytes-urine
[96] https://medlineplus.gov/urinarytractinfections.html
[97] https://www.tuasaude.com/en/leukocytes-in-urine/
[98] https://my.clevelandclinic.org/health/diseases/9135-urinary-tract-infections
[99] https://pubmed.ncbi.nlm.nih.gov/19748419/
[100] https://www.mayoclinic.org/diseases-conditions/urinary-tract-infection/symptoms-causes/syc-20353447
