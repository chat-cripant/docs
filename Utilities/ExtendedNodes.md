---
label: Extended Nodes
order: -20
---

# Extended Nodes

The plugin also adds some useful basic nodes I think are missing in the base Unreal Engine.

## Lerp Nodes

Some lerp nodes have been added for basic variable types:

![](/static/images/Utilities/MissingLerpNodes.png)

## Misc Nodes

- `Spectate` node:
Allows you to set the player as spectator properly, without the need to  do it in C++ nor doing a "false" spectator mode by just possessing your spectator pawn. This node also flags properly the controller as spectator.

![](/static/images/Utilities/NodeSpectate.jpg)

- `Draw Debug Vector` node:
This node is a shortcut to avoid doing manual calculation each time you want to draw a debug vector. This is basically the same as a `Draw Debug Arrow` with the `Location` as `Line Start` and the `Location + Vector * Length` as `Line End`.

![](/static/images/Utilities/NodeDrawDebugVector.jpg)
