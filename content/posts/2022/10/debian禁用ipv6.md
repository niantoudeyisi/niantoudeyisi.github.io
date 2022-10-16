---
title: "Debian禁用ipv6"
date: 2022-10-16T20:44:28+08:00
draft: false
categories:
- Linux
tags:
- Linux
- Debian
---





vps下载github 的脚本不知道怎么下载不下来。禁用ipv6就好了原因未知。似乎是vps没ipv6导致

网上的方案。现在是我的了  XD



```
临时禁用
echo "1" > /proc/sys/net/ipv6/conf/all/disable_ipv6 临时禁用所有接口的ipv6
echo "1" > /proc/sys/net/ipv6/conf/eth0/disable_ipv6 临时禁用eth0接口的ipv6



nano /etc/sysctl.conf

net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
net.ipv6.conf.lo.disable_ipv6 = 1
然后sysctl -p
看文档说sysctl命令是 内核运行时动态的修改内核的运行参数
```





---



出处 https://www.cnblogs.com/weihua2020/p/14083798.html



