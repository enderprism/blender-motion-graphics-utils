# Emission

Emission is a modifier to put on any object to give it a solid color that isn't affected by lights.

The main difference from using a material is that parameters are specified per object.
It also has more features than a material, such as having transparency and a quick visibility toggle (easier to use than hiding from the viewport since the object stays selected).

It has 5 parameters:

1. `Color`: the color of the object.
   _Default: white_
2. `Strength`: the emission strength for that object.
   _Default: `1.0`_
3. `Alpha`: the opacity of the object. A value of `1.0` means the object is fully visible.
   _Default: `1.0`_
4. `Visible`: a checkbox to quickly hide an object without adding `Alpha` keyframes.
   _Default: `True`_
5. `Shadeless`: whether the object casts shadows or not.
   _Default: `True`_

### Example

| Viewport                                             | Modifier                                  |
| ---------------------------------------------------- | ----------------------------------------- |
| <img src="/assets/emission-viewport.png" height=200> | <img src="/assets/emission-viewport.png"> |

> [!NOTE]
> Objects don't glow by default. The one in the example does because:
>
> 1. Its Emission strength is above `1.0`.
> 2. There is a `Glare` node in the compositor set to `Bloom`, and viewport compositing is turned on.
