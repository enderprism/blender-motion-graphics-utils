# Echo Transform

Echo Transform serves as a workaround for one of geometry node's limitations, being that when captured in a node group, the rotation of an object (from the `Object Info` node) is wrapped in the range `[-180°, 180°]`, because rotations are probably stored as quaternions instead of eulers.

The problem arises when an object with [Echo](/modifiers/echo.md) rotates above that range: the interpolated rotation slowly goes the other way to the opposite extreme.

Echo Transform works by applying transformations on the object in geometry nodes and _storing the rotation as an euler_.

[Echo](/modifiers/echo.md) can then retrieve this accurate rotation data along with the rest of the transformation and work accordingly.

> [!INFO]
> When changing an object's location through Echo Transform, its origin will not move with it. To other objects, it will be as if the affected object had never been transformed. **If you intend on parenting objects to one with Echo Transform, make sure to also change the object's regular transform.**

### Example

| Viewport                                                  | Modifier                                       |
| --------------------------------------------------------- | ---------------------------------------------- |
| <img src="assets/echo-transform-viewport.png" height=200> | <img src="assets/echo-transform-modifier.png"> |
