---
title: "Writing and Compiling win32 Programs under Linux"
description: "One of my development records"
date: 2022-02-28T14:24:36-05:00
draft: false
tags: [C, C++, Windows, win32, Linux]
categories: IT
---

**The term "win32" in this article is the common name for winapi in mainland China programmers' circles, not specifically for 32-bit winapi (not to mention 64-bit, we also calling the earlier 16-bit winapi "win32" since the appearance of 32-bit winapi).**

# Feasibility

Thanks to the MinGW (Minimalist GNU for Windows) project, it is perfectly feasible to compile win32 applications as long as not involve higher-level packaging (MFC, WPF, etc.). (There are actually various tricks to use MFC and WPF, but I don't recommend it, and if you want to do that, it might be better to use MSVC under Wine)

**Of course, since the original MinGW project doesn't support 64-bit, I'm referring to [MinGW-w64](https://www.mingw-w64.org) here (not the same project as the original MinGW).**

# Installation

Generally speaking, all major Linux distributions include MinGW-related packages in their official repositories, but if you distribution don't, or if you need something other than what is already in the official repositories, you can download the source code and compiled executables from the official website ~ **see https://www.mingw-w64.org/downloads/ for details**

I'm now using Fedora 35, I've followed the [official documentation](https://docs.fedoraproject.org/en-US/packaging-guidelines/MinGW/) as reference to install MinGW.  
**Unless the official documentation sucks, it is recommended to follow the official documentation.**

# Usage

**"MinGW doesn't produce toolchain, it's just a mover and shaker of GNU toolchain." **

In general use, it is the same as the GNU toolchain except for the different names of the commands. For example, to compile a 64-bit C program, just replace `gcc` with `x86_64-w64-mingw32-gcc`.  
In addition to the compiler, there are a number of other tools in MinGW for use with the compiler (the GNU build tools that come with Linux cannot be used with the MinGW compiler, or require additional configuration). **When configuring the IDE or text editor, be sure to replace the full set of tools with MinGW's!**  
As for the specific tools, I won't list them all here, **you can search for `mingw` in the `/usr/bin` directory after installation.**

**Header files, library files, and the other MinGW toolchain files can be found in the `/usr/x86_64-w64-mingw32` and `/usr/i686-w64-mingw32` directories.**

# Thoughts

Win32 development without MFC is too painful...