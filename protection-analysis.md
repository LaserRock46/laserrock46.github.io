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

### Point Outline Shader

<img src="/docs/assets/images/Silhouette Image000.png" title="Silhouette Shader" style="width: 100%;">

### Optymalne rysowanie setek czerwonych punktów

Czerwone punkty (HitPoints) są renderowane w czasie trawnia Coroutine przez Graphics.DrawMesh dzięki czemu nie trzeba tworzyć i zarządzać obiektami. 

Użycie MaterialPropertyBlock daje możliwość ustawiania alphy dla każdego punktu indywidualnie bez tworzenia setek instancji materiału które mogłyby obciążyć pamięć.

Podczas symulacji w jednym momencie na ekranie może być nawet 300 punktów.

<script src="https://gist.github.com/LaserRock46/66f90cb24b09bc5c58a1dd5b4aa212af.js"></script>

### Problem z sortowaniem transparentnych obiektów

## [back](./)
