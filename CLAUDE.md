# PTS — Private Travel Services

Luxury travel сайт для бронирования яхт, бизнес-джетов, вилл и консьерж-сервиса.

## Файлы проекта

- `index.html` — главная страница
- `aviation.html` — бизнес-авиация
- `villas.html` — виллы и отели
- `yachts.html` — яхт-чартер
- `concierge.html` — консьерж-сервис
- `style.css` — единая дизайн-система для всех страниц
- `shared.js` — общий JS: курсор, анимации, sticky nav, форма

## Дизайн-система

**Шрифты:**
- Golos Text — основной (навигация, кнопки, текст, подписи)
- Cormorant Garamond — заголовки секций и hero
- JetBrains Mono — лейблы, теги, мелкие подписи

**Цветовая палитра (светлая тема, earth tones):**
- `--bg: #f5f1eb` — основной фон
- `--bg2: #ede8df` — фон альтернативных секций
- `--bg3: #e4ddd3` — hover-состояния
- `--honey: #b8844e` — основной акцент
- `--honey-lt: #cc9d6a` — светлый акцент
- `--charcoal: #2f2e2b` — тёмный текст
- `--mocha: #4a3f32` — средний тёмный
- `--text-muted: #6b5d4f` — приглушённый текст
- `--text-dim: #9e8f80` — совсем приглушённый

**Hero-секция:**
Frosted glass карточка поверх full-screen фото.
Класс `.hero-glass` — `backdrop-filter: blur(18px)`, фон `rgba(245,241,235,.82)`.
Структура: `.hero-label` → `.hero-title` (с `<em>` для italic honey) → `.hero-sep` → `.hero-sub` → `.hero-actions`

**Компоненты:**
- `.btn-primary` — honey-кнопка с белым текстом
- `.btn-ghost` — текст + стрелка-линия
- `.reveal` + `.visible` — анимация появления при скролле (IntersectionObserver в shared.js)
- `[data-stagger]` — stagger для дочерних `.reveal`
- `.marquee-band` / `.marquee-track` — бегущая строка
- `.form-section` + `.form-layout` — секция с формой (2 колонки)
- `.field-group` + `.field-label` + `input/textarea/select` — поля формы

## Деплой

Git → GitHub → Vercel (автодеплой при push в main).
Файлы лежат в корне репозитория.
Локальный путь: `~/Загрузки/01 work/pts-site`

## Важные правила при правках

- Не трогать структуру `style.css` — все стили общие для 5 страниц
- Новые стили для конкретной страницы добавлять в `<style>` внутри того HTML-файла
- Шрифты подключены через Google Fonts в `style.css` — не дублировать в HTML
- Форма на каждой странице: id=`contactForm` и id=`formSuccess` — не менять, shared.js их ищет по этим id
- Курсор кастомный — `cursor: none` на `body`, элементы `.cursor` и `.cursor-ring` должны быть в каждом HTML
