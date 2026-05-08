# Kaş Experiences — Frontend Prototype

Single-file HTML prototype для встречи с Gul (8 мая 2026, Linckia 15:20).

## Запустить

```bash
open index.html      # macOS
# или
python3 -m http.server 5173 && open http://localhost:5173/index.html
```

5 экранов через нижнюю tab-bar (Home / Activity / Book / Mine / Gül).

## Design system

### Палитра — Mediterranean / Lycian coast

| Token | Hex | Назначение |
|---|---|---|
| `--c-sea-deep` | `#0a3a4a` | Deep Lycian water — admin BG, accents |
| `--c-sea` | `#1d6e87` | Mid-water blue — links, info |
| `--c-sea-light` | `#67a8be` | Shallow turquoise — soft accent |
| `--c-stone` | `#f1e9d8` | Antalya stone cream — card BG |
| `--c-cream` | `#faf6ee` | Body BG (warm off-white) |
| `--c-sunset` | `#d6541d` | Sunset terracotta — CTA, accents |
| `--c-amber` | `#e6a417` | Paragliding amber — highlight |
| `--c-ink` | `#15171a` | Near-black warm — text, dark BG |

### Типографика

- **Display:** Fraunces (italic + bold mix). Заголовки клампят до `13vw` mobile / `96px` cap. letter-spacing `-0.03em`–`-0.04em`.
- **Body:** General Sans (Fontshare). 16px / 1.5.
- **Mono:** JetBrains Mono — eyebrows, meta, статусы, locale.

### Композиция

- Mobile-first (max-width 480px на desktop, центр).
- Asymmetric hero: italic display + bold standalone slab + цвет на одно слово.
- Editorial cards: фото 5:4 → title с italic accent → meta-row → footer с CTA arrow.
- Grain overlay: SVG feTurbulence opacity 0.06, multiply.
- Sticky `book-bar` pill на activity detail.
- TMA tab-bar — pill в `var(--c-ink)`, активный pill — `var(--c-sunset)`.

### Компоненты

| Class | Назначение |
|---|---|
| `.brand-bar` | Top sticky brand + locale |
| `.tabs` / `.tab` | Bottom tab navigation (TMA-style) |
| `.hero` / `.hero-title` / `.hero-photo` | Editorial hero с фото |
| `.cat-chip` | Categories strip (3 accent variants) |
| `.exp` | Featured experience card |
| `.detail-hero` / `.book-bar` | Detail screen with sticky reserve |
| `.field` / `.qty` / `.times` / `.prepay-card` | Booking flow controls |
| `.bk` (data-status) | Booking row (4 статуса: pending/confirmed/paid/done) |
| `.req` | Admin inbox card |
| `.btn-primary` | Primary CTA pill |

### TMA-specific

- `var(--tg-theme-bg-color)` fallback на `--c-cream`
- `safe-area-inset-top/bottom` зашиты в paddings
- `Telegram.WebApp.ready() + expand()` в инлайн-скрипте
- pill-tabs дружат с iOS Home Indicator

## Что НЕ реализовано в прототипе

- Real backend / Telethon / TWA SDK init
- React/Vite (это раздаточный single-file HTML — для встречи)
- TR/RU локализация (placeholders на EN)
- Admin: реальные actions
- Платёжный provider (Iyzico/Stripe placeholder только)

## Следующий спринт (после встречи)

1. Решить с Gul branding/copy/языки
2. Скаффолд Vite + React + TWA SDK
3. Перенести компоненты как React (1-в-1 разметку и стили)
4. FastAPI + SQLite + bot @kasexperiences_bot для admin notifications
5. Iyzico (TR) или ручная оплата по ссылке
