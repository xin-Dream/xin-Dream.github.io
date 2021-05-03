---
title: hexo配置记录
date: 2021-01-25 23:50:58
tags: hexo
categories: [hexo]
---
> ## 安装Node.js
1. 下载
    + 下载地址：[Node.js](https://nodejs.org/en/download/)
2. 验证
    + 在命令行窗口依次输入以下命令
    ```bash
    node -v
    npm -v
   ```


> ## 安装Git及使用SSH免密登陆
- 该步骤可参考[git使用笔记](https://xin-dream.github.io/2021/01/28/git%E4%BD%BF%E7%94%A8%E7%AC%94%E8%AE%B0/)

> ## 新建Repository

1. 注意Repository的名字需要与github名称一致
```bash
用户名.github.io
```
2. 创建完成后，就可以在https://用户名.github.io访问到你的repository

> ## 本地安装hexo
1. 在资料盘的位置新建一个hexo文件夹，使用Git bash或cmd打开该文件夹
2. 执行以下命令
    ```bash
    npm install -g hexo-cli
    ```
    + 有可能速度会很慢
    + 可以先执行以下命令
    ```bash
    # 使用国内镜像
    npm install -gd express --registry=http://registry.npm.taobao.org
    # 永久设置镜像地址
    npm config set registry http://registry.npm.taobao.org
    ```

3. hexo初始化及静态页面显示
```bash
#先执行以下命令
hexo init    # 初始化
npm install  # 安装组件

hexo g # 生成静态页面
hexo s # 开启本地服务器
# 开启服务器后，在浏览器输入localhost:4000
# 即可访问hexo默认页面
# ctrl+C 停止服务器
```


> ## 生成第一篇博客并部署到github  

1. 修改配置  
```bash
#在blog文件夹内打开_config.yml，在文件末尾添加如下内容

deploy:
  type: 'git'
  repo: 
    github: git@github.com:用户名/用户名.git # 这里的地址是github里新建的repository的ssh链接
  branch: master


  #请区分好_config.yml文件，这里是整个博客的配置文件，后续的主题设置中还有一个主题的_config.yml文件
``` 


2. 安装Git部署插件
```bash
npm install hexo-deployer-git --save
``` 
3. 在cmd或Git bash中打开上一步生成的blog文件夹，创建第一篇博客
```bash
hexo new "第一篇博客"
# 可以看到/blog/source/_posts中生成了“第一篇博客.md”
# 在该文件中编辑内容，然后执行以下命令

hexo clean # 清楚缓存以及生成的静态页面，建议每次部署前执行一次
hexo g     # 生成静态页面
hexo d     # 部署至github
# 执行完这一步后，等几分钟在进入“用户名.github.io”，就可以看到部署的博客了

# 为了编辑博客的内容和排版，我们在部署前可以先在本地预览
hexo s    # 开启本地服务器
# 在浏览器中输入"localhost:4000"
#每次编辑完.md文件，刷新一下本机页面即可看到编辑的内容
```


> ## hexo文件夹目录结构
```bash
|--blog
    |--source        #存放用户资源
        |--_posts    #存放新建博客的文章内容
        |--***       #后续新建页面时，会生成单独的文件夹
    |--public        #网站文件
    |--themes        #主题文件
    |--scaffolds     #模板文件夹
    |--package.json  #应用程序信息
```
> ## 结语
本篇博客记录hexo的初次安装过程，后续将继续更新修改主题、博客编辑等文章。如有误差请与我联系。
