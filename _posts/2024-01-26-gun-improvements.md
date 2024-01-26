---
layout: post
title:  "Gun Improvements"
date:   2024-01-26 09:30:00 -0600
tags: rhythm-station weekly-update game-design
comments: true
---


# Gun Improvements

This week I've largely been fiddling around with how the guns act in the game and I think I'm happy with the results. I have a clip below of how the shotgun currently works. It now only shoots every other beat, and there is a pump action that you have to wait for between each shot. I played around with what happens when you try to shoot off beat, or before you're allowed to shoot again (before the pump action finishes). Right now I settled on giving 1 grace misfire in your last 3 shots. The bad shot will still happen (but do less damage) if you're mostly shooting on beat. However, if you start shooting off beat consecutively, or shoot multiple times before your current shot has finished, the gun will now jam and not let your fire until you wait for the jam to finish. While there is a sound effect for the gun jam, I've tried to make it really obvious to the player by turning the beat indicator red while this is happening.

<div align="center">
  <video style="max-width: 600px; width: 100%;" controls>
    <source src="/assets/videos/blogs/gun-improvements/shotgun-revamp.mp4" type="video/mp4">
  Your browser does not support the video tag.
  </video> 
</div>

Weston