# Google Ads Kurulum Rehberi — EasyShareCode.com

## Adım Adım Detaylı Anlatım (2025/2026 Arayüzü)

> ⚠️ Google Ads arayüzü sık güncellenir. Bu rehber Mayıs 2026 itibarıyla günceldir.

---

## BÖLÜM 1: Hesap Oluşturma (Zaten yoksa)

### 1.1 Google Ads Hesabı Aç
1. **ads.google.com** adresine git
2. Google hesabınla giriş yap (iş için ayrı bir Gmail önerilir)
3. "New Google Ads Account" veya "Yeni Google Ads Hesabı" seçeneğine tıkla
4. **ÖNEMLİ:** Google seni "Smart Campaign" (Akıllı Kampanya) oluşturmaya yönlendirecek — bunu ATLA
5. Sayfanın altında küçük yazıyla "Switch to Expert Mode" veya "Uzman Moduna Geç" linki var — **buna tıkla**
6. "Create an account without a campaign" (Kampanya olmadan hesap oluştur) seçeneğini seç
7. Ülke: United Kingdom, Para birimi: GBP (£), Saat dilimi: London seç
8. "Submit" / "Gönder" tıkla

### 1.2 Ödeme Bilgilerini Gir
1. Sol menüden **Billing** (Faturalandırma) > **Settings** (Ayarlar)
2. Kredi kartı veya banka kartı bilgilerini gir
3. Fatura adresi gir
4. "Submit" tıkla

---

## BÖLÜM 2: Conversion Tracking (Dönüşüm Takibi) — KAMPANYADAN ÖNCE YAP

> ⚠️ Bu adımı kampanya oluşturmadan ÖNCE yap. Yoksa Google neyin işe yaradığını ölçemez.

### 2.1 Conversion Action Oluştur
1. Sol menüde **Goals** (Hedefler) ikonuna tıkla (bayrak ikonu)
2. **Conversions** > **Summary** seçeneğine tıkla
3. **"+ New conversion action"** (Yeni dönüşüm eylemi) butonuna tıkla
4. **"Website"** seç (App Store linki web sitenden gidiyor)
5. Domain olarak `easysharecode.com` yaz, "Scan" tıkla

### 2.2 Manuel Conversion Tanımla
1. **"+ Add a conversion action manually"** tıkla
2. Ayarlar:
   - **Category:** "Purchase" veya "Other" (App Store'a yönlendirme)
   - **Conversion name:** "App Store Click" yaz
   - **Value:** "Don't use a value" seç (veya £2.99 premium değeri)
   - **Count:** "One" seç (kullanıcı başına bir kez say)
   - **Click-through conversion window:** 30 days
   - **Attribution model:** "Data-driven" (varsayılan, değiştirme)
3. **"Done"** tıkla, sonra **"Save and continue"**

### 2.3 Tracking Kodunu Siteye Ekle
1. Google sana bir **Google Tag** verecek
2. İki seçenek var:
   - **A) Google Tag Manager kullan** (önerilir) — Tag Manager ID'ni al, siteye ekle
   - **B) Doğrudan HTML'e ekle** — `<head>` tagının içine yapıştır
3. **Event snippet'i** App Store butonunun tıklanmasına bağla:
   - App Store linkine `onclick` event ekle veya
   - GTM'de "Click URL contains apps.apple.com" trigger'ı oluştur

> 💡 **Basit yöntem:** Hugo sitenin `layouts/partials/head.html` dosyasına Google Tag'i ekle. App Store butonlarına `id="appstore-cta"` ekle ve GTM'de bu ID'ye tıklamayı conversion olarak say.

---

## BÖLÜM 3: Kampanya Oluşturma

### 3.1 Yeni Kampanya Başlat
1. Sol menüde **Campaigns** (Kampanyalar) ikonuna tıkla
2. Açılan sayfada **"Campaigns"** sekmesine tıkla
3. Mavi **"+"** butonuna tıkla → **"New campaign"** seç

### 3.2 Hedef Seç
1. **"Website traffic"** (Web sitesi trafiği) seç
   - Neden: Amacımız insanları landing page'e getirip App Store'a yönlendirmek
2. Conversion goal olarak az önce oluşturduğun "App Store Click" görünecek — seçili bırak
3. **"Continue"** tıkla

