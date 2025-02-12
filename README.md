# Motion Graphics Utils
An asset library containing useful modifiers for motion graphics.

https://github.com/user-attachments/assets/b330d70a-29cf-48d3-8430-172994039bb1


## Modifiers

### Emission
Emission is a modifier to put on any object to give it an emission.

The main difference from using a material is that parameters are specified per object.
It also has more features than a material, such as having transparency and a quick visibility toggle (easier to use than hiding from the viewport since the object stays selected).

It has 5 parameters:
1. `Color`: the color of the object.
   _Default: white_
3. `Strength`: the emission strength for that object.
   _Default: `1.0`_
4. `Alpha`: the opacity of the object. A value of `1.0` means the object is fully visible.
   _Default: `1.0`_
5. `Visible`: a checkbox to quickly hide an object without adding `Alpha` keyframes.
   _Default: `True`_
6. `Shadeless`: whether the object casts shadows or not.
   _Default: `True`_

| Viewport | Modifier |
|---|---|
| <img src="https://github.com/user-attachments/assets/ce891b9d-e5c9-403b-89e8-2b8f227bb9d5" height=200> | <img src="https://github.com/user-attachments/assets/4d827fea-3681-4d2c-9e03-6367acba00f2"> |



### Echo
Echo is a modifier to put on any object to give it a motion trail, remade from AE's effect with the same name (often used by [stcubing](https://stcubing.com/) in his videos).
It is framerate dependent as it's based on a simulation zone. Default values are made to work at 60fps.

Echo saves the object's position, rotation, and scale over time, as well as its Emission property if that modifier is present (must be placed before Echo).

It has 2 parameters:
1. `Lifetime`: controls how long the motion trail is.
   _Default value: `2`_
3. `LOD`: controls the smoothness of the trail. A higher `LOD` will make the trail more smooth but can impact performance.
   _Default value: `10`_

| Viewport | Modifier |
|---|---|
| <img src="https://github.com/user-attachments/assets/34ab884c-bb13-4d95-a9be-270ce74dc780" height=200> | <img src="https://github.com/user-attachments/assets/a2d2a838-950e-4483-966a-8c85c85f97d5"> |

> [!WARNING]
> Since Echo will save properties of Emission, and simulation zones are cached, you will not see the effects of changing Emission properties unless clearing the cache (by going back to frame 0).
> You can also work around this limitation by disabling Simulation Nodes caching in the `Physics` tab of the `Property` panel.
>
> ![image](https://github.com/user-attachments/assets/2985b937-09b7-404f-bc02-2005524be09d)



### Emission Decay
Emission Decay is a modifier placed **after** Echo that will change an Emission property depending on the age of an Echo duplicate. These properties are Hue, Saturation, Value (for the Color), Strength and Alpha.

It has 2 parameters:
1. `Property`: the property that will be decayed.
   _Default: Hue_
3. `Rate`: how much the property will change depending on age.
   _Default: `-0.1`_

| Viewport | Modifier |
|---|---|
| <img src="https://github.com/user-attachments/assets/0b7e4a07-5f3f-4ff5-b141-2e2c187f9c98" height=200> | <img src="https://github.com/user-attachments/assets/bf7f20c5-9da3-4a8e-b6fd-6b04450d2f1d"> |

> [!NOTE]
> You can only decay a single property within the modifier, but the modifier can be applied multiple times on the same object with different properties.
