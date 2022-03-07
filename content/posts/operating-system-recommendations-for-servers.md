---
title: "操作系统推荐（服务器篇）"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2022-03-07T00:00:21-05:00
draft: false
tags: [操作系统, Windows, Linux, macOS, BSD]
categories: IT
---

# 虚拟机集群主机
## [Proxmox Virtual Environment](https://www.proxmox.com)
（+3）基于 Debian 的 Linux 发行版，质量高。  
（+2）开源免费。  
（-1）没有良好的技术支持服务。  
（-1）难以支撑大规模集群。  
总分：3  
评价：适合有一定技术但资金不足的初创团队使用。
## [VMware EXSi](https://www.vmware.com/products/esxi-and-esx.html)
（+3）VMware 出品，质量高。  
（-5）不开源不免费。  
（+3）有优秀的付费技术支持服务。  
（+2）支撑大规模集群毫无问题。  
总分：3  
评价：适合资金足够的团队使用。
## [OpenBSD](https://www.openbsd.org/)
（+3）最注重安全性的 BSD 发行版，质量高。  
（+2）开源免费。  
（+1）许可证宽松。  
（-2）没有技术支持服务。  
（-3）并非被设计用于虚拟机集群主机，虽然可以通过第三方软件实现。  
总分：1  
评价：适合技术水平高的团队或个人使用。
# 虚拟机集群客户机/物理机
## [Debian Stable](https://www.debian.org/)
（+3）老牌 Linux 发行版，以稳定著称，质量高。  
（+2）开源免费。  
（+1）保证了基本功能完备的情况下，系统资源占用较低。  
（-2）没有技术支持服务。  
总分：4  
评价：适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。
## [Slackware](http://www.slackware.com/)
（+3）老牌 Linux 发行版，以稳定著称，质量高。  
（+2）开源免费。  
（+1）保证了基本功能完备的情况下，系统资源占用较低。  
（-2）没有技术支持服务。  
（-1）官方的包管理器不够现代化，无法处理依赖关系。  
总分：3
评价：适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。
## [Red Hat Enterprise Linux](https://redhat.com/rhel/)
（+3）Red Hat 出品，质量高。  
（-4）开源但不免费。  
（+3）有优秀的付费技术支持服务。  
（+1）Linux 服务器的事实标准。  
总分：3  
评价：适合资金足够的企业使用。
## [Rocky Linux](https://rockylinux.org/)
（+3）RHEL 的一个克隆，质量高。  
（+2）开源免费。  
（-2）没有技术支持服务。  
（+1）Linux 服务器的事实标准。  
总分：4  
评价：适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。
## [Ubuntu Server](https://ubuntu.com/)
（-1）质量一般。  
（+2）开源免费。  
（+3）有优秀的付费技术支持服务。  
总分：4  
评价：适合有一定技术的个人或企业使用。
## [FreeBSD](https://www.freebsd.org/)
（+3）有 Linux 兼容层的 BSD 发行版，质量高。  
（+2）开源免费。  
（+1）许可证宽松。  
（-2）没有技术支持服务。  
总分：4  
评价：适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。
## [OpenBSD](https://www.openbsd.org/)
（+3）最注重安全性的 BSD 发行版，质量高。  
（+2）开源免费。  
（+1）许可证宽松。  
（-2）没有技术支持服务。  
总分：4  
评价：适合有一定技术的个人、资金不足或不愿耗资在服务器系统的企业使用。
## [Windows Server](http://microsoft.com/en-us/windows-server/)
（-3）BUG 多，质量差，安全性低。  
（-2）系统资源占用高。  
（-5）不开源不免费。  
（+5）有非常优秀的付费技术支持服务。  
（+2）对用户操作非常友好。  
总分：-3  
评价：除非有特殊需求（付费使用 Microsoft 的全套服务器相关软件、服务等）不要用。君不见 Microsoft Azure 上主要跑的都不是 Windows Server（Microsoft 自己都觉得烂XD）。
# 总结
有一个系统上榜了两次，OpenBSD。  
我觉得 BSD 系的系统几乎都是同类系统的佼佼者，开源的桌面系统有 FreeBSD，服务器系统有 OpenBSD，硬件兼容性高的有 NetBSD，成功的商业化桌面系统有 macOS，甚至游戏主机方面， PlayStation 也是基于 FreeBSD 的。  
**至于我为什么不用 FreeBSD，因为自己现在用的破电脑用 FreeBSD 无法联网（我试了很多系统，没问题的只有 Fedora 和 Ubuntu，明明原装系统是 Windows 7，装上了也无法联网。我可以肯定不是驱动问题。）。**