---
description: >-
  Welcome to the R-THAAAAAAÏ documentation book. Wether you are just looking to
  play the game or an independant dev trying to get your hands on our game, this
  is the place for you.
cover: .gitbook/assets/rtype_doc_cover.png
coverY: -230.79006772009024
layout: landing
---

# R-THAAAAAAï

> The mid ‘80s was a renaissance for shooters. In 1985, Konami released _Gradius_. Not long later, in 1987, Irem released _R-Type_. These are two of the most important games in the genre. It’s completely stunning that, in its relative infancy, Irem could shape a game as ingenious as _R-Type_. One of the premiere side-scrolling shooters, _R-Type_ moved a bit slower than your typical twitch games, with a meticulous pace and almost leisurely scrolling. The idea wasn’t to simply blast everything on the screen, although you could certainly try. The idea was, quite simply, to stay alive. Naturally, given the claustrophobic nature of the levels, swarming with enemies from every angle, this was never an easy task. [R-Type - Hardcore Gaming, October 5, 2004](http://www.hardcoregaming101.net/r-type/)

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption><p>Original R-TYPE mimic dragon</p></figcaption></figure>

This game is informally called a Horizontal Shmup (e.g. Shoot’em’up), and while R-Type is not the first one of its category, this one has been a huge success amongst gamers in the 90’s, and had several ports, spin-offs, and 3D remakes on modern systems. Other similar and well known games are the Gradius series and Blazing Star on Neo Geo.

## Our take on the R-TYPE and an EPITECH project

As you could have underdstood by now, this project is part of the educational program at EPITECH in the 3rd year of the PGE cursus (Programme Grandes Écoles).\
In this project we were asket to make **our own version of R-TYPE**... but with a twist not featured in the original game (nor in the remakes by the way): our version is a **network game**, where one-to-four players will be able to fight together the evil Bydos ! Wellp, too bad for you, you'll be fighting a giant spagetthi monster instead.

### See also

{% content-ref url="welcome/installation-processes.md" %}
[installation-processes.md](welcome/installation-processes.md)
{% endcontent-ref %}

{% content-ref url="how-to-play.md" %}
[how-to-play.md](how-to-play.md)
{% endcontent-ref %}

## Technical stack of the project

R-THAAAAAAÏ is based on multiple (2) libraries, one for displaying things to the screen and playing audio, namely SFML. SFML is,  as per stated on their website: [https://www.sfml-dev.org](https://www.sfml-dev.org), multi-media, multi-platform and also multi-language. Which is quite handy.

The other libray that R-THAAAAAAÏ uses is a general purpose C++ development library called Boost. Boost offers a large variety of library that make C++ development much easier.\
For this project, we only used the networking (`boost-asio`), thread (`boost-threads`) and configuration parsing (`boost-property-tree`) modules of the Boost library.
