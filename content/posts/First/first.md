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

# Deep-dive
## How does Spotify recommend music to users?

The “Discovery Weekly” algorithms look at two fundamental pieces of information. First, it looks at what are the songs that you have listened to and liked or added to your playlists; Second, it looks at the songs in other people’s playlists. They leverage these two basic pieces of information and decide what songs to recommend to a specific user. For example, if someone has 5 songs in one of their playlists and you have 4 of them in your library, then chances are you are also going to like the fifth song that’s in their playlist. And that song will therefore appear in your “Discovery Weekly”.

<figure style="text-align: center;">
  <img src="/img/sc2.png" alt="Screenshot" style="width: 40%; max-width: 700px;">
  <figcaption>Source: https://qz.com/571007/the-magic-that-makes-spotifys-discover-weekly-playlists-so-damn-good
</figcaption>
</figure>

This technique is called “Collaborative Filtering”, which is widely applicable to other services as well. For example, Amazon uses this technique to recommend items by looking at your purchase history and that of others. Netflix uses this to recommend shows and movies based on your watch history and other people’s watch history. Other examples include Youtube’s video recommendations, Facebook’s friend suggestions, Uber Eats’ restaurant suggestions, etc. And the algorithm works even better when there is a large user base as collaborative filtering gets more useful when there are more users. However, it is worth noting that with more users and data, it will require more computing power and storage, which can be a big scalability challenge as their user base grows.

One interesting assumption embedded in this technique is that people’s playlists are all connected in some way. A visual representation could be a huge network of millions of dots with each dot representing a playlist. Some playlists connect to a lot of other playlists and some only connect to 20 other playlists or less. But no matter how eccentric and unique a musician is, Spotify can still find ways to connect them to the right audience that likes their style of music.

To really resonate with users like a good friend, Spotify uses a second method called “taste profile” to recommend songs to its users. They profile the users’ music tastes, based on their listening behavior and habits, by generating and grouping clusters of artists, genres, and micro-genres — not just as broad as “pop” or “jazz” but as fine-grained as “synthpop”, “southern souls”, and “New Americana”.

## Strategic Analysis

### 1. Spotify's mission
> Unlock the potential of human creativity – by giving a million creative artists the opportunity to live off their art and billions of fans the opportunity to enjoy and be inspired by it.

### 2. Spotify's market share
According to [Statista](https://www.statista.com/statistics/653926/music-streaming-service-subscriber-share/), a global business data platform, Spotify has about 30% of the market share worldwide in the music streaming industry, the most out of all music providers.

<figure style="text-align: center;">
  <img src="/img/sc3.png" alt="Screenshot" style="width: 60%; max-width: 700px;">
  <figcaption>Share of music streaming subscribers worldwide in the 1st quarter of 2020, by company. Source: Statista
</figcaption>
</figure>

### 3. Spotify’s competitors

Competitors include Apple, Amazon, Google (YouTube), Pandora, etc.

### 4. Spotify’s users
At the time of writing, around 30% of listeners are Millennials, with 25% being Gen Z. Interestingly, 19% of users are above the age of 55.

As of March 2020, Spotify offers 4 billion playlists for users to listen to in 79 countries and has 286 million monthly active users (MAU), including 113 million Premium subscribers.

As of March 2020, Spotify has more than 50 million tracks, 1 million podcasts, and 4 billion playlists.

**A large user base and a large content library are crucial for Spotify to carve out a niche and differentiate itself from its competitors.**

### 5. Spotify’s financials
- Revenue 2019: ~$6.76 billion with Premium subscribers accounted for about 90% of its revenue.
- Business model: 30-day free trial, Ad-based free tier, premium plans (regular, family, student); with some plans, it is bundled up with other companies/services such as Hulu subscription in the student plan.

### 6. New features

- [Blend](https://techcrunch.com/2021/08/31/spotify-officially-launches-blend-allowing-friends-to-match-their-musical-tastes-and-make-playlists-together/), September 2021
- [Podcast Playlists](https://newsroom.spotify.com/2020-04-21/spotifys-new-podcast-playlists-will-help-you-discover-your-next-obsession/), June 2020
- [Spotify Kids](https://newsroom.spotify.com/2020-03-31/spotify-kids-is-now-available-in-the-u-s-canada-and-france/), March 2020

## The value of personalization and recommendations

### Why is Spotify investing so much time and money in bettering its recommendation system?

The first reason is that it differentiates Spotify from its competitors such as Apple Music and YouTube music. It is widely considered that Spotify’s recommendation system is better than Apple Music’s. The truth is, in all content businesses, music content or movie assets, content is a commodity. Any song sounds more or less the same on all these platforms. And anyone with enough money can buy the licenses and build their own library of content. Therefore, Spotify needs to carve out a niche to differentiate itself from competitors—building the best recommendation system.

I will assume this is also similar for video streaming businesses but I am also aware that different video streaming services such as Netflix are investing a lot of money to provide the best video streaming quality (e.g. 4K vs. 1080p) while reducing buffer time and in-app response time. So maybe in this sense, it is slightly different than the music streaming world. But nonetheless, it is still 100% true that content is a commodity.

The second reason is that the performance of the recommendation system will directly impact user retention. A good recommendation makes users more likely to continue with the service. And the more a user uses Spotify, the more the app understands the user, and the better the recommendation will get. Also, keep in mind that any personal data that a user puts into an app raises the “switching cost” since the user will have to input that data into other apps. On that front, one common challenge for any recommendation system is the “cold start”, meaning that it is always hard to provide the right recommendation at the beginning for a new user as there isn’t enough data about this user for the system to give an effective recommendation.

In conclusion, investing in personalization and recommendations is great for both listeners and the company — a savvy business move as it helps differentiate itself from its competitors as well as effectively retains users.

## What are the key metrics Spotify looks at when evaluating recommendation performance?