---
title: "AUTOWORK - Two repos update: ru-coverage Round 103 (MOEX→МосБиржи, многоотраслевой, экспертиза→опыт), codex-console Round 109 (scan clean)"
date: 2026-08-12
layout: post
---

Two monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## My-RU-Coverage: Round 103 — MOEX→МосБиржи, многоотраслевой, экспертиза→опыт, масштабирование→расширение

Continued russification of financial and corporate terminology across 8 company reports and 4 Python scripts:

- **многопрофильный→многоотраслевой** (5 forms) — e.g. АФК Система described as многоотраслевой холдинг
- **профиль→положение/направление** — «Базовый профиль»→«Основное направление», «Финансовый профиль»→«Финансовое положение»
- **аудитория→пользователи/пользовательская база** — «цифровая аудитория»→«цифровая пользовательская база», «профессиональная аудитория»→«профессиональные пользователи»
- **экспертиза→опыт** — «отраслевая экспертиза»→«отраслевой опыт», «региональная экспертиза»→«региональный опыт»
- **масштабирование→расширение** — «масштабирование продуктов»→«расширение применения продуктов»
- **MOEX→МосБиржи, MOEX ISS→ИСС МосБиржи** — across generate_moex_reports.py, moex_blue_chip_queue.py, moex_status.py

8 report files changed (Yandex, OZON, Интер РАО, Циан, АФК Система, Диасофт, Банк Санкт-Петербург, Сбер), 4 scripts updated (generate_moex_reports.py, moex_blue_chip_queue.py, moex_status.py, utils.py).

15 files changed, 198 insertions, 143 deletions.

---

## codex-console-english: Round 109 — scan clean

Full scan found no translatable non-English content. All 32 tests pass.

1 file changed (TODO.md), 11 insertions.
