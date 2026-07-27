<h1 align="center">Hi there, I'm Toksa 👋</h1>

<p align="center">
  <i>Python backend developer · Telegram bots &amp; Mini Apps · PostgreSQL · Cybersecurity student</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/aiogram_3.x-2CA5E0?style=flat-square&logo=telegram&logoColor=white" alt="aiogram">
  <img src="https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Electron-47848F?style=flat-square&logo=electron&logoColor=white" alt="Electron">
</p>

---

I build **production systems that real businesses run on** — Telegram bots that replace paper
accounting, Mini Apps that mirror them one-to-one, and desktop tools that turn manual routine
into one click. Alongside that I study **cybersecurity**: networks, secure configuration and
hands-on InfoSec practice.

## 🚀 What I Do

- 🐍 **Backend & Automation** — async Python (aiogram 3, asyncpg, aiohttp), event-sourced
  PostgreSQL schemas, background pollers, external API integrations.
- 📱 **Telegram Mini Apps** — aiohttp server + vanilla-JS frontend inside the bot process,
  HMAC `initData` validation as the single trust boundary, full feature parity with chat.
- 🖥️ **Desktop apps** — Electron + Node, media pipelines on `yt-dlp` / FFmpeg.
- 🛡️ **Cybersecurity** — network architecture, hardening, traffic analysis, secure secret
  handling (tokens never reach the frontend).
- 🐧 **Linux & DevOps** — VPS deploys, Docker, Caddy/nginx reverse proxy, systemd, backups.

## 🛠️ Tech Stack

| | |
|---|---|
| **Languages** | Python · JavaScript · SQL · Bash · C++ *(learning)* |
| **Backend** | aiogram 3.x · asyncio · aiohttp · asyncpg · Pyrogram |
| **Databases** | PostgreSQL (Neon.tech) · SQLite · event sourcing, views, migrations |
| **Frontend** | Telegram Mini Apps (vanilla JS, no build step) · HTML/CSS |
| **Desktop** | Electron · Node.js · yt-dlp · FFmpeg |
| **Docs & data** | openpyxl · WeasyPrint · Jinja2 · matplotlib |
| **Scraping** | Selenium · BeautifulSoup · Requests |
| **Ops & security** | Git · Linux · Docker · Wireshark · Cisco networking basics |

## 📌 Projects

