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

To do this we first have to detect the cards. We will do this using the '**Raycast**' functions, which __fire__ rays that when colliding with an object give us information about it.

Since it is a performance consuming operation, we will use some tricks to optimize it. The first one is that we will create a [layer](https://docs.unity3d.com/Manual/use-layers.html) to discard objects that are not involved in the operation. We will named it '__DragAndDrop__'.

![Layers](/Dawn-Of-The-Cards/images/dragging_and_dropping_3d_cards/layers.jpg "Layers")

We will also limit the ray length to the maximum distance our camera sees, since as a general rule we are not interested in objects we are not going to see. This distance is '__Camera.main.farClipPlane__'.

Since the '**Raycast**' operation is going to be used inside the '**Update**' loop (it is going to be executed every frame), it is always a good idea to avoid allocating memory if we can avoid it. So we will create a [Ray](https://docs.unity3d.com/ScriptReference/Ray.html) and use the function [Physics.RaycastNonAlloc](https://docs.unity3d.com/ScriptReference/Physics.RaycastNonAlloc.html).

The code to detect the cards would look something like this:

```c#
  // Layer of the objects to be detected.
  [SerializeField]
  private LayerMask raycastMask;

  // How many impacts of the beam we want to obtain.
  private const int HitsCount = 5;

  // Information on the impacts of shooting a ray.
  private readonly RaycastHit[] raycastHits = new RaycastHit[HitsCount];
  
  // Ray created from the camera to the projection of the mouse
  // coordinates on the scene.
  private Ray mouseRay;

  /// <summary>
  /// Returns the Transfrom of the object closest to the origin
  /// of the ray.
  /// </summary>
  /// <returns>Transform or null if there is no impact.</returns>
  private Transform MouseRaycast()
  {
    Transform hit = null;

    // Fire the ray!
    if (Physics.RaycastNonAlloc(mouseRay,
                                raycastHits,
                                Camera.main.farClipPlane,
                                raycastMask) > 0)
    {
      // We order the impacts according to distance.
      System.Array.Sort(raycastHits,
                        (x, y) => x.distance.CompareTo(y.distance));


      // We are only interested in the first one.
      hit = raycastHits[0].transform;
    }

    return hit;
  }  
```

Before calling this function, we must update '__mouseRay__' with the mouse coordinates. We will do it with this code:

```c#
  mouseRay = Camera.main.ScreenPointToRay(Input.mousePosition);
```

> ⚠️ **In this post I will use the old [Input](https://docs.unity3d.com/ScriptReference/Input.html) for simplicity, but it is recommended to use the new [Input System](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.4/manual/QuickStartGuide.html).** ⚠️

In order to get all this to work on a card, we must first add a '[Collider](https://docs.unity3d.com/ScriptReference/Collider.html)'. Without this component, our ray would pass through the card without detecting it. A '[Box Collider](https://docs.unity3d.com/Manual/class-BoxCollider.html)' is a good choice for the type of geometry of a card, but if you need more precision you can use a '[Mesh Collider](https://docs.unity3d.com/Manual/class-MeshCollider.html)'.

The second thing to do is to assign the '__layer__' we have selected to the chart. We are now ready to detect a card.

![Ray hit](/Dawn-Of-The-Cards/images/dragging_and_dropping_3d_cards/rayhit.gif "Ray Hit")

Now we can start moving our cards. First we are going to define two interfaces, the first one is **IDrag**, for objects that you can drag.

```c#
/// <summary>
/// Draggable object.
/// </summary>
public interface IDrag
{
  /// <summary> Can it be draggable? </summary>
  public bool IsDraggable { get; }

  /// <summary> A Drag operation is currently underway. </summary>
  public bool Dragging { get; set; }
  
  /// <summary> Mouse enters the object. </summary>
  /// <param name="position">Mouse position.</param>
  public void OnPointerEnter(Vector3 position);
  
  /// <summary> Mouse exits object. </summary>
  /// <param name="position">Mouse position.</param>
  public void OnPointerExit(Vector3 position);

  /// <summary> Drag begins. </summary>
  /// <param name="position">Mouse position.</param>
  public void OnBeginDrag(Vector3 position);

  /// <summary>A drag is being made. </summary>
  /// <param name="deltaPosition"> Mouse offset position. </param>
  /// <param name="droppable">
  /// Object on which a drop may be made, or null. </param>
  public void OnDrag(Vector3 deltaPosition, IDrop droppable);

  /// <summary> The drag operation is completed. </summary>
  /// <param name="position">Mouse position.</param>
  /// <param name="droppable">
  /// Object on which a drop may be made, or null. </param>
  public void OnEndDrag(Vector3 position, IDrop droppable);
}
```

And the second is **IDrop**, for objects that can accept IDrag objects.

```c#
/// <summary>
/// Accept draggable objects.
/// </summary>
public interface IDrop
{
  /// <summary> Is it droppable? </summary>
  public bool IsDroppable { get; }

  /// <summary> Accept an IDrag? </summary>
  /// <param name="drag">Object IDrag.</param>
  /// <returns>Accept or not the object.</returns>
  public bool AcceptDrop(IDrag drag);

  /// <summary> Performs the drop option of an IDrag object. </summary>
  /// <param name="drag">Object IDrag.</param>
  public void OnDrop(IDrag drag);
}
```

As you can see, it is **IDrop** that will authorize an **IDrag**, with its **AcceptDrop** method, whether or not to accept a drop operation to be executed on it.

With these two interfaces ready we can start with the one in charge of handling the drag and drop operations of our cards. We can call it '**DragAndDropManager**'. An operation of
A drag & drop operation can be divided into:

- There is no drag operation at present.
  - Cards must be detected under the mouse pointer.
    - If a card is detected and the left mouse button is pressed, a drag operation is started and the **OnBeginDrag** method must be called.
    - If there is a detected card and no button is being pressed, the **OnPointerEnter** and **OnPointerExit** methods of the detected card are called.
- A drag operation is in progress.
  - If the left mouse button is pressed, the card should be moved and the **OnDrag** method should be called.
  - If it is not, the drag operation must be finished and the **OnEndDrag** method must be called.

**🚧 WORK IN PROGRESS 🚧**