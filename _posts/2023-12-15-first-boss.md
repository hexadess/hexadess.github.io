---
layout: post
title:  "First Boss - Movement"
date:   2023-12-15 09:30:00 -0600
tags: rhythm-station weekly-update ai
comments: true
---

# First Boss - Movement

This week I've been working on the first boss for Rhythm Station. I had this idea that I wanted the boss' movement to exclusively use a
grapple and pull mechanic to chase the player. These movements would be synchronized to the beat of the music.
E.g. beat 1 - grapple, beat 2 - pull, beat 3 - grapple, etc. Here was my rough sketch of the idea:

{:refdef: style="text-align: center;"}
![Rough sketch of grapple/pull movement idea](/assets/images/blogs/first-boss/boss-movement-idea.png){: width="250" }
{: refdef}

I started out trying to implement this. Initially I tried using <a href="https://en.wikipedia.org/wiki/Ray_casting " target="_blank">raycasts</a> to dynamically find
a short path to the player. This has the benefit of automatically handling changes to the environment. If an object is destroyed, the raycasts
just won't hit that object anymore.

{:refdef: style="text-align: center;"}
![Image of boss pathfinding using raycasts](/assets/images/blogs/first-boss/raycast-movement.png){: width="600" }
{: refdef}

While this did work in finding a path to the player, it proved to be too costly in practice, as I was experiencing freezing while the pathfinding was running.

I decided to try a different approach. Because the boss has a designated level, I thought I could just manually specify anchor points that the
boss is allowed to use to move through the level. Here's what all those points connected up looks like:

{:refdef: style="text-align: center;"}
![Image of anchor points connected](/assets/images/blogs/first-boss/anchor-points-graph.png){: width="600" }
{: refdef}

With this, I was able to run a graph algorithm (<a href="https://en.wikipedia.org/wiki/A*_search_algorithm" target="_blank">A*</a>) over the points to find the shortest
path to the player.

{:refdef: style="text-align: center;"}
![Gif of pathfinding to player](/assets/images/blogs/first-boss/a-star-pathfinding.gif){: width="600" }
{: refdef}

The last thing I needed to do for this method was to manually update the graph whenever an obstacle is destroyed. I just store a mapping between destructible
objects and the anchor points they have. When an obstacle is destroyed, we find the relevant anchor points and remove them from the pathfinding graph.

{:refdef: style="text-align: center;"}
![Gif of path update after destroying obstacle](/assets/images/blogs/first-boss/dynamic-path-updates.gif){: width="600" }
{: refdef}

Now I was able to implement some movements for the boss. What I have is still fairly crude and needs polish, but here's a glimpse of the boss movement
in action

{:refdef: style="text-align: center;"}
![Gif of boss movement](/assets/images/blogs/first-boss/boss-movement.gif){: width="600" }
{: refdef}

Weston