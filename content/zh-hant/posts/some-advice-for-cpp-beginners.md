---
title: "给 C++ 初学者的一些建议"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2022-02-19T09:33:19-05:00
draft: false
tags: [C/C++]
categories: IT
---

# 基础
* 在学 C++ 之前先学 C 语言，掌握堆栈等基本概念，并能够熟练使用指针和宏。
* 新版本的特性先不要学，哪怕只是用于学习而非生产，也建议只使用长期支持的稳定版本。
# 应用
* 先别急着深入学习模板等 C++ 高级特性，对新手而言，把 C++ 当作“带类的 C”是最稳妥的使用方法。
* STL 里有的东西就不要去找第三方库了（除非这个库真的比 STL 的那部分好并且长期有人维护）。
* Boost 可以用，但也仅仅只是可以用，因为坑太多。对新手而言，很多时候难以分辨是自己写的程序的问题还是编译器或 Boost 的问题（STL 就好得多，毕竟 Boost 是 STL 的上游）。
# 编译器
* Windows 下不建议使用 MSVC 以外的编译器，否则坑很多。
* Linux 下 Clang 和 GCC 均可，但我一般建议使用 GCC。
* macOS 下建议 Clang。
# IDE
**VSCode 不是 IDE，是文本编辑器，所以不在这个推荐列表内（当然，我推荐它，因为我没钱买 IDEA Ultimate 却需要写 JNI，它帮了大忙:D）。**
* Qt 开发者可以直接用 Qt 的工具链。
* Eclipse 和 Code::Blocks 老用户可以继续用，这两个 IDE 不是不好，是难以上手，当然对老用户而言没什么问题。
* Windows 下建议 Visual Studio 和 MSVC 配合使用，如果用惯了 JetBrains 系的 IDE 也可以用 CLion，其他不推荐。
* Linux 下，建议 CLion，KDE 桌面也可以使用 KDevelop，但其他桌面不建议（因为 KDevelop 的依赖会带一大堆 KDE 的软件包，这也是 KDE 应用的通病，耦合度太高），GNOME 桌面也可以使用 GNOME Builder（这个其他桌面用也没什么问题），其他不推荐。
* macOS 下建议 XCode，如果觉得不好用，就换 AppCode/CLion，其他没有更好的了。