---
title: "Linux 发行版推荐"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2022-03-23T06:58:26-04:00
lastmod: 2022-03-24T07:37:25-04:00
draft: false
tags: [操作系统, Linux]
categories: IT
---

# 个人使用
## 面向 Linux 新手
**其实 Linux 桌面系统的易用和桌面环境也有很大的关系，我建议新手使用 GNOME/KDE。**
### [Debian Testing/Unstable](https://www.debian.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：DPKG/APT  
软件包格式：deb  
默认软件：全部开源  
官方软件仓库：开源/闭源分开存放  
维护者：Debian 社区  
个人评价：质量高、软件包多、开箱即用、资料丰富、精简可靠；上手难度较低。  
默认不带闭源固件，安装这些固件对新手而言有一定的门槛。  
Stable 源软件包太旧，一般用于服务器，个人使用建议换 Testing/Unstable 源（滚动更新）。
### [Fedora Workstation](https://getfedora.org/)
**个人推荐指数：3/5**  
是否稳定版：否  
官方包管理器：RPM/Yum/DNF  
软件包格式：rpm  
默认软件：全部开源  
官方软件仓库：开源/闭源分开存放  
维护者：Red Hat 公司  
个人评价：质量高、软件包多、开箱即用、资料丰富；上手难度低。  
相比 Debian 稍显臃肿。  
若要满足日常使用，需要配置第三方软件源，对新手而言有一定的门槛。
### [openSUSE Tumbleweed](https://www.opensuse.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：RPM/Zypper  
软件包格式：rpm  
默认软件：部分开源  
官方软件仓库：开源/闭源分开存放  
维护者：SUSE 公司  
个人评价：质量高、软件包多、开箱即用、资料丰富、配置方便（YaST 久负盛名）；上手难度低。  
有稳定版（openSUSE Leap），但个人使用建议用滚动版（稳定版软件包会比较旧）。
### [Manjaro](https://manjaro.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：Pacman/Pamac  
软件包格式：pkg.tar.xz/pkg.tar.zst  
默认软件：部分开源  
官方软件仓库：开源/闭源混合存放  
维护者：Manjaro 社区  
个人评价：质量高、软件包多、开箱即用、资料丰富；上手难度低。  
自带显卡驱动工具，对安装显卡驱动友好。  
和 [Arch Linux](https://archlinux.org/) 一脉相承，可能是软件包最多的 Linux 发行版，而且比 Arch Linux 稳定。
## 面向有一定经验的 Linux 用户
### [Parrot OS Security](https://www.parrotsec.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：DPKG/APT  
软件包格式：deb  
默认软件：部分开源  
官方软件仓库：开源/闭源分开存放  
维护者：Parrot OS 社区  
个人评价：质量高、软件包多、开箱即用、安全可靠；上手难度适中。  
基于 Debian Testing，和 [Kali Linux](https://www.kali.org/) 正好相反，是一个注重防御的渗透测试发行版。  
最注重安全性的 Linux 发行版之一。
### [Slackware Current](http://www.slackware.com/)
**个人推荐指数：3/5**  
是否稳定版：否  
官方包管理器：Slackpkg  
软件包格式：tgz/txz  
默认软件：部分开源  
官方软件仓库：开源/闭源混合存放  
维护者：Patrick Volkerding  
个人评价：质量高、软件包多、精简可靠；上手难度较高。  
官方的包管理器不够现代化，无法处理依赖关系（可以安装第三方包管理器）。  
现存最古老的 Linux 发行版，BSD 风格的 Linux 发行版，以稳定著称。  
个人使用建议换 Current 源（稳定版软件包会比较旧）。
### [Arch Linux](https://archlinux.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：Pacman  
软件包格式：pkg.tar.xz/pkg.tar.zst  
默认软件：全部开源  
官方软件仓库：开源/闭源混合存放  
维护者：Arch Linux 社区  
个人评价：质量高、软件包多、资料丰富、系统精简；上手难度较高。  
没有系统安装程序，需要纯手动安装，并且系统稳定性差。  
软件包数量远超 Debian 家族。  
[ArchWiki](https://wiki.archlinux.org/) 提供了非常丰富的高质量文档。
## 面向 Linux 老玩家
### [NixOS Unstable](https://nixos.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：Nix  
软件包格式：使用 Nix 语言进行管理，格式不定  
默认软件：全部开源  
官方软件仓库：开源/闭源混合存放  
维护者：NixOS 社区  
个人评价：质量高、软件包多、新潮可靠；上手难度非常高。  
没有系统安装程序，需要纯手动安装。  
采用 Nix 包管理器和 Nix 表达式语言，以相当具有颠覆性的方式管理整个系统，因此原生支持无需手动配置的系统备份、恢复和回滚。  
Nix 包管理器需要手动配置安装软件，同时支持二进制安装和源码安装，具有非常强的自定义性。  
软件包数量远超 Debian 家族。  
[NixOS Manual](https://nixos.org/manual/nixos/) 和 [NixOS Wiki](https://nixos.wiki/) 提供了非常丰富的高质量文档。  
个人使用建议换 Unstable 源（稳定版软件包会比较旧）。
### [Qubes OS](https://qubes-os.org/)
**个人推荐指数：3/5**  
是否稳定版：是  
官方包管理器：RPM/Yum  
软件包格式：rpm  
默认软件：全部开源  
官方软件仓库：只提供开源软件  
维护者：Invisible Things Lab  
个人评价：质量高、开箱即用、安全可靠；上手难度较高。  
用基于 Xen 的虚拟化技术来保障安全性，日常使用依赖于虚拟机系统（默认有 Debian、Fedora 和 Whonix）。  
默认的虚拟机系统软件包会比较旧，建议自己添加一些滚动更新系统供日常使用。  
最注重安全性的 Linux 发行版之一。
### [Gentoo Linux](https://www.gentoo.org/)
**个人推荐指数：3/5**  
是否稳定版：否  
官方包管理器：Portage  
软件包格式：使用 git 进行管理，格式不定（源码包）；xpak/gpkg（二进制包）  
默认软件：全部开源  
官方软件仓库：只提供开源软件  
维护者：Gentoo 基金会  
个人评价：质量高、软件包多、资料丰富、系统精简；上手难度非常高。  
没有系统安装程序，并且安装过程中所有程序都必须在本地编译。  
Portage 包管理器类似 BSD 的 Ports，主要的软件安装方式是下载源码然后在本地编译，也支持二进制安装。  
软件包数量远超 Debian 家族。  
[Gentoo Wiki](https://wiki.gentoo.org/) 提供了非常丰富的高质量文档。
# 用于服务器
## 免费系统
### [Debian Stable](https://www.debian.org/)
**个人推荐指数：4/5**  
是否稳定版：是  
官方包管理器：DPKG/APT  
软件包格式：deb  
默认软件：全部开源  
官方软件仓库：开源/闭源分开存放  
维护者：Debian 社区  
个人评价：质量高、软件包多、开箱即用、资料丰富、精简可靠；适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。  
老牌 Linux 发行版，以稳定和精简著称。
### [Rocky Linux](https://rockylinux.org/)
**个人推荐指数：4/5**  
是否稳定版：否  
官方包管理器：RPM/Yum/DNF  
软件包格式：rpm  
默认软件：全部开源  
官方软件仓库：开源/闭源分开存放  
维护者：Rocky Enterprise 软件基金会  
个人评价：质量高、软件包多、开箱即用、资料丰富；适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。  
是 RHEL 的克隆，RHEL 是 Linux 服务器的事实标准；没有官方的技术支持服务。
### [Slackware](http://www.slackware.com/)
**个人推荐指数：3/5**  
是否稳定版：否  
软件包格式：tgz/txz  
默认软件：部分开源  
官方软件仓库：开源/闭源混合存放  
维护者：Patrick Volkerding  
个人评价：质量高、软件包多、精简可靠；但官方的包管理机制不够现代化，无法处理依赖关系（可以安装第三方包管理器）；适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。  
现存最古老的 Linux 发行版，BSD 风格的 Linux 发行版，以稳定著称；没有官方的技术支持服务。
## 付费系统
### [Red Hat Enterprise Linux](https://redhat.com/rhel/)
**个人推荐指数：3/5**  
是否稳定版：否  
官方包管理器：RPM/Yum/DNF  
软件包格式：rpm  
默认软件：部分开源  
官方软件仓库：开源/闭源分开存放  
维护者：Red Hat 公司  
个人评价：质量高、软件包多、开箱即用、资料丰富；Linux 服务器的事实标准；适合资金足够的企业使用。  
开源但不免费；有优秀的官方的付费技术支持服务。
# 感想
我不会再推荐任何 Ubuntu 家族的系统了。事实证明，它们坑都很多。