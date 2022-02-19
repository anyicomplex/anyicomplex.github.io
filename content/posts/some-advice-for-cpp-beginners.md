---
title: "给C++初学者的一些建议"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2022-02-19T09:33:19-05:00
draft: false
tags: [C/C++]
categories: IT
---

### 基础
* 在学C++之前先学C语言，掌握堆栈等基本概念，并能够熟练使用指针和宏。
* 新版本的特性先不要学，哪怕只是用于学习而非生产，也建议只使用长期支持的稳定版本。
### 应用
* 先别急着深入学习模板等C++高级特性，对新手而言，把C++当作“带类的C”是最稳妥的使用方法。
* STL里有的东西就不要去找第三方库了（除非这个库真的比STL的那部分好并且长期有人维护）。
* Boost可以用，但也仅仅只是可以用，因为坑太多。对新手而言，很多时候难以分辨是自己写的程序的问题还是编译器或Boost的问题（STL就好得多，毕竟Boost是STL的上游）。
### 编译器
* Windows下不建议使用MSVC以外的编译器，否则坑很多。
* Linux下Clang和GCC均可，但我一般建议使用GCC。
* macOS下建议Clang。
### IDE
**VSCode不是IDE，是文本编辑器，所以不在这个推荐列表内（当然，我推荐它，因为我没钱买IDEA Ultimate却需要写JNI，它帮了大忙:D）。**
* Qt开发者可以直接用Qt的工具链。
* Eclipse和Code::Blocks老用户可以继续用，这两个IDE不是不好，是难以上手，当然对老用户而言没什么问题。
* Windows下建议Visual Studio和MSVC配合使用，如果用惯了JetBrains系的IDE也可以用CLion，其他不推荐。
* Linux下，建议CLion，KDE桌面也可以使用KDevelop，但其他桌面不建议（因为KDevelop的依赖会带一大堆KDE的软件包，这也是KDE应用的通病，耦合度太高），GNOME桌面也可以使用GNOME Builder（这个其他桌面用也没什么问题），其他不推荐。
* macOS下建议XCode，觉得不好用就换AppCode/CLion，其他没有更好的了。