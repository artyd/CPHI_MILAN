# Постачальники · Alliance Group 95 — CPHI Milan 2026

Статичний сайт-довідник постачальників (self-contained, без бекенду). Готовий до розгортання на **GitHub Pages**.

## Структура

```
site/
├─ index.html                      # сайт (уся база вшита всередину, працює автономно)
├─ .nojekyll                       # вимикає Jekyll на GitHub Pages
├─ data/                           # вихідна база даних (JSONL/JSON)
│  ├─ companies.jsonl              # компанії
│  ├─ contacts.jsonl               # контакти
│  ├─ profiles.jsonl               # профілі
│  ├─ quotes.jsonl                 # позиції та ціни
│  ├─ ranking.jsonl                # рейтинг постачальників (1162)
│  ├─ thread_states.jsonl          # стани переписок
│  └─ cphi-milan-2026-exhibitors.json
├─ suppliers/                      # 1162 постачальники, по 3 md на кожного
│  └─ <slug>/
│     ├─ 01-kontakty.md
│     ├─ 02-pozytsii-ta-tsiny.md
│     └─ 03-zvit-pro-robotu.md
├─ ЗВЕДЕННЯ.md
├─ КОНТАКТИ.csv
└─ УЧАСНИКИ-CPHI-MILAN-2026.md
```

> `index.html` не залежить від папок `data/` та `suppliers/` — уся база вбудована в сам файл.
> Ці папки збережені як першоджерело даних.

## Розгортання на GitHub Pages

```bash
git init
git add .
git commit -m "CPHI Milan 2026 suppliers site"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

Далі: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / root**.
Сайт буде доступний за адресою `https://<user>.github.io/<repo>/`.

## Локальний перегляд

Просто відкрийте `index.html` у браузері.
