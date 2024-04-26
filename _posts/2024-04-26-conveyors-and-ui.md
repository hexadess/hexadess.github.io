---
layout: post
title:  "Font, Calibration, and Conveyors"
date:   2024-04-26 09:30:00 -0600
tags: rhythm-station weekly-update graphics game-design
comments: true
---

# General

After releasing the demo of the game last week, I downloaded it on my steam deck and attempted to play it on my T.V. I found a couple things difficult so I worked at improving them.

# Font

While fun, the original font was hard to read. It was especially noticable when trying to read at T.V. distances. I knew I needed to change the font out to fix the problem so I spent some
time on that. Ultimately I found what I think is a winner:

<div align="center" class="d-flex justify-content-around flex-wrap">
  <img alt="Image of ui with new font" src="/assets/images/blogs/conveyors-and-ui/font.png" style="padding: 6px; max-width: 1000px; min-width: 300px;"/>
</div>

Easy to read, but still not completely boring.

# Calibration

Calibration is the other thing I struggled with on my T.V. Previously there was just one set of bars that blinked to the beat of the music. I found it hard to tell if my
changes to the audio/visual offset were doing anything. To improve this, I've added another set of bars that blink as if there were no offset adjustments at all. The direct
visual comparison between the modified and unmodified version definitely help me see the affect of my changes better and figure out an offset that works for my setup.

<div align="center" class="d-flex justify-content-around flex-wrap">
  <img alt="Image of calibration menu" src="/assets/images/blogs/conveyors-and-ui/calibration.png" style="padding: 6px; max-width: 1000px; min-width: 300px;"/>
</div>

# Conveyors

For a while I've been on-off working on a conveyor belt obstacle and this week I finally made a level that uses them. I still may tweak their implementation some more, but
they are functional now.

<div align="center" class="d-flex justify-content-around flex-wrap">
  <img alt="Image of level with conveyors" src="/assets/images/blogs/conveyors-and-ui/conveyors.png" style="padding: 6px; max-width: 1000px; min-width: 300px;"/>
</div>

Weston