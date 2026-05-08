# BotFather setup — @kasexperiences_bot

Эту часть Тим делает руками в @BotFather (3 минуты).

## 1. Создать бота

```
/newbot
Bot name:     Kaş Experiences
Bot username: kasexperiences_bot   (или kashexperiences_bot если занято)
```

BotFather пришлёт `BOT_TOKEN` — сохранить в `~/kas-activities/backend/.env` как:
```
BOT_TOKEN=...
ADMIN_USER_ID=64242118    # Tim для теста, потом сменить на Gul
GUL_USER_ID=1851412638
```

## 2. Описание (`/setdescription`)

```
Curated activities in Kaş, Antalya — boat trips to Kekova, diving, SUP, paragliding,
sunset yachts, padel and more. Book in one place, prepay 30%, talk to Gül directly.
```

## 3. About (`/setabouttext`)

```
One place for everything Kaş. Built with locals, run by Gül.
```

## 4. Commands (`/setcommands`)

```
start - Открыть приложение / Open app
book - Каталог активностей / Browse activities
mine - Мои бронирования / My bookings
help - Помощь / Help
contact - Связаться с Gül
```

## 5. Menu Button → Telegram Mini App (`/setmenubutton` → URL)

```
Button text:  Open app
Button URL:   https://kas.timzinin.com   (когда задеплоим)
```

Для теста — пока Vercel preview URL или локальный ngrok.

## 6. Configure Mini App (`/newapp`)

```
Bot:           @kasexperiences_bot
App title:     Kaş Experiences
Description:   Curated activities in Kaş — boat, dive, paraglide, sport
Photo:         logo.png (256×256)
GIF:           hero.gif (необязательно, но нужно потом записать)
Web App URL:   https://kas.timzinin.com
Short name:    open  (даст ссылку t.me/kasexperiences_bot/open)
```

## 7. Inline placeholder (опционально, `/setinlineplaceholder`)

```
Search activities…
```

## 8. Профиль бота

- **Аватар:** круглый логотип — sea-blue + sunset gradient mark из бренд-бара (28px → 256px). Сейчас в прототипе — `radial-gradient(circle at 30% 30%, var(--c-amber), var(--c-sunset) 60%, var(--c-sea-deep))`.
- **Цвет хедера:** sunset terracotta `#d6541d`.

## 9. Webhook / Polling

После деплоя backend:

```bash
# Webhook
curl -X POST "https://api.telegram.org/bot<TOKEN>/setWebhook" \
  -d "url=https://api.kas.timzinin.com/webhook"
```

Или aiogram polling — для локальной разработки.

## После всего

Когда бот создан — Тим присылает `BOT_TOKEN` в чат, я разворачиваю backend skeleton (FastAPI + aiogram + SQLite) и привязываю TMA URL.
