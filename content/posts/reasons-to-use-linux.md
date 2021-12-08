---
title: "使用Linux的理由"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2021-12-08T08:17:44-05:00
draft: false
tags: [操作系统, Linux]
categories: IT
---

***本文仅代表个人观点，欢迎留言讨论。***  

# 1.轻量级
（以x86_64操作系统为例，针对日常使用，因此注重轻量级精简太多功能的发行版不算在内）  
| 操作系统           | 最低CPU需求 | 最低内存需求 | 最低储存需求 |
|-------------------|-----------|------------|------------|
| Windows 11        | 1 GHz * 2 | 4 GB       | 64 GB      |
| Windows 10        | 1 GHz     | 2 GB       | 20 GB      |
| Windows 7         | 1 GHz     | 2 GB       | 20 GB      |
| Fedora 35 (GNOME) | 2 GHz     | 2 GB       | 15 GB      |
| Debian 11 (GNOME) | 1 GHz     | 1 GB       | 10 GB      |

**数据均来自官网**

Windows 11: https://support.microsoft.com/en-us/windows/windows-11-system-requirements-86c11283-ea52-4782-9efd-7674389a7ba3  
Windows 10: https://support.microsoft.com/en-us/windows/windows-10-system-requirements-6d4e9a79-66bf-7950-467c-795cf0386715  
Windows 7: https://support.microsoft.com/en-us/windows/windows-7-system-requirements-df0900f2-3513-a851-13e7-0d50bc24e15f  
Fedora 35: https://docs.fedoraproject.org/en-US/fedora/f35/release-notes/welcome/Hardware_Overview/  
Debian 11: https://www.debian.org/releases/stable/amd64/ch03s04.en.html  
antiX 21: https://antixlinuxfan.miraheze.org/wiki/How_to_install#System_requirements

**Windows 10的数据为早期版本（最新版的官方数据我没找到），最新版的最低硬件需求应和当前的Windows 11相当。**

GNOME是公认的占用资源最多的Linux桌面环境，而Fedora也是最为臃肿的Linux发行版之一。  
然而二者的组合除了CPU需求高于Windows 7外，其他都不逊色。  
而较为轻量的Debian 11和GNOME组合的硬件需求远低于Windows 7。  
如果换用轻量级桌面Xfce或LXDE，想必这一需求会低得多。  
然而Windows可换不了桌面......

# 2.安全
## 1.文件系统

所有POSIX操作系统的文件系统（Linux的ext系列、Solaris的ZFS等）都有严格的文件权限限制，只有被标记为“可执行”的文件才能运行。  
而Windows不同，其对“可执行”文件的界定仅仅按扩展名来划分。
这也是有历史原因的：  
* Windows的前身DOS和早期Windows使用FAT32文件系统，这个文件系统很简陋，不但不支持日志，而且完全不支持文件权限。
* 随着Windows NT 3.1内核的推出，NTFS取代FAT32成为了Windows的默认文件系统，这次总算支持文件权限了，然而其默认文件可执行。

**通过Access Control List（ACL）倒是可以修改默认文件权限，但这个功能又有多少Windows用户会去用呢？甚至大多数人都不知道Windows还有这个功能吧......**

## 2.操作系统

* Linux开源，在大量开发者的参与下，系统漏洞能够迅速被发现和得到修复，也不必担心被植入后门（当然，某些发行版会这么做，例如Ubuntu，所以各位选择发行版的时候要擦亮眼睛啊～）。  
* Windows完全闭源，开发环境十分封闭，不仅不利于系统漏洞的发现和修复，而且微软本身就在通过Windows窃取用户的隐私（早就是公开的秘密了～）。
* Mac OS X只有内核开源，完整的操作系统是闭源的，结论同Windows。

## 3.软件

### Windows

* 没有统一的软件源，需要自行寻找，但找到的软件源不一定可靠——例如很多下载站都会篡改安装包，注入病毒。
* 如果采取明文传输协议（HTTP、FTP等），很可能遭遇中间人攻击——软件在下载途中被篡改，注入病毒，然而不是所有软件源都会提供校验码的......
* 不是所有软件都有“自动更新”功能，手动更新又要重复一遍之前下载的操作，重新面对一次相同的危险。
* Windows是专有软件的天下，因此很多软件本身就是植入了后门的～

### Linux

* 在Linux发行版安装软件，多数时候都是通过GUI/CLI从发行版官方仓库安装，少数时候自己下载源码编译或安装第三方软件包。  
* 绝大多数发行版维护的软件仓库都能够保证软件来源可靠，且绝大多数包管理器都自带校验机制。  
* 无论软件是否支持“自动更新”，包管理器都能“自动更新”。  
* Linux下绝大多数软件都是开源的，如果你对安全性有较高的要求，在Linux下完全可以不使用任何闭源软件。

### Mac OS X

* Linux的前三条和Windows的最后一条。

# 3.可定制性高

**Linux的可定制性绝不是Windows和Mac OS X能比拟的。**  

## 图形界面

### Windows

* 图形界面是内核的一部分，无法修改。
* 微软对API开放程度不够，美化插件作用有限。

### Mac OS X

* 图形界面是其软件生态的一部分，换成其他的会导致大量软件无法运行。

### Linux
* 桌面环境（Desktop Environment）、窗口管理器（Window Manager）、显示服务器（Display Server）都是可以更换的。  
例如：可以用X Server作为显示服务器，也可以用Wayland；窗口管理器可以用IceWM、JWM，也可以用i3WM、Awesome；桌面环境可以用简洁的GNOME、华丽的KDE，也可以用轻量级的Xfce、LXDE......
* 更何况还有大量的主题插件、美化插件，可以把Linux装点的像Mac OS X，也可以改成Windows的样子，当然，更多的是自成一派的风格～

## 系统修改

**有时会有删去系统中某些用不上功能的需求。**

### Windows
* 内核不开源，几乎无法修改。
* 是一个环环相扣的整体结构，难以精简，且精简一般难以保证安全性。

### Mac OS X
* 虽然内核开源，但上层架构不开源，因此修改难度极高。
* 精简难度同上。

### Linux
* 绝大多数Linux发行版对自行修改和编译内核都是友好的。
* 完全开源且充分模块化，因此精简起来十分容易，Tiny Core Linux甚至完成了构建只有12MB的带有图形界面的操作系统的壮举。

# 4.生态完善

**此条主要针对Mac OS X以外的BSD。**

* 作为三大桌面操作系统之一，越来越多的软件适配了Linux版本，而且Linux平台下本身多年积累的软件生态也越发成熟（例如GIMP之于PhotoShop，Linux生态的很多开源软件能够完美替代同类的商业软件）。
* Mac OS X以外的BSD因为极度缺乏软件，日常使用一般会有问题（有Linux兼容层的除外）。