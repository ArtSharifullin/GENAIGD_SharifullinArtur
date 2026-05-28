# Final Report (черновик) — Moonlit Harvest: Хранитель Грани

**Студент:** Sharifullin Artur  
**Дата:** 2026-05-28  
**Статус:** черновик перед финальной защитой; обновлять по мере закрытия пунктов из midterm.

> Быстрая навигация: [final.md](../final.md) · [index.md](../index.md)

---

## Summary

Проект — pixel-art игра с двойным ритмом (ферма / лунный лес). К midterm готовы GDD, style bible, серия героя, 3 скрингена, пайплайн ComfyUI W04–W09 и документированные параметры воспроизведения.

---

## Deliverables (план final)

| Компонент | Статус | Где |
|-----------|--------|-----|
| GDD | ✓ | [GDD.md](../GDD.md) |
| Style bible + refs | ✓ | [style/](../style/), [refs/](../refs/) |
| 3 скрингена | ✓ | [index.md](../index.md) |
| Персонаж + 4+ вариации | ✓ (6 кадров) | `outputs/selected/01–06-w06-hero-*.png` |
| Окружения 3–5 | ⚠ (2+ кадра) | depth-scene, hub, combat |
| UI/иконки 3–5 | ⚠ (1 артефакт + death UI) | HotM, death screen |
| Workflows 3–5 | ✓ (6 файлов) | [workflows/](../workflows/) |
| Audio / video / 3D | ✗ | `media/` — к модулям курса |
| Отчёт + воспроизведение | ✓ черновик | этот файл, [final.md](../final.md) |

---

## Как воспроизвести

Полная инструкция: [final.md](../final.md).

**Модели:** SDXL Base 1.0.  
**Фиксированные параметры:** steps 30, CFG 7.0, DPM++ 2M Karras, 1024×1024, seeds 42424242+ (см. workflow-notes).  
**Графы:** w04 → w05/w06 → w07 → w08 → w09.

**Provenance:** генерации — ComfyUI (локально / cloud); тексты GDD — LLM; pixel-текст UI — ручная постобработка.

---

## Известные ограничения

- IP-Adapter / Flux 2 Klein — только аналитика и рефы (см. workflow-notes W09).
- Часть файлов в `outputs/selected/` — учебные A/B, не входят в midterm-лист 12.
- SH04 outpaint и дневной герой — в backlog ([comfyui-missing-assets-guide.md](../logs/comfyui-missing-assets-guide.md)).

---

## Test plan перед защитой

- [ ] `index.md` открывается на GitHub с картинками
- [ ] Все workflow из index импортируются в ComfyUI без missing nodes
- [ ] Selected ≤ 20, подписи актуальны
- [ ] GDD §12.5 совпадает с фактическими workflow-именами
- [ ] Презентация 4 мин: pitch → 3 скрингена → 1 workflow → план до релиза
