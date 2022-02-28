---
title: "在Linux下编写和编译win32程序"
description: "我的一次踩坑记录"
date: 2022-02-28T14:24:36-05:00
draft: false
tags: [C/C++, Windows, win32, Linux]
categories: IT
---

**本文所说的“win32”是中国大陆程序员圈子对“winapi”的俗称，不是特指32位“winapi”（别说64位了，自从32位winapi出现，对早期16位的winapi我们也这么叫）。**
## 可行性
得益于MinGW（Minimalist GNU for Windows）这个项目，只要不涉及到比较高层次的封装（MFC、WPF等），是完全可行的。（实际上也有各种奇技淫巧使用MFC和WPF，但我不建议那么做，如果真要那么做，在Wine下使用MSVC也许会更好一点）

**当然，因为原MinGW项目不支持64位，我这里说的MinGW都是指[MinGW-w64](https://www.mingw-w64.org)（和原MinGW不是同一个项目）。**
## 安装
一般而言，主流Linux发行版的软件源都会包含MinGW相关的软件包，当然，如果没有，或者需要官方源已有软件包以外的功能，也可以自己去官网下载源码和编译好的可执行文件什么的～**详情请参阅 https://www.mingw-w64.org/downloads/**

我现在使用的操作系统是Fedora 35，是参考这篇[官方文档](https://docs.fedoraproject.org/en-US/packaging-guidelines/MinGW/)装的。  
**除非官方文档太烂，否则还是建议跟着官方文档来。**
## 使用
**“MinGW不生产工具链，只是GNU工具链的搬运工。”**

除了命令的名称不同以外，其他都和GNU工具链一样，举个例子，编译64位C语言程序，把“gcc”换成“x86_64-w64-mingw32-gcc”即可。  
除编译器以外，MinGW里还有不少其他的工具，用于和编译器配套使用（Linux原装的GNU构建工具无法和MinGW编译器配套使用，或者需要额外配置）。**配置IDE或文本编辑器的时候，一定要把全套工具都换成MinGW的！**  
至于具体有哪些工具，我这里就不一一列举了，**安装好后可以在“/usr/bin”目录下搜索“mingw”**。

**头文件和库文件等可以在“/usr/x86_64-w64-mingw32”和“/usr/i686-w64-mingw32”目录下找到。**

## 总结
不使用MFC的win32开发太痛苦了......