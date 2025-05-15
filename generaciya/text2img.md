---
description: Генерация текста в изображение
---

# Text2Img

### **Оглавление**

* [Общая инфа](text2img.md#obshaya-infa)
* [Смешивание](text2img.md#smeshivanie)
* [Лайфхаки](text2img.md#laifkhaki)
  * [Шпаргалки](text2img.md#shpargalki)
  * [Генераторы](text2img.md#generatory)
    * [Seed, CLIP skip & CFG scale](text2img.md#seed-clip-skip-and-cfg-scale)

### Общая инфа

По сути вся генерация построена на тегах.

* Promnt:&#x20;

```
solo, 1man, red t-shirt, blue sports trousers, run in forest, full length, 
<lora:Concept Art Ultimatum Style LoRA_Pony XL v6:1.0> digital art, 
<lora:SDXL_Dices_Mega_Detail_v1:1.0> highdetail, 
<lora:Semi-real pretty fantasy - XL pony v2_0:0.7>, 
```

* Negative promt:&#x20;

```
easynegative, 3d, imperfect eyes, deformed pupils, deformed iris, bad proportions, bad anatomy, deformed hands, deformed eyes, deformed face, text, watermark, 
```

* Model: `SDXL`
* Size: `768x1024`

<figure><img src="../.gitbook/assets/00007-ponyDiffusionV6XL_v6StartWithThisOne-solo 1man red t shirt blue sports trousers.jpg" alt="" width="375"><figcaption></figcaption></figure>

В негаnивных указываются правки, которые хотите избежать - но в моем случае это готовые подборки `./models/embeddings` :

{% file src="../.gitbook/assets/ng_deepnegative_v1_75t.pt" %}

{% file src="../.gitbook/assets/easynegative (1).safetensors" %}

{% file src="../.gitbook/assets/easynegative.safetensors" %}

Допустим нам не нужны длинные штаны и указываем в _**negative promt**_ - `long sports trousers`

<figure><img src="../.gitbook/assets/00013-ponyDiffusionV6XL_v6StartWithThisOne-solo 1man red t shirt blue sports trousers.jpg" alt="" width="375"><figcaption></figcaption></figure>

Иногда надо выделить тег (или набор тегов). Для этого используют скобки:

* ((тег)) - чем больше скобок тем важнее тег - solo, 1man, muscular, in gym, (full shot: 1.5),
* (тег: 1.0) - можно указывать весы и числами - `1man, in gym, (muscularity: 1.0)`

<figure><img src="../.gitbook/assets/MyCollages.jpg" alt="" width="563"><figcaption></figcaption></figure>

Есть еще теги в квадратных скобках - они, наоборот, уменьшают вероятность.

Еще увидел, что можно юзать плюс и минус - но ни разу не видел и не испольовал.

### Смешивание

`solo, animal, [cat: dog: 0.9], (full shot: 1.5),`

Работает криво, но все зависит от модели.

<figure><img src="../.gitbook/assets/MyCollages (1).jpg" alt="" width="563"><figcaption><p>0.1 -> 0.9</p></figcaption></figure>

### Лайфхаки

#### Шпаргалки

Вынес в отдельную страницу - [**LINK**](text2img.md#shpargalki)

#### Генераторы

Между вами и Stable Diffusion есть текстовый анализатор (возможно какой-то старый ChatGPT или его аналог), поэтому составление тегов это полный гемор.&#x20;

Чтоб составить адекватный запрос, можно юзать генераторы - например, [Stable Diffusion Prompt Generator](https://flowgpt.com/p/stable-diffusion-prompt-generator-6).

<figure><img src="../.gitbook/assets/Screenshot Capture - 2024-05-14 - 10-20-10.png" alt=""><figcaption></figcaption></figure>

Как видите генератор накидал еще кучи фигни, но самое главное что он сделал negative promts, что кайф (и никакой easynegative или ng\_deepnegative\_v1\_75t не нужен).

Иногда генератор не устанавливает весы, но если без них работает криво, то можно ручками.

<figure><img src="../.gitbook/assets/00322-ultimateHentai_v50-An athletic man clad in a vibrant red.jpg" alt="" width="240"><figcaption></figcaption></figure>

#### Seed, CLIP skip & CFG scale

Если вам понравился арт который сгенерировала SD, то можно генерировать ее повторно - не меняем промты и сохраняем **seed**. Это позволяет менять одну картинку с помощью **CFG scale** и **CLIP skip**.

**CLIP skip** не сильно нам поможет, но как вариант можно поиграться.&#x20;

Основной инструмент, который я пока освоил, **CFG scale** - он слегка меняет изображение, если зафиксировать **seed**. Но для более точной настройки лучше допиливать теги.

<figure><img src="../.gitbook/assets/MyCollages (1) (2).jpg" alt="" width="563"><figcaption></figcaption></figure>
