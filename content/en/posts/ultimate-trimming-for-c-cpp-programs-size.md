---
title: "Ultimate Trimming for C/C++ Programs Size"
description: "This article represents only my personal view, welcome to leave a message to discuss"
date: 2022-02-28T15:45:19-05:00
lastmod: 2022-03-06T23:09:04-05:00
draft: false
tags: [C, C++]
categories: IT
---

# Causes

Program release has always been a major problem for programmers, especially in the distribution of applets.  
If you wrote a small program with limited functionality, but it depends on a heavy runtime in dozens of megabytes, I believe that many users will not think it's worth to use.  

**If you refute me with reasons like "hard disks are now at a cabbage price" or "network bandwidth is worthless now that we're in the 5G era", then please close this blog post immediately because it's not written for you.**

# Methods

## 1. Dynamically runtime calls

As long as the target device contains the runtime and dependent libraries required by the program, it can be reduced in size by dynamically calling.

### *nix

This is not a problem on the *nix platform, because it must contain the available C/C++ runtime, and it is modular in terms of libraries, so you only need to specify the corresponding dependencies if you use the package manager, otherwise you have to install them manually.  
If you don't want to bother the user and don't use a package manager, then you have to reduce the dependencies and use only the libraries that are necessarily included in the target platform.

### Windows

Windows is not modular in terms of libraries, except for some basic C/C++ runtime libraries, so there is only one way to reduce dependencies.  
However, if you want to be compatible with older systems, the number of libraries that must be included is extremely limited, and even some of the basic C/C++ runtime libraries are not always included, so you either have to bother the user or use older runtime libraries.

1. Use Visual C++ 6.0  
C/C++ programs compiled with VC6.0 only requires one runtime library, msvcrt.dll, which has been included in the system since Windows 2000.
2. Use the msvcrt version of MinGW and do not use C++ functions that are not supported by msvcrt  
If you don't want to use a compiler like VC6.0, which has been out of maintenance for years, and you want to ensure compatibility and trim size, then using the msvcrt version of MinGW and not using C++ features that are not supported by msvcrt is a good solution.  
In this case, the msvcrt version of MinGW compiles the same C/C++ program as VC6.0, with only requires msvcrt.dll as runtime library.

## 2. Adjusting compiler parameters

I don't think I need to say much about this. Specifying the compiler to optimize the code and not inserting debug informations is a basic skill.

## 3. Use compression shells

Compression shells such as UPX, ASPack, etc. can compress the size of the program, but they take up extra memory (because you have to decompress the compressed program into memory) and slow down the startup time (though not too much).  
My advice for this method is: do only if you need.

# Thoughts

After thinking about it, it's really not necessary to be so stingy now...These days, applets under 5M are basically within the acceptable range of users, while uncompressed executables of 20M...30M executables can be generally compressed to 5M or less.