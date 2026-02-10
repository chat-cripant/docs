---
label: Max FPS
order: -100
---

# Max FPS

A new configuration file parameter is added by the plugin to allow you to setup automatically the maximum FPS of the editor.

By default, the editor is at 120 fps, but on middle end computers, this could be too much. The engine allows you to change the max FPS by modifying the `t.MaxFPS` variable through the command line.

However, this variable is not modifiable from the `.ini` files.

This plugin adds this option, you can set the `t.MaxFPS` variable through the `.ini` files.

To do that, you can for example open the `DefaultEditor.ini` in your project's `Config` directory, and add those lines:

```ini
[Utilities]
t.MaxFPS=60
```

Then, when you open the editor for your project, the plugin will set automatically the `t.MaxFPS` variable to the value you want.
