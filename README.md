# Kaş Experiences

Kaş'taki tüm aktiviteleri tek yerde rezerve ettiren bir Telegram Mini App + web uygulaması — Kekova'ya tekne turu, deniz kaplumbağaları ile SUP, Babadağ'dan yamaç paraşütü, Kaş limanında gün batımı yelken turu, tenis, Uyuyan Dev tırmanışı, Patara'da at biniciliği ve dahası.

Kaş'ta yaşayan **Gül (@supkas07)** için Mayıs 2026'da Tim Zinin tarafından geliştirildi. Farklı yerel acentelerden gelen rezervasyonlar tek bir admin panelinde toplanır; opsiyonel %30 ön ödeme alınır ve müşteri ile son temas Telegram üzerinden yapılır.

## Canlı uygulama

- 📱 **Telegram Mini App:** https://t.me/kasexperiences_bot/open
- 🌐 **Tarayıcıda açın:** https://timzinin.com/kas-activities/

Her iki bağlantı aynı tek-sayfalık prototipi açar. Telegram bağlantısına tıklandığında uygulama doğrudan Telegram içinde açılır, hiçbir kurulum gerekmez.

## Beş ekran

Alt sekme çubuğundan geçilir:

1. **Home / Discover** — kategori şeritleri (Sea & Boat, Water Sports, Adventure, Tours, Sports, Wellness) ve haftanın öne çıkan deneyimleri. Her aktivite kartında küçük bir takvim şeridi var: yaklaşan tarihler ve saatler doğrudan görünüyor.
2. **Activity** — seçilen aktivitenin detayı: full-bleed fotoğraf, açıklama, dahil olan hizmetler, operatör profili (yıldız puanı + yıllık trip sayısı), tarih şeridi, sticky "Reserve" butonu.
3. **Booking** — kişi sayısı stepper'ı, saat seçimi (uygun olmayan saatler otomatik devre dışı), isim/telefon alanı, **%30 ön ödeme toggle'ı** (€42 şimdi, kalan €98 teknede), özet ve "Confirm & pay" butonu.
4. **My bookings** — kullanıcının kendi rezervasyonları. Dört durum, sol tarafta renk şeridiyle: `pending` (kehribar) → `confirmed` (turkuaz) → `paid` (terra-kotta) → `done` (gri).
5. **Gül admin** — koyu temalı gelen kutusu: bekleyen başvurular avatar + isim + tarih ile, hızlı Confirm / Message / Decline butonları, üstte günlük istatistikler (yeni başvuru sayısı, ön ödeme toplamı, haftalık trip sayısı).

## Teknoloji

Tek dosyalık çalışan prototip:
- Vanilla HTML + CSS + ~30 satır JavaScript (ekran geçişleri)
- Akdeniz paleti CSS değişkenleri olarak: deep Lycian blue `#0a3a4a`, Antalya stone cream `#f1e9d8`, sunset terracotta `#d6541d`, paragliding amber `#e6a417`
- **Fraunces** (italic display) + **General Sans** (gövde) + **JetBrains Mono** (meta)
- Mobil-öncelikli; masaüstünde 480px max-width, ortada
- Telegram WebApp SDK init satır içi (`Telegram.WebApp.ready() + expand()`)
- iOS safe-area-inset uyumlu
- Tüm görseller Unsplash CDN üzerinden, lokal asset yok
- Sayfa üzerinde gerçekçi doku için ince SVG grain overlay

Planlanan backend (kod henüz yazılı değil, mimarisi `docs/` içinde):
- FastAPI + aiogram + SQLite
- Iyzico (Türkiye için ideal) veya Stripe ön ödeme
- Bot tarafında her yeni rezervasyon admin'e bildirim
- Twenty CRM (kendi kendine barındırılan) lead kaydı

## Repo yapısı

```
kas-activities/
├── index.html              # ana çalışan prototip
├── frontend/
│   ├── index.html          # aynı dosyanın repo dışı kaynağı
│   ├── README.md           # design system detayları
│   ├── bot-avatar.png      # Telegram bot profil resmi (512×512)
│   └── app-cover.png       # Web App kapak görseli (640×360)
├── content/
│   └── activities-seed.md  # @russ_kas Telegram kanalından derlenmiş aktivite kataloğu
├── docs/
│   ├── context.md          # Gül'ün ses notları (TR/RU/EN), proje brifi
│   └── botfather-setup.md  # @kasexperiences_bot adım adım kurulum kılavuzu
└── backend/
    └── .env                # bot token (gitignored)
```

## Yerelde çalıştırma

```bash
git clone https://github.com/TimmyZinin/kas-activities.git
cd kas-activities
open index.html              # macOS — doğrudan tarayıcıda açar

# veya bir HTTP sunucusuyla:
python3 -m http.server 5173
# http://localhost:5173 adresine gidin
```

Telegram Mini App olarak test etmek için ayrı bir HTTPS URL gerekir (BotFather sadece HTTPS kabul eder). GitHub Pages otomatik halleder; özel kurulum için `docs/botfather-setup.md` dosyasına bakın.

## Geliştirici notları

- Tüm tasarım tokenleri `index.html` içindeki `:root` CSS değişkenlerinde — palet, yazı tipleri, spacing scale, border-radius değerleri.
- Yeni aktivite eklemek için: `<article class="exp">` bloğunu kopyalayıp fotoğraf URL'sini ve içeriği değiştirin. Yedi yeni eklenen aktivite örnek olarak duruyor.
- `next-dates` şeridi şu an statik; production'da `/api/availability/{activity_id}` endpoint'inden doldurulması planlanıyor.
- Yatay kaydırılan kategori ve tarih şeritleri scrollbar gizleniyor; iOS'ta momentum scroll çalışıyor.
- Admin paneli koyu tema kasıtlı — operatör için hızlı triaj odağı; ana uygulama crema/açık.

## Lisans

MIT. Forklayın, müşterilerinize uyarlayın, başka şehirler için kullanın (Antalya, Fethiye, Bodrum şablonu olarak ideal).

— Tim Zinin · [@timzinin](https://t.me/timzinin)
