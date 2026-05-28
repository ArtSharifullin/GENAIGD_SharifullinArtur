# ComfyUI — недостающие прогоны и промпты

Задачи, которые **ещё не закрыты** или требуют **повторного** запуска. Параметры по умолчанию: SDXL Base 1.0, steps 30, CFG 7.0, DPM++ 2M Karras, 1024×1024.

Связанные документы: [refs/controlnet.md](../refs/controlnet.md) · [shots/shot-list.md](../shots/shot-list.md) · [workflows/README.md](../workflows/README.md)

---

## 1. SH04 — Outpaint босса (приоритет High)

**Проблема:** W07 outpaint сделан для UI-смерти, не для босса.  
**Workflow:** `w07_img2img_inpaint_outpaint.json`  
**Source:** `images/selected/04_moon_lord_boss_seed42424242.png`  
**Направление:** расширить по бокам и вверх под слайд 16:9, сохранить силуэт игрока внизу.

**Positive (кратко):**
```
pixel art boss scene, Black Moon Guardian, translucent purple shadow body, golden #ffa800 eyes,
small player silhouette bottom center, Eclipse Temple, giant black moon golden ring,
dark #191c21 background, epic scale, retro 32bit, no text
```

**Negative:** `blurry, text, watermark, photorealistic, extra limbs, cropped boss`

**После прогона:** сравнить с `09-moon-lord-upscale-after.png`; лучший — в final selected.

---

## 2. Canny — ночная поляна / алтарь (HW08 доработка)

**Проблема:** `08-canny-scene-01.png` — UI, не локация.  
**Workflow:** `w08_controlnet_depth_canny.json` (ветка Canny)  
**Input:** скетч контуров: арка, тропа, круг поляны, силуэты деревьев (без персонажей).

**Positive:**
```
pixel art night forest clearing, glowing moon flowers #ffa800, dark trees silhouettes,
altar stone circle center, fog edges #191c21, top-down isometric hint,
mysterious calm tension, retro 32bit
```

**Negative:** `daytime, bright sky, realistic, text, characters, neon colors`

**Цель:** A03 / SH04 mood, файл: `outputs/selected/08-canny-location-01.png` (создать при прогоне).

---

## 3. Depth — дневная ферма SH01 (уточнение)

**Input:** depth-карта из hub или изометрический блок-аут.  
**Workflow:** `w08_controlnet_depth_canny.json` (Depth ~0.75)

**Positive:**
```
pixel art game main menu, top-down isometric farm, morning, house smoke chimney,
garden beds, dark forest horizon, pale moon daytime sky, cozy #191c21 shadows #ffa800 accents,
retro 32bit, gameplay screenshot feel, no readable text
```

---

## 4. Дневной Элиан (A01 день)

**Workflow:** `w06_multiprompt.json` или `w04_sdxl_txt2img.json`  
**Seed:** новый (например 42424270).

**Constants block:**
```
Elian farmer, straw hat, simple brown shirt #8b5a2b, pants #4a3728, relaxed slouched posture,
lunar hoe on back, warm daylight, no glowing eyes, no hood, pixel art portrait 3/4
```

**Negative:** `hood, glowing eyes, talisman glow, night, cloak, warrior pose, realistic`

**Output:** `outputs/selected/07-w06-hero-day.png`

---

## 5. Лунная пыльца — UI иконка (A07)

**Workflow:** `w04_sdxl_txt2img.json`, latent 512×512 → resize 32/64 в Aseprite.

**Positive:**
```
pixel art item icon, moon dust crystal shard, amber glow #ffa800, transparent edges,
dark #191c21 background, simple readable shape, game inventory, retro 32bit
```

---

## 6. Теневой волк (A08)

**Positive:**
```
pixel art enemy shadow wolf, semi-transparent purple black body, golden #ffa800 eyes only,
dynamic lunge pose, minimal detail, readable silhouette 32x32 scale, dark forest #191c21
```

---

## Чеклист перед добавлением в selected

- [ ] Совпадает с [style/Style-bible.md](../style/Style-bible.md)
- [ ] Палитра `#191c21` + `#ffa800` (и `#88ccff` только для магии)
- [ ] Нет AI-текста на изображении
- [ ] Имя файла: `NN-wXX-описание.png`
- [ ] Запись в [workflow-notes.md](workflow-notes.md)
