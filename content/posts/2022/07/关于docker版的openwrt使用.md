---
title: "关于docker版的openwrt使用"
date: 2022-07-10T22:48:26+08:00
draft: false
categories:
- Docker
tags:
- Docker
- OpenWrt
---



## 起因

​	以前玩树莓派的时候发现的openwrt-Rpi项目，然后看到了大佬[^1]配置，基于docker的openwrt旁路由的教程

​	我这边简单归纳一下，便于自己日后使用；

1. 打开网卡混杂模式
2. 创建网络
3. 拉镜像
4. 运行
5. 修改网络
6. 关openwrt的DHCP(如果需求是 指定设备走特定网关 就选择关掉)

```
sudo ip link set eth0 promisc on
#######---

docker network create -d macvlan --subnet=192.168.123.0/24 --gateway=192.168.123.1 -o parent=eth0 macnet
docker network ls
########---

docker pull sulinggg/openwrt:latest
##############---

docker run --restart always --name openwrt -d --network macnet --privileged registry.cn-shanghai.aliyuncs.com/suling/openwrt:latest /sbin/init


# --restart always参数表示容器退出时始终重启，使服务尽量保持始终可用；

#--name openwrt参数定义了容器的名称；

# -d参数定义使容器运行在 Daemon 模式；

# --network macnet参数定义将容器加入 maxnet网络；

# --privileged 参数定义容器运行在特权模式下；

# registry.cn-shanghai.aliyuncs.com/suling/openwrt:latest为 Docker 镜像名

# /sbin/init定义容器启动后执行的命令。

#########---

docker exec -it openwrt bash

vim /etc/config/network

config interface 'lan'
        option type 'bridge'
        option ifname 'eth0'
        option proto 'static'
        option ipaddr '192.168.2.100'
        option netmask '255.255.255.0'
        option ip6assign '60'
        option gateway '192.168.2.1'
        option broadcast '192.168.2.255'
        option dns '192.168.2.1'
        
        
/etc/init.d/network restart

###---

```







[^1]:[在Docker 中运行 OpenWrt 旁路网关 | 美丽应用 (mlapp.cn)](https://mlapp.cn/376.html)