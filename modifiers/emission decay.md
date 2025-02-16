# Emission Decay

Emission Decay is a modifier placed **after** Echo that will change an Emission property depending on the age of an Echo duplicate. These properties are Hue, Saturation, Value (for the Color), Strength and Alpha.

It has 2 parameters:

1. `Property`: the property that will be decayed.
   _Default: Hue_
2. `Rate`: how much the property will change depending on age.
   _Default: `-0.1`_

### Example

| Viewport                                                  | Modifier                                       |
| --------------------------------------------------------- | ---------------------------------------------- |
| <img src="assets/emission-decay-viewport.png" height=200> | <img src="assets/emission-decay-modifier.png"> |

> [!NOTE]
> You can only decay a single property within the modifier, but the modifier can be applied multiple times on the same object with different properties.