### 3.3 Kampanya Tipi Seç
1. **"Search"** (Arama) seç — DİĞERLERİNİ SEÇME (Performance Max, Display vs. değil)
2. **"Continue"** tıkla

### 3.4 Kampanya Adı
1. Kampanya adı: **"EasyShareCode — EN — Search"** yaz
2. Bu isimlendirme ileride dil bazlı kampanyaları ayırt etmeni sağlar

---

## BÖLÜM 4: Kampanya Ayarları

### 4.1 Networks (Ağlar)
1. **"Search Network"** — İŞARETLİ bırak ✓
2. **"Display Network"** — İŞARETİ KALDIR ✗
   - ⚠️ Bu çok önemli! Display Network'ü açık bırakırsan bütçen alakasız sitelerde harcanır

### 4.2 Locations (Konumlar)
1. **"Enter another location"** tıkla
2. **"United Kingdom"** yaz ve seç
3. **ÖNEMLİ:** "Location options" (Konum seçenekleri) linkine tıkla
4. **"Presence: People in or regularly in your targeted locations"** seç
   - "Presence or interest" SEÇME — bu, UK hakkında araştırma yapan herkesi hedefler
5. Exclude (Hariç tut): Bir şey ekleme

### 4.3 Languages (Diller)
1. **"English"** seç
2. İleride dil bazlı kampanyalar için ayrı kampanya oluşturacağız

### 4.4 Budget (Bütçe)
1. **Daily budget:** £10 yaz (günlük)
   - Aylık yaklaşık £300 harcar (Google bazı günler %20 fazla harcayabilir ama aylık limiti aşmaz)
2. İlk hafta sonuçlara göre artırabilirsin

### 4.5 Bidding (Teklif Stratejisi)
1. Google "What do you want to focus on?" diye soracak
2. **"Conversions"** seç
3. "Set a target cost per action" — İLK BAŞTA İŞARETLEME
   - Yeterli veri toplandıktan sonra (50+ conversion) CPA hedefi koyarsın
4. **"Maximize conversions"** otomatik seçilecek — bu doğru

### 4.6 Ad Schedule (Reklam Takvimi) — Opsiyonel
1. "Show more settings" veya "More settings" linkine tıkla
2. **"Ad schedule"** bölümünü bul
3. Şimdilik "All day" bırak — ilk verilere göre sonra daraltırsın

### 4.7 Device Targeting
1. ⚠️ Kampanya seviyesinde cihaz seçimi YOKTUR yeni arayüzde
2. Kampanya oluşturduktan SONRA: Campaigns > Devices sekmesinden bid adjustment yaparsın
3. Şimdilik geç, sonra ayarlayacağız

---

## BÖLÜM 5: Ad Group Oluşturma

### 5.1 İlk Ad Group
1. **Ad group name:** "Share Code General" yaz
2. **Ad group type:** "Standard" seçili bırak

### 5.2 Keywords (Anahtar Kelimeler) Ekle
Aşağıdaki kelimeleri keyword kutusuna yapıştır (her satıra bir tane):

```
uk share code
share code uk visa
how to store share code
share code expired
share code wallet
save share code
share code app
uk immigration share code
store share code safely
share code apple wallet
```

**Match Type Açıklaması:**
- Kelimeyi olduğu gibi yazarsan → **Broad Match** (geniş eşleşme) — Google benzer aramaları da gösterir
- `"uk share code"` → **Phrase Match** (öbek eşleşme) — bu sırayı içeren aramalar
- `[uk share code]` → **Exact Match** (tam eşleşme) — sadece bu arama

> 💡 **Öneri:** İlk başta **Phrase Match** kullan. Her kelimenin başına ve sonuna tırnak işareti koy:

```
"uk share code"
"share code uk visa"
"how to store share code"
"share code expired"
"share code wallet"
"save share code"
"share code app"
"uk immigration share code"
"store share code safely"
"share code apple wallet"
```

---

## BÖLÜM 6: Reklam Oluşturma (Responsive Search Ad)

### 6.1 Final URL
1. **Final URL:** `https://easysharecode.com/share-code-wallet/` yaz
2. **Display path:** `easysharecode.com / share-code / wallet` yaz
   - Bu, reklamda görünen URL'dir (gerçek URL'yi değiştirmez)

### 6.2 Headlines (Başlıklar) — En az 3, en fazla 15 ekle
Her biri max 30 karakter. Şunları yaz:

