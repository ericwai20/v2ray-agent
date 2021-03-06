# 脚本使用方法介绍

# 目录

- [1.脚本安装、重新执行](#1脚本安装-重新执行)
    * [1.安装](#1安装)
    * [2.重新打开脚本](#2重新打开脚本)
- [2.功能介绍](#2功能介绍)
    * [1.安装&任意组合安装](#1安装任意组合安装)
        + [1.安装](#1安装-1)
        + [2.任意组合安装](#2任意组合安装)
    * [2.账号管理](#2账号管理)
        + [1.查看账号](#1查看账号)
        + [2.查看订阅](#2查看订阅)
        + [3.添加用户](#3添加用户)
        + [4.删除用户](#4删除用户)
    * [3.更换伪装站点](#3更换伪装站点)
    * [4.更新证书](#4更新证书)
    * [5.更换CDN节点](#5更换cdn节点)
    * [6.ipv6人机验证](#6ipv6人机验证)
    * [7.流媒体工具](#7流媒体工具)
    * [8.core版本管理](#8core版本管理)
    * [9.trojan-go版本管理](#9trojan-go版本管理)
    * [10.更新脚本](#10更新脚本)
    * [11.BBR、DD脚本](#11bbr-dd脚本)
    * [12.查看日志](#12查看日志)
    * [13.卸载脚本](#13卸载脚本)
- [3.答疑](#3答疑)
    * [1.哪一种线路是最好的？](#1哪一种线路是最好的)
    * [2.是否支持流量统计？](#2是否支持流量统计)
    * [3.流控[xtls-rprx-direct、xtls-rprx-splice]答疑](#3流控xtls-rprx-directxtls-rprx-splice答疑)
    * [4.GCP挖矿或者其余警告被封实例](#4gcp挖矿或者其余警告被封实例)
    * [5.智能DNS的作用](#5智能dns的作用)

# 1.脚本安装、重新执行

## 1.安装

- 最新版

```
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/mack-a/v2ray-agent/master/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```

- 稳定-v2.2.24

```
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/mack-a/v2ray-agent/9ae23c13a56460d8c14f27c8eb65efc73b173f46/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```

- 稳定-v2.1.27

```
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/mack-a/v2ray-agent/3f8ea0aa364ae2e1e407056074c11b448396261f/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```

## 2.重新打开脚本

- 1.重新打开

```
# 执行
vasma
```

- 2.自定义打开命令

```
# 替换下方的 abc 为自己想要定义的命令
echo "alias abc=vasma" >> ~/.bashrc & source ~/.bashrc 
```

# 2.功能介绍

## 1.安装&任意组合安装

### 1.安装

- [安装]会安装 VLESS/VMess/Trojan三种协议
- 会根据不同的内核，安装当前内核支持的最新的配置

### 2.任意组合安装

- [任意组合安装]可以安装 VLESS/VMess/Trojan三种协议
- 采用VLESS回落，所以0是必须安装的，也是默认安装的，不管选择哪一个种安装内容都会安装0。
- 支持VLESS+TLS/XTLS+TCP、VLESS+TLS+WS[CDN]、VMess+TLS+TCP、VMess+TLS+WS[CDN]、Trojan、Trojan+WS[CDN]
- 支持WS的支持Cloudflare

## 2.账号管理

### 1.查看账号

### 2.查看订阅

- 1.默认不生成订阅文件，只有在查看订阅后才会生成订阅文件。
- 2.每次添加、删除用户时，需要重新查看订阅才会重新生成

### 3.添加用户

- 1.可以添加一个或者多个用户
- 2.添加一个用户时会提示是否自定义UUID和用户名称、添加多个用户时会随机分配名称和UUID

### 4.删除用户

## 3.更换伪装站点

- 如需手动更换请将要替换的文件拷贝到此[/usr/share/nginx/html]目录下
- 其余的伪装站点请到脚本中查看

## 4.更新证书

- 1.支持手动更新证书
- 2.[不支持手动拷贝进去的证书进行更新](https://github.com/mack-a/v2ray-agent/blob/master/documents/install_tls.md)

## 5.更换CDN节点

- 适用于VLESS+TLS+WS[CDN]、VMess+TLS+WS[CDN]、Trojan+WS[CDN]
- [具体详解请查看此文章](https://github.com/mack-a/v2ray-agent/blob/master/documents/optimize_V2Ray.md)

## 6.ipv6人机验证

- 解决vps打开Google后频繁出现人机验证
- 需要自己申请HE的ipv6地址
- 脚本会检测是否支持ipv6

## 7.流媒体工具

- 支持检测是否解锁Netflix
- 支持DNS流媒体解锁，需自行购买流媒体解锁DNS

## 8.core版本管理

- 1.支持不同内核[v2ray-core、xray-core]升级回退、可以回退五个版本

## 9.trojan-go版本管理

- 1.支持trojan-go更新、回退

## 10.更新脚本

- 支持在线更新脚本

## 11.BBR、DD脚本

- [集成ylx2016的脚本](https://github.com/ylx2016/Linux-NetSpeed)

## 12.查看日志

## 13.卸载脚本

- 卸载后会保留acme目录的证书文件防止下次安装时重新签发，签发多次后在一段时间内就不可以签发

# 3.答疑

## 1.哪一种线路是最好的？

- 没有最好的只有最适合的
- 建议自己多测试找出适合自己的

## 2.是否支持流量统计？

- 不支持，此功能以后也不会写。

## 3.流控[xtls-rprx-direct、xtls-rprx-splice]答疑

- xtls-rprx-direct为服务端，xtls-rprx-splice为客户端，并且仅支持linux[路由器、软路由]、android

## 4.GCP挖矿或者其余警告被封实例

- GCP不建议使用代理，自从GCP改为3个月后，开始封禁大流量实例，和脚本无关。

## 5.智能DNS的作用

- [具体详解请查看此文章](https://github.com/mack-a/v2ray-agent/blob/master/documents/optimize_V2Ray.md)