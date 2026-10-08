# 🔍 FaceTracker Pro

<div align="center">

```
███████╗ █████╗  ██████╗███████╗████████╗██████╗  █████╗  ██████╗██╗  ██╗███████╗██████╗ 
██╔════╝██╔══██╗██╔════╝██╔════╝╚══██╔══╝██╔══██╗██╔══██╗██╔════╝██║ ██╔╝██╔════╝██╔══██╗
█████╗  ███████║██║     █████╗     ██║   ██████╔╝███████║██║     █████╔╝ █████╗  ██████╔╝
██╔══╝  ██╔══██║██║     ██╔══╝     ██║   ██╔══██╗██╔══██║██║     ██╔═██╗ ██╔══╝  ██╔══██╗
██║     ██║  ██║╚██████╗███████╗   ██║   ██║  ██║██║  ██║╚██████╗██║  ██╗███████╗██║  ██║
╚═╝     ╚═╝  ╚═╝ ╚═════╝╚══════╝   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝
                              ██████╗ ██████╗  ██████╗ 
                              ██╔══██╗██╔══██╗██╔═══██╗
                              ██████╔╝██████╔╝██║   ██║
                              ██╔═══╝ ██╔══██╗██║   ██║
                              ██║     ██║  ██║╚██████╔╝
                              ╚═╝     ╚═╝  ╚═╝ ╚═════╝ 
```

