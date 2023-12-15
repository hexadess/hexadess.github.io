---
layout: post
title:  "Health and Movement"
date:   2023-12-08 12:30:00 -0600
tags: rhythm-station weekly-update game-design
comments: true
---

# Health and Movement

Last week I attended a local game design meetup and showed off Rhythm Station to a few people. I got a few interesting suggestions, but the ones the piqued my curiosity the most
were related to health and movement.

### Health

The initial suggestion related to health was "What if there was no health?". I quickly thought this was a bad idea because the game is a roguelike. It would be extremely punishing to die
in one hit. After mentioning that I didn't think it fit the genre, the person testing my game said "What if you replaced health with retries?". This was an interesting idea to me.
You die in one hit, but each run you get some number of retries to burn through. If you still have retries left, you just restart the current room when hit. I haven't really seen other roguelikes
that do things this way and I thought it could be good for pattern learning. E.g. A common roguelike theme is that you finally make it to a boss and then proceed to die quickly because you don't yet know
the boss' attack patterns. With retries, you would have a few attempts to learn the initial attack which might help you progress faster. 

I quickly implemented this feature at the start of the week to see what it was like. Initially, all I did was swap the player's health for retries and tested it out. Levels felt a bit too long for this
style of play and it was really annoying to die in the last wave of a room and have to restart the whole thing over. I thought part of the reason for this was that the enemies were too tanky. If I die
in one hit, why should they take four hits before dying? So I reduced enemy health so they only took 1-2 shots (depending on the type of enemy) before they died. While this did allow rooms to be completed
faster and made them not feel punishing to have to restart, it had other consequences. The variation between guns didn't really matter anymore. Why would I want a powerful close range shotgun over a long range
pistol if they're both killing the enemies in one or two hits. Long range is now always preferred. Another one was that status effects no longer mattered. Currently the player and enemies can become burned,
poisoned, etc, which slowly drains health from anyone affected. This no longer matters since the player dies in one hit and the enemies die in one or two. 

For these reasons, I decided to go back to the regular health system. Given that the example for where the feature might be useful was boss fights, I'm exploring doing something around that. E.g. Maybe
at the boss fight you can trade a portion of your health for the ability to retry the boss if you die. That way players can get more attempts while learning, and experienced players can save their health.

### Movement

So far, the player's movement has been unrestricted in Rhythm Station. You can move in any direction at any time. I initially had gone this route because I find having to press a button to move every beat very
tiring. <a href="https://store.steampowered.com/app/247080/Crypt_of_the_NecroDancer/" target="_blank">Crypt of the Necrodancer</a> (CotN) is where my experience on this comes from. While I enjoy that game, I can only play it in smaller bursts because of the relentlessness of having to tap a button every single beat.

{:refdef: style="text-align: center;"}
![Image of player moving freely](/assets/images/blogs/health-and-movement/continuous-movement.gif){: width="400" }
{: refdef}

It had been suggested by a few people who have tried my game that maybe it'd be good to have discrete movement similar to CotN, but I've been fairly adamant about not doing this for the reason above. Further, I want Rhythm
Station to feel a little more fast paced, and making the movement discrete definitely makes it feel closer to turn-based. At this recent game design meetup, someone tried my game and suggested that maybe it'd be cool if the character only moved on beat,
but you didn't have to actually press the buttons on beat. It just took whatever movement input was set during the beat and did that. I actually had tried this before, and it didn't end up working out because the beat window
is pretty small and you either just inch along every beat, or you crank up the on-beat movement so much that you're basically teleporting every beat, which is hard to control. But this time the suggestion made me think,
"What if the player dashed every beat but didn't move otherwise?". Dashes last longer than the on-beat window, so it doesn't feel like your teleporting, but the movement definitely feels in line with the beat due to the dash
getting kicked off every beat. I coded up the change to see what it was like.

{:refdef: style="text-align: center;"}
![Image of player dashing on beat](/assets/images/blogs/health-and-movement/beat-movement.gif){: width="400" }
{: refdef}

I made the enemies and projectiles move like this as well so everything was dashing to the beat. It was kind of fun to move like this, but once I started trying to play the game, it became apparent that it was way harder to aim when movement is
happening like this. You have to shoot on beat, but every beat you and the enemies suddenly lunge in a direction, making the enemies hard to track. I did find it easier to track the beat of the music with this style of movement though. Another observation
was that the pace felt slower than before, which I didn't like as much personally. After a bit more thought, I realized this would also limit me to having to do all movement to the beat of music. I had ideas in the back of my head that it would be
cool to make some things in the game move to the melody of the music instead of beat, for example. It would not really be viable to do this if you were restricted to beat movement as you could become a sitting duck to something happening to the melody.
Limiting everything to beat movement may not be bad, but it was a restriction to be aware of. Eventually I decided to go back to the continuous movement, but I'm still contemplating implementing this style of movement in some capacity. Having only enemies do this might be the way to go. It gives some improved beat tracking, but doesn't hinder aiming as much, while still leaving the possibility open for things to move to parts of the music other than the beat.  

Weston