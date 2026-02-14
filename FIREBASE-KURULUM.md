# 🔥 Amiral Battı - Firebase Online Multiplayer Kurulum

## 📋 Gereksinimler

- Google hesabı (Gmail)
- Web tarayıcı
- 10-15 dakika

---

## 🚀 Adım 1: Firebase Projesi Oluşturun

1. **Firebase Console'a gidin:**
   - [https://console.firebase.google.com](https://console.firebase.google.com)
   - Google hesabınızla giriş yapın

2. **Yeni proje oluşturun:**
   - "Add project" veya "Proje ekle" butonuna tıklayın
   - Proje adı girin: `amiral-batti` (veya istediğiniz bir ad)
   - "Continue" / "Devam" tıklayın
   - Google Analytics'i kapatabilirsiniz (isteğe bağlı)
   - "Create project" / "Projeyi oluştur" tıklayın
   - Proje hazır olana kadar bekleyin (30 saniye)

---

## 🗄️ Adım 2: Realtime Database Ekleyin

1. **Sol menüden "Build" → "Realtime Database" seçin**

2. **"Create Database" butonuna tıklayın**

3. **Konum seçin:**
   - Europe (eur3) - Avrupa için önerilen
   - "Next" tıklayın

4. **Güvenlik kurallarını seçin:**
   - **"Start in TEST MODE"** seçin (ÖNEMLİ!)
   - "Enable" tıklayın

5. **Database URL'inizi not edin:**
   - Üstte göreceksiniz: `https://PROJE-ADI-default-rtdb.europe-west1.firebasedatabase.app`
   - Bu URL'i kopyalayın, lazım olacak!

---

## 🔐 Adım 3: Güvenlik Kurallarını Ayarlayın

**ÖNEMLİ:** Test modunda database 30 gün sonra kapanır. Kalıcı kullanım için kuralları güncelleyin:

1. **Realtime Database sayfasında "Rules" sekmesine gidin**

2. **Aşağıdaki kuralları yapıştırın:**

```json
{
  "rules": {
    "games": {
      "$roomCode": {
        ".read": true,
        ".write": true,
        ".indexOn": ["createdAt"]
      }
    }
  }
}
```

3. **"Publish" butonuna tıklayın**

---

## 🔑 Adım 4: Web App Config Bilgilerini Alın

1. **Firebase Console'da sol üstteki "Project Overview" (Projeye genel bakış) tıklayın**

2. **"</>" (Web) ikonuna tıklayın**

3. **App adı girin:**
   - `Amiral Batti Web` gibi bir ad
   - "Register app" tıklayın

4. **Config bilgilerini kopyalayın:**

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "amiral-batti-xxxxx.firebaseapp.com",
  databaseURL: "https://amiral-batti-xxxxx-default-rtdb.europe-west1.firebasedatabase.app",
  projectId: "amiral-batti-xxxxx",
  storageBucket: "amiral-batti-xxxxx.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef123456"
};
```

5. **Bu bilgileri bir yere kaydedin!**

---

## 📝 Adım 5: HTML Dosyasını Güncelleyin

1. **`amiral-batti-online.html` dosyasını bir metin editöründe açın**
   - Notepad, VS Code, veya herhangi bir editör

2. **18-25. satırları bulun:**

```javascript
const firebaseConfig = {
    apiKey: "YOUR-API-KEY-HERE",
    authDomain: "YOUR-PROJECT-ID.firebaseapp.com",
    databaseURL: "https://YOUR-PROJECT-ID-default-rtdb.firebaseio.com",
    projectId: "YOUR-PROJECT-ID",
    storageBucket: "YOUR-PROJECT-ID.appspot.com",
    messagingSenderId: "YOUR-MESSAGING-SENDER-ID",
    appId: "YOUR-APP-ID"
};
```

3. **Kopyaladığınız Firebase config ile değiştirin**

4. **Dosyayı kaydedin**

---

## 🎮 Adım 6: Oyunu Test Edin

### Bilgisayarda Test:

1. **`amiral-batti-online.html` dosyasına çift tıklayın**
2. **İsminizi girin ve "Yeni Oda Oluştur" tıklayın**
3. **Oda kodunu not edin** (örn: ABC123)
4. **Yeni bir tarayıcı sekmesi açın** (veya farklı tarayıcı)
5. **Aynı HTML dosyasını açın**
6. **Farklı isim girin ve oda kodunu yazıp "Odaya Katıl" tıklayın**
7. **3. oyuncu için tekrarlayın**

### Telefondan Test:

1. **HTML dosyasını bir web hosting'e yükleyin** (GitHub Pages, Netlify vs.)
2. **Telefon tarayıcısından URL'i açın**
3. **Her cihazdan farklı isimle bağlanın**

---

## 🌐 Adım 7: Web'de Yayınlayın

### GitHub Pages ile:

1. **GitHub'da yeni repository oluşturun**
2. **`amiral-batti-online.html` dosyasını `index.html` olarak yükleyin**
3. **Settings → Pages → Source: main branch**
4. **URL'niz:** `https://kullaniciadi.github.io/repo-adi`

