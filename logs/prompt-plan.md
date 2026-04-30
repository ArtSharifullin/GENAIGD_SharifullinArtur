# Prompt Plan — Lesson 04
## Moonlit Harvest: Хранитель Грани

### Цель генерации
Создать 4 концепт-изображения, поддерживающих визуальную гипотезу игры (Pixel Art, Lunar Fantasy, палитра `#191c21` + `#ffa800` + лунные акценты). Результаты будут использоваться как референсы для спрайт-листов, ночных локаций, UI и маркетинговых материалов.

### Приоритетные ассеты (из GDD)

| № | Тип | Описание | Приоритет |
|---|-----|----------|-----------|
| 1 | **Персонаж** | Игрок в Лунном режиме (вид сверху/сбоку, светящийся клинок, окружение теней) | Высокий |
| 2 | **Боевая сцена** | Идеальное уклонение от тени (золотая вспышка, замедление, контратака) | Высокий |
| 3 | **Локация** | Светящаяся поляна ночью (лунные цветы, алтарь, туман войны по краям) | Средний |
| 4 | **UI экран** | Экран смерти "Ты умер" с потерей Лунной пыльцы и ночных культур | Средний |

### Обязательные признаки (5 шт.)

1. **Pixel Art стиль** (базовый масштаб 32x32 или 16x16 тайлы)
2. **Тёмная палитра** (`#191c21` как доминанта фона, глубокая ночь)
3. **Лунные акценты** (`#ffa800` для свечения культур, идеальных уклонений, магии)
4. **Читаемый силуэт** персонажа/тени на расстоянии (важно для ночной навигации)
5. **Атмосфера** таинственного, напряжённого лунного леса (уют + опасность)

### Ограничения (5 шт.)

1. `NO` realistic / photorealistic / 3D render
2. `NO` яркие/кислотные цвета (кроме лунных золотых акцентов)
3. `NO` текст на изображениях (кроме UI экрана смерти)
4. `NO` деформированные конечности / артефакты анатомии
5. `NO` перегруженная композиция / визуальный шум (ночь должна быть «чистой»)

### Критерии отбора (Selection Criteria)

| Критерий | Вес | Метод проверки |
| :--- | :--- | :--- |
| Соответствие Pixel Art стилю | 30% | Визуальная оценка чёткости пикселей, отсутствие сглаживания |
| Читаемость силуэта | 25% | Тест на уменьшенной копии (25% масштаб) — тень/игрок должны различаться |
| Соответствие палитре | 20% | Проверка доминанты `#191c21` / акцента `#ffa800` / ночных цветов |
| Атмосфера (лунная/напряжённая) | 15% | Эмоциональная оценка: должно быть «жутко, но красиво» |
| Техническое качество | 10% | Отсутствие артефактов, двойных голов, искажений, глитчей |

### Positive Prompt Template
[OBJECT/SCENE], pixel art style, lunar fantasy game concept,  
#191c21 dark night background, #ffa800 moon glow accents,  
moonlight lighting, [COMPOSITION], mysterious tense atmosphere,  
detailed, retro 32bit, glowing elements

### Negative Prompt (Unified)
low quality, blurry, text, watermark, logo, deformed anatomy,  
extra limbs, bad hands, cropped, duplicate elements,  
photorealistic, 3d render, bright neon colors, cartoon, anime,  
cute, happy, daylight, sunny, ugly, distorted, disfigured,  
poor details, bad art, oversaturated


---

## Детализация по каждому ассету

### Ассет №1: Персонаж — Игрок в Лунном режиме

**Описание:** Игрок (фермер/хранитель) в ночной экипировке. В руке — светящийся лунный клинок или лунная мотыга. Вокруг персонажа — слабое золотое свечение (лунный ореол). Глаза светятся `#ffa800`. Фон — тёмный лес с силуэтами деревьев.

**Positive Prompt:**
pixel art, game character sprite, farmer in lunar mode,  
holding glowing moon blade, golden #ffa800 eyes,  
white #ffffff glowing aura around character,  
#191c21 dark forest background, tree silhouettes,  
isometric view, 32x32 pixel scale, retro gaming style,  
mysterious guardian of the forest, detailed pixel shading

**Negative Prompt:** (общий + дополнительные)
no realistic, no 3d, no cartoon face, no smiling, no farm clothes,  
no daylight, no bright green grass


**Seed (фиксированный):** `4201`

**Ожидаемый результат:** Тёмный силуэт фермера-хранителя с узнаваемым светящимся оружием, контрастирующий с фоном.

---

### Ассет №2: Боевая сцена — Идеальное уклонение от тени

**Описание:** Крупный план боя ночью. Игрок уклоняется от атаки тени (размытый силуэт тени на заднем плане). Момент идеального уклонения — золотая вспышка `#ffa800`, эффект замедления (визуальные «полосы» времени). Игрок в динамичной позе (свайп влево/вправо).

