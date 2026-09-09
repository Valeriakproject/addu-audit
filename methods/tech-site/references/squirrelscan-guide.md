# SquirrelScan — установка и использование

SquirrelScan — локальный CLI-аудитор сайтов для AI-агентов. 230+ правил в 21 категории. Работает локально и бесплатно, без аккаунта и API-ключа. **Это статический краулер: он не кликает кнопки и не отправляет формы** — интерактив закрывается через chrome-devtools MCP (см. `interactive-procedure.md`).

## Установка

Глобально через npm (требуется Node.js):
```bash
npm install -g squirrelscan
squirrel --version
```

Под Windows есть и отдельный установщик:
```powershell
iwr -useb https://squirrelscan.com/install.ps1 | iex
```

Фолбэк без глобальной установки:
```bash
npx squirrelscan audit <domain>
```

## Основная команда

```bash
squirrel audit <domain> [флаги]
```

Полезные флаги:
- `-f <format>` — формат вывода: `console`, `json`, `html`, `markdown`, `text`, `llm`, `xml`.
- `-m <N>` — ограничить число страниц (например `-m 25` для быстрого прогона).
- `-o <file>` — файл вывода.

Режимы покрытия (по размеру сайта):
- **quick** — ~25 страниц (быстрая проверка);
- **surface** — ~100 страниц с выборкой по паттернам;
- **full** — ~500 страниц.

## Как запускаем в скилле

В папку клиента `documents/{slug}-techaudit/raw/`:
```bash
# машиночитаемый вывод для парсинга
squirrel audit <domain> -f json -o documents/{slug}-techaudit/raw/squirrel.json -m <pages>
# человекочитаемый HTML на всякий случай
squirrel audit <domain> -f html -o documents/{slug}-techaudit/raw/squirrel.html -m <pages>
```

Для небольшого сайта берём quick/surface. Если CLI недоступен (политика npm) — `npx squirrelscan audit ...` или пропускаем squirrel-часть и помечаем покрытие как сокращённое (честно отразить в отчёте).

## Что берём из JSON-вывода

- общий health-score (0–100);
- разбивку по категориям с severity и рекомендациями;
- список битых ссылок/редиректов;
- mixed-content и проблемы HTTPS;
- SEO/картинки/доступность/crawl.

Эти находки сливаем с результатами интерактивного прохода, дедуплицируем и переводим в бизнес-язык для отчёта. Сырой `squirrel.json`/`squirrel.html` оставляем в `raw/` как доказательную базу.

## Важно
- Сайт может быть на HTTP и в кодировке windows-1251 (как allprint-service.ru) — squirrel это обрабатывает, но всегда сверяемся с фактическим рендером в браузере.
- Не передавать в отчёт клиенту сырые англоязычные формулировки squirrel — переписывать на понятный язык владельцу бизнеса.
