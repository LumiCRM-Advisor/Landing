# Lumi Landing — инструкция для разработчика

## Структура проекта

```
Landing/
├── index.html          # Главная страница
├── modules/            # Страницы модулей
│   ├── recruiting.html
│   ├── operations.html
│   ├── hrm.html
│   ├── hse.html
│   ├── requests.html
│   └── rotation.html
├── logo.png            # Логотип
└── vercel.json         # Конфиг деплоя
```

Чистый HTML/CSS/JS — никаких фреймворков, сборщиков, node_modules.

---

## Локальный запуск

Просто открыть `index.html` в браузере. Или через Live Server в VS Code:

1. Установить расширение [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
2. ПКМ на `index.html` → **Open with Live Server**
3. Откроется на `http://127.0.0.1:5500`

---

## Workflow для правок

```bash
git clone https://github.com/LumiCRM-Advisor/Landing.git
cd Landing

# Создать ветку для своих правок
git checkout -b design/название-правки

# ... вносишь изменения ...

git add .
git commit -m "fix: описание что изменил"
git push origin design/название-правки
```

После пуша создать Pull Request на GitHub — автоматически создастся preview на Vercel для проверки.

---

## Что можно трогать

| Файл | Что там |
|------|---------|
| `index.html` | Весь лендинг: Hero, Features, Pricing, Footer |
| `modules/*.html` | Страницы отдельных модулей |
| `logo.png` | Логотип (заменять с тем же именем) |

---

## Что НЕ трогать

- `vercel.json` — конфиг деплоя, не менять
- `.vercel/` — служебная папка Vercel
- `sitemap.xml`, `robots.txt` — SEO файлы, менять только по согласованию

---

## Деплой

- `main` ветка → автодеплой на прод (lumicrm.ru/landing или отдельный домен)
- Любой PR → автоматический preview URL от Vercel

Вопросы — писать в Telegram: @dglvt
