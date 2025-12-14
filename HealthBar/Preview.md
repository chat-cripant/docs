---
label: Preview
order: 10
---

# The Preview Feature

![](/static/images/HealthBar/chb_preview_demo.gif){width=50%}

The Preview layer allows you to visualize a "projected" change in values before it becomes permanent.
This is commonly used to show incoming damage (flashing red segment) or incoming healing (flashing green segment).

### Behavior

The preview bar is an independent layer that can be set to a specific value.

- **Incoming Damage**: If `PreviewValue < CurrentValue`, the preview bar will be smaller than the main bar. The gap between them visually represents the damage that is about to be taken (or any decrease meaning if the bar is not for health, like stamina, mana, etc.).

- **Incoming Healing**: If `PreviewValue > CurrentValue`, the preview bar extends beyond the main bar, visually representing the health that will be gained (or any increase meaning if the bar is not for health, like stamina, mana, etc.).

### Configuration

![](/static/images/HealthBar/chb_preview_settings.jpg)

- **Enable Preview**: Turns on/off the preview. Use that to display/hide the preview at runtime.
- **Preview Value**: The integer target value to preview.
- **Preview Over Fade**: A Z-order flag. If true, the preview layer will take precedence over the "Fade" layer (will be rendered on top).
