---
title: "How does Spotify recommend music to its users?"
description: "Deep-dive into Spotify's recommendation system."
date: 2021-09-28
categories:
    - Blog
tags:
    - Testtag
image: ""
toc: true
sidebar:
    toc: true
---

[![Read my article](https://img.shields.io/badge/Read%20the%20article%20on%20Medium-black?style=flat&logo=medium&logoColor=white)](https://medium.com/@wenpeizhang/how-does-spotify-recommend-music-to-its-users-aeaae645c33f)

# Background

In 2015, Spotify launched its very first “Discover Weekly” playlists to its users and it became an instant hit. Within 6 months of launch, this playlist was streamed over 1.7 billion times, according to the company.

Nowadays, we can see a few more playlists or collections uniquely curated for each user, such as “Trending genres for you”, “Uniquely yours” (collection), “Based on your recent listening”, “More Like [Artist Name]”, and “More of what you like”. Its recommendation system covers not only music but podcasts as well, such as a curated list of “Shows you might like”. At the time of writing, my Spotify homepage has 21 “component positions” vertically, and 8 of them directly indicate music recommendations, such as “More Like [Artist Name]”. And for the rest, nearly all 13 of them have embedded some sort of recommending mechanism into the collections in their positions with the exception of “The state of music today”, which I assume is intended to introduce users to new genres and music, with which the users might discover new music tastes either similar to or unlike what they were used to before.


<figure style="text-align: center;">
  <img src="/img/sc1.png" alt="Screenshot" style="width: 40%; max-width: 700px;">
  <figcaption>Component positions on my Spotify Homepage on my iOS device at the time of writing.
</figcaption>
</figure>

But how does Spotify recommend music (50 millions+ tracks, 1 million+ podcasts) to users? Why is the recommendation system so important to Spotify? How do companies like Spotify figure out if its recommendation system is working well or not? What are the key metrics they look at when evaluating recommendation performance?

# How does Spotify recommend music to users?

The “Discovery Weekly” algorithms look at two fundamental pieces of information. First, it looks at what are the songs that you have listened to and liked or added to your playlists; Second, it looks at the songs in other people’s playlists. They leverage these two basic pieces of information and decide what songs to recommend to a specific user. For example, if someone has 5 songs in one of their playlists and you have 4 of them in your library, then chances are you are also going to like the fifth song that’s in their playlist. And that song will therefore appear in your “Discovery Weekly”.

### Background
My background information goes here.

### Interests
My interests include:
- Interest 1
- Interest 2
- Interest 3

## What I'll Write About

I plan to write about several topics:

### Technical Topics
- Programming
- Web Development
- Data Science

### Other Topics
- Personal experiences
- Learning journey
- Future plans

## Conclusion

Thanks for reading my first post!

### adding another 
x
xxxxxxx
xxxxxxxxxxx
xxxxxxxxxx
- Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans
- - Personal experiences
- Learning journey
- Future plans