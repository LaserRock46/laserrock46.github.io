---
layout: default
title: Isometric Tactical RPG
description: Projekt taktycznego RPG z walką w czasie rzeczywistym inspirowany klasycznym Falloutem
---

<video width="160%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="/docs/assets/videos/Isometric shooter overhead and cursor anchor.mp4" type="video/mp4">
</video>

## Co udało mi się do tej pory zrobić:


### UX: Praca kamery a celowanie

Dodałem funkcję która podczas obrotu kamery blokuje kursor w miejscu w które celuje gracz, działanie można zobaczyć na powyższym video. To ważne bo gra jest w czasie rzeczywistym. 


### Wizualizacja szans na trafienie i rozrzutu

System który tak jak w wielu taktycznych grach pokazuje procentową wartość szans na trafienie bazując na odległości i rozrzucie.

<img src="/docs/assets/images/isometric shooter screen.png" title="isometric shooter screen" style="width: 100%;">

### Animator i system poruszania

* Postać jest w stanie biegać/chodzić w 8 kierunkach.
* Zmieniać pozy dla trybu uzbrojonego i nieuzbrojonego.
* Płynnie przechodzić miedzy stanem uzbrojonego, nieuzbrojonego.
* Animator posiada Blend tree dla obrotu postaci w miejscu co umożliwia jej obrót w dowolne miejsce wskazane kursorem.

<img src="/docs/assets/images/animator small.png" title="animator" style="width: 100%;">

<video width="160%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="/docs/assets/videos/Isometric shooter rotate.mp4" type="video/mp4">
</video>




