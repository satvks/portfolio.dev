---
banner_alt: FMOD and Unity development
banner: /blog/FMOD_Unity_Projects/unity-fmod-logo.png
title: FMOD and Unity Journey
description: It's been a long year & a lot has happened so I wanted to recap it all
date: '2024-09-15'
---

## :speaker: FMOD and Unity  

---

### A First Look at Parametrized/Adaptive Sound

My first time working with spatial audio in FMOD was in December 2021. The project was rather simple: a cityscape with spatial audio where cars could be heard passing behind a tunnel and ambient sounds of a busy city faded in and out.

![CitySoundscape](/blog/FMOD_Unity_Projects/FMOD_Cityscape_First_Prototype.png)

This concept evolved in the following project. An ambient horror game with footstep sound effects  adaptive to different flooring types. For each type of flooring, sounds were modulated and randomized by certain parameters \(e.g. pitch, volume) of the sounds in a way to make them sound less repetitive and more natural. Additionally, each flooring type had a unique effects chain which allowed us to reuse some sound assets, getting a lot out of a little (effectively easing storage). Sound files can be big!

![Horror Project Game](/blog/FMOD_Unity_Projects/fmod_horror.gif)

![Horror Project Audio](/blog/FMOD_Unity_Projects/FMOD_2.png)

### Grand Heresy

Grand Heresy was a capstone project from my final quarter in college. Working alongside 3 others, I led music composition, sound synthesis, and FMOD/Unity implementation. Our primary interest in FMOD was its spatialized audio features, in addition to it being a reliable sound engine. The result was quite easily mixed—mixing unsettling ambient audio, engaging level music, and one-shot sound effects were all manageable due to FMOD’s mastering capabilities.

[*Game Trailer of Grand Heresy*](https://www.youtube.com/watch?v=p7kH4GKrCqU)

