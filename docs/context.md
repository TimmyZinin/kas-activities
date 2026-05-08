# Kaş Activities — Context Brief

**Дата:** 2026-05-08
**Контакт:** Gul_ (@supkas07, +90 532 408 8974, Telegram user_id 1851412638)
**Встреча:** Linckia, Каш, 15:20 (8 мая 2026)

## 1. Voice message transcription (Gul, 2026-05-08 12:27, 69s)

### Turkish original (Whisper-1, lang=turkish, confidence high)

> Kaş Antalya'da yaşıyorum. Kaş aktiviteleriyle ilgileniyorum. Fakat her aktivite farklı ajentalarda. Bütün aktiviteleri, kekova turu, dalış organizasyonları, sapport turları, tenis ve benzeri sporları, tüm aktiviteleri bir arada görmek istediğim bir aplikasyon yapmak istiyorum. Sadece rezervasyon alıp ön ödeme alternatifli olarak bu uygulamayı görmek istiyorum. Kullanıcılar hangi gün ve hangi saatte müsaitlik olup olmadığını gördüklerinde bana rezervasyon yapıyorlar ve tek bir kullanıcıya bu rezervasyonlar düşüyor. Sonrasına gelen bildirimle biz kendilerine geri dönüp ödeme alıyoruz. Ön ödeme şeklinde olacak.

### Русский перевод

> Я живу в Каше (Анталья). Занимаюсь активностями в Каше. Но каждая активность — у разного агентства. Хочу сделать приложение, где все активности видны в одном месте: тур на Кекову, дайвинг-организации, SUP-туры, теннис и подобные виды спорта — все вместе. Хочу видеть только бронирование с опцией предоплаты. Когда пользователи видят свободные дни и часы — делают бронирование у меня, и все бронирования падают одному пользователю-админу. После уведомления мы связываемся с клиентом и принимаем оплату. Формат — предоплата.

### English (working language for further chat)

> I live in Kaş, Antalya. I'm involved in Kaş activities, but each one is at a different agency. I want to make an app where all activities are visible in one place — Kekova tour, diving organisations, SUP tours, tennis and similar sports — everything together. I want this app to take reservations with a prepayment option. When users see availability by day and hour, they make a reservation with me, and all reservations land with one admin user. After receiving a notification, we get back to them and take payment. Prepayment-style.

## 2. Прошлая переписка (Telegram, 2026-05-08, EN)

| Time UTC | Who | Message |
|---|---|---|
| 09:51 | Tim | Thats Tim |
| 11:11 | Tim | Hey hey, let's have a coffee and I'll help you with the app |
| 11:12 | Gul | Hey, let's meet at Linckia at 14:30? |
| 11:24 | Tim | I am on a call till 15:00, can we meet 15:20 there? |
| 11:27 | Gul | Ofc, take your time |
| 11:42 | Tim | cool, see you there |
| 12:27 | Gul | 🎤 voice (transcribed above) |

## 3. Product brief (extracted)

**Vision:** один агрегатор всех активностей Каша, где клиент видит availability и бронирует с предоплатой; все брони идут одному админу (Gul) для подтверждения и оплаты.

**Must-have:**
- Каталог активностей (multi-agency)
- Календарь availability по день/час
- Reservation flow (имя/телефон/кол-во людей/дата/слот)
- Predyplata (prepayment) опция
- Notification к одному admin user (Telegram)
- Admin: подтверждает → берёт оплату → меняет статус

**Format:** Telegram Mini App (TMA) + web version (тот же UI на public URL)

## 4. Open questions (для встречи 15:20 в Linckia)

- [ ] Кто партнёры-агентства? (вероятно Larsoy/Captain Ergun, Kotik Go, плюс знакомые Gul)
- [ ] Комиссия модель? (% с предоплаты, фикс с заявки, или подписка для агентств)
- [ ] Платёжный провайдер? Iyzico (TR), Stripe или ручная оплата по факту контакта?
- [ ] Языки: TR / RU / EN — три? Какой главный?
- [ ] Бренд: название, логотип, домен (kashexperiences.com? kasapp.com? booking.kas?)
- [ ] Кто админ? Только Gul или несколько? Roles нужны?
- [ ] Cancellation/refund политика
- [ ] Сезонность: пик май-октябрь, межсезонье — что показываем?
