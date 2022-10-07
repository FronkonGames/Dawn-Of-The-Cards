---
title: "Making A 3D Card In Blender 🃏"
date: 2022-09-24

categories: ['Devblog']
tags: ['Devblog']

#author: ""
showDate: false
categories: false
tags: false
---

![Promo](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/promo.png "Promo")

The first thing a card game needs is... cards.

<!--more-->

And why in 3D? It would be _easier_ to do it in 2D, but to have more options in terms of effects and also to differentiate from the rest I decided that my card game would be 3D.

I was going to need a 3D editor, and in my modest opinion [Blender](https://www.blender.org/) is unbeatable in quality / price.
Especially if you take into account that it is free ;).

![Blender](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/blender.jpg "Blender")

Once installed, in an empty scene, I added a plane using the menu '**Add > Mesh > Plane**'.
To make it easier to handle, I set the top camera by pressing '**7**' on the numeric pad.

![3D plane](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/plane.jpg "3D plane")

There is no standard size for a card. A Bridge card measures 57.15 x 88.9 mm, while a Poker card measures 62 x 88 mm.
This size is known as [B8 in ISO 216](https://formaty.info/en/B8/). Since it is the best known, it is the size I will use.

![B8 ISO 216](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/b8.jpg "B8 ISO 216")

However, I am not really interested in the size itself, but in the ratio between width and height or _aspect ratio_. In the case
case of a Poker card is **0.7** (62 / 88).

To achieve that _aspect ratio_, with the plane selected, press '**S**' and then '**X**', and typing '**0.7**' (62 / 88) will get the _aspect ratio_ I'm looking for.

![Plane 0.7](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/plane_07.jpg "Plane 0.7")

To round corners I use the '**Bevel**' modifier.

![Card bevel](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/card_bevel.jpg "Card bevel")

And to give it a little thickness the modifier '**Solidify**'.

![Card solidify](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/card_solidify.jpg "Card solidify")

Now I applied all the transformations pressing '**Ctrl+A**', so that the scale of the final geometry is 1.

![Transforms](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/transform.jpg "Transforms")

And the modifiers.

![Apply](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/apply.jpg "Apply")

It was time for the materials. But first I created some UV coordinates in the '**UV Editing**' tab and selecting a _cube projection_.

![UV](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/uv.jpg "UV")

As its name indicates, this tool creates the coordinates by projecting a cube on the model.

![Cube UV](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/cube_uv.png "Cube UV")

It may not be the best option for rounded edges, but it is the easiest one. You can adjust the coordinates by hand using the window on the left.

In the '**Shading**' tab, I created three materials: 'FrontFace', 'BackFace' and 'Border'. I selected the front face and the 'FrontFace
the 'FrontFace' material, and clicked the '**Assign**' button to associate them.

With '**CONTROL + 7**' I switched to the back view and performed a similar operation.
similar operation.

To assign the border material, select the two faces and invert the selection.

![Assign](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/assign.jpg "Assign")

Now it was only left to export to FBX to the Unity project.

The only change I made in the export options was in '**Apply Scalings**', which I set to '**FBX Units Scale**' so that in Unity
would export the scale correctly.

![Export](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/export.jpg "Export")

Until next time... **stay gamedev, stay awesome!**

<p align=center>
[📥 DOWNLOAD BLENDER SCENE 📥](/Dawn-Of-The-Cards/images/making_a_3d_card_in_blender/card.blend)
</p>