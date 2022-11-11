---
description: How to configure the game
---

# Configuration

### Assets

Assets are loaded at the execution of a client with a content.ini file located in the asset folder.

If you need to implement a new asset, you need to add it to in the corresponding section (here texture) with a key and a path.



### Config

{% code title="config.ini" %}
```ini
[texture]
...
menu=assets/textures/buttons/menu.png
[bgm]
bgm1=assets/audio/bgm/bgm1.ogg
[sfx]
laser=assets/audio/sfx/laser.ogg
splash_screen=assets/audio/sfx/splash_screen.ogg
[font]
nasa=assets/fonts/nasa.otf
[keybind]
up=Z
...
[game]
fps=60
[server]
host=localhost
port=8000
```
{% endcode %}

Here is the configuration of the game you can change: background music (in bgm section), sounds (in sfx section), font (you got it), keybinds (guess what), fps, and server info.
