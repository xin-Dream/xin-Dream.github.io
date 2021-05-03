---
title: Win10在非系统盘安装WSL(ubuntu18.04)
date: 2021-04-23 20:57:06
tags: 
    [VMware,WSL] 
categories: 
    [操作系统,WSL]
---

# 注：安装为WSL1，后续将对其升级

# 在Windows中修改配置
1. 在设置中打开  “开发人员模式”

{% asset_img 设置.png This is an image %}


2. 在控制面板中打开程序与功能，打开  “应用或关闭Windows功能”，选择“适用于Linux的Windows子系统“并重启。
{% asset_img 控制面板.png This is an image %}



# 下载子系统安装包
选择喜欢的安装包下载到非系统盘的位置。
建议在安装软件的分区内新建Ubuntu文件夹，并下载到里面，因为后续将会安装在这个文件夹。

[手动下载适用于 Linux 的 Windows 子系统发行版包](https://docs.microsoft.com/zh-cn/windows/wsl/install-manual)

# 安装并启动
找到刚才的文件夹，将下载好的安装包后缀名改为zip，并解压。
解压后运行ubuntu18.04.exe，安装完成后就可以设置用户名与密码。
{% asset_img 结构01.png This is an image %}

# 安装后的结构
注：升级到wsl2后目录结构将有所变化
{% asset_img 结构02.png This is an image %}
{% asset_img 结构03.png This is an image %}


