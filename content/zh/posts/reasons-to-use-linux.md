---
title: "使用 Linux 的理由"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2021-12-08T08:17:44-05:00
lastmod: 2022-03-01T19:12:02-05:00
draft: false
tags: [操作系统, Linux]
categories: IT
---

# 1.轻量级

（以 x86_64 操作系统为例，针对日常使用，因此注重轻量级精简太多功能的发行版不算在内）  
| 操作系统           | 最低 CPU 需求 | 最低内存需求 | 最低储存需求 |
|-------------------|-------------|------------|------------|
| Windows 11        | 1 GHz * 2   | 4 GB       | 64 GB      |
| Windows 10        | 1 GHz       | 2 GB       | 20 GB      |
| Windows 7         | 1 GHz       | 2 GB       | 20 GB      |
| Fedora 35 (GNOME) | 2 GHz       | 2 GB       | 15 GB      |
| Debian 11 (GNOME) | 1 GHz       | 1 GB       | 10 GB      |

**数据均来自官网**

Windows 11: https://support.microsoft.com/en-us/windows/windows-11-system-requirements-86c11283-ea52-4782-9efd-7674389a7ba3  
Windows 10: https://support.microsoft.com/en-us/windows/windows-10-system-requirements-6d4e9a79-66bf-7950-467c-795cf0386715  
Windows 7: https://support.microsoft.com/en-us/windows/windows-7-system-requirements-df0900f2-3513-a851-13e7-0d50bc24e15f  
Fedora 35: https://docs.fedoraproject.org/en-US/fedora/f35/release-notes/welcome/Hardware_Overview/  
Debian 11: https://www.debian.org/releases/stable/amd64/ch03s04.en.html

**Windows 10 的数据为早期版本（最新版的官方数据我没找到），最新版的最低硬件需求应和当前的 Windows 11 相当。**

GNOME 是公认的占用资源最多的 Linux 桌面环境，而 Fedora 也是最为臃肿的 Linux 发行版之一。  
然而二者的组合除了最低 CPU 需求高于 Windows 7 外，其他都不逊色。  
而较为轻量的 Debian 11 和 GNOME 组合的最低硬件需求低于 Windows 7。  
如果换用轻量级桌面 XFCE 或 LXDE，想必这一需求会低得多。  
然而 Windows 可换不了桌面......

# 2.安全

## 1.文件系统

所有 POSIX 操作系统的文件系统（Linux 的 ext 系列、Solaris 的 ZFS 等）都有严格的文件权限限制，只有被标记为“可执行”的文件才能运行。  
而 Windows 不同，其对“可执行”文件的界定仅仅按扩展名来划分。
这也是有历史原因的：  
* Windows 的前身 DOS 和早期 Windows 使用 FAT32 文件系统，这个文件系统很简陋，不但不支持日志，而且完全不支持文件权限。
* 随着 Windows NT 3.1 内核的推出，NTFS 取代 FAT32 成为了 Windows 的默认文件系统，这次总算支持文件权限了，然而其默认文件可执行。

**通过 Access Control List（ACL）倒是可以修改默认文件权限，但这个功能又有多少 Windows 用户会去用呢？甚至大多数人都不知道 Windows 还有这个功能吧......**

## 2.操作系统

* Linux 开源，在大量开发者的参与下，系统漏洞能够迅速被发现和得到修复，也不必担心被官方植入后门（当然，某些发行版会这么做，例如 Ubuntu，所以各位选择发行版的时候要擦亮眼睛啊～）。  
* Windows 完全闭源，开发环境十分封闭，不仅不利于系统漏洞的发现和修复，而且微软本身就在通过官方植入的后门窃取用户的隐私（早就是公开的秘密了～）。
* macOS 只有内核开源，完整的操作系统是闭源的，结论同 Windows。

## 3.软件

### Windows

* 没有统一的软件源，需要自行寻找，但找到的软件源不一定可靠——例如很多下载站都会篡改安装包，注入病毒。
* 如果采取明文传输协议（HTTP、FTP等），很可能遭遇中间人攻击——软件在下载途中被篡改，注入病毒，然而不是所有软件源都会提供校验码的......
* 不是所有软件都有“自动更新”功能，手动更新又要重复一遍之前下载的操作，重新面对一次相同的危险。
* Windows 是专有软件的天下，因此很多软件本身就是植入了后门的～

### Linux

* 在 Linux 发行版安装软件，多数时候都是从发行版官方仓库安装，少数时候自己下载源码编译或安装第三方软件包。  
* 绝大多数发行版维护的软件仓库都能够保证软件来源可靠，且绝大多数包管理器都自带校验机制。  
* 无论软件是否支持“自动更新”，包管理器都能“自动更新”。  
* Linux 下绝大多数软件都是开源的，如果你对安全性有较高的要求，在 Linux 下完全可以不使用任何闭源软件。

### macOS

* Linux 的前三条 和Windows 的最后一条。

# 3.可定制性高

**Linux 的可定制性绝不是 Windows 和 macOS 能比拟的。**  

## 图形界面

### Windows

* 图形界面是内核的一部分，无法修改。
* 微软对API开放程度不够，美化插件作用有限。

### macOS

* 图形界面是其软件生态的一部分，换成其他的会导致大量软件无法运行。

### Linux

* 桌面环境（Desktop Environment）、窗口管理器（Window Manager）、显示服务器（Display Server）都是可以更换的。  
例如：可以用 X Server 作为显示服务器，也可以用 Wayland；窗口管理器可以用 IceWM、JWM，也可以用 i3WM、Awesome；桌面环境可以用简洁的 GNOME、华丽的 KDE，也可以用轻量级的 XFCE、LXDE......
* 更何况还有大量的主题插件、美化插件，可以把 Linux 装点的像 macOS ，也可以改成 Windows 的样子，当然，更多的是自成一派的风格～

## 系统修改

**有时会有删去系统中某些用不上功能的需求。**

### Windows

* 内核不开源，几乎无法修改。
* 是一个环环相扣的整体结构，难以精简，且精简一般难以保证安全性。

### macOS

* 虽然内核开源，但上层架构不开源，因此修改难度极高。
* 精简难度同上。

### Linux

* 绝大多数 Linux 发行版对自行修改和编译内核都是友好的。
* 完全开源且充分模块化，因此精简起来十分容易，Tiny Core Linux 甚至完成了构建只有 12MB 的带有图形界面的操作系统的壮举。

# 4.生态完善

**此条主要针对 macOS 以外的 BSD。**

* 作为三大桌面操作系统之一，越来越多的软件适配了 Linux 版本，而且 Linux 平台下本身多年积累的软件生态也越发成熟（例如 GIMP 之于 PhotoShop，Linux 生态的很多开源软件能够完美替代同类的商业软件）。
* macOS 以外的 BSD 因为极度缺乏软件，日常使用一般会有问题（有 Linux 兼容层的除外）。