# Emission

Emission is a modifier to put on any object to give it a solid color that isn't affected by lights.

The main difference from using a material is that parameters are specified per object.
It also has more features than a material, such as having transparency and a quick visibility toggle (easier to use than hiding from the viewport since the object stays selected).

It has 7 parameters:

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
6. **Modifier stack**: The following properties need to be set before any Echo bake.
   1. `As Instance`: whether to turn the object into an instance. Use with Echo with `Realize Instances` disabled.
      _Default: `True`_
   2. `Echo`: enables compatibility with Echo when `As Instance` is enabled. Enabling it without an Echo after it will make the object invisible (this is hacky, I haven't found a way to detect Echo modifiers after Emission in the modifier stack).
      _Default: `False`_

### Example

| Viewport                                             | Modifier                                  |
| ---------------------------------------------------- | ----------------------------------------- |
| <img src="/assets/emission-viewport.png" height=200> | <img src="/assets/emission-modifier.png"> |

> [!NOTE]
> Objects don't glow by default. The one in the example does because:
>
> 1. Its Emission strength is above `1.0`.
> 2. There is a `Glare` node in the compositor set to `Bloom`, and viewport compositing is turned on.
