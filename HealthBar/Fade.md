---
label: Fade
order: -10
---

# The Fade Feature

![](/static/images/HealthBar/chb_fade_demo.gif){width=50%}

The Fade layer provides a "catch-up" animation, often used to visualize recent damage (sometimes called a "lag bar" or "chip damage").
When the current value drops, the main bar drops instantly, but the fade bar lingers and then shrinks smoothly.

### How it Works

- **Trigger**: When `CurrentValue` changes, the system detects a difference.
- **Delay**: The bar waits for `FadeDelay` seconds.
- **Animation**: The bar interpolates from the old value to the new value over `FadeDuration` seconds.

### Configuration

![](/static/images/HealthBar/chb_fade_settings.jpg)

- **Fade Type**: Determines when the effect triggers:
  - **None**: Turns off the feature completely.
  - **PositiveOnly**: Triggers only when value increases (e.g. healing).
  - **NegativeOnly**: Triggers only when value decreases (e.g. damage).
  - **PositiveAndNegative**: Triggers on any change.
- **Fade Delay**: How long the fade bar waits after the last change before fading out.
  If any change is done to the value during this time, the delay resets.
- **Fade Duration**: How long it takes for the fading to reach the current value.
  If the value changes during this time, the fade will reach the last change done before the start of the fade, then will do a new fade to the new value.
- **Fade Curve**: A float curve asset that controls the interpolation speed (e.g., Ease-Out, Linear). If no asset is provided, it fallbacks to a linear interpolation.
