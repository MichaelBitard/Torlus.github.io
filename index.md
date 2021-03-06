---
layout: page
title: Welcome!
tagline: You have just reached my home page. Enjoy your stay...
---
{% include JB/setup %}

## About

I am Gregory Estrade, a.k.a **Torlus**, a software developer and a self-taught hardware hacker. I especially like reverse-engineering stuff, and use *FPGAs* to emulate ASICs. I also like to experiment concepts in various fields of computer programming, but not only.

## Projects

They are available on [GitHub](https://github.com/torlus/), but if you feel like there is something missing, please contact me.

Here are my latest projects so far:

- *Raspberry Pi* (partial) support in *QEMU*. Please check my [QEMU fork](https://github.com/Torlus/qemu).

- Legacy systems implemented into FPGAs: *Atari Jaguar* (videos [here](http://www.youtube.com/watch?v=l6KWd-LPwKg) and [here](http://www.youtube.com/watch?v=Mk850f7ICVM)), *Nec PC-Engine* (or TurboGrafx-16) in a FPGA (videos [here](http://www.youtube.com/watch?v=V0jXQXZHToE) and [here](http://www.youtube.com/watch?v=gVt4fZFnMpw)),
*SEGA Megadrive* (or Genesis) in a FPGA (video [here](http://www.youtube.com/watch?v=ilzKiW21T9Y)).

I am also hosting a [blog](http://torlus.com/floppy/) and [forum](http://torlus.com/floppy/forum) for the [HxC Floppy Drive Emulator](http://hxc2001.free.fr/floppy_drive_emulator/index.html), which is an amazing project from a friend of mine.

I also like to talk and give interviews, whatever the topic is about.

## Blog

I am not really a blogger. However, I will try to keep this part updated.

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
