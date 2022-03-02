---
title: "在 Linux 下编写和编译 win32 程序"
description: "我的一次踩坑记录"
date: 2022-02-28T14:24:36-05:00
draft: false
tags: [C/C++, Windows, win32, Linux]
categories: IT
---

**本文所说的 win32 是中国大陆程序员圈子对 winapi 的俗称，不是特指32位 winapi（别说64位了，自从32位 winapi 出现，对早期16位的 winapi 我们也这么叫）。**
# 可行性
得益于 MinGW（Minimalist GNU for Windows）这个项目，只要不涉及到比较高层次的封装（MFC、WPF等），是完全可行的。（实际上也有各种奇技淫巧使用 MFC 和 WPF，但我不建议那么做，如果真要那么做，在 Wine 下使用 MSVC 也许会更好一点）

**当然，因为原 MinGW 项目不支持64位，我这里说的 MinGW 都是指 [MinGW-w64](https://www.mingw-w64.org)（和原 MinGW 不是同一个项目）。**
# 安装
一般而言，主流 Linux 发行版的软件源都会包含 MinGW 相关的软件包，当然，如果没有，或者需要官方源已有软件包以外的功能，也可以自己去官网下载源码和编译好的可执行文件什么的～**详情请参阅  https://www.mingw-w64.org/downloads/**

我现在使用的操作系统是 Fedora 35，是参考这篇[官方文档](https://docs.fedoraproject.org/en-US/packaging-guidelines/MinGW/)装的。  
**除非官方文档太烂，否则还是建议跟着官方文档来。**
# 使用
**“MinGW 不生产工具链，只是 GNU 工具链的搬运工。”**

除了命令的名称不同以外，其他都和 GNU 工具链一样，举个例子，编译64位 C 语言程序，把 `gcc` 换成 `x86_64-w64-mingw32-gcc` 即可。  
除编译器以外，MinGW 里还有不少其他的工具，用于和编译器配套使用（Linux 原装的 GNU 构建工具无法和 MinGW 编译器配套使用，或者需要额外配置）。**配置 IDE 或文本编辑器的时候，一定要把全套工具都换成 MinGW 的！**  
至于具体有哪些工具，我这里就不一一列举了，**安装好后可以在 `/usr/bin` 目录下搜索 `mingw`**。

**头文件和库文件等可以在 `/usr/x86_64-w64-mingw32` 和 `/usr/i686-w64-mingw32` 目录下找到。**

# 感想
不使用 MFC 的 win32 开发太痛苦了......