![Python 3.6+](https://img.shields.io/badge/Python-3.6%2B-blue.svg)
![OS Linux](https://img.shields.io/badge/Supported%20OS-Linux-yellow.svg)
![License MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Version 2.0](https://img.shields.io/badge/Version-2.0-red.svg)
[![CI](https://github.com/waleedshamhan2050-sys/FaceTracker-Pro/actions/workflows/ci.yml/badge.svg)](https://github.com/waleedshamhan2050-sys/FaceTracker-Pro/actions/workflows/ci.yml)

**أداة متقدمة للبحث عن حسابات المستخدمين في وسائل التواصل الاجتماعي عن طريق صورة الشخص أو اسمه**

[English](#english) | [العربية](#العربية)

</div>

---

## العربية

### 📋 نظرة عامة

**FaceTracker Pro** هي أداة OSINT (استخبارات المصادر المفتوحة) متقدمة تستخدم تقنيات التعرف على الوجوه والبحث العكسي عن الصور للعثور على حسابات الأشخاص في منصات التواصل الاجتماعي.

### ✨ المميزات

- 🔎 **البحث بالصورة**: رفع صورة شخص والبحث عن حساباته في السوشال ميديا
- 👤 **البحث بالاسم**: إدخال اسم الشخص للبحث عن حساباته
- 📸 **Instagram**: البحث والتحقق من حسابات انستقرام
- 📘 **Facebook**: البحث في حسابات فيسبوك ومطابقة الوجوه
- 🐦 **Twitter/X**: البحث في حسابات تويتر
- 🎥 **YouTube**: البحث في قنوات يوتيوب
- 🔄 **البحث العكسي**: استخدام Google Reverse Image Search
- 🧠 **التعرف على الوجوه**: مطابقة ذكية للوجوه باستخدام face_recognition
- 📊 **تقارير احترافية**: إنشاء تقارير PDF و JSON بالنتائج
- 🐳 **Docker Support**: دعم كامل لـ Docker

### 🛠️ المتطلبات

- Python 3.6+
- Linux (Ubuntu/Debian/Arch)
- Firefox أو Chrome WebDriver
- اتصال بالإنترنت

### 📦 التثبيت

#### الطريقة السريعة
```bash
git clone https://github.com/waleedshamhan2050-sys/FaceTracker-Pro.git
cd FaceTracker-Pro
chmod +x install.sh
./install.sh
```

#### التثبيت اليدوي
```bash
git clone https://github.com/waleedshamhan2050-sys/FaceTracker-Pro.git
cd FaceTracker-Pro
pip3 install -r requirements.txt
```

#### باستخدام Docker
```bash
docker build -t facetracker-pro .
docker run -it facetracker-pro
```

### ⚙️ الإعداد

1. **إعداد WebDriver**: حمّل [GeckoDriver](https://github.com/mozilla/geckodriver/releases) أو [ChromeDriver](https://chromedriver.chromium.org/)
2. **تعديل الإعدادات**: عدّل ملف `config.json` حسب احتياجاتك
3. **إضافة الصور**: ضع صور الشخص المطلوب في مجلد `known/`

### 🚀 طريقة الاستخدام

#### البحث الأساسي
```bash
python3 facetracker.py
```

#### تخطي بحث فيسبوك
```bash
python3 facetracker.py --skipfb
```

#### إنشاء تقرير JSON
```bash
python3 facetracker.py --json report.json
```

#### وضع Docker
```bash
python3 facetracker.py --docker --name "اسم الشخص"
```

#### استخدام قائمة روابط فيسبوك
```bash
python3 facetracker.py --skipfb --facebookList urls.txt
```

### 📁 هيكل المشروع

```
FaceTracker-Pro/
├── facetracker.py          # البرنامج الرئيسي
├── face_recog.py           # محرك التعرف على الوجوه
├── config.json             # ملف الإعدادات
├── requirements.txt        # المكتبات المطلوبة
├── install.sh              # سكربت التثبيت التلقائي
├── dockerfile              # ملف Docker
├── grabber/                # وحدات جمع البيانات
│   ├── facebook.py         # جامع بيانات فيسبوك
│   ├── google.py           # البحث العكسي عبر قوقل
│   ├── instagram.py        # جامع بيانات انستقرام
│   └── imageraider.py      # البحث العكسي عبر ImageRaider
├── utils/                  # أدوات مساعدة
│   ├── config.py           # إدارة الإعدادات
│   └── console.py          # واجهة سطر الأوامر
├── report/                 # نظام التقارير
│   ├── report.py           # مولد التقارير
│   └── template.html       # قالب التقرير
├── known/                  # مجلد الصور المرجعية
└── Example.pdf             # مثال على التقرير
```

### ⚙️ ملف الإعدادات (config.json)

| الإعداد | الوصف | القيمة الافتراضية |
|---------|-------|-------------------|
| `SLEEP_DELAY` | التأخير بين الطلبات (ثواني) | 5 |
| `GOOGLE_IMG_PAGES` | عدد صفحات بحث قوقل | 3 |
| `JITTERS` | دقة التعرف على الوجوه | 10 |
| `INSTA_VALIDATION_MAX_IMAGES` | حد صور التحقق من انستقرام | 12 |
| `WEBDRIVER.ENGINE` | محرك المتصفح | firefox |

### 📊 التقارير

الأداة تنشئ تقارير احترافية تحتوي على:
- روابط الحسابات المكتشفة
- تنبؤات قوقل
- حسابات انستقرام المتحقق منها
- متاحة بصيغة **PDF** و **JSON**

---

## English

### 📋 Overview

**FaceTracker Pro** is an advanced OSINT (Open Source Intelligence) tool that uses facial recognition and reverse image search to find social media accounts.

### ✨ Features

- 🔎 **Image Search**: Upload a person's photo to find their social media accounts
- 👤 **Name Search**: Enter a person's name to search for their profiles
- 📸 **Instagram**: Search and validate Instagram profiles
- 📘 **Facebook**: Search Facebook profiles with face matching
- 🐦 **Twitter/X**: Search Twitter accounts
- 🎥 **YouTube**: Search YouTube channels
- 🔄 **Reverse Search**: Google Reverse Image Search integration
- 🧠 **Face Recognition**: Smart face matching using face_recognition library
- 📊 **Professional Reports**: Generate PDF and JSON reports
- 🐳 **Docker Support**: Full Docker support

### 🚀 Quick Start

```bash
git clone https://github.com/waleedshamhan2050-sys/FaceTracker-Pro.git
cd FaceTracker-Pro
pip3 install -r requirements.txt
python3 facetracker.py
```

### 📖 Usage

```bash
# Basic search
python3 facetracker.py

# Skip Facebook search
python3 facetracker.py --skipfb

# Generate JSON report
python3 facetracker.py --json output.json

# Docker mode
python3 facetracker.py --docker --name "Person Name"
```

### 🔧 Configuration

Edit `config.json` to customize:
- Search depth and delay
- WebDriver settings
- Face recognition sensitivity
- Platform-specific filters

---

### ⚠️ تنبيه قانوني | Legal Disclaimer

> هذه الأداة مخصصة للأغراض التعليمية والبحثية فقط. المستخدم مسؤول عن الاستخدام القانوني والأخلاقي للأداة. لا تستخدم هذه الأداة لانتهاك خصوصية الآخرين.

> This tool is intended for educational and research purposes only. The user is responsible for legal and ethical use. Do not use this tool to violate others' privacy.

---

### 👨‍💻 المطور | Developer

**Waleed Shamhan** - Full Stack Developer & Security Researcher

- 💼 [LinkedIn](https://linkedin.com/in/waleed-shamhan-b33a41301)
- 💻 [GitHub](https://github.com/waleedshamhan2050-sys)
- 📢 [Telegram](https://t.me/Programmer_sitting2026)

---

### 🤝 Contributing | المساهمة

Contributions are welcome! | المساهمات مرحب بها!

1. Fork the project | انسخ المشروع
2. Create your feature branch | أنشئ فرعاً لميزتك (`git checkout -b feature/AmazingFeature`)
3. Commit your changes | احفظ تغييراتك (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch | ارفع الفرع (`git push origin feature/AmazingFeature`)
5. Open a Pull Request | افتح طلب دمج

---

### 📄 الرخصة | License

هذا المشروع مرخص تحت رخصة MIT - انظر ملف [LICENSE](LICENSE) للتفاصيل.

---

<div align="center">

⭐ **إذا أعجبك المشروع، لا تنسى تحط نجمة!** ⭐

</div>
