---
title: "Xlib 编程注意事项 1"
description: "本文仅代表个人观点，欢迎留言讨论"
date: 2022-02-20T11:02:21-05:00
lastmod: 2022-02-20T11-25-31-05:00
draft: false
tags: [C/C++, Linux, X11]
categories: IT
---

- 谨慎使用 `XGrabPointer`，使用前一定要做好强制退出程序的准备（今天我被坑到了，还不止一次QAQ）