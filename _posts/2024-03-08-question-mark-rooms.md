---
layout: post
title:  "Question Mark Rooms"
date:   2024-03-08 09:30:00 -0600
tags: rhythm-station weekly-update game-design
comments: true
---

# Minor Updates

I've tied up a few loose ends from the work I did <a href="/2024/03/01/shop-art-tutorial.html">last week</a>. I've hooked up the tutorial to the starter room so now it's actually accessible in game.
I've also done a little improvement on the shop items algorithm so that the items are all unique.

# Question Mark Rooms

One of the room types I added to my game is question mark room. I had the idea of wanting rooms with unknown outcomes (fairly standard in roguelikes), but until now I hadn't actually implemented any.
This week I finally started adding some to the game. I wanted these events to be mostly give and take in nature. You get something good at a cost.

<div align="center" class="d-flex justify-content-around flex-wrap">
  <img alt="Image of Question Mark Room 1" src="/assets/images/blogs/question-mark-rooms/question-mark-1.png" style="padding: 10px; max-width: 600px; min-width: 300px;"/>
  <img alt="Image of Question Mark Room 2" src="/assets/images/blogs/question-mark-rooms/question-mark-2.png" style="padding: 10px; max-width: 600px; min-width: 300px;"/>
</div>

Above are two examples of what you could encounter. The first one is losing some health to gain money. Events like this are pretty common in roguelikes. The second event makes it so beats alternate
between giving bonus damage and hurting you. This is a much more unique event that only really works for my game. Although I will have a bunch of events like the first one, in general I'd like to add
as many events as I can like the second one where the beat mechanic is embraced. If you have an idea for events that relate to the musical aspect of the game, leave a comment below. I'd love to hear your ideas.

Weston