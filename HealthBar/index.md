---
label: Health Bar
icon: heart
---

# Health Bar Plugin

[![](/static/images/HealthBar/thumbnail.jpg){width="500"}](https://fab.com/listings/c1350561-e596-4bed-aa28-12aab5c18d85){target="blank"}

<style>
    .center {
        text-align: center;
    }
</style>

:::center
[!button variant="info" icon="download" size="l" target="blank" text="Get it on Fab!"](https://fab.com/listings/c1350561-e596-4bed-aa28-12aab5c18d85)
:::

The Crux Health Bar is a highly customizable UMG/Slate widget designed for all types of games.
It extends the standard progress bar functionality with built-in support for "damage preview", smooth "catch-up" fading animations, and dual-axis filling strategies.

The widget is built on a custom Slate implementation (SCXHealthBar) for performance and exposes a standard UMG interface (UCXHealthBar).

### General Settings

![](/static/images/HealthBar/chb_settings.jpg)

- **Max Value**  
  This value determines what is the 100% value (used to compute current percentage with `CurrentValue / MaxValue`).

- **Current Value**  
  This is the current value for the data shown by the widget (used to compute current percentage with `CurrentValue / MaxValue`).

- **Padding**  
  This defines the filling bounding box. The 0% and 100% will be determined by taking into account this area.  
  
  > [!note]
  > You can toggle the `Draw Debug` in the advanced section to visualize the padding.  
  > It will be depicted by a yellow rectangle when the widget is selected.
  
  ![](/static/images/HealthBar/chb_padding.jpg){width=50%}

- **Filling Strategy**  
  This widget supports filling on both axes simultaneously.
  You can make any combination of those values:
  - **Horizontal**: LeftToRight, RightToLeft, FillFromCenter, or None.
  - **Vertical**: TopToBottom, BottomToTop, FillFromCenter, or None.

  ![](/static/images/HealthBar/chb_horizontal_demo.gif){width=50%}

- **Fill Type**  
  - **Mask**: The image is clipped (masked) to show progress. Useful for complex textures that shouldn't be distorted.
  - **Scale**: The image geometry itself is scaled. Useful for simple gradients or solid colors.

  ![](/static/images/HealthBar/chb_scalemask_demo.gif){width=50%}

You can get more details on the features by visiting the following pages:

[!ref](./Preview.md)
[!ref](./Fade.md)
[!ref](./MaterialParams.md)
[!ref](./MaterialNode.md)