**Positive Prompt:**
pixel art combat scene, perfect dodge mechanic,  
player character dodging shadow monster attack,  
#ffa800 golden flash explosion at dodge moment,  
slow motion visual effect, motion lines,  
#191c21 dark background, shadow enemy silhouette,  
dynamic action pose, side view, 32-bit retro style,  
tense action atmosphere


**Negative Prompt:** (общий + дополнительные)
no static pose, no peaceful scene, no blood, no gore,  
no realistic shadows, no 3d models


**Seed (фиксированный):** `4202`

**Ожидаемый результат:** Динамичная сцена, где золотая вспышка чётко отделяет момент уклонения, силуэт игрока читается на фоне тени.

---

### Ассет №3: Локация — Светящаяся поляна ночью

**Описание:** Ночная поляна в лунном лесу. На земле — светящиеся лунные цветы и грибы (свечение `#ffa800` и `#88ff88`). В центре или на заднем плане — древний алтарь с пульсирующим лунным светом. По краям — туман войны (тьма). Атмосфера: таинственная, красивая, но опасная.

**Positive Prompt:**
pixel art environment, glowing night meadow,  
lunar flowers and mushrooms, #ffa800 and #88ff88 glow,  
ancient stone altar with pulsing moon light,  
#191c21 dark edges as fog of war, starry night sky,  
top-down view, 16x16 tiles, mysterious beautiful atmosphere,  
retro rpg game location


**Negative Prompt:** (общий + дополнительные)
no daytime, no bright colors except glows, no cartoon,  
no empty space, no modern buildings


**Seed (фиксированный):** `4203`

**Ожидаемый результат:** Узнаваемая ночная локация с чёткими зонами света и тьмы, где светящиеся растения служат ориентирами.

---

### Ассет №4: UI экран — Экран смерти

**Описание:** Экран после смерти ночью. Тёмный фон с красным оттенком (`#440000`). По центру — надпись "ТЫ УМЕР" пиксельным шрифтом. Ниже — статистика: «Собрано Лунной пыльцы: 250 → потеряно 125», «Ночных культур: 3 → потеряно 3». Кнопки (можно просто текстовыми блоками): «Вернуться на ферму», «Повторить ночь». Лёгкий эффект глитча/красной каймы.

**Positive Prompt:**
pixel art UI screen, game over death screen,  
#191c21 background with #440000 red tint,  
"YOU DIED" pixel font centered, dark fantasy style,  
statistics text below: "Moon Dust: 250 -> lost 125",  
"Night Crops: 3 -> lost 3", two text buttons:  
"Return to Farm" and "Retry Night",  
subtle red border glitch effect, retro game over mood


**Negative Prompt:** (общий + дополнительные)
no realistic fonts, no 3d buttons, no windows UI,  
no white background, no complex graphics,  
no actual readable text (just placeholder style)


**Seed (фиксированный):** `4204`

**Ожидаемый результат:** Атмосферный экран смерти в пиксельном стиле, с намёком на текст (SDXL может не уметь рендерить читаемый текст — это ожидаемо, текст добавим постфактум).

---

## Workflow параметры (базовые)

| Параметр | Значение |
|----------|----------|
| **Модель** | SDXL Base 1.0 / PixelArt-XL (тест) |
| **Шаги** | 30-40 |
| **CFG Scale** | 7-9 |
| **Sampler** | DPM++ 2M Karras |
| **Resolution** | 768x768 (для последующего даунскейла до 256x256) |
| **Batch size** | 4 варианта на ассет |
| **Seed** | Фиксированные (4201-4204) |

---

## Процесс отбора

1. **Генерация** — 4 варианта на ассет (всего 16 изображений)
2. **Фильтрация** — удалить явный брак (артефакты, деформации)
3. **Оценка по критериям** (30/25/20/15/10 баллов)
4. **Выбор лучшего** на ассет (4 итоговых изображения)
5. **Пост-обработка** — при необходимости:
   - Приведение к чистой палитре (Aseprite)
   - Удаление артефактов
   - Ручная прорисовка ключевых деталей

---

## Чеклист перед генерацией

- [ ] Установлена модель SDXL + PixelArt чекпоинт (если доступен)
- [ ] Зафиксированы seed для воспроизводимости
- [ ] Подготовлена папка `outputs/selected/`
- [ ] Negative prompt скопирован без ошибок
- [ ] Для каждого ассета настроен свой positive prompt

---

## Ожидаемые файлы на выходе

| Ассет | Имя файла | Размер |
|-------|-----------|--------|
| Персонаж | `moonlit_harvest_character.png` | 768x768 |
| Боевая сцена | `moonlit_harvest_combat.png` | 768x768 |
| Локация | `moonlit_harvest_location.png` | 768x768 |
| UI экран | `moonlit_harvest_death_screen.png` | 768x768 |

---
