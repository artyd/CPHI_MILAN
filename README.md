# Постачальники · Alliance Group 95 — CPHI Milan 2026

Статичний сайт-довідник постачальників (self-contained, без бекенду), готовий для **GitHub Pages**.

🔗 **Репозиторій:** https://github.com/artyd/CPHI_MILAN
🌐 **Сайт (після ввімкнення Pages):** https://artyd.github.io/CPHI_MILAN/

## Структура

```
.
├─ index.html                      # сайт — уся база вшита всередину, працює автономно
├─ .nojekyll                       # вимикає Jekyll на GitHub Pages
├─ data/                           # вихідна база даних (JSONL/JSON)
│  ├─ companies.jsonl              # компанії (1710)
│  ├─ contacts.jsonl               # контакти (1685)
│  ├─ profiles.jsonl               # профілі (1091)
│  ├─ quotes.jsonl                 # позиції та ціни (9955)
│  ├─ ranking.jsonl                # рейтинг постачальників (1162)
│  ├─ thread_states.jsonl          # стани переписок (5306)
│  └─ cphi-milan-2026-exhibitors.json
├─ suppliers/                      # 1162 постачальники, по 3 md на кожного (3486 файлів)
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

## Ввімкнути GitHub Pages

1. Відкрити **Settings → Pages**: https://github.com/artyd/CPHI_MILAN/settings/pages
2. **Source** → `Deploy from a branch`
3. **Branch** → `main`, папка `/ (root)` → **Save**

Через 1–2 хвилини сайт буде доступний за адресою https://artyd.github.io/CPHI_MILAN/

## Оновлення сайту

```bash
git add -A
git commit -m "оновлення даних"
git push
```

## Локальний перегляд

Просто відкрийте `index.html` у браузері.
