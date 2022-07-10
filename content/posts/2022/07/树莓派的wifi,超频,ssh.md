---
title: "树莓派的wifi,超频,ssh"
date: 2022-07-10T23:12:44+08:00
draft: false
categories:
- Raspberry
tags:
- Raspberry
---





## wifi

开机连接wifi然后新建一个wpa_supplicant.conf

```
country=CN
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
ssid=""
psk=""
key_mgmt=WPA-PSK
priority=1
}

```

## 超频

```
# /boot/config.txt
force_turbo=0
arm_freq=2000
over_voltage=6
```

## ssh

就是创建一个SSH或者ssh 文件名的文件即可