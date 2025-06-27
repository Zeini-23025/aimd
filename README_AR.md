# AIMD - مولد ملفات README بالذكاء الاصطناعي

**AIMD** هو أداة سطر أوامر تقوم تلقائيًا بإنشاء ملف `README.md` احترافي لأي مشروع باستخدام ذكاء Gemini من Google.

## 🚀 التثبيت السريع

### المتطلبات

- بايثون 3.6 أو أحدث
- مفتاح API من Google AI Studio ([احصل عليه من هنا](https://aistudio.google.com/app/apikey))
- اتصال بالإنترنت

### ويندوز
```cmd
git clone https://github.com/babe051/aimd.git
cd aimd
# شغّل كمسؤول
setup-windows.bat
```

### لينكس/ماك
```bash
git clone https://github.com/babe051/aimd.git
cd aimd
chmod +x setup-unix.sh
sudo ./setup-unix.sh
```

## 📖 طريقة الاستخدام

بعد التثبيت، استخدم الأمر `aimd` من أي مجلد:

```bash
# إنشاء README للمجلد الحالي
aimd .

# إنشاء README لمشروع محدد
aimd /path/to/project

# مثال على ويندوز
aimd C:\Users\username\projects\myapp

# تجاهل ملفات/مجلدات معينة
aimd . -i node_modules "*.log" temp/

# اسم ملف مخصص وحد أقصى للملفات
aimd . --output DOCUMENTATION.md --max-files 100

# أنماط تجاهل متعددة
aimd . -i "*.pyc" "__pycache__/" ".env*" "logs/"
```

## 🛠️ خيارات الأوامر

| الخيار | الوصف | مثال |
|--------|-------|-------|
| `path` | مسار مجلد المشروع | `aimd /projects/webapp` |
| `--output` | اسم ملف الإخراج (افتراضي: README.md) | `--output DOCS.md` |
| `--max-files` | الحد الأقصى للملفات (افتراضي: 50) | `--max-files 100` |
| `-i, --ignore` | ملفات/مجلدات إضافية للتجاهل | `-i logs/ "*.tmp"` |

## ⚙️ الميزات

- 🤖 **مدعوم بالذكاء الاصطناعي**: يستخدم Gemini من Google لإنشاء توثيق ذكي
- 📂 **تحليل ذكي**: يكتشف هيكل المشروع والتقنيات المستخدمة تلقائيًا
- 🚫 **تصفية ذكية**: يحترم ملفات `.gitignore` وأنماط التجاهل المخصصة
- 🎯 **متعدد المنصات**: يعمل على ويندوز، لينكس، وماك
- ⚡ **معالجة سريعة**: أشرطة تقدم وتعامل فعال مع الملفات
- 🎨 **إخراج احترافي**: توثيق جاهز لـ GitHub مع رموز تعبيرية وهيكل منظم

## 📁 ما الذي يتم تحليله؟

يقوم AIMD بتحليل مشروعك بذكاء:

✅ **يشمل:**
- ملفات الشيفرة المصدرية (`.py`, `.js`, `.html`, `.css`, إلخ)
- ملفات الإعدادات (`package.json`, `requirements.txt`, إلخ)
- ملفات التوثيق
- هيكل المشروع والاعتمادات

❌ **يتم تجاهله تلقائيًا:**
- مجلد `.git/`
- مجلد `node_modules/`
- مجلد `__pycache__/`
- الملفات الثنائية والصور
- الملفات الكبيرة (>5MB)
- الملفات المطابقة لأنماط `.gitignore`

## 📊 مثال على الإخراج

```bash
$ aimd .
🚀 Starting AIMD - AI Markdown Generator
📂 Target path: /home/user/myproject
📄 Output file: /home/user/myproject/README.md (in target directory)
--------------------------------------------------
🔍 Analyzing: /home/user/myproject...
📄 README will be saved to: /home/user/myproject/README.md
📂 Processing files |████████████| 25/50 [00:02<00:01]
🎉 README generated successfully!
✅ README.md generated successfully at /home/user/myproject/README.md
--------------------------------------------------
🎉 All done! Your README.md has been generated successfully.
📁 Location: /home/user/myproject/README.md
```

## 🗂️ هيكل ملفات التثبيت

### ويندوز
```
C:\Windows\System32\aimd\
├── aimd.py          # السكريبت الرئيسي
├── generator.py     # منطق التوليد
├── utils.py         # الأدوات المساعدة
└── aimd.bat         # سكريبت الأوامر المحلي

C:\Windows\System32\
└── aimd.bat         # أمر عام (يستدعي السكريبت المحلي)
```

### لينكس/ماك
```
/usr/local/lib/aimd/
├── aimd.py          # السكريبت الرئيسي
├── generator.py     # منطق التوليد
└── utils.py         # الأدوات المساعدة

/usr/local/bin/
└── aimd             # سكريبت الأوامر العام
```

## 🗑️ إزالة التثبيت

### ويندوز
```cmd
# شغّل كمسؤول
uninstall-windows.bat
```

### لينكس/ماك
```bash
sudo ./uninstall-unix.sh
```

### إزالة يدوية
**ويندوز:**
```cmd
del "C:\Windows\System32\aimd.bat"
rmdir /s "C:\Windows\System32\aimd"
```

**لينكس/ماك:**
```bash
sudo rm /usr/local/bin/aimd
sudo rm -rf /usr/local/lib/aimd
```

## 🔧 استكشاف الأخطاء

### مشاكل شائعة

**"Permission denied" أثناء التثبيت**
- **ويندوز**: شغّل التثبيت كمسؤول
- **لينكس/ماك**: استخدم `sudo ./setup-unix.sh`

**"Command not found: aimd"**
- تحقق من اكتمال التثبيت بنجاح
- جرب فتح نافذة طرفية جديدة
- تحقق من وجود الملفات في مجلدات التثبيت

**"No readable files found"**
- تأكد أن المجلد يحتوي على ملفات شيفرة
- تحقق من أنماط التجاهل
- جرب زيادة حد `--max-files`

**"Failed to connect to Google AI Studio"**
- تحقق من اتصال الإنترنت
- تحقق من صحة مفتاح API
- تأكد من وجود الصلاحيات اللازمة للمفتاح

## 🤝 المساهمة

المساهمات مرحب بها! للمساهمة:

1. قم بعمل fork للمستودع
2. أنشئ فرع ميزة (`git checkout -b feature/amazing-feature`)
3. أضف تعديلاتك (`git commit -m 'Add amazing feature'`)
4. ادفع الفرع (`git push origin feature/amazing-feature`)
5. افتح Pull Request

## 📄 الرخصة

هذا المشروع مرخص تحت رخصة MIT - راجع ملف [LICENSE](LICENSE) للمزيد من التفاصيل.

## 🛡️ الأمان

- **سلامة مفاتيح API**: لا تضع المفاتيح في الشيفرة مباشرة
- **المتغيرات البيئية**: استخدم المتغيرات البيئية للبيانات الحساسة
- **صلاحيات الملفات**: سكريبتات التثبيت تتعامل مع الصلاحيات بشكل آمن
- **تثبيت آمن**: يتم وضع الملفات في مجلدات النظام القياسية

## 🔄 سجل الإصدارات

- **v1.0.0**: الإصدار الأول مع دعم متعدد المنصات
- توليد README بالذكاء الاصطناعي بالكامل
- تصفية ذكية للملفات ودعم gitignore
- أشرطة تقدم وتفاعل مرئي
- تثبيت كأمر عام

---
## 👥 المساهمون

- [<img src="https://github.com/babe051.png" width="32" height="32" style="border-radius:50%"/>](https://github.com/babe051)  
  **محمد فال** – [@babe051](https://github.com/babe051)

- [<img src="https://github.com/Zeini-23025.png" width="32" height="32" style="border-radius:50%"/>](https://github.com/Zeini-23025)  
  **زيني شيخ** – [@Zeini-23025](https://github.com/Zeini-23025)

**صنع بحب للمطورين الذين يحبون التوثيق الجيد! 🚀📝**
