---
label: Material Parameters
order: -50
---

# Custom Material Parameters

The widget automatically attempts to create Dynamic Material Instances (MIDs) for the brushes assigned to it.

If your materials contain specific parameters, the widget will update them every frame during the `OnPaint` cycle, allowing you to create advanced shaders (e.g. moving patterns, borders, tiling, etc.) that react to the bar's state.

### Exposed Parameters

> [!Note]
> If the brush uses a standard texture, these parameters are simply **ignored**.  
> They are **only** relevant if a **customized Material** is used.

![](/static/images/HealthBar/chb_materialparams.jpg)

{.compact}

| Parameter Name | Type | Description |
| --- | --- | --- |
| `WidgetLocalRect` | `Vector4` | The local geometry of the widget.<br>`X`, `Y`: Top-Left position<br>`Z`, `W`: Width and Height |
| `WidgetMargins` | `Vector4` | The padding values set on the widget.<br>`X`: Left<br>`Y`: Top<br>`Z`: Right<br>`W`: Bottom
| `WidgetProgress` | `Vector4` | Current fill status.<br>`X`, `Y`: Fill Fraction (0.0 to 1.0) on X and Y axes.<br>`Z`, `W`: Anchor point (0.0=Start, 0.5=Center, 1.0=End). |
| `WidgetPositive` | `Scalar` | Context-sensitive boolean flag.<br>`1.0`: The specific bar (Preview/Fade) represents a "positive" delta (Healing/Gain).<br>`0.0`: Represents a "negative" delta (Damage/Loss). |