### Netlify ile:

1. **[netlify.com](https://netlify.com) → Sites → Deploy manually**
2. **Dosyayı sürükle-bırak**
3. **Anında yayında!**

---

## 🎯 Oyun Nasıl Oynanır?

### 1. Oda Oluşturma:
- Bir oyuncu "Yeni Oda Oluştur" tıklar
- Oda kodu alır (örn: **ABC123**)
- Bu kodu diğer oyunculara söyler

### 2. Katılma:
- Diğer 2 oyuncu "Odaya Katıl" tıklar
- Oda kodunu girer
- Lobiye katılır

### 3. Hazırlık:
- Her oyuncu kendi cihazında gemilerini yerleştirir
- "Hazırım" butonuna tıklar
- 3 oyuncu hazır olunca oyun başlar

### 4. Oyun:
- Sırası gelen oyuncu hedef seçer
- Ateş eder
- Vurduğunda tekrar atış hakkı kazanır
- Iskaladığında sıra diğerine geçer

### 5. Kazanma:
- Son kalan oyuncu kazanır! 🏆

---

## 🔧 Sorun Giderme

### "Firebase is not defined" hatası:
- Config bilgilerini doğru yapıştırdığınızdan emin olun
- Tarayıcıyı yenileyip tekrar deneyin

### Oyun bağlanmıyor:
- İnternet bağlantınızı kontrol edin
- Firebase Console'da Database'in aktif olduğunu kontrol edin
- Güvenlik kurallarının doğru olduğunu kontrol edin

### Oda bulunamadı:
- Oda kodunu doğru yazdığınızdan emin olun (BÜYÜK HARF)
- Oda oluşturan kişi hala bağlı mı kontrol edin

### Mobilden oynarken sorun:
- Tam ekran için tarayıcının tam ekran modunu kullanın
- Yatay mod önerilir
- Safari veya Chrome kullanın

---

## 💡 İpuçları

✅ **Her cihaz kendisi için oynar** - Artık tek cihaz paylaşmanıza gerek yok!
✅ **Oda kodu paylaşın** - WhatsApp, SMS ile gönderebilirsiniz
✅ **3 kişi aynı anda** - Her biri kendi telefonundan
✅ **Ücretsiz** - Firebase free tier yeterli (100 eşzamanlı bağlantı)
✅ **Gerçek zamanlı** - Hamleler anında yansır

---

## 📊 Firebase Ücretsiz Limitleri

- **Eşzamanlı bağlantı:** 100 kullanıcı
- **Depolama:** 1 GB
- **Veri transfer:** 10 GB/ay
- **Database yazma:** 20K/gün

**Not:** Küçük aile/arkadaş grupları için fazlasıyla yeterli! 🎉

---

## 🆘 Destek

Sorun yaşarsanız:

1. Firebase Console → Database → Data sekmesinden verileri kontrol edin
2. Tarayıcı Console'da (F12) hata mesajlarına bakın
3. Config bilgilerini tekrar kontrol edin

---

## 🎉 Keyifli Oyunlar!

Artık kızlarınız her biri kendi cihazından aynı anda oynayabilir! 🚢⚓📱
