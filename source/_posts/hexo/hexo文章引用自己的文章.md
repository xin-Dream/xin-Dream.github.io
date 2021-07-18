---
title: hexo文章引用自己的文章
date: 2021-07-18 16:11:16
tags: hexo
categories: [hexo]
---


之前对post中的文章没有分类，所以忽略了所在文件夹。分类后偶尔发现引用文章会失效，才发现路径问题

**所在文件夹是指：在source/_posts目录下文章的分类文件夹**

```bash

{% post_link 所在文件夹/文章名称 %}

{% post_link 所在文件夹/文章名称  引用时文章名称%}

```