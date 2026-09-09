# Landing Page CRO Audit

Быстрый (1-2 часа) эвристический CRO-аудит одностраничных сайтов.

## Что внутри

- [SKILL.md](SKILL.md) — инструкция для Claude, активация скилла, workflow
- [heuristics-checklist.md](heuristics-checklist.md) — чеклист LIFT + CCD + структура лендинга + mobile
- [prioritization.md](prioritization.md) — упрощённый PXL + веса MECLABS для приоритизации
- [russian-landing-specifics.md](russian-landing-specifics.md) — специфика РФ (152-ФЗ, источники трафика, платежи, Метрика)
- [report-template.md](report-template.md) — шаблон итогового отчёта
- [audits/](audits/) — папка с готовыми аудитами клиентов

## Когда использовать

Говори Claude «сделай CRO-аудит лендинга {URL}» или просто «посмотри на лендинг {URL}» — скилл активируется автоматически.

Подходит для:
- Рекламных лендингов под PPC (Директ, Google Ads, таргет)
- Quiz-лендингов, лид-магнитов
- SEO-посадок одностраничного формата
- Продающих страниц инфопродуктов, курсов, вебинаров
- Presale-лендингов SaaS и B2B услуг

**НЕ** для:
- Интернет-магазинов → используй `estore-audit`
- Многостраничных корпоративных сайтов → используй `multi-page-cro-audit`

## Методологическая база

- **LIFT Model** (WiderFunnel) — 6 факторов конверсии
- **Conversion-Centered Design** (Oli Gardner, Unbounce) — Attention Ratio и структура
- **MECLABS Conversion Sequence Heuristic** — веса факторов
- **PXL-упрощённый** (CXL) — приоритизация через Impact × Effort
- **Chrome DevTools MCP + audit-website (squirrelscan)** — технический аудит

## Два режима глубины

- **Экспресс** (1-1.5 часа) — для presale и быстрых проверок
- **Стандарт** (2-3 часа) — для платных аудитов с подробными гипотезами

## Где сохраняются отчёты

`landing_page_audit/audits/{YYYY-MM-DD}-lp-audit-{client-slug}.md`

Скриншоты — в `audits/{client-slug}-assets/`.

## Клиентская версия отчёта

Markdown → PDF через Pandoc или Typora («Экспорт → PDF»). Ничего больше не нужно.
