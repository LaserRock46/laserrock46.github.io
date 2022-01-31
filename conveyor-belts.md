---
layout: default
title: Conveyor Belts z Satisfactory
description: System budowania przenośników taśmowych znany z gier factory builder w wersji freeform
---
<video width="100%" title="Conveyor Belts" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/7bzxichn2a071/DASH_720.mp4" type="video/mp4">
</video>

## Główne Cechy

* Możliwość budowania i łączenia ze sobą przenośników taśmowych
* W pełni funkcjonalne przenośniki, transportują i przekazują towary między sobą
* System zapobiegający budowaniu przenośników nie spełniającyh wymagań jak długość, nachylenie, koszt, kolizja z innymi obiektami
* Możliwość importowania własnych modeli przenośników

## Wyzwania

### Optymalizacja

* Mesh jest generowany tylko raz po zmianie pozycji
* Jest możliowść importowania uproszczonego mesh dla collidera
* Funkcja regulowania LOD(ilość pętli w pasie) na podstawie tolerancji kątów między punktami. 
* Jeden materiał dla ruchomych i statycznych części pasa. Użycie w meshu vertex color koloru zielonego oznacza które miejsca będą animowane przez materiał

<img src="/docs/assets/images/Zrzut ekranu (36).png" title="" style="width: 50%;">

### Jak uzyskać właściwy kształt?

<video width="100%" title="Conveyor Belts Shape" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/sn8q7sdxqj081/DASH_720.mp4" type="video/mp4">
</video>

Do tworzenia łuków nie używam żadnych algorytmów jak bezier ponieważ mają swoje ograniczenia.

* Szukanie łuków polega na uformowaniu dla każdego końca pasa dwóch okręgów z transformów po lewej i prawej stronie (oznaczone białym kolorem). 
* Następnie funkcja GetNearestPoints() szuka najbliższe okregi dla przeciwnego końca.
* Funkcja GetArcEndPointsIndex() porównuje listy Transformów z najbliższych okręgów szukając punktów o najbardziej podobnej rotacji i zwraca ich indexy z tablic w których się znajdują. Indexy to oznaczają w którym miejscu okręgu kończy się łuk.
* I w końcu funkcja GetArcPoints() zwraca tablicę transformów z łukiem wyciętym z okręgu. (Wycięty łuk oznaczono kolorem czerwonym)

<script src="https://gist.github.com/LaserRock46/d30606c007ca58af157257124ad4ec38.js"></script>

### Importowanie własnych modeli

Stworzyłem skrypt który przechwytywuje i sortuje dane z meshów stworzonych w programach do grafiki 3D. Dane te są przechowywane w Scriptable Object i używane przez komponent odpowiedzialny za ekstrudowanie mesha.


Modele muszą spełniać takie warunki jak posiadanie dwóch symetrycznych pętli, vertex color dla elementów ruchomych i uv.

<img src="/docs/assets/images/Zrzut ekranu (35).png" title="" style="width: 50%;">

### Ekstrudowanie mesha

<script src="https://gist.github.com/LaserRock46/fab8f0f65441fb07346467969fe242f4.js"></script>

### Płynny ruch obiektów na pasie

<video width="100%" title="Conveyor Belts" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/ygo2mjs3tj081/DASH_720.mp4" type="video/mp4">
</video>

Kiedy zrobiłem show-off tego projektu na reddit, kilka osób zapytało mnie jak zrobić by obiekty na pasie poruszały się w taki sposób bez użycia fizyki więc uznałem że warto to opisać tutaj.

Realistyczną orientację obiektu na pasie można uzyskać poprzez skierowanie go w punkt który stanowi pozycję obiektu na pasie + połowa długości obiektu.

Przy użyciu funkcji GetLookAtPosition() zwracana jest pozycja na który ma patrzeć transform, następnie dzięki GetTransformDirection() jest uzyskiwany kierunek dla transform.forward.

<script src="https://gist.github.com/LaserRock46/b64ce390094cef99aae99932a7185c67.js"></script>


## [back](./)
