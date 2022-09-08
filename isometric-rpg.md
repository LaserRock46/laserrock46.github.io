---
layout: default
title: Isometric Tactical RPG
description: Projekt taktycznego RPG z walką w czasie rzeczywistym inspirowany klasycznym Falloutem
---

<iframe src="https://www.youtube.com/embed/uTK1imkOC5w?cc_load_policy=1&?vq=hd1080&rel=0" width="560" height="315" title="Unnamed Post Apocalyptic Isometric RPG" frameborder="0" allowfullscreen></iframe>

## Co udało mi się do tej pory zrobić:

### Wizualizacja szans na trafienie i rozrzutu

System który tak jak w wielu taktycznych grach pokazuje procentową wartość szans na trafienie i rozrzut.

### Taunts (odzywki)

System werbalnej reakcji przeciwnika na zadane obrażenia, często bardzo wulgarnej. Pozwoliłem sobie skopiować kilka odzywek z Fallout 2.

### UX: Praca kamery a celowanie

Dodałem funkcję która podczas obrotu kamery blokuje kursor w miejscu w które celuje gracz, działanie można zobaczyć na powyższym video. To ważne bo gra jest w czasie rzeczywistym. 

### Płynne przejście pomiędzy ragdollem a animacją

Po upadku postać jest w stanie płynnie przejść do animacji wstawania i dopasowuję klip w zależności od tego czy ciało jest skierowane w dół lub w górę.

<iframe width="560" height="315" src="https://www.youtube.com/embed/c2uYzSl7n0Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Animator i system poruszania

* Postać jest w stanie biegać/chodzić w 8 kierunkach.
* Zmieniać pozy dla trybu uzbrojonego i nieuzbrojonego.
* Płynnie przechodzić miedzy stanem uzbrojonego, nieuzbrojonego.
* Animator posiada Blend tree dla obrotu postaci w miejscu co umożliwia jej obrót w dowolne miejsce wskazane kursorem.

<img src="/docs/assets/images/animator small.png" title="animator" style="width: 100%;">






