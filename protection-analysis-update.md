---
layout: default
title: Protection Analysis - Aktualizacja
description: Moim zadaniem rekrutacyjnym było stworzenie tej aktualizacji 
---


<video width="130%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/nyk0exefe6j81/DASH_720.mp4" type="video/mp4">
</video>

[https://v.redd.it/nyk0exefe6j81/DASH_720.mp4](https://v.redd.it/nyk0exefe6j81/DASH_720.mp4)

Celem zadania było dodanie do istniejącego systemu wizualizacji kalkulatora penetracji, efektów wystrzelenia wieży i pożaru silnika.

### Source

[https://github.com/LaserRock46/WT-XRay](https://github.com/LaserRock46/WT-XRay)

### Funkcje

System wyświetla informacje o:

* Materiale z którego jest wykonany element pancerza. Każdy materiał ma współczynnik RHAe co ma wpływ na wytrzymałość pancerza.
* Grubość zapisaną w komponencie pancerza
* Efektywna grubość i efektywna grubość z uwzględnieniem materiału wyrażona w RHAe
* Kąt uderzenia pocisku
* Konstrukcyjny kąt nachylenia pancerza

Na podstawie tych danych, informacji o wartości penetracji pocisku z uwzględnieniem jej utraty na dystansie i uwzględnieniu kąta przy którym pocisk na pewno zrykoszetuje system oceniania czy jest możliwa penetracja lub rykoszet.

 <div id="banner" style="overflow: hidden;justify-content:space-around;">
    <div class="" style="max-width: 20%;max-height: 20%;display: inline-block;">
        <img src="/docs/assets/images/Screenshot%(64).png">
    </div>

    <div class="" style="max-width: 20%;max-height: 20%;display: inline-block;">
        <img src="/docs/assets/images/Screenshot%(65).png">
    </div>

    <div class="" style="max-width: 20%;max-height: 20%;display: inline-block;">
        <img src="/docs/assets/images/Screenshot%(66).png">
    </div>
    </div>
  
### Implementacja

#### Elementy pancerza

<video width="100%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="/docs/assets/videos/Armor Panels.mp4" type="video/mp4">
</video>

Tutaj przydała się umiejętność obsługi blendera, model został pocięty na elementy pancerza i oczyszczony z zbędnych detali które mogły by wpłynąć na wyniki.
Każdy mesh zawiera collider i komponent ArmorPanel w którym są zapisane grubość i typ pancerza.

W skrypcie ArmorTypesData są zapisane rodzaje pancerza i współczynniki RHA

<script src="https://gist.github.com/LaserRock46/0fc301530d2f9433ad49d954d342e1ad.js"></script>

#### Efektywna grubość pancerza

<video width="120%" title="" loop="" autoplay="" playsinline="" muted="true">
<source src="/docs/assets/videos/Test Effective Thickness.mp4" type="video/mp4">
</video>

Na tym video widać jak testuję czy wynik algorytmu pokrywa się z rzeczywistością.
Czerwona linia zaczyna się w miejscu w które trafił raycast a kończy na tylnej płaszczyźnie której pozycję obliczył algorytm.
Jak widać obliczenia pokrywają się z rzeczywistą grubością mesha. Pod kątem 60* efektywna grubość podwaja się, również w War Thunder pod tym samym kątem grubość się podwoiła co oznacza że algorytm działa.

Algorytm polega na sprawdzeniu odległości od punktu uderzenia (armorFrontSurface) do punktu przecięcia z płaszczyzną (armorBackSurface).
Pozycja (armorBackSurface) jest odsunięta w kierunku normal vector miejsca w które uderzył pocisk i grubości pancerza.

<script src="https://gist.github.com/LaserRock46/97423155de41946796df2f54e5456e99.js"></script>



## [back](./)
