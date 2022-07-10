---
title: "关于我所知道的Android刷机方案"
date: 2022-07-10T22:59:48+08:00
draft: false
categories:
- 刷机
tags:
- 刷机
- 折腾
- Android
---





## 背景

​	很久以前做过的操作了；这边就是简单的记录一下

> 这几天沉迷刷机 索尼xp 小米8lite 小米平板1 
>
> 索尼xp刷得很顺利 一步到位。
>
> 小米8lite 也很顺利刷成pixel的系统 是真的好用。下一步手机就决定pixel了。（最近的一次刷机已经刷挂掉了，暂时也没时间修复 。2020.7.10）
>
> 然后小米平板1 出了点问题 。我猜测是rom有问题。

感谢这个网站[^1]的大佬们。

## 过程

1. 充满电
2. 解bl
3. 刷twrp
4. 刷rom 双清  四清

## 问题

> 1 需要注意twrp 是否是可用的

## 常用指令

> fastboot flash recovery twrp.img
>
> fastboot oem reboot-recovery
>
> adb sideload Magisk.zip

## 感受

> xda刷各种rom是真的快乐。
>
> 自己好菜啊。
>
> 然后有一种 前人栽树后人乘凉的感觉。要是自己一点点摸索都不知道刷多少砖才能整好一个rom。
>
> 自己遇到的问题基本上都会有人遇到过，真是奇妙的感觉。



[^1]:[XDA Forums (xda-developers.com)](https://forum.xda-developers.com/)