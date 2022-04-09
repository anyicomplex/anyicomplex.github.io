---
title: "Some advice for C++ beginners"
description: "This article represents only a personal view, welcome to leave a message to discuss"
date: 2022-02-19T09:33:19-05:00
draft: false
tags: [C++]
categories: IT
---

# Fundamentals

* Learn C first before learning C++, master basic concepts such as stacks and piles, be comfortable with pointers and macros.
* Latest C++ features should not be learned yet, even if only for learning and not production, it is also recommended to use only long-term supported stable versions.

* Applications

* Don't rush into advanced C++ features such as templates yet.
* Don't look for a third-party library if it's the same feature available in the STL (unless it's really better than that part of the STL and has been maintained for a long time).
* Boost can be used, but only just, because there are too many pitfalls. For newbies, it's often hard to know if it's a bug with your own program or with the compiler or Boost (STL is much better, after all, Boost is upstream of STL).

# Compilers

* Under Windows, compilers other than MSVC are not recommended, otherwise there are many pitfalls.
* Clang/LLVM and GCC are both fine for Linux, but I generally recommend GCC.
* Clang/LLVM is recommended for macOS.

# IDE

**VSCode is not an IDE, it's a text editor, so it's not in this recommendation list (of course, I recommend it because I can't afford to buy IDEA Ultimate but need to write JNI, and it helps a lot :D).**
* Qt developers can use Qt's toolchain directly.
* Old users of Eclipse and Code::Blocks can continue to use, these two IDEs are not bad, both of them just difficult to get started, but of course there is nothing problem for old users.
* Visual Studio and MSVC are recommended for Windows users, or CLion if you are used to the JetBrains IDE; not recommended for other IDEs.
* Under Linux, CLion is recommended, KDE desktop can also use KDevelop, but other desktops are not recommended (because KDevelop's dependencies will bring a large number of KDE packages, which is also the common problem of KDE applications, too much coupling), GNOME desktop can also use GNOME Builder (this is no problem for other desktops), other IDEs are not recommended.
* XCode is recommended for macOS users, if you don't think it's good for use, you can switch to AppCode or CLion, nothing else is better.