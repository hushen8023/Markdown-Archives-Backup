title: hexo+github搭建个人博客
date: 2017-7-13 15:49:00
categories: "Hexo教程" #文章分类
tags: [hexo,git]
description: "之前一直有了解hexo，也想静下心来写点东西，可苦于没有时间。难得闲下来，于是乎花点时间利用hexo、gitbub、node.js以及git客户端搭建一个个人博客。"
---
<Contents>
利用hexo、gitbub、node.js以及git客户端搭建个人博客，在此总结记录一下，方便以后用到。
# 环境部署: #
## 安装node.js  ##
 下载地址：[https://nodejs.org/en/](https://nodejs.org/en/ "下载地址")
## 安装git客户端  ##
下载地址：[https://git-scm.com/download](https://git-scm.com/download "下载地址")

	安装方式都是默认，建议安装的目录都是采用英文的全路径。
# 安装hexo #


1. 在任意位置右击鼠标选择Git Bash Here进入命令行，输入hexo的安装命令：`npm install -g hexo`

2. 在D:\tools下新建hexo文件夹，进入hexo文件夹，右击鼠标选择Git Bash Here进入命令行，输入hexo初始化命令：`hexo init`；安装依赖包：`
npm install`；（会在当前hexo文件夹内生成很多hexo的配置文件和配置文件夹）
![](http://hushen8023.github.io/articleImg/1.png )
3. 继续输入命令：`hexo g `（hexo g #完整命令为hexo generate,用于生成静态文件）
4. 继续输入命令：`hexo s` （hexo s #完整命令为hexo server,用于启动服务器，主要用来本地预览）
 ![](http://hushen8023.github.io/articleImg/2.png )

本地已经搭建好了一个基于hexo的博客，根据提示输入[http://localhost:4000](http://localhost:4000)即可访问，可能会出现一直加载问题，请看底端**遇见的问题**解决。终止是用ctrl+c命令。

以上是本地部署的，只有本地才能访问，如何才能在互联网上访问呢，需要把hexo发不到GitHub上去。
首先必须得有GitHub账号，这里就不展示GitHub的注册了，默认已有GitHub的账号。
> 创建repository
 ![](http://hushen8023.github.io/articleImg/3.png )
 ![](http://hushen8023.github.io/articleImg/4.png )

上图是因为我已经创建了一个hushen8023.github.io的项目，所以报错的。

> 编辑hexo文件夹下的_config.yml文件，参照下图
 ![](http://hushen8023.github.io/articleImg/5.png )

如果你是第一次使用Github或者是已经使用过，但没有配置过SSH，则可能需要配置一下:在Git Bash输入以下指令（任意位置点击鼠标右键：`ls -al ~/.ssh`），检查是否已经存在了SSH keys。

如果不存在就没有关系，如果存在的话，直接删除.ssh文件夹里面所有文件：
 ![](http://hushen8023.github.io/articleImg/6.png )

> 在Git Bash命令行中继续输入指令：`ssh-keygen -t rsa -C "szys_hs@126.com"`
> (注意：后面部分为你GitHub的邮箱，而且出现提示让你输入的时候直接先回车，好像需要3次)
 ![](http://hushen8023.github.io/articleImg/7.png )

> 继续命令行：`ssh-agent -s`
 ![](http://hushen8023.github.io/articleImg/8.png )

> 继续命令行：`ssh-add ~/.ssh/id_rsa`（输入之后，我这边出错了，不知道你出错没）
 ![](http://hushen8023.github.io/articleImg/9.png )
如果出错了，请输入以下指令：`eval ssh-agent -s ssh-add`
 ![](http://hushen8023.github.io/articleImg/10.png )

操作到这一步，基本上是完成了，接下来就是添加SSH key到GitHub账户中去，输入指令：`clip < ~/.ssh/id_rsa.pub`（注意，输入完指令之后，表示已经拷贝，直接可以ctrl + v粘贴即可），在setting中的这个SSH keys的title随便取
 ![](http://hushen8023.github.io/articleImg/11.png )

> 测试：输入指令：`ssh -T git@github.com`
 ![](http://hushen8023.github.io/articleImg/12.png )
以上就表示SSH配置好了，执行以下命令部署到Github上。

> 执行指令：`hexo g`(hexo g #完整命令为hexo generate,用于生成静态文件)

> 执行指令：`hexo d`(hexo d #完整命令为hexo deploy,用于将本地文件发布到github上)
 ![](http://hushen8023.github.io/articleImg/13.png )

> 安装指令：`npm install hexo-deployer-git –save`

安装完成之后，继续执行`hexo d`
> 
> 访问连接，比如我的hushen8023.github.io
 ![](http://hushen8023.github.io/articleImg/14.png )


# 发表文章: #
1. 在Git Bash下输入命令：`hexo new “my new post”`(会在hexo文件夹下比如我：D:\tools\hexo\source\_posts文件夹下生成一个my-new-post.md文件）；
2. 编辑这个新生成的文件，推荐使用[Markdownpad](http://markdownpad.com/)工具编辑；
3. 写完文章后，你可以使用
> $ `hexo g`生成静态文件。

> $ `hexo s`在本地预览效果。

> $ `hexo d`同步到github


# 遇见的问题： #
1. 安装完node.js、git和hexo完，输入[http://localhost:4000](http://localhost:4000)一直在加载，就是出不来hexo的页面，在网上查阅了很多资料，显示4000的端口可能被占用，可以修改端口：`hexo server -p 8888`
 ![](http://hushen8023.github.io/articleImg/15.png )
然后就成功了。
 ![](http://hushen8023.github.io/articleImg/16.png )
2. 把本地hexo部署到github上去访问时出现问题，一直404；如下图
 ![](http://hushen8023.github.io/articleImg/17.png )

*解决方案：*
> 
> 在github上新建Repositories的时候，Repository name的值必须是`github的账号名.github.io`的格式，比如我：`hushen8023.github.io`
![](http://hushen8023.github.io/articleImg/18.png )
 
> 拷贝完密钥到github之后，需要在邮件中确认重新登陆的。
 ![](http://hushen8023.github.io/articleImg/19.png )
 
> 检查在github中生成的hexo的目录结构是否完整
 ![](http://hushen8023.github.io/articleImg/20.png )
如果还未解决，等上10分钟左右，一般需要解析下。访问：[http://hushen8023.github.io/](http://hushen8023.github.io/)即可
 ![](http://hushen8023.github.io/articleImg/21.png )

# hexo指令总结 #
1. `hexo c` #hexo clean 清除缓存
2. `hexo s` #启动本地服务
3. `hexo g` #生成静态文件
4. `hexo d` #部署到GitHub上去
5. `hexo server - p 8888` #更改端口，本地测试
6. `hexo n` "新文章" #hexo new "新文章"
7. `hexo new page tags`#创建一个标签云
8. `hexo new page about`#创建关于我

# 参考文献 #
[http://moxfive.coding.me/yelee/](http://moxfive.coding.me/yelee/)

[http://tengj.top/2016/02/22/hexo1/](http://tengj.top/2016/02/22/hexo1/)

[http://blog.csdn.net/imail2016/article/details/51762873](http://blog.csdn.net/imail2016/article/details/51762873)

[http://www.voidking.com/2016/05/13/deve-gitcafe-to-coding/](http://www.voidking.com/2016/05/13/deve-gitcafe-to-coding/)

