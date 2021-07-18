---
title: hexo博客加密
date: 2021-04-22 13:15:49
tags: hexo
categories: [hexo]
---

原文参考连接：[hexo-blog-encrypt](https://github.com/D0n9X1n/hexo-blog-encrypt/blob/master/ReadMe.zh.md)

# 1. 安装

```bash
npm install --save hexo-blog-encrypt
```
# 2. 启用
在文章的**_Config.yaml**文件中添加以下语句

```
encrypt：
    enable: true
```

# 3. 使用

在文章开头添加以下内容

```bash

password: # 要设置的密码

message: 输入密码，查看文章
```