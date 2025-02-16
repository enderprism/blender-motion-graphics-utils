# Echo

Echo is a modifier to put on any object to give it a motion trail, remade from AE's effect with the same name (often used by [stcubing](https://stcubing.com/) in his videos).
It is framerate dependent as it's based on a simulation zone. Default values are made to work at 60fps.

Echo saves the object's position, rotation, and scale over time, as well as its Emission property if that modifier is present (must be placed before Echo).

It has 2 parameters:

1. `Lifetime`: controls how long the motion trail is.
   _Default value: `2`_
2. `Subdivisions`: controls the smoothness of the trail. Higher `Subdivisions` will make the trail more smooth but can impact performance.
   _Default value: `3`_
   _This property is split into 2 parameters, `Preview` and `Render`, to be able to achieve higher detail without impacting viewport performance._

### Example

| Viewport                                         | Modifier                              |
| ------------------------------------------------ | ------------------------------------- |
| <img src="/assets/echo-viewport.png" height=200> | <img src="/assets/echo-modifier.png"> |

> [!WARNING]
> Since Echo will save properties of Emission, and simulation zones are cached, you will not see the effects of changing Emission properties unless clearing the cache (by going back to frame 0).
> You can also work around this limitation by disabling Simulation Nodes caching in the `Physics` tab of the `Property` panel.
>
> ![image](assets/echo-warning.png)
