---
description: Немного информации.
---

# Models, VAE и LoRA

* [Model](page-1.md#model)
* [LoRA](page-1.md#lora)

## Model

* Файл с обученной моделью, по которой будут генерироваться изображения.
  * SakushiMix: [https://civitai.com/models/78056/sakushimix-finished](https://civitai.com/models/78056/sakushimix-finished)
  * AniVerse: [https://civitai.com/models/107842?modelVersionId=428028](https://civitai.com/models/107842?modelVersionId=428028)

<figure><img src=".gitbook/assets/MyCollages(1).jpg" alt="" width="563"><figcaption></figcaption></figure>

* Формат:&#x20;
  * **ckpt (pickle tensor)** - это стандартный формат для моделей, которые мы используем с SD. Их минус в том, что при желании в файл можно запихнуть вредоносный код.
  * **safetensors (safetensor)** - доработанный формат для моделей, суть существования которого в том, чтобы нельзя было засунуть в модель что-то вредное. Также модель в этом формате грузиться быстрее чем модель в формате **ckpt**.
*   Битность расчетов - **fp16/fp32/bf16**

    * Чем больше тем точнее расчеты, но нужно больше памяти

    <figure><img src=".gitbook/assets/fp16,32.jpg" alt="" width="563"><figcaption><p>Но не все так прекрасно как на картинке :)</p></figcaption></figure>

    * Мой тест - разница ну ХЗ

    <figure><img src=".gitbook/assets/MyCollages (2).jpg" alt="" width="480"><figcaption><p>Слева fp16,справа fp32</p></figcaption></figure>
* **EMA** и **no-EMA** (Exponential Moving Averaging)- весы обучения, основывалось ли тренировка на предыдущих результатах.
* **Pruned** - как понял, облегченная модель.
* **VAE** (Variational AutoEncoder) - модель для img -> latent space -> img, где в латентном состоянии нейросети ищет пересечение, обрабатывается и перегоняется опять в изображение.
  * Подробнее: [https://youtu.be/Afw-Edl61w0](https://youtu.be/Afw-Edl61w0)

## LoRA

Это небольшие обученные модели для Stable Diffusion, которые вносят дополнительные изменения в генерацию изображений и используются вместе со стандартными моделями. Отлично подходит если хотите, чтоб сохранить стиль или какой-то элемент генерации (например, лица).

Надо внимательно подбирать, т.к. LoRA может быть не совместима с моделью (тупо не работает).

Пример:

* Модель: [https://civitai.com/models/4201/realistic-vision-v60-b1](https://civitai.com/models/4201/realistic-vision-v60-b1)
* LoRA: [https://civitai.com/models/8729?modelVersionId=11101](https://civitai.com/models/8729?modelVersionId=11101)

<figure><img src=".gitbook/assets/lora.jpg" alt="" width="563"><figcaption><p>Три разных прогона и +- один результат</p></figcaption></figure>

## Источники

* Model:&#x20;
  * [https://dtf.ru/howto/1868999-vse-chto-nuzhno-znat-pro-modeli-stable-diffusion-chast-1](https://dtf.ru/howto/1868999-vse-chto-nuzhno-znat-pro-modeli-stable-diffusion-chast-1)
  * [https://dtf.ru/howto/1890976-vse-chto-nuzhno-znat-pro-modeli-stable-diffusion-chast-2](https://dtf.ru/howto/1890976-vse-chto-nuzhno-znat-pro-modeli-stable-diffusion-chast-2)
* Lora:
  * [https://vk.com/@mystablediffusion-stable-diffusion-chto-takoe-modeli-lora-i-kak-ih-ispolzovat](https://vk.com/@mystablediffusion-stable-diffusion-chto-takoe-modeli-lora-i-kak-ih-ispolzovat)
