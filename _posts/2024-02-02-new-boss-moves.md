---
layout: post
title:  "New Boss Moves"
date:   2024-02-02 09:30:00 -0600
tags: rhythm-station weekly-update ai
comments: true
---


# Boss Update

This past week I've continued working on the first boss for Rhythm Station. Specifically, I've added 2 new moves that the boss does. One is a goo claw. While chasing the player, the boss always checks if the player could be hit with a claw.
If the player can be hit, it throws a claw out at the player. Adding this move ended up eating a lot of time as there were some technical difficulties with the game engine (<a href="https://godotengine.org/" target="_blank">Godot</a>) I'm using that I'll describe more below. The second move I've added is a goo throwing frenzy where the boss spins really fast and tosses out a bunch of goo. Essentially a bullet hell move.

# Claw Attack

Fair warning, this section gets quite technical. For the claw attack, I wanted the claw to come from one of the arms of the boss. This means after each grapple/pull move, I needed to do a check from each arm to see if either were capable of hitting the boss. I initially implemented this as a <a href="https://en.wikipedia.org/wiki/Ray_casting">raycast</a>, but I ran into a problem. Raycasts don't have any width to them. So I was often finding the raycast would say yes, this arm
has a direct path to the player right now, but when the claw was thrown out it would snag on some obstacle along the way. This is because the claw actually has some width to it that the cast does not account for. So I started
brainstorming what I could do to overcome this. My initial thought was to do multiple raycasts for each arm starting at each side of the claw instead of just one starting from the center of the claw. If all raycasts for an arm
could see the player, the claw should be able to move to the player without hitting anything on the way. This seemed okay, but I decided to look around at what else Godot had to offer.

I quickly found the <a href="https://docs.godotengine.org/en/stable/classes/class_shapecast2d.html">ShapeCast2D</a> class. From the description: "This is similar to RayCast2D, but it allows for sweeping a region of space, rather than just a straight line". This seems to be exactly what I need! So I set about to start using this. This ended up being a hug time sink. I could not get the ShapeCast2D to return consistent results. A lot of the time it would
only return 1 collision result even though there were multiple objects along the path that should've collided with the cast. I checked out the Godot discord server and I found a recent case of somone else also struggling to use this class.
I reached out to see if they figured how to use it but they hadn't.

As I was curious to what's going on and Godot is open source, I started poking around on the Godot Github repo to see if I could find how this was working. I tracked the cast to
<a href="https://github.com/godotengine/godot/blob/master/servers/physics_2d/godot_space_2d.cpp#L256">here</a>, but was starting to feel a little lost. Like I'd need to download the source and trace it in a debugger to more easily tell what was 
happening. This would be a much bigger time investment than just browsing Github source files. Right around this time, however, an idea popped into my head. What if I just made the shape that is being swept in this cast to be the size of the
entire cast.  I ended up trying this an it worked! I was able to get all objects that collided with the shapecast consistently. All I then had to do is find the closest one and see if it was the player. If it was, we have a clear path to the
player. Otherwise, the claw will get snagged on something along the way. The boss will have to move (if the other arm also has no line of sight) and try again.

Since I got this working, I updated the person in the discord server I talked to about my current solution so they could do the same. After looking around Github some more to see if there were any open issues related to the 
ShapeCast2D, I found an issue for improving the ShapeCast2D docs. I decided to jump on there and share my experience around how it seemed to be behaving for me. A contributor responded that I should file a bug report since they weren't sure if
the behaviour I was seeing was due to some error in using the class on my end. So I ended up spending some more time doing that. You can check out the report I made <a href="https://github.com/godotengine/godot/issues/87845">here</a>.

All in all, it would have been much faster to just do the two raycasts for each arm, but the shape cast seemed like it was a better fit for my case. If you're using a less mature engine or framework such as Godot, you just have to accept that 
some of your time will be spent debugging / reporting engine issues. As a believer in OSS (open source software), this is an acceptable trade off for me.

# Goo Tornado

The second move implementation went much smoother. Every so often in the boss's state machine, I transition to this goo tornado attack. The boss spins in a circle while flinging out goo in 8 directions around it. It alternates
22.5 degress between shots to create a fairly standard bullet hell pattern where you have to move back and forth to dodge the goo. There was one fun bug I had while implementing this where I forgot to clean up the goo blobs after they hit
something. Since none of the blobs got cleaned up and were constantly colliding with things, they kept spamming the goo hit audio sound and it was quite obnoxious. Here a clip of it. I've lowered the volume to save your ears:
<div align="center">
  <video style="max-width: 600px; width: 100%;" controls>
    <source src="/assets/videos/blogs/new-boss-moves/GooThrowBug.mp4" type="video/mp4">
  Your browser does not support the video tag.
  </video> 
</div>

# Putting it all together

Here's a video of the boss in it's current state. You can see it transition between chasing the player, throwing it's claw, and throwing a lot of goo. It still needs more refinement (the claw is almost impossible to dodge right now), but
it's definitely coming along.
<div align="center">
  <video style="max-width: 600px; width: 100%;" controls>
    <source src="/assets/videos/blogs/new-boss-moves/MelodigooCurrentState.mp4" type="video/mp4">
  Your browser does not support the video tag.
  </video> 
</div>

Weston