```
1.  UK Share Code — Always Ready
2.  Store in Apple Wallet Instantly
3.  Never Lose Your Share Code
4.  Share Code App — Free Download
5.  Your Code, One Tap Away
6.  Track Share Code Expiry Dates
7.  Offline Access to Share Codes
8.  Store Family Share Codes
9.  QR Code Display Included
10. Share Code Expires? Get Alerts
11. Trusted by UK Visa Holders
12. Add Share Code to Wallet
13. Access Code Without Internet
14. 30-Day Code? Set Reminders
15. Secure Share Code Storage
```

**Pin (Sabitleme) Önerisi:**
- Headline 1 pozisyonuna "UK Share Code — Always Ready" sabitle (pin ikonu)
- Headline 2 pozisyonuna "Store in Apple Wallet Instantly" sabitle
- Diğerlerini Google'ın test etmesine izin ver

### 6.3 Descriptions (Açıklamalar) — En az 2, en fazla 4 ekle
Her biri max 90 karakter:

```
1. Store your UK Home Office share code securely. Add to Apple Wallet for instant access.
2. Expiry reminders, QR display, offline access. Track codes for your whole family. Free.
3. Share codes expire in 30-90 days. Get alerts before they do. Download free on App Store.
4. Keep your immigration share code ready for employers, landlords & border control.
```

### 6.4 Sitelink Extensions (Ek Linkler)
Reklam oluşturma sayfasının altında "More asset types" veya "Sitelinks" bölümü var:

| Sitelink Text | Final URL | Description |
|---------------|-----------|-------------|
| Apple Wallet Feature | https://easysharecode.com/share-code-wallet/ | Add share code to Apple Wallet |
| Expiry Reminders | https://easysharecode.com/expiry-reminder/ | Never miss code expiration |
| Right to Rent | https://easysharecode.com/right-to-rent/ | Ready for landlord checks |
| Download Free | https://easysharecode.com/ | Get started with free plan |

### 6.5 Callout Extensions
"Callouts" bölümüne şunları ekle:
- Works Offline
- Apple Wallet
- 32 Languages
- Family Sharing
- Free to Start
- QR Code Display

### 6.6 Reklamı Kaydet
1. Sağ üstte **"Ad strength"** (Reklam gücü) göstergesi var
2. "Good" veya "Excellent" olmasını hedefle (en az 3 farklı headline teması gerekir)
3. **"Save and continue"** veya **"Next"** tıkla

---

## BÖLÜM 7: Diğer Ad Group'ları Ekle

Kampanya oluşturulduktan sonra diğer ad group'ları ekle:

### 7.1 Yeni Ad Group Ekleme
1. Sol menüden **Campaigns** > kampanyanı seç
2. **"Ad groups"** sekmesine tıkla
3. Mavi **"+"** butonuna tıkla

### 7.2 Ad Group B — eVisa Focused
- **Ad group name:** "eVisa Focused"
- **Keywords (phrase match):**
```
"evisa share code"
"uk evisa status"
"prove immigration status uk"
"evisa wallet"
"digital immigration status"
"evisa uk app"
"store evisa details"
"evisa share code app"
"uk evisa holder app"
"evisa proof of status"
```
- **Final URL:** `https://easysharecode.com/share-code-wallet/`
- **Headlines & Descriptions:** `google-ads-plan.md` dosyasındaki Ad Group B'den al

### 7.3 Ad Group C — Right to Rent
- **Ad group name:** "Right to Rent"
- **Keywords:** `google-ads-plan.md` Ad Group C keywords
- **Final URL:** `https://easysharecode.com/right-to-rent/`

### 7.4 Ad Group D — Expiry FOMO
- **Ad group name:** "Expiry FOMO"
- **Keywords:** `google-ads-plan.md` Ad Group D keywords
- **Final URL:** `https://easysharecode.com/expiry-reminder/`

### 7.5 Ad Group E — Travel
- **Ad group name:** "Travel Border"
- **Keywords:** `google-ads-plan.md` Ad Group E keywords
- **Final URL:** `https://easysharecode.com/travel/`

---

## BÖLÜM 8: Negative Keywords (Negatif Anahtar Kelimeler)

### 8.1 Negatif Kelime Listesi Oluştur
1. Sol menüde **Keywords** > **Negative keywords** sekmesine git
2. Mavi **"+"** tıkla
3. "Add negative keywords" > "Campaign" seviyesinde ekle
4. Şunları yapıştır:

