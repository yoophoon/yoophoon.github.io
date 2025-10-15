---
title: 使用hexo及配置butterfly主题(二)
tags:
  - butterfly
  - hexo
categories:
  - web
  - blog
keywords: 'Hexo,Butterfly,Blog'
description: 在Hexo框架及Butterfly主题都已经安装好之后，就可以进行个性化配置了，这篇博客记录下我的配置
top_img: >-
  https://note.youdao.com/yws/api/personal/file/WEB94e77097cf15bbfc3ba5c045da678ac2?method=download&shareKey=29de4fac82c9c6ce2621d81ce5607f56
cover: 'https://i.loli.net/2021/02/24/5O1day2nriDzjSu.png'
abbrlink: 4948a004
date: 2022-06-17 00:52:55
updated:
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

# 菜单栏设置
导航栏配置在`menu:`下方，一级菜单格式：`L1MenuName: path||icon`；二级菜单格式如下所示：
```YML
L1MenuName||ico||hide: 
  L2MenuName1: /menuPath1/||icon 
  L2MenuName2: /menuPath2/||icon 
```
{% note info modern %}
菜单栏似乎最多只支持二级菜单
{% endnote %}
{% note info modern %}
链接菜单可以由`./source/_data/link.yml`补充信息，虽然`./source/link/index.md`也能添加
{% endnote %}
# 代码块设置
按下面设置即可，备注都有可选项
```YML
highlight_theme: mac light #  代码块主题 可选：darker / pale night / light / ocean / mac / mac light / false
highlight_copy: true # 是否显示复制按钮 copy button
highlight_lang: true # 是否显示代码类型 show the code language
highlight_shrink: false # 是否收起 true: shrink the code blocks / false: expand the code blocks | none: expand code blocks and hide the button
highlight_height_limit: false # 高度限制 unit: px
code_word_wrap: false # 是否自动换行
```
# 版权及复制设置
设置版权信息及是否显示
```YML
post_copyright:
  enable: true
  decode: false
  author_href: yoophoon.gitee.io
  license: CC BY-NC-SA 4.0
  license_url: https://creativecommons.org/licenses/by-nc-sa/4.0/
```
设置是否在复制内容后添加版权信息
```YML
copy:
  enable: true
  copyright:
    enable: true
    limit_count: 50
```
# 社交图标设置
社交图标指的是头像下面的那些图标，其设置格式为`icon link || description`，具体设置可参考<font title="_config.butterfly.yml" color="yellblue">配置</font>进行
# 本地搜索
## 安装搜索插件
执行命令，安装本地搜索插件
>$ npm install hexo-generator-search --save  
## 配置
在根目录下的`_config.yml`中配置
```yml
search:
  path: search.xml #文件路径，扩展名为`.json`则会输出JSON文件，否则输出XML文件
  field: post  #搜索类型 post for all blogs,page for all pages,All for all
  content: true #是否对正文进行搜索，flase for title&metaInfo
  template: #./search.xml 搜索模板，可选设置
```
{% note info modern %} 
如果某些页面不想被搜索到可以在编写时`front matter`中添加`indexing: false`即可使该文章不被检索
{% endnote %} 
# 数学(推荐使用KATEX)
## 准备工作
卸载对应的渲染器
```BASH
npm un hexo-renderer-marked --save # 如果有安裝這個的話，卸載
npm un hexo-renderer-kramed --save # 如果有安裝這個的話，卸載

npm i hexo-renderer-markdown-it --save # 需要安裝這個渲染插件
npm install @neilsustc/markdown-it-katex --save #需要安裝這個katex插件
```
配置根目录的_config.yml
```YAML
markdown:
  plugins:
    - plugin:
      name: '@neilsustc/markdown-it-katex'
      options:
        strict: false
```
## 编写公式
{% note info modern %} 
相关的书写格式可以参考[支持格式](https://katex.org/docs/support_table.html)
{% endnote %}
$x^2+y^2+Dx+Ey+F=0$  

$\begin{align} a&=b+c \\ d+e&=f \end{align}$  

$\begin{Bmatrix*}[r] 0 & -1 \\ -1 & 0 \end{Bmatrix*}$  
# 图片设置
设置看主题配置文件`_config.butterfly.yml`即可，这里不做赘述
# 字数统计
## 安装插件
要实现字数统计需要安装`hexo-wordcount`插件，安装命令为`npm install hexo-wordcount --save`
{% note warning modern %} 
未安装插件在生成博客时会报错
{% endnote %}
## 设置主题配置文件
```YAML
wordcount:
  enable: true
  post_wordcount: true
  min2read: true
  total_wordcount: true
```
---
# 图片描述
`photofigcaption`是用来设置是否 显示图片描述文字的，false则不显示文字，true则显示文字  
![图片](https://note.youdao.com/yws/api/personal/file/WEB94e77097cf15bbfc3ba5c045da678ac2?method=download&shareKey=29de4fac82c9c6ce2621d81ce5607f56)
{% note info modern %} 
推荐将该属性设置为`true`，如不需显示文字可在[]中留空即可
{% endnote %}
# 绘制图表
使用mermaid标签可以绘制Flowchart（流程图）、Sequence diagram（时序图 ）、Class Diagram（类别图）、State Diagram（状态图）、Gantt（甘特图）和Pie Chart（圆形图），具体可以查看[mermaid文档](https://mermaid-js.github.io/mermaid/#/)
使用前修改配置文件_config.butterfly.yml
```YML
mermaid:
  enable: true
  # built-in themes: default/forest/dark/neutral
  theme:
    light: default
    dark: dark
```
{% tabs mermaid用法 %}
<!-- tab 饼图-->
```YAML
{% mermaid %}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
{% endmermaid %}
```
{% mermaid %}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
{% endmermaid %}
<!-- endtab -->
<!-- tab 流程图-->
```YAML
{% mermaid %} 
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
{% endmermaid %}
```
{% mermaid %} 
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
{% endmermaid %}
<!-- endtab -->
{% endtabs %}


