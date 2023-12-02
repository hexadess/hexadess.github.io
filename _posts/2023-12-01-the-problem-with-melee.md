---
layout: post
title:  "The Problem with Melee"
date:   2023-12-01 12:30:00 -0600
comments: true
---

# The Problem with Melee

With Rhythm Station being a roguelike game, I wanted ways for players to be able to differentiate runs and create builds that would work for certain styles of play.
Initially the only things the player could do were shoot and dash. A few people that played the game had asked for the ability to melee and I thought this would be a good way to differentiate builds.
There could be items that improved melee or made short range combat more lucrative and the same for long range combat. So I added melee as an action the player could do at any time.

{:refdef: style="text-align: center;"}
![Image of player meleeing](/assets/images/blogs/the-problem-with-melee/hand-melee.gif){: width="400" }
{: refdef}

I added stamina (blue bars in the GIF) that would get used up when the player dashed or melee'd, but would refill every beat if they were not doing either of those things.
I thought this worked well with the shooting, which had a similar mechanism of using bullets and refilling while the player wasn't shooting. Players would have to balance between
melee, dash, and shooting, adding a depth of skill to the game. So I gave a build of the game to a few people with this added. And guess what? NO ONE used the melee feature.
To me, the game was more fun when I was mixing everything. So I asked them why they weren't using melee. The overwhelming reason was that it felt too dangerous. Players are very risk averse
in a roguelike game since they only have one life. They'll play very cautiously to avoid taking any damage. Sitting back and shooting was simply a more viable strategy to beat the game.
You have more time to react to any incoming projectiles and it completely avoids getting hit with enemy melee attacks.

I wanted players to play faster and take risks, as this felt more fun and exciting to me personally. Taking some inspiration from Doom, where you have to kill enemies to gain health,
I thought of the idea that I could give the player a very limited amount of ammo and they would have to kill enemies to get more. This way after they unloaded their clip, they'd
be forced to use melee if they hadn't been able to kill an enemy in that time for a refill. Further, players who mixed shooting and melee together would almost never run out of ammo and
be able to continue this style forever. So I gave another build of the game out with this in place. Annnnd guess what? People overwhelming thought this version of the game was worse than the
previous one. They didn't like being forced into using melee and were frustrated by how limited their ammo was. No one switched their gameplay style to try and mix together melee and shooting like I intended.
I believe part of the reason for this is it takes a lot of skill to be able to mix between different types of attacks while making sure you are doing everything to the beat of the music.
The other part is that people still want to limit risk as much as possible. So they sit back and shoot for as long as they can, and then only start meleeing when they have no other option.
Then they just feel like melee is really punishing to use compared to shooting.

Back to the drawing board. What if instead of being able to melee and shoot at the same time, you could only do one or the other? I.e. What if the player couldn't melee with their off hand, and there were a
mix of dedicated melee and ranged weapons. I thought this had a few benefits. It would still make runs different based on whether the player had a melee or ranged weapon and they would have to choose items/upgrades
that worked well with their weapon. Another one is that it simplified gameplay. Players only have one attack button to worry about hitting on beat. And finally, I thought dedicated melee weapons could have slightly
more range than just the player's claw, making it a bit easier to use. So I quickly whipped up a bat melee weapon to test out

{:refdef: style="text-align: center;"}
![Image of player holding bat](/assets/images/blogs/the-problem-with-melee/Bat.png){: width="400" }
{: refdef}

After just playtesting the game myself for a while, I could tell this was going to be another failure. The game was still just easier to play with the gun and I was always taking more hits when using the bat.
The small amount of extra range you got from the bat was not enough extra reaction time to make a difference. The only way to make the melee weapons not feel bad was to make them one-hit kill the enemies, which
just felt really OP compared to the guns. It also makes upgrades pretty useless. Why do I need any short range combat improvements when I'm already one-hitting all the enemies?

Feeling a bit discouraged at this point, I took a step back from this situation and worked on a few other things. After a week or so I decided to "follow the fun". What everyone was having the most fun doing was shooting.
So I made the decision to scrap melee from the game altogether. This did throw a wrench into my plans to differentiate builds by melee vs ranged combat, however. I needed to think of something new to accomplish this.
I came up with the idea to have different types of guns. Some of them with shorter range and more damage (e.g. shotgun) and some of them with longer range and less damage (e.g. pistol). This would still allow for
different builds based on whether you were using a shorter range weapon or a longer range one. After building out three different guns, they all end up feeling good to play with!

<div align="center">
  <img alt="Image of player shooting shotgun" src="/assets/images/blogs/the-problem-with-melee/shotgun-shot.png" width="400" style="margin: 10px;"/>
  <img alt="Image of player shooting assault rifle" src="/assets/images/blogs/the-problem-with-melee/assault-rifle-shot2.png" width="400" style="margin: 10px;"/>
  <img alt="Image of player shooting pistol" src="/assets/images/blogs/the-problem-with-melee/pistol-shot.png" width="400" style="margin: 10px;"/>
</div>

So I've decided to leave melee out of the game and just focus on having different guns. Melee seemed like a really good idea in theory, but it just didn't work out in practice.
There probably is some combo of design decisions out there that would make melee viable, but I wasn't finding them. One of my takeaways from this is to consider building towards the player's natural tendencies.
E.g. A constant here was that players always liked/preferred shooting. Instead of trying to force them to shoot less and melee, I think it would have been better to think "Player's really like shooting.
How can I emphasize this feature and make it as fun as possible?". The second takeaway just reinforces something I already believed, which is that playtesting is king. You may think something is a good idea, but
until you get it into the hands of players, you really have no idea how they're going to use / react to it.

Weston