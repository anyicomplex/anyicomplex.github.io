---
title: "Xlib编程注意事项 1"
date: 2022-02-20T11:02:21-05:00
draft: false
tags: [C/C++, Linux, X11]
categories: IT
---

- 谨慎使用XGrabPointer，使用前一定要做好强制退出程序的准备（今天我被坑到了，还不止一次QAQ）