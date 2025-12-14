---
label: 9-Slice Material Node
order: -51
---

# 9-Slice Material Node

![](/static/images/HealthBar/chb_9slice_node.jpg)

Since I was not happy with the default `Draw as Box` of Unreal Engine, I've created a custom material node to make the 9-slice of the UV in the material.

By default, the 9-slice of UE (the `Draw as Box`) will stretch the borders when the size of the widget is smaller than the size of the borders.

So I've implemented a custom 9-slice node, usable in materials, which properly handles the border's UVs when the size of the widget is smaller than the size of the borders.

![](/static/images/HealthBar/chb_9slice_demo.gif){width=50%}

The main issue is that this node needs some data not accessible by default in the material.
The needed data are: the widget local size (not the draw size), and the brush's margin for the box.

The plugin will passes automatically those parameters to the materials of the widget.
You can see [the Material Parameters](./MaterialParams.md) to know how to include the parameters in your own materials.

The plugin also includes a basic material named `MM_CHB` using this node.
If you just want to change the images and colors, you can create material instances of this basic material.
