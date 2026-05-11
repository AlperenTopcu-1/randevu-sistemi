# 📅 Randevu Sistemi — Çok Amaçlı Rezervasyon Uygulaması

![Python](https://img.shields.io/badge/Python-3.10-blue) ![Flask](https://img.shields.io/badge/Flask-2.x-green) ![SQLite](https://img.shields.io/badge/SQLite-3-lightgrey) ![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-ORM-red) ![Flask--Login](https://img.shields.io/badge/Flask--Login-Auth-yellow)

Berber, kafe, spor salonu gibi farklı işletmelerin randevu ve rezervasyon süreçlerini yönetmelerine olanak tanıyan, müşteri ve işletme sahibi rollerini destekleyen tam kapsamlı bir Flask web uygulaması.

---

## ✨ Özellikler

- 👤 **İki Farklı Kullanıcı Rolü** — Müşteri ve işletme sahibi olarak ayrı kayıt & giriş akışı
- 🏪 **İşletme Profili Yönetimi** — İşletme türü, açıklama, çalışma saatleri belirleme
- 🪑 **Kaynak Yönetimi** — Masa, koltuk, usta gibi rezerve edilebilir kaynaklar ekleme / silme
- 📆 **Randevu Alma** — Müşteriler işletmelere göz atarak uygun saatte rezervasyon yapabilir
- ⚡ **Çakışma Kontrolü** — Aynı kaynak için aynı zaman dilimine çift rezervasyon önlenir
- ❌ **İptal & Silme** — Müşteri veya işletme sahibi kendi yetki alanındaki randevuları yönetebilir
- 🔐 **Güvenli Kimlik Doğrulama** — Werkzeug ile şifre hashing, Flask-Login ile oturum yönetimi

---

## 🛠 Teknolojiler

| Katman | Teknoloji |
|--------|-----------|
| Backend | Python 3.x / Flask |
| Veritabanı | SQLite / SQLAlchemy ORM |
| Frontend | HTML / CSS / Jinja2 Templates |
| Kimlik Doğrulama | Flask-Login / Werkzeug |
| Deployment | Geliştirme: Flask Dev Server |

---

## 📁 Proje Yapısı

```
randevu-sistemi/
├── app.py                          # Ana uygulama, rotalar ve iş mantığı
├── models.py                       # SQLAlchemy model tanımları
├── requirements.txt                # Bağımlılıklar
├── static/
│   └── style.css                   # Genel stil dosyası
└── templates/
    ├── base.html                   # Temel şablon (tüm sayfalar kalıtır)
    ├── index.html                  # Giriş sayfası
    ├── login.html                  # Kullanıcı girişi
    ├── register.html               # Kayıt formu (rol seçimi dahil)
    ├── business_dashboard.html     # İşletme sahibi paneli
    ├── customer_dashboard.html     # Müşteri paneli (işletmeleri listeleme)
    └── booking.html                # Randevu alma sayfası
```

---

## 🚀 Kurulum

```bash
# 1. Repoyu klonla
git clone https://github.com/AlperenTopcu-1/randevu-sistemi.git
cd randevu-sistemi

# 2. Bağımlılıkları yükle
pip install -r requirements.txt

# 3. Uygulamayı başlat
python app.py
```

> 🌐 Tarayıcında aç: `http://localhost:5000`
> 
> 📝 Veritabanı (`randevu_v2.db`) ilk çalıştırmada otomatik oluşturulur.

---

## 🗄️ Veritabanı Şeması

| Tablo | Alanlar |
|-------|---------|
| `user` | id, username, email, password, role |
| `business` | id, owner_id, name, type, description, open_time, close_time |
| `resource` | id, business_id, name, capacity |
| `appointment` | id, user_id, resource_id, start_time, end_time, status |

---

## 🔄 Kullanıcı Akışı

```
Kayıt (Müşteri / İşletme Sahibi)
        │
        ▼
   Giriş Yap
   ┌──────────────────────────────┐
   │                              │
   ▼                              ▼
Müşteri Paneli             İşletme Paneli
İşletmeleri Gör            İşletme Profili Oluştur
Randevu Al                 Kaynak Ekle / Sil
Randevu İptal Et           Randevuları Yönet
```

---

## 👨‍💻 Geliştirici

Alperen Topcu — [@AlperenTopcu-1](https://github.com/AlperenTopcu-1)
