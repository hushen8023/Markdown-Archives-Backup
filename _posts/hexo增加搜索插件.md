title: hexo搜索插件
date: 2017-07-18 10:20:18 #文章生成時間
categories: "hexo教程" #文章分類目錄 可以省略
tags: [hexo] #标签
description: "hexo官网除了提供丰富的主题之外，还提供了很多插件用来丰富博客的内容，搜索功能是一个博客基本的功能。"
---
<Contents>
不同的主题对应的搜索插件配置不太一样，因为不同的主题js方法不太一样，小编在此总结的是[yelee](https://github.com/hushen8023/hexo-theme-yelee)主题下支持的插件配置方法。

在hexo的根目录下安装两个插件：`npm install hexo-generator-search --save npm install hexo-generator-searchdb –save`

会在D:\tools\hexo\node_modules目录下生成两个文件夹hexo-generator-search和hexo-generator-searchdb.


在当前主题下D:\tools\hexo\themes\yelee\_config.xml里
 
![](http://hushen8023.github.io/articleImg/22.png )

本地测试结果：
 
![](http://hushen8023.github.io/articleImg/23.png )

除了搜素插件之外，hexo还支持很多其他的插件配置，比如：评论、分享等等。详细请参照[http://moxfive.coding.me/yelee/1.Getting-Started/installation.html](http://moxfive.coding.me/yelee/1.Getting-Started/installation.html "http://moxfive.coding.me/yelee/1.Getting-Started/installation.html")