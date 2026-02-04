# Fake Ads → Real Game: AAA Ürün Tasarım Dokümanı

## 0) Ürün Vizyonu
**Amaç:** Mobil reklamlarda görülen sahte oyunları, **%100 gerçek, oynanabilir, ticari seviyede** bir AAA ürününe dönüştürmek. Oyun; mobil + PC + tablet üzerinde akıcı, uzun ömürlü ve bağımlılık yapan derinlikte olacak. Görsel olarak reklamlarla aynı “tad” korunurken, içerik tamamen gerçek sistemlerle desteklenecek.

**Kısa pitch:** “Reklamdaki yalan oyun değil… onun gerçekten olması gereken hali.”

---

## 1) Görsel Kimlik & Sanat Yönetimi
### 1.1 Stil Rehberi
- **Aydınlatma:** soft ama kontrastlı, güçlü **global illumination** hissi.
- **Materyaller:** PBR tabanlı, gerçekçi ama stilize (gerçekçilik + okunabilirlik dengesi).
- **Karakterler:** yüksek poligon, yüzeyde micro-detail, **squash & stretch** destekli.
- **Kamera:** izometrik temel + dinamik zoom + sinematik açı geçişleri (kritik anlarda açı değişimi).

### 1.2 Teknik Shader Seti
- **Outline shader** (ince, okunabilirlik ve “oyuncu odak” için)
- **Glow shader** (ödül, kapı, tuzak, pickup)
- **Soft shadow** (mobilde uyarlanmış, PC’de daha zengin)
- **Depth of Field** (sinematik vurgu)
- **Hafif motion blur** (tempo hissi, aksiyon anlarında)

### 1.3 Performans Hedefleri
- **Mobil:** 60 FPS sabit
- **PC:** 120 FPS hedef
- **Asset streaming + LOD** her platformda zorunlu

---

## 2) Animasyon Sistemi (Kritik)
**Felsefe:** Oyundaki her öğe “yaşıyor” hissi verecek. Robotik hareket yok.

### 2.1 Animasyon Katmanları
- **Procedural Animation:** karakter denge, adım yerleşimi, kameraya adaptif.
- **IK/FK hibrit:** el/kol temasları ve etkileşim anları.
- **Secondary motion:** saç, kıyafet, aksesuar, çevre objeleri.
- **Hit reaction:** darbe geri bildirimi, titreme, deform.
- **Juice & feedback:** UI dahi nefes alır gibi mikro animasyonlarla tepki verir.

### 2.2 Örnek Sistemler
- **Idle varyasyonları:** 3–5 farklı idle, çevresel uyarana bağlı.
- **Eylem sonrası rebound animasyonu:** vurduktan sonra esneme ve toparlanma.

---

## 3) Ana Oyun Mekanikleri (Fake → Real)
Reklamların “sahte” mekanikleri gerçeğe dönüştürülür. Her mekanik **basit → birleşik → meta** şeklinde evrilir.

### 3.1 Kapı Seçme (Door Choice)
- Gerçek fizik: kapılar ağırlık + momentumla açılır.
- Kapılar **gerçek parametreye** bağlıdır: düşman tipi, çevre tuzağı, loot havuzu.
- Strateji: “risk/ödül” yönetimi, kapıların tahmin edilebilir ama tam RNG olmayan yapısı.

### 3.2 Sayı Arttırma (Merge/Multiplier)
- Gerçek hesaplama sistemi: güç “stat” olarak artar (HP, DMG, Crit, speed).
- Multiplier, kısa vadede güçlü ama uzun vadede zayıf olabilir → **build çeşitliliği**.

### 3.3 Tuzaklardan Kaçma
- Fizik tabanlı: momentum, çarpışma ve çevresel zincir reaksiyonları.
- Tuzaklar rastgele değil **öğrenilebilir pattern + skill ceiling** sağlar.

### 3.4 IQ Puzzle / Doğru Yol
- Çözüm birden fazla olabilir.
- Deneyerek çözme: fizik motoru + objelerle etkileşim.

---

## 4) 100+ Bölüm Sistemi
### 4.1 İçerik Planı
- Minimum **100 bölüm** (özel tasarım + procedural).
- **Her 10 bölüm**: yeni mekanik
- **Her 20 bölüm**: yeni düşman türü
- **Her 30 bölüm**: yeni tema

### 4.2 Tema Örnekleri
- Zindan
- Buz Diyarı
- Volkan
- Cyber Şehir
- Antik Tapınak
- Uzay İstasyonu
- Zaman Kırılması Evreni

### 4.3 Procedural + Handcrafted
- Procedural: tekrar oynanabilirlik, sürpriz.
- Handcrafted: sinematik anlar, özel boss tasarımları.

---

## 5) Meta Sistem (Bağımlılık Katmanı)
### 5.1 Karakter Geliştirme
- **Skill Tree** (3 ana yol: saldırı, defans, kontrol)
- **Ekipman sistemi** (loot + upgrade + set bonus)
- **Kozmetik** (monetization + kişiselleştirme)

### 5.2 Sosyal & Rekabet
- **Leaderboard** (haftalık / aylık)
- **Boss raid** (co-op)
- **Günlük/Haftalık görevler**
- **Achievement sistemi**

---

## 6) Fizik & Etkileşim
- Kapılar ağırlıkla açılır, farklı momentum değerlerine sahiptir.
- Tuzaklar zincirleme reaksiyon yaratır.
- Oyuncu çevreyi “deneyerek” çözebilir.
- Tek doğru yol yok → çoklu çözüm.

---

## 7) UI / UX (Apple Seviyesi)
- Minimal, temiz.
- **Glass + blur efektleri**.
- Parallax katmanları.
- Mikro animasyonlar: butonlar fiziksel hissiyat verir.
- Kullanıcı **hiç düşünmeden** kullanabilir, ama derinliği keşfeder.

---

## 8) Ses & Müzik
- **Adaptive müzik:** ortam/tempo/tehlike durumuna göre değişir.
- Her aksiyona özel SFX.
- UI bile sesli (soft click + confirm).
- Spatial audio desteği.

---

## 9) Optimizasyon
- 60 FPS mobile, 120 FPS PC.
- **Memory leak yok** (profiling + strict asset yönetimi).
- Asset streaming ile açık dünya etkisi.
- LOD sistemleri zorunlu.

---

## 10) Dağıtım ve Ürünleşme
- Steam + App Store + Google Play hedef.
- 1M kullanıcıya ölçeklenebilir backend.
- LiveOps: yeni mekanik, seasonal event.

---

## 11) Sonuç
Bu oyun, fake reklamların “utanç” kaynağı değil, onların **gerçek karşılığı** olacak.
Oyunu gören biri “Bu, reklamdaki yalan oyun değil… onun gerçekten olması gereken hali.” diyecek.

