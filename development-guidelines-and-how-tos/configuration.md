---
description: How to configure the game
---

# ⚙ Configuration

### Assets

Our definition of an asset is any ressources that must be loaded by the SFML as textures, font or sounds.

Assets are loaded at the execution of a client with a content.ini file located in the asset folder.

If you need to implement or modify an asset, you need to add or modify it into the corresponding section with a key and a path.



### Config

{% code title="config.ini" %}
```ini
[texture]
...
players=assets/textures/player.gif
menu=assets/textures/menu/menu.png
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

Here is the configuration of the game you can change: background music (in bgm section), sound effects (in sfx section), font (you got it), keybinds (guess what), fps, and server info.



### Textures

Textures can be modified with certain conditions: your texture must be the same size as the previous one, and if it is a spritesheet, their must be as many steps as the previous one, at the same location, in order to avoid textures completly laggy and resized.

However, if you want to add a new texture to the game this is pretty easy: just add it in the \[texture] section with a key (describing what the texture is, try to be as precise as possible) equal to a path to the asset (assets/textures/...).

In the code, our component Drawable will handle the texture just by precising the key at his creation. Our component Animate is in charge to make move the sprite sheets, by creating multiple rectangle and displaying them with a delay.

{% hint style="info" %}
See src/client/getWorld.cpp, their is multiple example of utilisation of Drawable and Animable components, don't forget to add an Activable component to your entity else it will not be display.
{% endhint %}

### Sounds and Fonts

Unlike the textures, sounds and fonts are easier to change cause of no resizement or anything, same in terms of additions.

At the moment only one font is used by our Client, but feel free to add more if it stays in tunes with the space/retro theme.



### Keybinds

All keybinds handled by SFML are available, you can change those already used, or add some if needed in your feature.

{% hint style="info" %}
You can use F15 to shoot if you want, try it if your keyboard is big enough :smile:

(we said every keys)
{% endhint %}

