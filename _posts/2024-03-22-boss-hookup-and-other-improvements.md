---
layout: post
title:  "Boss Hookup and other Improvements"
date:   2024-03-22 09:30:00 -0600
tags: rhythm-station weekly-update graphics
comments: true
---

# Black Hole Ability

Continuing on from last week, I've improved the look of the black ability. Here's a before and after:

<div align="center" class="d-flex justify-content-around flex-wrap">
  <img alt="Image of old black hole ability" src="/assets/images/blogs/boss-hookup-and-other-improvements/black-hole-old.gif" style="padding: 6px; max-width: 500px; min-width: 300px;"/>
  <img alt="Image of new black hole ability" src="/assets/images/blogs/boss-hookup-and-other-improvements/black-hole-new.gif" style="padding: 6px; max-width: 500px; min-width: 300px;"/>
</div>

# Ability Icons

I've added icons for the abilities so that you can distinguish what ability you currently have active. Previously every ability was just represented by a placeholder star icon. Here's a screenshot of a debug
menu I made where you can see the currently available abilities. If you look closely at the bottom right, you can see the player's current ability is the sentry turret.

<div align="center">
  <img alt="Image of abilities" src="/assets/images/blogs/boss-hookup-and-other-improvements/ability-debug.png" style="max-width: 600px; width: 100%; min-width: 300px;"/>
</div>

# Various Debug Tools

I spent a decent chunk of this week just making debug tools for myself to be able to test out the game easier. The abilities menu pictured above is one of those tools. It allows me to change to any
ability at any time during gameplay. Other debug tools I made were a menu to apply any question mark events at any time, and a menu to manipulate player stats (health, credits, speed, etc) while playing.

# Boss Hookup

I had previously been working on the game's first boss fight and have made several posts on the progress of that. The thing is, the boss was never accessible while playing a run of the game. I would just load myself straight
into the boss room to test it out. I've now changed it so that the second last room of each section is a shop, and the last room of each section is the boss fight. I've also minorly improved the graphics
of the path selection scene.

<div align="center" class="d-flex justify-content-around flex-wrap">
  <img alt="Image path selection for the third last room of the section" src="/assets/images/blogs/boss-hookup-and-other-improvements/path-select-third-last.png" style="padding: 6px; max-width: 400px; min-width: 300px;"/>
  <img alt="Image path selection for the second last room of the section" src="/assets/images/blogs/boss-hookup-and-other-improvements/path-select-second-last.png" style="padding: 6px; max-width: 400px; min-width: 300px;"/>
  <img alt="Image path selection for the last room of the section" src="/assets/images/blogs/boss-hookup-and-other-improvements/path-select-last.png" style="padding: 6px; max-width: 400px; min-width: 300px;"/>
</div>

Weston