---
layout: default
title: Devlog 1 - Kalkulator Penetracji
description: Udało mi się zaimplementować wiele mechanik z systemów penetracji War Thunder
---


<video width="180%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/ukg883sa4ni81/DASH_720.mp4" type="video/mp4">
</video>

### Source

https://github.com/LaserRock46/WT-XRay

### Funkcje

System wyświetla informacje o:

* Materiale z którego jest wykonany element pancerza. Każdy materiał ma współczynnik RHAe co ma wpływ na wytrzymałość pancerza.
* Grubość zapisaną w komponencie pancerza
* Efektywna grubość i efektywna grubość z uwzględnieniem materiału wyrażona w RHAe
* Kąt uderzenia pocisku
* Konstrukcyjny kąt nachylenia pancerza

Na podstawie tych danych, informacji o wartości penetracji pocisku z uwzględnieniem jej utraty na dystansie i uwzględnieniu kąta przy którym pocisk na pewno zrykoszetuje system oceniania czy jest możliwa penetracja lub rykoszet.

### Implementacja

#### Elementy pancerza

<video width="100%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="/docs/assets/videos/Armor Panels.mp4" type="video/mp4">
</video>

Tutaj przydała się umiejętność obsługi blendera, model został pocięty na elementy pancerza i oczyszczony z zbędnych detali które mogły by wpłynąć na wyniki.
Każdy mesh zawiera collider i komponent ArmorPanel w którym są zapisane grubość i typ pancerza.

#### Efektywna grubość pancerza

<video width="100%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="/docs/assets/videos/Test Effective Thickness.mp4" type="video/mp4">
</video>


#### Pozostałe czynniki



## [back](./)
