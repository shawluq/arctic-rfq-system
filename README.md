# Arctic Ship Repair - RFQ (Request for Quotation) System

## 📋 Overview
Profesyonel bir satınalma tekliflendirme sistemi. Tüm RFQ'ları (Fiyat Talep İstekleri) Google Sheets'te merkezi olarak yönet, tedarikçi cevaplarını otomatik takip et, karşılaştır ve karar ver.

---

## 🎯 Sistem Yapısı

### **1. Master RFQ Database** (Ana Tablo)
Tüm açık ve kapalı RFQ'ların takibi:
- RFQ ID, Tarih, Talep Edilen Ürün
- Tedarikçiler ve Cevap Durumu
- Fiyat, Teslim Süresi, Ödeme Şartları
- Status (Açık / Kapalı / Bekleme)

### **2. Vendor Response Form** (Tedarikçi Formu)
Tedarikçilerin dolduracağı standardize form:
- Otomatik email linki
- Validasyonlu input alanları
- Auto-populate backlink to Master Sheet

### **3. Comparison & Analysis** (Karşılaştırma)
- En ucuz, en hızlı, en güvenilir tedarikçi
- Fiyat vs. Teslim Süresi analizi
- Supplier Performance Score

### **4. Follow-up Tracking** (Takip Listesi)
- Hangisine mail gönderildi
- Cevap verenler ve vermeyenler
- Otomatik reminder zamanı

### **5. Historical Data** (Geçmiş Veriler)
- Geçmiş RFQ'lar ve sonuçlar
- Tedarikçi reliability score
- Trending fiyatlar

---

## 🚀 Kurulum (5 Dakika)

### Step 1: Google Sheets'te Spreadsheet Oluştur
```
https://sheets.google.com → "+ Yeni Dosya" → "Boş Spreadsheet"
Adı: "Arctic Ship Repair - RFQ System 2026"
```

### Step 2: Repository'deki Template'leri Kopyala
Aşağıdaki dosyaları indir ve Google Sheets'e kopyala:
- `sheets/01-Master-RFQ-Database.csv`
- `sheets/02-Vendor-Response-Template.csv`
- `sheets/03-Comparison-Analysis.csv`

### Step 3: Sheets Oluştur
Google Sheets'te 5 ayrı Sheet oluştur (tabs):
1. **Dashboard** (Özet)
2. **RFQ Master** (Tüm talepler)
3. **Vendor Responses** (Gelen cevaplar)
4. **Analysis** (Karşılaştırma)
5. **Follow-up** (Takip listesi)

### Step 4: Email & Automation Kur
- `email-templates/` klasöründeki emailler kullan
- Google Forms ile Vendor Response Form yap
- Zapier veya Apps Script ile otomasyonu kur

---

## 📊 Kullanım Akışı

### **Yeni RFQ Başlat:**
```
1. Dashboard'da "Yeni RFQ" butonuna tıkla
2. Ürün bilgileri gir → Otomatik ID atanır
3. Tedarikçileri seç
4. Email gönder (template'i kopyala)
5. Takip listesine ekle
```

### **Cevapları Takip Et:**
```
1. Vendor Response Sheet'de cevapları gör
2. Analysis sheet'de otomatik karşılaştırma
3. En iyi 3 option vurgula
4. Follow-up reminder gelirse: Eskal et
```

### **Karar Ver & Sonuçla:**
```
1. Best price, best delivery, best reliability seç
2. Müşteriye teklif mailini gönder
3. RFQ Status'ü "Closed" yap
4. Historical data'ya kaydet
```

---

## 📧 Email Templates

Tedarikçilere gönderilecek 3 tip email:

1. **Initial RFQ Email** - İlk talep
2. **Reminder Email #1** - 4 saat sonra (cevap yoksa)
3. **Reminder Email #2** - 24 saat sonra (tekrar cevap yoksa)

Tüm template'ler `email-templates/` klasöründe.

---

## 🔧 Otomasyonlar (İsteğe Bağlı)

