---
title: ubuntu中命令记录
date: 2021-05-12 20:37:22

categories: 
    [Linux,ubuntu]
---

# 1. 重新挂载硬盘

## 1. 安装图形化磁盘管理工具
```bash
sudo apt-get install gparted

# 与其他基本工具一样，格式化并新建分区即可
```

## 2. 添加挂载目录
```bash
sudo vim /etc/fstab

# 按文件中目录添加语句
<file system>                      <mount point>              <type>  <options>    <dump>  <pass>
UUID=xx(这一项在gparted中可以查到)  /home/dream/data(挂载目录)  ext4    defaults    0   0

# 重启后即可查看挂载目录
```

## 3. 解锁

```bash
sudo chmod -R 777 /home/dream/data      #该权限
sudo chargp dream /home/dream/data      #改所属的组
sudo chown dream  /home/dream/data      #改所有者
```

# 2. 创建软链接

```bash
ln -s [源文件或目录] [目标文件或目录]

ln -s data /home/dream/data
# 当前目录下data 指向 /home/dream/data
```