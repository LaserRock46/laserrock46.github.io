---
layout: default
title: Protection Analysis z War Thunder
description: This is sample page
---

<video width="100%" title="Protection Analysis." loop="" autoplay="" playsinline="" muted="true">
<source src="https://v.redd.it/sj2vpwdcmj081/DASH_720.mp4" type="video/mp4">
</video>

## Główne Cechy

## Wyzwania

### Powtarzalny wynik niezależnie od prędkości pocisków

Symulacja penetracji jest oparta na Raycastach dzięki czemu obciążenie cpu obliczaniem fizyki trwa tylko jedną klatkę a nie przez cały czas trwania symulacji tak jak w przypadku użycia rigidbodies i nie trzeba się martwić o overshooting colliderów.

Przy wystrzale z użyciem RaycastAll() są generowane kolizje ze wszystkimi obiektami na trasie lotu pocisku po czym startuje Coroutine trwająca przez czas lotu i wywołuje metodę  ExecuteProjectileCollision(float coverage) która na podstawie dystansu pokonanego przez pocisk zadaje obrażenia celom które się z nim spotkały. 

<script src="https://gist.github.com/LaserRock46/cca00c6096a5089699b5bf67c94c1ea2.js"></script>

### Point Outline Shader

<img src="/docs/assets/images/Silhouette Image000.png" title="Silhouette Shader" style="width: 100%;">

### Optymalne rysowanie setek czerwonych punktów

Czerwone punkty (HitPoints) są renderowane w czasie trawnia Coroutine przez Graphics.DrawMesh dzięki czemu nie trzeba tworzyć i zarządzać obiektami. 

Użycie MaterialPropertyBlock daje możliwość ustawiania alphy dla każdego punktu indywidualnie bez tworzenia setek instancji materiału które mogłyby obciążyć pamięć.

Podczas symulacji w jednym momencie na ekranie może być nawet 300 punktów.

<script src="https://gist.github.com/LaserRock46/66f90cb24b09bc5c58a1dd5b4aa212af.js"></script>

### Problem z sortowaniem transparentnych obiektów

Niektóre obiekty z niebieskim materiałem x-ray mimo że znajdowały się dalej były rysowane przed obiektami z przodu. W unity sortowanie transparentych meshy zależy od odległości punktu początkowego mesha do kamery więc trzeba zadbać by origin był w centrum geometrii a w przypadku dużych obiektów jak gąsienice pomogło pocięcie na mniejsze kawałki. 

## [back](./)
