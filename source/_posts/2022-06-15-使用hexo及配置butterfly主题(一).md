---
title: 使用hexo及配置butterfly主题
tags:
  - Hexo
  - Buttfly
  - Nodejs
  - Git
categories: web
keywords: web,html
description: 前端的小文章
date: 2022-06-15 21:05:05
cover: https://i.loli.net/2021/02/24/5O1day2nriDzjSu.png
top_img: #
---

# 使用HEXO  
>Hexo     **快速、简洁且高效的博客框架**  
>Butterfly  **一次撰写、多端适用的主题**  
## Hexo使用的准备工作
### 安装Nodejs
[Nodejs](http://nodejs.cn/)官网提供了适用各平台的不同版本的安装包，windows平台安装安装选项保持默认就行，无需其他设置。
### 配置Nodejs
``` bash
//设置/查看全局模块存放路径
npm config set prefix "全局模块存放路径" 
npm config get prefix
//设置/查看缓存文件路径 
npm config set cache "缓存路径"  
npm config get cache
//安装模块，加上-g后缀则安装至全局路径中
npm install "模块名" -g
//查看已安装全局模块
npm list -g
```
### 安装Hexo模块
``` bash
//将hexo的模块安装至全局路径方便后期使用
npm install hexo-cli -g
```
## Hexo生成博客并浏览
前期准备工作完成之后，我们可以使用hexo生成博客了，创建我们博客存放的文件夹并使用powershell在博客文件夹下使用`hexo init`或直接在博客文件存放目录使用powershell使用`hexo init 'blogName'`进行初始化博客。
接下来使用`hexo g`命令生成博客的静态文件，使用`hexo s`命令启动本地博客服务，待命令行提示：
>INFO  Hexo is running at http://localhost:4000/ . Press Ctrl+C to stop.
即可在浏览器地址栏输入`http://localhost:4000/`访问我们第一次生成的博客。
下面是完整的命令语句：
```Bash
//在博客存放的文件夹中创建并初始化博客
hexo init myblog
//生成博客的静态文件
hexo g
//启动本地服务
hexo g
```
## Hexo配置
浏览我们的博客时发现有些内容与我们所需要的不相符，这时就需要我们进行配置来生成我们自己的个性化博客了，使用VSCode打开文件博客目录下的`_config.yml`文件，并修改其对应的内容，下面是我自己的配置内容：
>文件不显示`.yml`后缀是因为我们没开启系统的显示文件后缀功能，启用相关功能后缀即可正常显示
```yml
# 站点设置
title: yoophoon #网页标题
subtitle: note #网页副标题
description: record somethiing interesting #描述
keywords: yoophoon #关键字
author: yoophoon #作者
language: zh-CN #语言 zh-CN/zh-TW/en
timezone: Asia/Shanghai #时区
```
# 安装Butterfly并进行配置
可能Hexo生成的样式不能满足我们的期望，不着急，Hexo提供了很多的[主题样式](https://hexo.io/themes/)供我们选择，我使用的是Butterfly，下面来讲一讲Butterfly的安装及配置过程。
## 安装Butterfly
butterfly的包名是<a href="https://github.com/jerryc127/hexo-theme-butterfly"><font color="seablue">hexo-theme-butterfly</font></a>，是一款基于[hexo-theme-melody](https://github.com/Molunerfinn/hexo-theme-melody)，该主题提供了如下三种安装方式：  
{% tabs installButterfly %}
<!-- tab GIT安装(github)@fab fa-github-square-->
>git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly  
{% note info simple %}  
升级方法：在主题目录下，运行 `git pull`  
{% endnote %}
<!-- endtab -->

<!-- tab GIT安装(gitee)@fab fa-git-square-->
>git clone -b master https://gitee.com/immyw/hexo-theme-butterfly.git themes/butterfly  
{% note info simple %}  
升级方法：在主题目录下，运行 `git pull` 
{% endnote %}
<!-- endtab -->

<!-- tab NPM安装@fab fa-npm-->
>npm i hexo-theme-butterfly  
{% note info modern %}  
升级方法：在 **Hexo** 根目录下，运行 `npm update hexo-theme-butterfly`
{% endnote %}
<!-- endtab -->
{% endtabs %}  
## 应用主题
修改Hexo根目录下的`_config.yml`，把主题改为`butterfly`  
>theme: butterfly  
## 安装插件
主题需要安装pug以及stylus的渲染器，可用以下命令安装：
```Powershell
npm install hexo-renderer-pug hexo-renderer-stylus --save  
```
{% note info simple %}  
Hexo及Butterfly的安装工作已经全部完成，后面开始主题的配置
{% endnote %}


