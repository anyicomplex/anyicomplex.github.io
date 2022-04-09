---
title: "Reasons to Use Linux"
description: "This article represents only my personal view, welcome to leave a message to discuss"
date: 2021-12-08T08:17:44-05:00
lastmod: 2022-03-01T19:12:02-05:00
draft: false
tags: [Operating System, Linux]
categories: IT
---

# 1. Lightweight

(x86_64 operating system for example, for daily use; so the distributions focused on lightweight that streamlining too many features are excluded)  
| Operating system | Minimum CPU requirements | Minimum memory requirements | Minimum storage requirements |
|-------------------|-------------|------------|------------|
| Windows 11 | 1 GHz * 2 | 4 GB | 64 GB |
| Windows 10 | 1 GHz | 2 GB | 20 GB |
| Windows 7 | 1 GHz | 2 GB | 20 GB |
| Fedora 35 (GNOME) | 2 GHz | 2 GB | 15 GB |
| Debian 11 (GNOME) | 1 GHz | 1 GB | 10 GB |

**All referenced data come from the system's official website**

Windows 11: https://support.microsoft.com/en-us/windows/windows-11-system-requirements-86c11283-ea52-4782-9efd-7674389a7ba3  
Windows 10: https://support.microsoft.com/en-us/windows/windows-10-system-requirements-6d4e9a79-66bf-7950-467c-795cf0386715  
Windows 7: https://support.microsoft.com/en-us/windows/windows-7-system-requirements-df0900f2-3513-a851-13e7-0d50bc24e15f  
Fedora 35: https://docs.fedoraproject.org/en-US/fedora/f35/release-notes/welcome/Hardware_Overview/  
Debian 11: https://www.debian.org/releases/stable/amd64/ch03s04.en.html

**The data for Windows 10 is for an earlier version (I couldn't find official data for the latest version), and the minimum hardware requirements for the latest version should be comparable to the current Windows 11.**

GNOME is recognized as the most resource-intensive Linux desktop environment, and Fedora is one of the most bloated Linux distributions.  
However, the combination of the two is no worse than Windows 7, except for the fact that the minimum CPU requirements are higher.  
The lighter Debian 11 and GNOME combinations have lower minimum hardware requirements than Windows 7.  
If you switch to a lightweight desktop environment, XFCE or LXDE, this requirement will be much lower.  
However, Windows can't switch desktop environments...

## 2. Security

## 1. File system

All POSIX operating systems' file systems (ext series for Linux, ZFS for Solaris, etc.) have strict file permission restrictions, and only files marked as "executable" can be run.  
Unlike Windows, which defines "executable" files only by their extensions.
There are also historical reasons for this.  
* Windows' predecessor DOS and early Windows used the FAT32 file system, which was very rudimentary, neither support logging, nor support file permissions at all.
* With the introduction of the Windows NT 3.1 kernel, NTFS replaced FAT32 as the default file system for Windows, this time, it finally supporting file permissions, however its default file permission includes "executable".

**The default file permission can be changed through the Access Control List (ACL), but how many Windows users will use this feature? Most people don't even know that Windows has this feature... **

## 2. Operating system

* Linux is open source, with a large number of developers involved, system vulnerabilities can be quickly found and fixed, and do not have to worry about the official implantation of backdoors (of course, some distributions will do this, such as Ubuntu, so you have to be careful when choosing a distribution ~ ).  
* Windows is completely closed source, and the development environment is very closed, which is not only not conducive to the discovery and repair of system vulnerabilities, but also Microsoft itself is stealing users' privacy informations through official backdoors (it has been an open secret for a long time ~ ).
* macOS only kernel open source, the complete operating system is closed source, the conclusion is the same as Windows.

## 3. Software

### Windows

* There are no unified software sources, you need to find them yourself, but the ones you find are not always reliable - for example, many download sites tamper with the installation package and inject viruses.
* If you take explicit transfer protocols (HTTP, FTP, etc.), you are likely to encounter man-in-the-middle attacks - software is tampered with on the way to download, injecting viruses, however not all software sources provide checksums...
* Not all software has an "auto-update" function, so you have to repeat the same operation of downloading manually and face the same danger again.
* Windows is a world of proprietary software, so many of them have backdoors embedded by the developer.

### Linux

* When installing software on Linux distributions, most of the time you install it from the official repository of the distribution, but in a few cases you download the source code and compile it yourself or install third-party packages.  
* Most distributions maintain repositories that guarantee reliable sources, and most package managers have their own validation mechanisms.  
* Package managers can "auto-update" regardless of whether the software supports "auto-update" or not.  
* Most of the software under Linux is open source, so if you have high security requirements, you can use Linux without any closed-source softwares.

### macOS

* The first three for Linux and the last one for Windows.

# 3. Highly customizable

**Windows and macOS are in no way comparable to Linux in terms of customizability.**  

## Graphical interface

### Windows

* The graphical interface is part of the kernel and cannot be modified.
* Microsoft don't open enough APIs of Windows and beautification plugins are very limited in effects.

### macOS

* The graphical interface is part of its software ecosystem, and switching to something else would result in a lot of software not working.

### Linux
* Desktop Environment, Window Manager, and Display Server are all replaceable.  
For example, you can use X Server as display server, or Wayland; you can use IceWM, JWM, i3WM, Awesome... as window manager; you can use GNOME, KDE, XFCE or LXDE... as desktop environment.
* Not to mention the large amount of theme plugins, beautification plugins, you can decorate Linux like macOS, or change it to look like Windows, of course, more of them provides a self-contained distinctive style ~

## System modification

**Sometimes there is a requirement to delete certain features of the system that you won't use.**

### Windows

* The kernel is not open source and is almost impossible to modify.
* It is an interlocking whole structure that is difficult to streamline, and streamlining is generally difficult to ensure security.

### macOS

* Although the kernel is open source, the upper-layer architecture is not, making it extremely difficult to modify.
* Same difficulty in streamlining as above.

### Linux

* The vast majority of Linux distributions are friendly to modifying and compiling the kernel yourself.
* Fully open source and fully modular, so it is easy to streamline, and Tiny Core Linux has even accomplished the feat of building an operating system with a graphical interface that is only 12MB.

# 4. Software ecosystem

**This paragraph is mainly for BSDs other than macOS.**

* As one of the three desktop operating systems, more and more software ported to Linux, and the Linux platform itself also has accumulated years of software. The Linux software ecosystem is becoming more and more mature (for example, GIMP vs. PhotoShop, Many open source software can perfectly replace similar commercial software).
* BSDs (except macOS), because of the extreme lack of software, daily use will generally have problems (except for those with Linux compatibility layer).