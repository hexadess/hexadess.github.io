---
layout: post
title:  "Boss AI, Music, and Animation"
date:   2023-12-22 09:30:00 -0600
tags: rhythm-station weekly-update ai audio graphics
comments: true
---

# Boss AI

This week has been a bit chaotic due to the holidays approaching. Continuing on from last week I did some more work on Rhythm Station's first boss. I've implemented
a <a href="https://en.wikipedia.org/wiki/Finite-state_machine" target="_blank">state machine</a> for controlling the boss' behaviour. Now the boss can transition
between various states like "chase player", "attack player", "special attack", "take a breather", etc. Several of the states still need to be implemented so I don't
have much to visually show right now unfortunately.

# New Song?

One of the days of the week I was feeling inspired to play around with music so I started working on making a new song. I kind of like what I ended up with as a 
starting point for a piece, but I'm still not fully sure on it. I tested it out in the game and it did feel easy to find the beat with it. Here's a little clip
of it.

<div align="center">
  <figure>
    <figcaption>Clip of work in progress song:</figcaption>
    <audio controls src="/assets/audio/blogs/boss-ai-music-and-animation/Coinage-clip.ogg"></audio>
  </figure>
</div>


# Updated Animation

There's a lot that can be improved graphics-wise in my game. A lot of things could just be more detailed or animated better, but I can only do so much in a reasonable amount of time as a solo dev.
I had a thought that I should prioritize making the animations good for things that the player sees all the time to provide the highest value for the effort invested. The visual beat indicator
is something that's always on the screen and I thought I could improve this relatively shortly. Here's what the old beat animation looked like:

<div align="center" class="mb-2">
  <img alt="Gif old beat animation" src="/assets/images/blogs/boss-ai-music-and-animation/BoomboxAnimationOldLooped.gif" style="max-width: 600px; width: 100%;"/>
</div>

Essentially while on beat (inside a time window close to the beat), the boombox just gets bigger. I made a new animation that makes it feel a lot smoother. The new animation warps the boombox
as well as expands it over time. Individual elements such as the speakers expand more than the boombox as a whole, which I think this gives it a lot more flare. The animation
starts a little earlier and ends later than the previous one, but it gives more indication of the beat. The boombox is at it's largest and most warped exactly on the beat.

<div align="center" class="mb-2">
  <img alt="Gif of new beat animation" src="/assets/images/blogs/boss-ai-music-and-animation/BoomboxAnimationLooped.gif" style="max-width: 600px; width: 100%;"/>
</div>

Weston