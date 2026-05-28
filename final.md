# Final — Moonlit Harvest: Хранитель Грани

Краткая навигация для защиты и воспроизведения результатов. Подробный отчёт: [reports/2026-05-28-final.md](reports/2026-05-28-final.md).

## Что за игра

Уютная ферма днём и хардкорный лунный лес ночью. Игрок копит ресурсы на ферме и рискует ими в ночных вылазках, чтобы восстановить Сердце Луны.

## Ключевые артефакты

| Раздел | Путь |
|--------|------|
| GDD | [GDD.md](GDD.md) |
| Стиль | [style/Style-bible.md](style/Style-bible.md) |
| Midterm selected (12) | [outputs/selected/README.md](outputs/selected/README.md) |
| Скрингены | [index.md](index.md) § «Три скриншота геймплея» |
| Workflows | [workflows/](workflows/) |
| Логи | [logs/workflow-notes.md](logs/workflow-notes.md) |

## Как воспроизвести (кратко)

### Окружение

- **ComfyUI:** локальный (основной контур W04–W09) или cloud.comfy.org для txt2img.
- **Модель:** SDXL Base 1.0, VAE `sdxl_vae.safetensors` (если отдельно).
- **Пресеты:** Steps 30, CFG 7.0, Sampler `DPM++ 2M Karras`, Scheduler Karras, Latent 1024×1024.
- **Seed (база):** `42424242` (скрингены W04), серия героя `42424263–42424268`.

### Порядок запуска

1. Импортировать `workflows/w04_sdxl_txt2img.json` → промпты из [logs/prompt-plan.md](logs/prompt-plan.md) или [Shot-List.md](Shot-List.md).
2. Стиль героя: `w05_flux_style_series.json` (шаблон Flux в cloud) или SDXL-прогоны из [logs/workflow-notes.md](logs/workflow-notes.md) § Lesson 05.
3. Серия из 6 кадров: `w06_multiprompt.json`, блоки constants / style / modifier (вес modifier 0.3–0.45).
4. Правки: `w07_img2img_inpaint_outpaint.json` — denoise 0.5 для боя; inpaint маска UI; outpaint для SH03/SH04.
5. Композиция: `w08_controlnet_depth_canny.json` — Depth ~0.8, Canny ~0.7.
6. Upscale: `w09_simple_upscale_sdxl.json` — только для утверждённых кадров (босс: before/after в `outputs/selected/09-moon-lord-upscale-*.png`).

### Provenance

| Этап | Инструмент | Примечание |
|------|------------|------------|
| GDD, промпты | LLM (см. gdd-log) | Итерации концепта |
| Генерации W04–W09 | ComfyUI + SDXL | Параметры в workflow-notes |
| Flux style series | ComfyUI Cloud template | Имя файла `w05_flux_style_series.json` |
| Flux 2 Klein / IP-Adapter | Демо преподавателя | Не запускалось локально; план в W09 notes |
| Текст на UI | Aseprite / Figma | SDXL не генерирует читаемый pixel-текст |

### Что доделать к финалу

См. [logs/comfyui-missing-assets-guide.md](logs/comfyui-missing-assets-guide.md): дневной герой, canny-локация, outpaint SH04, иконки ресурсов.
