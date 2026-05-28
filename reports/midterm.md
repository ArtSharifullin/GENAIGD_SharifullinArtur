# Midterm Report — Moonlit Harvest: Хранитель Грани

**Студент:** Sharifullin Artur  
**Дата:** 2026-05-28  
**Репозиторий:** `GENAIGD_SharifullinArtur`

---

## 1. Что сделано

### GDD и дизайн

- Полный [GDD.md](../GDD.md): core loop (день/ночь/луна), механики, прогрессия, враги, локации, UI, нарративный срез.
- [logs/gdd-log.md](../logs/gdd-log.md) — итерации с LLM, уточнение USP и циклов.

### Визуальная система

- [style/Style-bible.md](../style/Style-bible.md): A/B тест стиля героя, выбран гибрид «мягкий лунный свет + читаемый силуэт», правила палитры и запреты, Reference rules (W09).
- [characters/Hero.md](../characters/Hero.md), [design/Design Constants (HW06).md](../design/Design%20Constants%20(HW06).md).
- Референсы: [refs/Character refs (HW05).md](../refs/Character%20refs%20(HW05).md), [refs/Location refs (HW06).md](../refs/Location%20refs%20(HW06).md), [refs/controlnet.md](../refs/controlnet.md), [refs/ip-adapter.md](../refs/ip-adapter.md).

### ComfyUI и ассеты

- Workflows W04–W09 в [workflows/](../workflows/).
- [logs/workflow-notes.md](../logs/workflow-notes.md): параметры, seed, выводы по img2img / multiprompt / ControlNet / W09.
- **12 файлов для проверки midterm** — см. [outputs/selected/README.md](../outputs/selected/README.md) и [index.md](../index.md).
- **3 скрингена:** ферма (меню), бой, экран смерти (+ босс и артефакт в расширенном наборе).

### Домашние задания (статус)

| HW | Статус | Комментарий |
|----|--------|-------------|
| W02–W04 | ✓ | GDD, prompt-plan, w04, первые selected |
| W05 | ✓ | Style bible, asset list, character refs |
| W06 | ✓ | 6 кадров героя, constants, location refs |
| W07 | ✓ | img2img/inpaint/outpaint, shot-list |
| W08 | ✓ | Depth + Canny, workflow; частичное расхождение сцены/режима (см. ниже) |
| W09 | ✓ | Таблица подходов, upscale босса, pipeline в GDD |

---

## 2. Что сломалось / риски

1. **SDXL и текст** — логотипы и UI-текст нечитаемы; план: Aseprite/Figma поверх генерации.
2. **Motion blur в бою** — размывает pixel art; частично снято img2img (denoise 0.5).
3. **ControlNet HW08** — Depth дал алтарную сцену вместо поляны; Canny привязан к UI, а не к локации. Зафиксировано в notes; повторные прогоны описаны в [comfyui-missing-assets-guide.md](../logs/comfyui-missing-assets-guide.md).
4. **Consistency героя** — дрейф капюшона между кадрами; ограничение modifier ≤ 0.45.
5. **Два каталога selected** — исторически `images/selected/` (W04) и `outputs/selected/` (W05+); для проверки используется явный список из 12 файлов в index.

---

## 3. Что дальше (до final)

1. Сгенерировать **дневной** вариант Элиана (соломенная шляпа).
2. Canny-прогон на **ночную поляну/алтарь** (не UI).
3. Outpaint для **SH04** (босс) — отдельный прогон.
4. Набор **UI/иконок** (Лунная пыльца, 3–5 элементов).
5. Сжать final selected до **≤20** с подписями в index.
6. Модули audio / video / 3d по регламенту курса.

---

## 4. Как проверить за 5 минут

1. Открыть [index.md](../index.md) — pitch, 3 скрингена, таблица 12 selected, 3 workflow.
2. Открыть [style/Style-bible.md](../style/Style-bible.md) § Chosen Baseline.
3. Открыть [workflows/w04_sdxl_txt2img.json](../workflows/w04_sdxl_txt2img.json) и [logs/workflow-notes.md](../logs/workflow-notes.md) § HW08.

---

## 5. Ключевые workflow для midterm

| Файл | Зачем |
|------|-------|
| `w04_sdxl_txt2img.json` | Скрингены и базовые ассеты |
| `w07_img2img_inpaint_outpaint.json` | Правки боевого и UI кадров |
| `w08_controlnet_depth_canny.json` | Управление композицией |
