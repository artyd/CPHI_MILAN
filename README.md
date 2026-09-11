# Постачальники · Alliance Group 95 — CPHI Milan 2026

Статичний сайт-довідник постачальників (self-contained, без бекенду), готовий для **GitHub Pages**.

🔗 **Репозиторій:** https://github.com/artyd/CPHI_MILAN
🌐 **Сайт (після ввімкнення Pages):** https://artyd.github.io/CPHI_MILAN/

## ⚠️ Дані до 2026-09-11 не підтверджені

Вибіркова перевірка (38 випадкових `thread`-ID з `data/thread_states.jsonl`, напряму через Gmail API) показала, що **37 з 38 посилань на листи не існують** у поштовій скриньці ("Requested entity was not found"). Це стосується всієї бази, накопиченої попередніми сесіями до 2026-09-11 (~1700 компаній, ~10 тис. котирувань, ~5300 тредів) — компанії, контакти, ціни й звіти в `suppliers/`, `data/*.jsonl`, `index.html`, `ЗВЕДЕННЯ.md`, `КОНТАКТИ.csv`.

**Перевірено й підтверджено напряму через Gmail** лише дані синхронізації за період **2026-08-20 → 2026-09-11** (58 нових постачальників + оновлення 88 існуючих, комміт `0c32870` і пізніші) — кожен `thread`-ID у цій частині вичитаний живим викликом `get_thread`.

Решту бази слід вважати чернеткою/непідтвердженою до повторної вичитки реальної пошти. Той самий банер показано на сайті (`index.html`).

## Структура

```
.
├─ index.html                      # сайт — уся база вшита всередину, працює автономно
├─ .nojekyll                       # вимикає Jekyll на GitHub Pages
├─ data/                           # вихідна база даних (JSONL/JSON)
│  ├─ companies.jsonl              # компанії (1768)
│  ├─ contacts.jsonl               # контакти (1842)
│  ├─ profiles.jsonl               # профілі (1160)
│  ├─ quotes.jsonl                 # позиції та ціни (10278)
│  ├─ ranking.jsonl                # рейтинг постачальників (1231)
│  ├─ thread_states.jsonl          # стани переписок (5582)
│  └─ cphi-milan-2026-exhibitors.json
├─ suppliers/                      # 1231 постачальник, по 3 md на кожного (3852 файли)
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
