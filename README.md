# EduLearn - Multilevel & IELTS Ingliz Tili Ta'lim Platformasi

Ushbu platforma ingliz tilini noldan professional darajagacha (Multilevel va IELTS) tizimli o'rganish uchun yaratilgan to'liq interaktiv veb-ilovadir.

## 📁 Loyiha Joylashuvi (Papka)
```text
C:\Users\user\.gemini\antigravity\scratch\edulearn-platform\
```

## 🚀 Qanday Ishga Tushiriladi?
Ilovada hech qanday murakkab o'rnatishlar (`npm`, `python` yoki boshqa kutubxonalar) talab etilmaydi!
Shunchaki `index.html` faylini istalgan brauzerda (Google Chrome, Microsoft Edge, Opera va hk) ikki marta bosib ochsangiz kifoya:
```text
file:///C:/Users/user/.gemini/antigravity/scratch/edulearn-platform/index.html
```

---

## 🌟 Asosiy Imkoniyatlar va Funksiyalar

### 1. Kirish va Onboarding (Tanishuv)
- **Google orqali kirish**: Foydalanuvchi ism-sharifini kiritib tizimga kiradi.
- **Interaktiv Slayder (Taqdimot)**: Landing sahifasida foydalanuvchini jalb qiluvchi 5 ta zamonaviy slayd (o'ng/chapga navigatsiya).
- **Maqsad tanlash**:
  - `Multilevel (CEFR B1-C1)`
  - `IELTS (Band 7.0+)`
- **Kunlik vaqt rejasi**: Minimal 1.5 soatdan 4 soatgacha (1.5, 2.0, 2.5, 3.0, 4.0 soat).
- **Darajani aniqlash**:
  - Bilmayman (0) yoki Beginner
  - Elementary (A2), Pre-Intermediate (B1), Intermediate (B2)
  - Yoki **15 ta savolli Placement Test (Daraja aniqlash testi)**. Natijaga ko'ra tizim avtomatik darajani ochadi!

### 2. Darslar Tuzilishi va Bosqichma-bosqich O'sish
- Har bir darajada 20 ta dars (Beginner uchun 20 dars to'liq yaratilgan).
- Har daraja boshida **PDF Coursebook** darslik kitobini yuklab olish imkoniyati.
- **1-Dars ochiq (unlocked)**.
- **2, 3, ... 20-darslar qulflangan (locked 🔒)**.
- **Keyingi darsni ochish mexanizmi**:
  - Foydalanuvchi qulflangan dars ustiga bosganda: *"Darsni ochish uchun sinov testiga tayyormisiz? -> Ready"* dialogi chiqadi.
  - Test topshiriladi (o'tilgan dars grammatikasi va lug'atlari).
  - Agar **70% dan yuqori** to'plasa -> Dars doimiy ochiq qoladi va qayta test topshirish talab etilmaydi!

### 3. Har bir Dars Ichidagi 5 ta Asosiy Bo'lim (Rasmdagi Tugmalar Uslubida)
1. **Video Lesson**: 10-15-20 daqiqalik video darslik, mavzu tushuntirishi va xulosalari.
2. **Cartoon / Movie Scene**: Speaking va Listening'ni oshirish uchun multfilm/film parchalari, subtitrlar va audio talaffuz.
3. **Vocabularies**: 35+ ta mavzuga oid muhim lug'at (so'z, fonetika, o'zbekcha tarjimasi, misollar va **🔊 Ovozli eshitish** tugmasi - ona tili so'zlovchisi kabi Web Speech API orqali talaffuz qiladi).
4. **Multiple Choice Test**: 15 ta darsga oid test savollari (70%+ to'plash talabi bilan).
5. **Gap tuzish va Tarjima (Interactive Practice)**: 15 ta o'zbekcha gapni ingliz tiliga tarjima qilib yozish va avtomatik tekshirish tizimi.

### 4. Vaqt Hisoblagichi (Real-time Time Tracker)
- Foydalanuvchi saytda qancha vaqt o'tkazayotganini soniyagacha sanab boradi (`00:00:00`).
- Kunlik maqsadiga (masalan, 2 soat) nisbatan foiz va progress-barni ko'rsatib turadi.
- Barcha ma'lumotlar brauzer xotirasida (LocalStorage) avtomatik saqlanadi.

### 5. Admin Boshqaruv Paneli
- **Kirish paroli / maxfiy kodi**: `@Abdukarim010` (Admin panel -> "⚙️ Sozlamalar" orqali xohlagan vaqtda o'zgartirish mumkin)
- Barcha o'quvchilar ro'yxati (Ismi, maqsadi, joriy darajasi, bugungi o'rganish vaqti, oxirgi kirgan vaqti).
- O'quvchi darajasini qo'lda tasdiqlash yoki o'zgartirish (Approve / Set Level).
- Yangi video darsliklarni havola (URL) orqali yuklash va darslarga biriktirish.

### 6. Dizayn va Ranglar Uslubi
- Foydalanuvchi yuborgan rasmdagi uslub asosida yaratilgan:
  - Qoramtir alyuminiy / to'q obsidian binafsha fon (`#0b0a14`, `#121124`, `#18162e`).
  - Dumaloq burchakli (pill shape `border-radius: 22px`) tugmalar.
  - Aktiv tugmada neon binafsha border (`#7c5cfa`) va yumshoq nur (`box-shadow: 0 0 20px rgba(124, 92, 250, 0.45)`).
  - Binafsha raqam nishonlari va toza oq shrift.

---

## 📂 Loyiha Fayllari Arxitekturasi
```text
edulearn-platform/
├── index.html               # Asosiy kirish veb-sahifasi
├── README.md                # Loyiha qo'llanmasi
├── css/
│   └── style.css            # Alyuminiy-binafsha mavzu va rasmdagi tugmalar dizayni
├── js/
│   ├── app.js               # Ilova logikasi, darslar ko'rinishi, quiz va mashqlar
│   ├── storage.js           # Ma'lumotlarni saqlash va foydalanuvchilar bazasi
│   ├── tracker.js           # Kunlik sarflangan vaqt hisoblagichi (Timer)
│   └── audio.js             # Inglizcha lug'atlarni ovozli talaffuz qilish dvigateli
├── admin/
│   └── admin.js             # Admin boshqaruv paneli (kod: @Abdukarim010)
├── data/
│   ├── curriculum.js        # Beginner (20 dars), Elementary, Pre-Inter, Inter, Multilevel, IELTS darslari
│   └── placement-test.js    # 15 ta savolli daraja aniqlash testi
└── assets/                  # Resurslar va kitoblar papkasi
```
