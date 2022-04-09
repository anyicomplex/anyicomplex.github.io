---
title: "Words for those Want to Develop Game in Java"
description: "This article represents only my personal view, welcome to leave a message to discuss"
date: 2021-10-07T02:23:11-05:00
lastmod: 2021-12-06T04:37:58-05:00
draft: false
tags: [Java, Game Develop]
categories: IT
---

# Is Java suitable for developing games?

**My answer is: NO.**  
If you're not focused on open source, established commercial solutions like Unity and GameMaker are obviously the best choices for you.  
If you're focused on open source, there are plenty of open source game engines out there (most of them written in C/C++) that are right up your alley. (Not listed here, please search in the major open source platforms by yourself)  
If none of the existing game engines satisfy you, you can try to write your own - but I don't recommend Java, or to be precise, any managed language, not even a compiled language with GC. Low-latency, real-time interaction is essential for video games, and managed languages are inherently inadequate in this regard. (Unity is developed in C#, but the underlying layer is still C/C++, and the C# code is AOT-compiled to improve performance)  
**If you don't have a reason to use Java, then please don't think about developing games in Java.**

# What if I have to use Java?

**The Java ecosystem is huge, and in fact, there's a few relatively mature solutions available.**

* [libGDX](https://libgdx.com/): focused on 2D, supported platforms: Windows/Linux/Mac/Android/iOS/HTML5
* [jMonkeyEngine](https://jmonkeyengine.org/): pure 3D, support platform: Windows/Linux/Mac/Android/iOS/HTML5

**I think the relatively mature Java game engine is only these two, the others are not mature enough.**  
**It is not a wise choice to try to develop 3D games with libGDX, and it is a rather irrational thing to develop 2D games with jMonkeyEngine.**

# Can Java develop large-scale games like King's Quest?

**Yes.**  
The downside of Java was never about "large-scale", or there wouldn't be so many servers running SpringBoot, a web backend framework written in Java.  
**The famous [PokeMMO](https://pokemmo.eu/) is developed with libGDX.**

# What do I need to learn about developing games in Java?

**On a desktop platform, it is almost impossible to get players to install the JRE specifically for your game.**  
Therefore, a lot of effort had to be put into packaging and streamlining the JRE, providing installation packages corresponding to different desktop platforms to ensure an out-of-box user experience.  
The size of the JRE used to be a problem, but the good news is that the size requirements for game files are not that high these days.  
**As for the other issues, they are not Java-specific, but are issues that all game developers have to deal with.**

# Can GraalVM's native-image technology be used for Java game development?

**Theoretically possible, but I don't recommend it.**  
Unless you have high requirements for reducing the size of your game files, doing so will only expose you to a lot of unnecessary hassles while losing a lot of Java features and third-party libraries.  
Making the Java bytecode completely AOT-compiled to native executable can reduce startup time and system resource usage, but none of this is the point of game development.  
**If you care about game file size, system resource usage, and startup time, then it's better to stop developing games in Java before it's too late.**