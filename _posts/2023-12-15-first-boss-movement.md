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

<div align="center">
  <img alt="Rough sketch of grapple/pull movement idea" src="/assets/images/blogs/first-boss/boss-movement-idea.png" style="max-width: 250px; width: 100%;"/>
</div>

I started out trying to implement this. Initially I tried using <a href="https://en.wikipedia.org/wiki/Ray_casting " target="_blank">raycasts</a> to dynamically find
a short path to the player. This has the benefit of automatically handling changes to the environment. If an object is destroyed, the raycasts
just won't hit that object anymore.

<div align="center">
  <img alt="Image of boss pathfinding using raycasts" src="/assets/images/blogs/first-boss/raycast-movement.png" style="max-width: 600px; width: 100%;"/>
</div>

While this did work in finding a path to the player, it proved to be too costly in practice, as I was experiencing freezing while the pathfinding was running.

I decided to try a different approach. Because the boss has a designated level, I thought I could just manually specify anchor points that the
boss is allowed to use to move through the level. Here's what all those points connected up looks like:

<div align="center">
  <img alt="Image of anchor points connected" src="/assets/images/blogs/first-boss/anchor-points-graph.png" style="max-width: 600px; width: 100%;"/>
</div>

With this, I was able to run a graph algorithm (<a href="https://en.wikipedia.org/wiki/A*_search_algorithm" target="_blank">A*</a>) over the points to find the shortest
path to the player.

<div align="center">
  <img alt="Gif of pathfinding to player" src="/assets/images/blogs/first-boss/a-star-pathfinding.gif" style="max-width: 600px; width: 100%;"/>
</div>

The last thing I needed to do for this method was to manually update the graph whenever an obstacle is destroyed. I just store a mapping between destructible
objects and the anchor points they have. When an obstacle is destroyed, we find the relevant anchor points and remove them from the pathfinding graph.

<div align="center">
  <img alt="Gif of path update after destroying obstacle" src="/assets/images/blogs/first-boss/dynamic-path-updates.gif" style="max-width: 600px; width: 100%;"/>
</div>

Now I was able to implement some movements for the boss. What I have is still fairly crude and needs polish, but here's a glimpse of the boss movement
in action

<div align="center">
  <img alt="Gif of boss movement" src="/assets/images/blogs/first-boss/boss-movement.gif" style="max-width: 600px; width: 100%;"/>
</div>

Weston