### **Google Apps Script** (Ücretsiz)
- Otomatik email gönderi
- Status güncellemesi
- Reminder notifikasyonları

### **Zapier Integration** (Ücretli: $10-30/ay)
- Gmail → Google Sheets
- Slack notifications
- Scheduled reminders

### **Google Forms** (Ücretsiz)
- Tedarikçilere form linki gönder
- Otomatik response collection
- Data validation

---

## 📈 KPI's & Metrics

Aylık olarak takip et:
- **Avg Response Time**: Tedarikçiler ortalama kaç saatte cevap veriyor?
- **Accuracy Score**: İlk cevap fiyatı = nihai fiyat mı?
- **Compliance Rate**: Talep edilen bilgileri veriyorlar mı?
- **Best Supplier**: En hızlı, en ucuz, en güvenilir kim?

---

## 💡 Pro Tips

1. **Email Subject Standartı**: Her mail başında `[RFQ-ID]` ekle
   ```
   [RFQ-NVS-0001] FAN MOTOR - Fiyat Talebi
   ```

2. **Response Deadline**: Her RFQ'da "Cevap deadline: XXX" belirt
   ```
   "Lütfen en geç 24 saat içinde cevap veriniz"
   ```

3. **Vendor Database**: Tedarikçi bilgilerini ayrı sheet'te tut
   ```
   Adı, Email, Phone, Category, Performance Score, Last Used
   ```

4. **Currency Standardization**: Hep USD'ye çevir
   ```
   EUR 100 = USD 110 (TCMB kuru kullan)
   ```

5. **Follow-up Otomasyonu**: Cevap verenleri reward et
   ```
   "Hızlı cevap veren tedarikçileri priority listesine al"
   ```

---

## 📁 Klasör Yapısı

```
arctic-rfq-system/
├── README.md
├── SETUP-GUIDE.md
├── sheets/
│   ├── 01-Master-RFQ-Database.csv
│   ├── 02-Vendor-Response-Template.csv
│   ├── 03-Comparison-Analysis.csv
│   ├── 04-Follow-up-Tracking.csv
│   └── 05-Vendor-Database.csv
├── email-templates/
│   ├── 01-Initial-RFQ-Email.txt
│   ├── 02-Reminder-Email-4h.txt
│   ├── 03-Reminder-Email-24h.txt
│   └── 04-Customer-Quotation-Email.txt
├── automation/
│   ├── google-apps-script.gs
│   ├── zapier-setup.md
│   └── google-forms-template.txt
└── analytics/
    ├── Monthly-KPI-Dashboard.csv
    └── Vendor-Performance-Report.csv
```

---

## 🎓 Training & Onboarding

Yeni ekip üyesi için:
1. Bu README'yi oku (5 dk)
2. `SETUP-GUIDE.md`'yi takip et (10 dk)
3. Örnek bir RFQ başlat (5 dk)
4. Email template'lerini kopyala (2 dk)

**Toplam: 22 dakika**

---

## ❓ FAQ

**Q: Ne sıklıkla kullanmalıyız?**
A: Her talep için. Sistem açık olsun, mail gönderirken otomatik RFQ database'e ekle.

**Q: Kaç tedarikçiye mail göndermeliyiz?**
A: Ürüne göre 3-5 tedarikçi ideal. Çok fazla = fazla mail, az = seçenek yok.

**Q: Follow-up ne kadar sonra yapmalıyız?**
A: T+4h, T+24h, T+48h. Sonra ürün listeyi değiştir.

**Q: Cevap gelmezse ne yapmalıyız?**
A: Status = "No Response", alternatif tedarikçi ekle, sonraki RFQ'da bu vendor'ı kullanma.

---

## 📞 Support

Sorun yaşarsan:
- GitHub Issues'da sorunu aç
- `SETUP-GUIDE.md`'deki troubleshooting section'a bak
- Slack/Email ile ekibe bildir

---

**Last Updated:** 2026-09-09
**Version:** 1.0
**Author:** Copilot RFQ System