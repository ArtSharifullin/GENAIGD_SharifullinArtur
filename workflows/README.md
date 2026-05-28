# Workflows — Moonlit Harvest

| Файл | Занятие | Назначение |
|------|---------|------------|
| [w04_sdxl_txt2img.json](w04_sdxl_txt2img.json) | W04 | Базовый txt2img SDXL, скрингены |
| [w05_flux_style_series.json](w05_flux_style_series.json) | W05 | Стилевые серии (Flux template в cloud; логика A/B в notes) |
| [w06_multiprompt.json](w06_multiprompt.json) | W06 | ConditioningCombine/Average — серия героя |
| [w07_img2img_inpaint_outpaint.json](w07_img2img_inpaint_outpaint.json) | W07 | img2img, inpaint, outpaint |
| [w08_controlnet_depth_canny.json](w08_controlnet_depth_canny.json) | W08 | ControlNet Depth + Canny |
| [w09_simple_upscale_sdxl.json](w09_simple_upscale_sdxl.json) | W09 | Simple upscale selected |

## Параметры по умолчанию (SDXL)

- Checkpoint: SDXL Base 1.0  
- Steps: 30 · CFG: 7.0 · Sampler: DPM++ 2M Karras · Scheduler: Karras  
- Latent: 1024×1024 · Seed base: 42424242  

Подробности и выводы: [logs/workflow-notes.md](../logs/workflow-notes.md).

## W07–W08

- Img2img: denoise 0.35 / 0.5 / 0.65 — рабочий **0.5** для боя.  
- ControlNet: Depth ~0.8, Canny ~0.7 (см. § HW08 в notes).  
- Недостающие прогоны: [logs/comfyui-missing-assets-guide.md](../logs/comfyui-missing-assets-guide.md).
