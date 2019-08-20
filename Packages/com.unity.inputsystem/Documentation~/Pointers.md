# Pointers

[`Pointer`](../api/UnityEngine.InputSystem.Pointer.html) devices are defined as [`InputDevices`](../api/UnityEngine.InputSystem.InputDevice.html) that track positions on a 2D surface. Three types of pointers are supported:

* [Touch](Touch.md)
* [Mouse](Mouse.md)
* [Pen](Pen.md)


## Controls

Each of these types implements a common set of controls. For a more detailed descriptions of these controls, refer to their [scripting reference](../api/UnityEngine.InputSystem.Pointer.html).

|Control|Type|Description|
|-------|----|-----------|
|[`position`](../api/UnityEngine.InputSystem.Pointer.html#UnityEngine_InputSystem_Pointer_position)|[`Vector2Control`](../api/UnityEngine.InputSystem.Controls.Vector2Control.html)|The current pointer coordinates in window space.|
|[`delta`](../api/UnityEngine.InputSystem.Pointer.html#UnityEngine_InputSystem_Pointer_delta)|[`Vector2Control`](../api/UnityEngine.InputSystem.Controls.Vector2Control.html)|The difference in `position` since the last frame.|
|[`press`](../api/UnityEngine.InputSystem.Pointer.html#UnityEngine_InputSystem_Pointer_press)|[`ButtonControl`](../api/UnityEngine.InputSystem.Controls.ButtonControl.html)|Whether the pointer or it's primary button is pressed down.|
|[`pressure`](../api/UnityEngine.InputSystem.Pointer.html#UnityEngine_InputSystem_Pointer_pressure)|[`AxisControl`](../api/UnityEngine.InputSystem.Controls.AxisControl.html)|Normalized pressure with which the pointer is currently pressed while in contact with the pointer surface (Only relevant for pressure sensitive devices, such as tablets and some touch screens).|
|[`radius`](../api/UnityEngine.InputSystem.Pointer.html#UnityEngine_InputSystem_Pointer_radius)|[`Vector2Control`](../api/UnityEngine.InputSystem.Controls.Vector2Control.html)|The size of the area where the finger touches the surface. Only relevant for touch input.|

## Window Space

Within player code, the coordinates are in the coordinate space of the player window.

Within editor code, the coordinates are in the coordinate space of the current [`EditorWindow`](https://docs.unity3d.com/ScriptReference/EditorWindow.html). This means that if you query [`Pointer.current.position`](../api/UnityEngine.InputSystem.Pointer.html#UnityEngine_InputSystem_Pointer_position) in [`UnityEditor.EditorWindow.OnGUI`](https://docs.unity3d.com/ScriptReference/EditorWindow.OnGUI.html), for example, the returned 2D vector will be in the coordinate space of your local GUI (same as [`UnityEngine.Event.mousePosition`](https://docs.unity3d.com/ScriptReference/Event-mousePosition.html)).