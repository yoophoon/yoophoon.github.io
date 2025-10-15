---
title: blogissues
tags:
  - issues
categories:
  - [web,blog,issues]
abbrlink: a0aad0d7
date: 2025-10-08 00:40:15
updated:
keywords:
description:
top_img:
cover:
comments:
toc:
toc_number:
toc_style_simple:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax:
katex:
aplayer:
highlight_shrink:
aside:
abcjs:
noticeOutdate:
---

# 搭建博客碰见的奇葩问题
## 文章的tags、categories
显示与否完全是玄学问题，启动服务器之后修改内容会正常显示
{% note info simple %}
问询官方后确认为hexo8.0的bug
{% endnote %}

## 博客信息无法显示运行时长
aside.card_webinfo.runtime_date，这个字段官网也没设置

# 需要手动安装的包
butterfly的配置有些需要自己手动安装npm包
## [hexo-wordcount](https://github.com/willin/hexo-wordcount)
统计博客和文章的字数

## [hexo-abbrlink](https://github.com/ohroy/hexo-abbrlink)
为文章生成短链，避免标题汉字编码之后太长

## [hexo-generator-searchdb](https://github.com/next-theme/hexo-generator-searchdb)
为站点生成搜索数据

## [hexo-deployer-git](https://github.com/hexojs/hexo-deployer-git)
博客部署工具

# hexo+butterfly Demo
[butterfly官网](https://github.com/jerryc127/butterfly.js.org)配置在github完全开源