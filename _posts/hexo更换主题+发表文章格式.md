title: hexo更换主题+发表文章格式
date: 2017-07-17 10:20:18 #文章生成時間
categories: "Hexo教程" #文章分類目錄 可以省略
tags: [hexo,个人博客] #标签
description: "搭建好了基于hexo+node.js+git的个人博客后，hexo官网还提供了各种各样绚丽的主题供用户选择，比如yelee主题、jacman主题、litten主题等等。同时在发表文章的时候要严格遵循hexo的语法格式，才能美观的展示博客内容。"
---
<Contents>
人靠衣装马靠鞍，hexo一样。[hexo官网](https://hexo.io/themes/)除了提供各种版本的维护之外，同时向用户提供了大量不同风格的主题，以jacman为例总结更换主题的操作。

# 下载主题 #
直接Git Bash命令行中输入命令：`$ git clone https://github.com/wuchong/jacman.git themes/jacman`（会再D:\tools\hexo\themes文件夹下生成一个jacman的文件夹）

# 修改配置文件 #
## 修改根目录下的_config.xml ##

修改hexo文件夹下_config.yml（根目录下的），内容如下（有注释，用Sublime Text(使用它的原因是默认是UTF-8编码，中文不会乱码)打开_config.yml文件，否则会乱码的）
注：
在每个参数的”：”后都要加一个空格修改网站相关信息;

    # Hexo Configuration
    ## Docs: https://hexo.io/docs/configuration.html
    ## Source: https://github.com/hexojs/hexo/

    # Site 网站
    title: 小福星独立博客   #网站标题
    subtitle: 既无三徙教，不闻过庭语   #网站副标题
    description: hello,every body!~ #网站描述
    author: sonny   #您的名字
    language: zh-CN #网站使用的语言
    timezone: #网站时区。Hexo 默认使用您电脑的时区
    
    # URL 网址
    ## 如果您的网站存放在子目录中，例如 http://yoursite.com/blog，则请将您的 url 设为 http://yoursite.com/blog 并把 root 设为 /blog/。
    url: http://hushen8023.github.io
    root: /
    permalink: :year/:month/:day/:title/
    permalink_defaults:
    
    # Directory 目录配置
    source_dir: source   #源文件夹，这个文件夹用来存放内容。
    public_dir: public   #公共文件夹，这个文件夹用于存放生成的站点文件。
    tag_dir: tags#标签文件夹
    archive_dir: archives  #归档文件夹
    category_dir: categories #分类文件夹
    code_dir: downloads/code #nclude code 文件夹
    i18n_dir: :lang#国际化（i18n）文件夹
    skip_render: #跳过指定文件的渲染，您可使用 glob 表达式来匹配路径。
    
    # Writing 文章
    new_post_name: :title.md # 新建文章默认文件名
    default_layout: post # 默认布局
    titlecase: false # Transform title into titlecase
    external_link: true # 在新标签中打开一个外部链接，默认为true
    filename_case: 0#转换文件名，1代表小写；2代表大写；默认为0，意思就是创建文章的时候，是否自动帮你转换文件名，默认就行，意义不大。
    render_drafts: false  #是否渲染_drafts目录下的文章，默认为false
    post_asset_folder: false #启动 Asset 文件夹
    relative_link: false  #把链接改为与根目录的相对位址，默认false
    future: true#显示未来的文章，默认false
    highlight:  #代码块的设置
      enable: true
      line_number: true
      auto_detect: false
      tab_replace:
    
    # Category & Tag 分类和标签的设置
    default_category: uncategorized   #默认分类
    category_map:   #分类别名
    tag_map:#标签别名
    
    # Date / Time format
    ## Hexo uses Moment.js to parse and display date
    ## You can customize the date format as defined in
    ## http://momentjs.com/docs/#/displaying/format/
    date_format: YYYY-MM-DD
    time_format: HH:mm:ss
    
    # Pagination 分页
    ## Set per_page to 0 to disable pagination
    per_page: 10  #每页显示的文章量 (0 = 关闭分页功能)
    pagination_dir: page  #分页目录
    
    # Extensions
    ## Plugins: https://hexo.io/plugins/
    ## Themes: https://hexo.io/themes/
    theme: jacman
    
    # Deployment
    ## Docs: https://hexo.io/docs/deployment.html
    deploy:
      type: git
      repository: https://github.com/hushen8023/hushen8023.github.com.git
      branch: master

## 修改主题目录下的_config.xml ##
修改新的主题jacman下的_config.yml(对应主题下的_config.xml)

    ##### 菜单 
    menu:
      主页 | Home: /
      归档 | Archives: /archives
      简介 | About: /about
    ## you can create `tags` and `categories` folders in `../source`.
    ## And create a `index.md` file in each of them.
    ## set `front-matter`as
    ## layout: tags (or categories)
    ## title: tags (or categories)
    ## ---
    
    #### 右边显示部分，按着排序进行排序，我用到了分类，标签，友情链接，微博，rss
    widgets: 
    - category
    - tag
    - links
    - weibo
    - rss
    
    #返回顶部按钮，totop。在博客右下脚显示一件返回顶部按钮
    totop: true   ## if you want to scroll to top in every post set the value to true
    #### RSS 地址
    rss: /atom.xml ## RSS address.
    
    #### Image 图片。包括各种图片，可以在jacman主题下source下img文件下找到各种图片，想要换成你的直接换就ok，当然名字扩展名最好用一样的
    imglogo:
      enable: true ## display image logo true/false.
      src: img/logo.png## `.svg` and `.png` are recommended,please put image into the theme folder `/jacman/source/img`.
    favicon: img/favicon.ico   ## size:32px*32px,`.ico` is recommended,please put image into the theme folder `/jacman/source/img`. 
    apple_icon: img/jacman.jpg ## size:114px*114px,please put image into the theme folder `/jacman/source/img`.
    author_img: img/author.jpg ## size:220px*220px.display author avatar picture.if don't want to display,please don't set this.
    banner_img: #img/banner.jpg ## size:1920px*200px+. Banner Picture
    ### Theme Color 
    theme_color:
    theme: '#2ca6cb'##the defaut theme color is blue
    
    # 代码高亮主题
    # available: default | night
    highlight_theme: default
    
    ####首页文章是否展开。默认为展开式，显示 Read More。
    index:
      expand: true   ## default is unexpanding,so you can only see the short description of each post.
      excerpt_link: Read More  
    ###是否在文章页面自动关闭侧边栏
    
    close_aside: false  #close sidebar in post page if true
    mathjax: false  #enable mathjax if true
    
    ### Creative Commons License Support, see http://creativecommons.org/ 
    ### you can choose: by , by-nc , by-nc-nd , by-nc-sa , by-nd , by-sa , zero
    creative_commons: none
    
    #### 作者信息，显示在网站底部。主要包括，文字介绍，以及图片。还有各种你的链接包括微博等等。换成你id就行；
    author:
      intro_line1:  "Hello ,I'm onePeace Page in csdn."## your introduction on the bottom of the page
      intro_line2:  " Stay hungary,stay foolish."  ## the 2nd line
      weibo: 2026326475 ## e.g. wuchong1014 or 2176287895 for http://weibo.com/2176287895
      weibo_verifier: 039d33aa  ## e.g. b3593ceb Your weibo-show widget verifier ,if you use weibo-show it is needed.
      tsina: 2026326475 ## e.g. 2176287895  Your weibo ID,It will be used in share button.
      douban: ## e.g. wuchong1014 or your id for https://www.douban.com/people/wuchong1014
      zhihu: wang-he-ping-78 ## e.g. jark  for http://www.zhihu.com/people/jark
      email: w_peace12@163.com ## e.g. imjark@gmail.com
      twitter:  wpeace1212  ## e.g. jarkwu for https://twitter.com/jarkwu
      github: wpeace1212## e.g. wuchong for https://github.com/wuchong
      facebook:  100006871362068  ## e.g. imjark for https://facebook.com/100006871362068
      linkedin: wpeace1212   ## e.g. wuchong1014 for https://www.linkedin.com/in/wuchong1014
      google_plus: wpeace1212   ## e.g. "111190881341800841449" for https://plus.google.com/u/0/111190881341800841449, the "" is needed!
      stackoverflow:  ## e.g. 3222790 for http://stackoverflow.com/users/3222790/jark
    ## if you set them, the corresponding  share button will show on the footer
    
    #### 目录，是否在文章中显示目录。显示在侧边栏；
    toc:
      article: true   ## show contents in article.
      aside: true ## show contents in aside.
    ## you can set both of the value to true of neither of them.
    ## if you don't want display contents in a specified post,you can modify `front-matter` and add `toc: false`.
    
    #### 友情链接
    links:
      开发者头条: http://toutiao.io/
      peace in csdn: http://blog.csdn.net/peace1213
      博客园： http://www.cnblogs.com/onepeace/
    
    
    #### 评论 国内用多说很好。注册账号，写在这里就ok
    duoshuo_shortname: rlovep   ## e.g. wuchong   your duoshuo short name.
    disqus_shortname: ## e.g. wuchong   your disqus short name.
    
    #### 主题自带分享，这里用了false
    jiathis:
      enable: false ## if you use jiathis as your share tool,the built-in share tool won't be display.
      id:## e.g. 1889330 your jiathis ID. 
      tsina: ## e.g. 2176287895 Your weibo id,It will be used in share button.
    
    ####网站统计，我用的时cnzz统计
    google_analytics:
      enable: false
      id:## google analytics ID.
      site:  ## 网站地址.
    ## You MUST upgrade to Universal Analytics first!
    ## https://developers.google.com/analytics/devguides/collection/upgrade/?hl=zh_CN
    baidu_tongji:
      enable: false
      sitecode: 140e36c412afe791813036c83f602b ## e.g. e6d1f421bbc9962127a50488f9ed37d1 your baidu tongji site code
    cnzz_tongji:
      enable: true
      siteid: 1255712369   ## e.g. 1253575964 your cnzz tongji site id
    
    #### Miscellaneous
    ShowCustomFont: true  ## you can change custom font in `variable.styl` and `font.styl` which in the theme folder `/jacman/source/css`.
    fancybox: true## if you use gallery post or want use fancybox please set the value to true.
    
    
    
    #### 自定义搜索，我用的时百度搜索
    google_cse: 
      enable: false
      cx:   ## e.g. 018294693190868310296:abnhpuysycw your Custom Search ID.
    ## https://www.google.com/cse/ 
    ## To enable the custom search You must create a "search" folder in '/source' and a "index.md" file
    ## set the 'front-matter' as
    ## layout: search 
    ## title: search
    ## ---
    baidu_search: ## http://zn.baidu.com/
      enable: true
      id: 16217304412639601221   ## e.g. "783281470518440642"  for your baidu search id
      site: http://zhannei.baidu.com/cse/search  ## your can change to your site instead of the default site
    
    tinysou_search: ## http://tinysou.com/
      enable: false
      id:  ## e.g. "4ac092ad8d749fdc6293" for your tiny search id
 
# 文章格式  #
    title: #标题
    date: 2017-07-17 10:20:18 #文章生成時間
    categories: "" #文章分類目錄 可以省略
    tags: [,] #标签，多个标签以数组形式
    description: "" #文章描述，用于列表展示
    ---
    <Contents>
    #开始正文...

# 参考文档 #

[https://hexo.io/themes/](https://hexo.io/themes/ "https://hexo.io/themes/")

[http://blog.csdn.net/peace1213/article/details/47010381](http://blog.csdn.net/peace1213/article/details/47010381 "http://blog.csdn.net/peace1213/article/details/47010381")

