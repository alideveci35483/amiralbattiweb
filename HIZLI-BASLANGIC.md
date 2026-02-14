# ⚡ Hızlı Başlangıç - 5 Dakikada Online Oyun

## 🎯 Ne Yapacaksınız?

Firebase (Google'ın ücretsiz servisi) ile gerçek zamanlı multiplayer oyun kuracaksınız.

**Sonuç:** Her oyuncu kendi telefonundan/tabletinden aynı anda oynayabilecek! 📱📱📱

---

## 🚀 5 Dakikalık Kurulum

### 1️⃣ Firebase Projesi Oluşturun (2 dakika)

🔗 **[console.firebase.google.com](https://console.firebase.google.com)** → Giriş yapın

1. **"Add project"** → Proje adı yazın: `amiral-batti`
2. **"Continue"** → Google Analytics: **KAPALI** → **"Create project"**
3. ✅ Proje hazır!

---

### 2️⃣ Database Ekleyin (1 dakika)

1. Sol menü → **"Build"** → **"Realtime Database"**
2. **"Create Database"**
3. Konum: **Europe (eur3)**
4. Mod: **"Start in TEST MODE"** ⚠️ ÖNEMLİ!
5. **"Enable"**

---

### 3️⃣ Config Bilgilerini Alın (1 dakika)

1. Sol üst → **"Project Overview"** (⚙️ yanında)
2. **"</>"** (Web) ikonuna tıklayın
3. App adı: `Amiral Batti` → **"Register app"**
4. **Config kodunu KOPYALAYIN:**

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "...",
  databaseURL: "...",  // ← Bu satır ÖNEMLİ!
  projectId: "...",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

---

### 4️⃣ HTML Dosyasına Yapıştırın (1 dakika)

1. **`amiral-batti-online.html`** dosyasını **Notepad** veya herhangi bir editörde açın

2. **18-25. satırları bulun** (aşağıdaki gibi):

```javascript
const firebaseConfig = {
    apiKey: "YOUR-API-KEY-HERE",  // ← Buraya
    authDomain: "YOUR-PROJECT-ID.firebaseapp.com",
    // ... vs
```

3. **Kopyaladığınız config ile DEĞİŞTİRİN**

4. **CTRL+S** ile kaydedin

---

### 5️⃣ Test Edin! (30 saniye)

**Bilgisayarda:**
- Dosyaya **çift tıklayın**
- **3 farklı tarayıcı sekmesi** açın
- Her sekmede farklı isimle girin
- Birinde **"Oda Oluştur"**, diğerlerinde **"Odaya Katıl"**

**Telefondan:**
- Dosyayı **GitHub Pages** veya **Netlify**'a yükleyin
- URL'i telefonda açın
- 3 farklı telefon/sekmeden bağlanın

---

## 📱 GitHub Pages'te Yayınlama (2 dakika)

1. **[github.com](https://github.com)** → Giriş yapın
2. **"New repository"** → İsim: `amiral-batti`
3. Dosyayı **`index.html`** olarak yükleyin
4. **Settings** → **Pages** → Source: **main branch** → **Save**
5. ✅ URL'niz hazır: `https://kullaniciadi.github.io/amiral-batti`

---

## 🎮 Nasıl Oynanır?

### Oyuncu 1 (Oda Sahibi):
1. URL'i aç
2. İsim gir
3. **"Yeni Oda Oluştur"** tıkla
4. **Oda kodunu not al** (örn: **ABC123**)
5. WhatsApp'tan arkadaşlara gönder

### Oyuncu 2 ve 3:
1. Aynı URL'i aç
2. İsim gir  
3. **"Odaya Katıl"** tıkla
4. **Oda kodunu yaz** (ABC123)
5. Gemileri yerleştir
6. **"Hazırım"** tıkla

### Oyun Başladı! 🎯
- Sırayla ateş edin
- Vurduğunuzda tekrar atış hakkı kazanırsınız
- Son kalan kazanır!

---

## ⚠️ Önemli Notlar

✅ **Config bilgilerini mutlaka değiştirin** - Yoksa çalışmaz!
✅ **TEST MODE** seçin - Kolay başlangıç için
✅ **databaseURL** mutlaka olmalı - Config'de bu satır önemli
✅ **Ücretsiz** - Firebase free tier yeterli

---

## 🆘 Hata Çözümleri

**"Firebase is not defined"**
→ Config bilgilerini kontrol edin, dosyayı kaydetmeyi unutmayın

**"Oda bulunamadı"**
→ Kod doğru mu? (BÜYÜK HARF önemli: ABC123)

**Bağlanamıyor**
→ İnternet var mı? Firebase Database aktif mi?

---

## 💰 Maliyet

**TAMAMEN ÜCRETSİZ!** 🎉

Firebase Free Tier:
- 100 eşzamanlı oyuncu
- 1 GB depolama
- 10 GB/ay veri

Aile/arkadaş oyunları için fazlasıyla yeterli!

---

## 🎊 Tebrikler!

Artık **gerçek zamanlı online multiplayer** oyununuz hazır!

Her oyuncu **kendi cihazından** oynayabilir! 🚢⚓📱

**Detaylı kurulum için:** `FIREBASE-KURULUM.md` dosyasına bakın
