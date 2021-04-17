---
title: ubuntu中安装常用软件及简单配置
date: 2021-01-28 22:04:42
tags: 
    [ubuntu,操作系统] 
categories: 
    [操作系统,ubuntu]
---
# 配置
## 设置sudo 免密码

```bash
sudo vim /etc/sudoers
#修改:%sudo ALL=(ALL:ALL) ALL
%sudo ALL=(ALL) NOPASSWD:ALL
#wq!   强制保存后退出
```
## 双系统时间不统一
参考[写给工程师的ubuntu20.04的最佳配置指南](https://juejin.im/post/5eb3a1556fb9a0434b73545c#heading-31)
1. 原因如下：

 - UTC(Coordinated Universal Time)，协调世界时（世界统一时间)；
 - GMT(Greenwich Mean Time)，格林威治标准时间。
 - Windows 把计算机硬件时间当作本地时间(local time)，所以在 Windows 系统中显示的时间跟 BIOS 中显示的时间是一样的。
 - 类 Unix 系统把计算机硬件时间当作 UTC， 所以系统启动后会在该时间的基础上，加上电脑设置的时区数(比中国就加8)，因此 Ubuntu 中显示的时间总是比 Windows 中显示的时间快 8 小时。
2. 解决方案：
禁用ubuntu中的UTC

```bash
timedatectl set-local-rtc 1 --adjust-system-clock
```
## 分屏终端

```bash
sudo apt-get install terminator
```
安装完成后要运行一下才能用

```bash
terminator
```


# 软件
## 网易云音乐
首先下载网易云音乐安装包

```bash
wget http://d1.music.126.net/dmusic/netease-cloud-music_1.1.0_amd64_ubuntu.deb
```
开始安装

```bash
sudo dpkg -i netease-cloud-music_1.1.0_amd64_ubuntu.deb
#如果有错误
sudo apt-get -f install
```
安装完成后启动时发现打不开
终端输入

```bash
netease-cloud-music
```
如果是出现

```bash
Failed to load module "canberra-gtk-module"

#解决
sudo apt-get install libcanberra-gtk
```
再次打开，可能还不行，只能后台打开，我也不知道为什么

```bash
sudo netease-cloud-music 
```

## vscode
官网下载deb包

```bash
https://code.visualstudio.com/docs/?dv=linux64_deb

sudo dpkg -i code_1.45.1-1589445302_amd64.deb
```
## QQ/微信
~~[Linux版QQ下载地址](https://im.qq.com/linuxqq/download.html)
下载完成后~~ 
```bash
#sudo dpkg -i linuxqq_1.0.1-b1-100_armhf.deb
```
以上方式安装的qq太老了，最后决定先安装wine，在安装qq

安装deepin-wine-for-ubuntu
```bash
git clone https://gitee.com/wszqkzqk/deepin-wine-for-ubuntu.git
cd deepin-wine-for-ubuntu
sudo ./install.sh
```
下载地址：
[微信](https://mirrors.aliyun.com/deepin/pool/non-free/d/deepin.com.wechat/)
[TIM](https://mirrors.aliyun.com/deepin/pool/non-free/d/deepin.com.qq.office/)

### 微信安装完成的问题
微信成功登录以后，中间会有一个小黑方块，据说是由于表情包弹窗引起的，没找到永久消除的办法
在任意一个聊天框输入一个表情，就可以消除黑方块

# 参考
[ubuntu新系统一次性配置](https://blog.csdn.net/bornfree5511/article/details/106470875)
[写给工程师的ubuntu20.04最佳配置指南](https://juejin.im/post/5eb3a1556fb9a0434b73545c#heading-31)