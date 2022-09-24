---
title: "Making a 3D card in Blender 🃏"
date: 2022-09-24

categories: ['Devblog']
tags: ['Devblog']

#author: ""
showDate: false
categories: false
tags: false
---

The first thing a card game needs is... cards.

<!--more-->

And why in 3D? It would be _easier_ to do it in 2D, but to have more options in terms of effects and also to differentiate myself from the rest I decided that my card game would be 3D.
differentiate myself from the rest I decided that my card game would be 3D.

For that I was going to need a 3D editor, and in my modest opinion [Blender](https://www.blender.org/) is unbeatable in quality / price.
Especially if you take into account that it is free ;).

![Blender](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/blender.jpg "Blender")

Once installed, in an empty scene, I added a plane using the menu '**Add > Mesh > Plane**'.
To make it easier to handle, I set the top camera by pressing '**7**' on the numeric pad.

![3D plane](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/plane.jpg "3D plane")

There is no standard size for a letter. A Bridge card measures 57.15 x 88.9 mm, while a Poker card measures 62 x 88 mm.
This size is known as [B8 in ISO 216](https://formaty.info/en/B8/). Since it is the best known, it is the size I will use.

![B8 ISO 216](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/b8.jpg "B8 ISO 216")

However, I am not really interested in the size itself, but in the ratio between width and height or _aspect ratio_. In the case
case of a Poker card is **1.42** (88 / 62).

To get that _aspect ratio_, with the plane selected, press '**S**' and then '**X**', and typing '**0.7**' (1 / 1.42) will get the _aspect ratio_ you are looking for.

![Plane 1.42](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/plane_07.jpg "Plane 1.42")

To round corners use the '**Bevel**' modifier.

![Card bevel](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/card_bevel.jpg "Card bevel")

And to give it a little thickness the modifier '**Solidify**'.

![Card solidify](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/card_solidify.jpg "Card solidify")

Until next time... **stay gamedev, stay awesome!**