---
label: Radial Bars
order: -15
---

# Radial Bars

![](/static/images/HealthBar/chb_radialbars_demo.gif){width=50%}

The plugin provide a way to create radial (circular) health/progress bars.

### Behavior

The `Radial` filling type behaves exactly as the `Scale` filling type.

However, there are some considerations to take into account.

First, a standard health/progress bar is fully defined directly using the WidgetRect, but a radial bar can't be fully defined by its WidgetRect.
So there are some new settings available when using the `Radial` filling type (see next section for more details).

Secondly, the full bar is anchored depending on the filling direction.
You can see an example on the animation below.
I made that in case you want your full bar to reflect the increase in max health or stamina for example, so your bar grows in the same direction as the filling direction.

![](/static/images/HealthBar/chb_radial_anchor.gif){width=70%}

!!!info
When using a texture with a border, the bar will not make a full circle.
If you want to make a full closed circle, please refer to the [Customize Your Bars](./Customize.md) page
!!!

### Configuration

![](/static/images/HealthBar/chb_radial_settings.jpg)

![](/static/images/HealthBar/chb_radial_settings_demo.gif)

- **Offset Angle**: Rotate the whole bar clockwise in degree, independent of filling direction.
- **Size Angle**: The angular size in degree of the whole bar.
- **Offset Radius**: Modify the radius of the bar. Mostly useful when using `Bottom to Top` filling direction.
- **Bar Thickness**: The radius size in pixels of the whole bar.
