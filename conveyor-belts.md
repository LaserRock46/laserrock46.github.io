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

<img src="/docs/assets/images/Zrzut ekranu (36).png" title="" style="width: 50%;">

### Jak uzyskać właściwy kształt?

<video width="100%" title="Conveyor Belts Shape" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/sn8q7sdxqj081/DASH_720.mp4" type="video/mp4">
</video>

Do tworzenia łuków nie używam żadnych algorytmów jak bezier ponieważ mają swoje ograniczenia.

* Szukanie łuków polega na uformowaniu dla każdego końca pasa dwóch okręgów z transformów po lewej i prawej stronie (oznaczone białym kolorem). 
* Następnie funkcja GetNearestPoints() szuka najbliższe okregi dla przeciwnego końca.
* Funkcja GetArcEndPointsIndex() porównuje listy Transformów z najbliższych okręgów szukając punktów o najbardziej podobnej rotacji i zwraca ich indexy z tablic w których się znajudują. Indexy to oznaczają w którym miejscu okręgu kończy się łuk.
* I w końcu funkcja GetArcPoints() zwraca tablicę transformów z łukiem wyciętym z okręgu.

<script src="https://gist.github.com/LaserRock46/d30606c007ca58af157257124ad4ec38.js"></script>

### Importowanie własnych modeli

<img src="/docs/assets/images/Zrzut ekranu (35).png" title="" style="width: 50%;">

### Płynny ruch obiektów na pasie

<video width="100%" title="Conveyor Belts" loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/ygo2mjs3tj081/DASH_720.mp4" type="video/mp4">
</video>



## [back](./)
