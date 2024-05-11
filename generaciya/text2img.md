---
description: Генерация текста в изображение
---

# Text2Img

По сути вся генерация построена на тегах.\
Promnt: `man, red t-shirt, blue sports trousers, run in forest, full length`\
Negative promt: `easynegative, ng_deepnegative_v1_75t`

<figure><img src="../.gitbook/assets/001.jpg" alt="" width="288"><figcaption></figcaption></figure>

В негаnивных указываются правки, которые хотите избежать - но в моем случае это готовые подборки `./models/embeddings` :

{% file src="../.gitbook/assets/ng_deepnegative_v1_75t.pt" %}

{% file src="../.gitbook/assets/easynegative.safetensors" %}

Допустим нам не нужны длинные штаны и указываем в _**negative promt**_ - `long sports trousers`

<figure><img src="../.gitbook/assets/00026-ultimateHentai_v50-man red t shirt blue sports trousers run.jpg" alt="" width="288"><figcaption></figcaption></figure>

Иногда надо выделить тег (или набор тегов). Для этого используют скобки:

* ((тег)) - чем больше скобок тем важнее тег - `1man, in gym, (muscularity)`
* (тег: 1.0) - можно указывать весы и числами - `1man, in gym, (muscularity: 0.1)`

<figure><img src="../.gitbook/assets/00053-sakushimixFinished_sakushimixFinal-1man full hight in gym muscularity 0 9.jpg" alt="" width="288"><figcaption></figcaption></figure>

Есть еще теги в квадратных скобках - хз как работает.\
PS. Девочку уже добавила модель сама 0\_о

`animal, [cat: dog: 0.9]`

<figure><img src="../.gitbook/assets/00071-aniverse_v30-animal cat dog 0 9.jpg" alt="" width="288"><figcaption></figcaption></figure>

`animal, [cat: dog: 0.1]`

<figure><img src="../.gitbook/assets/00070-aniverse_v30-animal cat dog 0 1.jpg" alt="" width="288"><figcaption></figcaption></figure>
