---
title: "Dragging And Dropping 3D Cards 🃏"
date: 2022-11-01
categories: ['Devblog']
tags: ['Devblog']
#author: ""
showDate: false
categories: false
tags: false
---

![Promo](/Dawn-Of-The-Cards/images/dragging_and_dropping_3d_cards/promo.gif "Promo")

Moving cards, with elegance.

<!--more-->

Now that I have defined [visually a card](https://fronkongames.github.io/Dawn-Of-The-Cards/article/rendering_a_card/), the next thing to do is to move it around the scene.

To do this we first have to detect the cards. We will do this using the '__Raycast__' functions, which __fire__ rays that when colliding with an object give us information about it.

Since it is a performance consuming operation, we will use some tricks to optimize it. The first one is that we will create a [layer](https://docs.unity3d.com/Manual/use-layers.html) to discard objects that are not involved in the operation. We will named it '__DragAndDrop__'.

![Layers](/Dawn-Of-The-Cards/images/dragging_and_dropping_3d_cards/layers.jpg "Layers")

We will also limit the ray length to the maximum distance our camera sees, since as a general rule we are not interested in objects we are not going to see. This distance is '__Camera.main.farClipPlane__'.

Since the '__Raycast__' operation is going to be used inside the '__Update__' loop (it is going to be executed every frame), it is always a good idea to avoid allocating memory if we can avoid it. So we will create a [Ray](https://docs.unity3d.com/ScriptReference/Ray.html) and use the function (Physics.RaycastNonAlloc)[https://docs.unity3d.com/ScriptReference/Physics.RaycastNonAlloc.html].

WORK IN PROGRESS