### 🍖 Production Accounting Bot — Telegram bot + Mini App
![closed source](https://img.shields.io/badge/closed_source-private_repo-6e7781?style=flat-square)
![in production](https://img.shields.io/badge/status-in_production-2ea44f?style=flat-square)

Full ERP-lite for a grill-kit manufacturer, running in production.
*Client system — the source is not public; below is what it does and how it's built.*

- Event-sourced PostgreSQL: no stored balances, every number is derived — full audit trail.
- **Manager approval queue** — a manager's operation lands in `pending_operations`, every admin
  gets a synced ✅/❌ card, atomic claim prevents double-apply.
- **Prom.ua + Nova Poshta integration** — order polling with 429 backoff, TTN catcher,
  parcel-phase tracking, sale auto-recorded on dispatch.
- **Payroll module** — hours × rate + bonus − advance, manager drafts blind, admin closes and
  prints Excel/PDF.
- **Telegram Mini App** with strict parity: same rights, same approval queue, same money gating.
- Nightly SQL backups, maintenance mode, audit log, forecasting and ABC/margin analytics.

`aiogram 3` · `asyncpg` · `Neon PostgreSQL` · `aiohttp` · `WeasyPrint` · `matplotlib`

---

### ⚙️ Foundry Accounting Bot — metal casting workflow
![closed source](https://img.shields.io/badge/closed_source-private_repo-6e7781?style=flat-square)
![in production](https://img.shields.io/badge/status-in_production-2ea44f?style=flat-square)

Same engine, retargeted at a metal-casting workflow — a study in reusing a core across domains.
*Client system — the source is not public.*

- Four-stage chain: **intake → flask packing → knockout → shipping**, each stage a DB event.
- Flask as a batch (header / contents / knockout), one metal per flask, knocked out in one go.
- Hard overflow guard: `good + defect ≤ quantity`, enforced atomically with `FOR UPDATE`.
- Metal consumption = Σ(good × weight × burn-loss), with the burn-loss coefficient living in a
  single place — one SQL function shared by views and reports so they can never disagree.
- Prom/Nova Poshta and payroll deliberately stripped out; Mini App parity kept.

`aiogram 3` · `asyncpg` · `PostgreSQL views & SQL functions` · `aiohttp`

---

### 🎵 [Music Grabber](https://github.com/Toksa88/yt) — desktop music app (Electron)
Search, stream and download music with proper tags and artwork. Ukrainian UI.

- Unified search across **YouTube Music, SoundCloud, iTunes and MusicBrainz**.
- Stream straight from results, visible playback queue, radio recommendations, lyrics.
- Downloads named `Artist - Title`, square-cropped embedded cover art, filled tags; whole albums
  as one job; automatic retries on 403/429/timeouts.
- Local library reads tags directly from files — no hidden database; tag editor with batch rename.
- Media keys and Windows SMTC integration, Discord Rich Presence.
- Honest about limits: Spotify / Apple Music are DRM-protected and **not** downloadable.

`Electron` · `Node.js` · `yt-dlp` · `FFmpeg`

---

<details>
<summary><h2>🇺🇦 Українською</h2></summary>

<br>

Роблю **системи, на яких реально працює бізнес** — Telegram-боти, що замінюють паперовий облік,
Mini App до них із повним паритетом, і десктопні застосунки, що згортають рутину в один клік.
Паралельно вчуся на **кібербезпеці**: мережі, захищені конфігурації, практика з InfoSec.

### 🚀 Чим займаюсь

- 🐍 **Бекенд і автоматизація** — асинхронний Python (aiogram 3, asyncpg, aiohttp),
  event-sourced схеми PostgreSQL, фонові цикли, інтеграції зі сторонніми API.
- 📱 **Telegram Mini Apps** — aiohttp-сервер + vanilla-JS фронт у тому ж процесі, що й бот;
  HMAC-валідація `initData` як єдина межа довіри, повний паритет із чатом.
- 🖥️ **Десктоп** — Electron + Node, медіапайплайни на `yt-dlp` / FFmpeg.
- 🛡️ **Кібербезпека** — архітектура мереж, хардненінг, аналіз трафіку, безпечне поводження
  з токенами (жоден секрет не потрапляє на фронт).
- 🐧 **Linux і DevOps** — деплой на VPS, Docker, реверс-проксі Caddy/nginx, systemd, бекапи.

### 🛠️ Стек

| | |
|---|---|
| **Мови** | Python · JavaScript · SQL · Bash · C++ *(вивчаю)* |
| **Бекенд** | aiogram 3.x · asyncio · aiohttp · asyncpg · Pyrogram |
| **Бази даних** | PostgreSQL (Neon.tech) · SQLite · event sourcing, view, міграції |
| **Фронтенд** | Telegram Mini Apps (vanilla JS, без збірки) · HTML/CSS |
| **Десктоп** | Electron · Node.js · yt-dlp · FFmpeg |
| **Документи й дані** | openpyxl · WeasyPrint · Jinja2 · matplotlib |
| **Скрапінг** | Selenium · BeautifulSoup · Requests |
| **Ops і безпека** | Git · Linux · Docker · Wireshark · основи мереж Cisco |

### 📌 Проєкти

#### 🍖 Бот обліку виробництва — Telegram-бот + Mini App
![closed source](https://img.shields.io/badge/код-закритий-6e7781?style=flat-square)
![in production](https://img.shields.io/badge/статус-у_продакшні-2ea44f?style=flat-square)

Повноцінний ERP-lite для виробника наборів для гриля, працює в продакшні.
*Клієнтська система — код не розголошується; нижче лише що вміє і як побудовано.*

- Event-sourced PostgreSQL: залишки не зберігаються, кожна цифра обраховується — повний аудит.
- **Черга підтверджень менеджера** — операція осідає в `pending_operations`, усі адміни бачать
  синхронізовану картку ✅/❌, атомарний claim не дає застосувати двічі.
- **Інтеграція Prom.ua + Нова Пошта** — опитування замовлень із backoff на 429, ловитель ТТН,
  трекінг фаз посилки, продаж записується автоматично при відправці.
- **Зарплатний модуль** — години × ставка + премія − аванс; менеджер вносить години наосліп,
  адмін закриває відомість і друкує Excel/PDF.
- **Telegram Mini App** із жорстким паритетом: ті самі права, та сама черга, те саме приховування грошей.
- Нічні SQL-бекапи, режим обслуговування, аудит-лог, прогноз закупівель, ABC- і маржинальний аналіз.

`aiogram 3` · `asyncpg` · `Neon PostgreSQL` · `aiohttp` · `WeasyPrint` · `matplotlib`

---

#### ⚙️ Бот обліку ливарного виробництва
![closed source](https://img.shields.io/badge/код-закритий-6e7781?style=flat-square)
![in production](https://img.shields.io/badge/статус-у_продакшні-2ea44f?style=flat-square)

Той самий рушій, перенацілений на лиття металу — приклад того, як ядро переживає зміну домену.
*Клієнтська система — код не розголошується.*

- Чотири стадії: **прихід → забивка опоки → вибивка → відправка**, кожна стадія — подія в БД.
- Опока як партія (шапка / вміст / вибивка), один метал на опоку, вибивка цілком за раз.
- Жорсткий захист від перебору: `гуд + брак ≤ кількість` у опоці, атомарно через `FOR UPDATE`.
- Витрата металу = Σ(гуд × вага × угар), а сам коефіцієнт угару живе в одному місці — спільна
  SQL-функція для view і звітів, тож вони фізично не можуть розійтися.
- Prom/НП і зарплату свідомо прибрано; паритет Mini App збережено.

`aiogram 3` · `asyncpg` · `PostgreSQL views & SQL-функції` · `aiohttp`

---

#### 🎵 [Music Grabber](https://github.com/Toksa88/yt) — десктопний музичний застосунок (Electron)
Пошук, прослуховування й завантаження музики з тегами та обкладинками. Український інтерфейс.

- Спільний пошук по **YouTube Music, SoundCloud, iTunes і MusicBrainz**.
- Програвання просто з результатів, видима черга відтворення, радіо-рекомендації, текст пісні.
- Файли `Виконавець - Назва`, вшита квадратна обкладинка, заповнені теги; цілі альбоми одним
  завданням; автоматичні повтори на 403/429/тайм-аутах.
- Сховище читає теги напряму з файлів, без власної бази; редактор тегів із пакетним перейменуванням.
- Медіаклавіші й панель Windows, статус у Discord.
- Чесно про межі: Spotify / Apple Music віддають DRM-потік і **не** завантажуються.

`Electron` · `Node.js` · `yt-dlp` · `FFmpeg`

</details>

## 📫 Contact

<p>
  <a href="mailto:antonxomiu@gmail.com"><img src="https://img.shields.io/badge/email-antonxomiu%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="email"></a>
  <a href="https://github.com/Toksa88/CV"><img src="https://img.shields.io/badge/CV-181717?style=flat-square&logo=github&logoColor=white" alt="CV"></a>
</p>