```
free visa
visa application
home office contact
gov.uk login
apply for visa
visa fees
visa appointment
biometric appointment
visa refusal
asylum
refugee
passport renewal
BRP card
visa extension
immigration lawyer
```

Bu kelimeler, uygulamayla ilgisi olmayan aramalarda reklamının gösterilmesini engeller.

---

## BÖLÜM 9: Kampanyayı Yayınla

### 9.1 Son Kontrol
1. Kampanya özetini gözden geçir:
   - ✓ Search Network ONLY (Display kapalı)
   - ✓ Location: United Kingdom (Presence only)
   - ✓ Language: English
   - ✓ Budget: £10/day
   - ✓ Bidding: Maximize Conversions
   - ✓ En az 1 ad group ve 1 reklam var
2. **"Publish campaign"** veya **"Launch"** tıkla

### 9.2 İnceleme Süreci
- Google reklamını 1-2 iş günü içinde inceler
- "Under review" (İnceleniyor) durumu normal
- Onaylanınca "Eligible" (Uygun) olur ve gösterilmeye başlar
- Reddedilirse neden belirtilir — genellikle küçük düzeltmelerle çözülür

---

## BÖLÜM 10: Kampanya Sonrası — Cihaz Ayarı

### 10.1 iOS Cihazlara Öncelik Ver
1. Kampanyanı seç > **"Devices"** sekmesine git (veya Insights & Reports > Devices)
2. Üç cihaz tipi göreceksin: Computers, Mobile, Tablets
3. **Computers** satırında "Bid adj." sütununa tıkla → **-50%** yaz (daha az göster)
4. **Mobile** → **+20%** yaz (daha fazla göster)
5. **Tablets** → **-30%** yaz

> Not: Google Ads'te doğrudan "sadece iOS" seçeneği yoktur. Ama mobil trafiğin büyük kısmı zaten hedef kitlendir. İlk verilere göre ayarlarsın.

---

## BÖLÜM 11: İlk Hafta Takip Kontrol Listesi

### Günlük (5 dakika)
- [ ] Kampanya durumunu kontrol et (active mi?)
- [ ] Harcamayı kontrol et (bütçeyi aşıyor mu?)
- [ ] Tıklama var mı?

### 3. Gün
- [ ] **Search Terms** raporunu kontrol et:
  - Campaigns > Keywords > Search terms
  - Alakasız aramalar varsa negatif kelime olarak ekle
- [ ] CTR'ye bak: %2'nin altındaysa headline'ları değiştir

### 7. Gün
- [ ] Hangi ad group en iyi performans gösteriyor?
- [ ] Hangi keywords tıklama alıyor?
- [ ] Conversion var mı? (App Store tıklaması)
- [ ] Düşük performanslı keyword'leri duraklat
- [ ] Bütçeyi artır veya azalt

---

## BÖLÜM 12: Sık Yapılan Hatalar — BUNLARI YAPMA

| ❌ Yapma | ✅ Yap |
|----------|--------|
| Display Network'ü açık bırakma | Sadece Search Network |
| "Presence or interest" location seçme | "Presence only" seç |
| Broad match keyword kullanma (ilk başta) | Phrase match ile başla |
| Tek bir ad group'a tüm keyword'leri koyma | Tema bazlı ad group'lar oluştur |
| Conversion tracking olmadan başlama | ÖNCE tracking kur |
| Smart Campaign kullanma | Expert Mode kullan |
| İlk gün bütçeyi yüksek tutma | £10/gün ile başla |
| Negatif keyword eklemeyi unutma | İlk günden ekle |
| Reklamı bir kez yazıp bırakma | Haftalık optimize et |

---

## Özet: Yapılacaklar Sırası

1. ☐ Google Ads hesabı aç (Expert Mode)
2. ☐ Ödeme bilgilerini gir
3. ☐ Conversion tracking kur (App Store Click)
4. ☐ Tracking kodunu siteye ekle
5. ☐ Kampanya oluştur (Search, UK, English, £10/day)
6. ☐ Ad Group A oluştur + keywords + reklam
7. ☐ Negative keywords ekle
8. ☐ Kampanyayı yayınla
9. ☐ Cihaz bid adjustment yap
10. ☐ 3. gün: Search terms kontrol
11. ☐ 7. gün: Performans değerlendirmesi
12. ☐ Ad Group B-E ekle (performansa göre)
