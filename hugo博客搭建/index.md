# hugo博客搭建


> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [pengpengyang94.github.io](https://pengpengyang94.github.io/2020/04/hugo%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2windows%E7%89%88/)

> 本文主要记录了我利用 Hugo + github 来搭建个人博客的主要流程，最初选择 Hugo 是无意中看到了一篇推文，后来在慢慢的了解下发现 Hugo 有搭建速度快、主题多这两大优势，尤其在搭建速度方面。

　　本文主要记录了我利用 Hugo + github 来搭建个人博客的主要流程，最初选择 Hugo 是无意中看到了一篇推文，后来在慢慢的了解下发现 Hugo 有搭建速度快、主题多这两大优势，尤其在搭建速度方面。

1. 新建 GitHub 库
--------------

新建 **repository**: [https://github.com/new](https://github.com/new)  
**Repository name** 中填写 `name.github.io`，注意 **name** 必须是 github 的账户名。

![](https://i.loli.net/2020/04/12/coRt5mWrwfpL2hK.png)

2. 下载并安装对应版本的 Hugo
------------------

不同版本下载地址: [https://github.com/gohugoio/hugo/releases](https://github.com/gohugoio/hugo/releases)  
我的电脑是 Windows 64 位的系统，所以下载下图所示版本的软件。

![](https://i.loli.net/2020/04/12/HY5RdL4SAtBDOIX.png)

注意：  
1. **解压后的目录即是安装目录**，根据需求设定解压位置。  
2. 建议将安装目录添加到系统环境变量中以方便日后调用。

安装结束后，在 **cmd** 中运行如下命令检查是否安装成功。

```
# 进入安装目录，若添加到系统环境变量中则不需要进入安装文件夹中
cd /install dir path/ 
# 检查是否安装成功
hugo version


```

若出现类似下图反应表示安装成功。

![](https://i.loli.net/2020/04/12/36BgRcPWbsHUF74.png)

3. 创建 Hugo 网站
-------------

```
cd /save dir path/ 

hugo new site yang-blog


```

4. 修改主题
-------

在 **yang-blog** 中新建一个 **themes** 的文件夹用于存储主题。  
Hugo Themes: [https://themes.gohugo.io](https://themes.gohugo.io/)

　　在上面链接中选择合适的主题，点击后进入主题介绍界面，其中包含安装说明，以 **Mainroad** 为例，分为以下两种情况：

### 4.1 已安装 Git

使用 `git` 下载主题，主题说明界面会看到如下安装说明。

![](https://i.loli.net/2020/04/12/LAoqbGi7WPQsOxI.png)

```
cd .\yang-blog\themes

git clone https://github.com/vimux/mainroad


```

### 4.2 未安装 Git

点击下图中的 **Download ** 选项，进入主题的 **Github** 界面。

![](https://i.loli.net/2020/04/12/Jy63FwNs4gfHxhU.png)

　　按照下图所示点击 **Clone or download** 中的 **Download ZIP** 选项，再将压缩包解压至 **themes** 文件夹中。

![](https://i.loli.net/2020/04/12/Tc4ld2akoj6Qsx8.png)

　　最后在 **yang-blog** 文件夹下的 `config.toml` 中添加一行 `theme = "mainroad"`，引号中间的是主题名称，至此主题就已经修改好了。

注意：可以在 `config.toml` 添加 `themesDir = "./themes/"` 来设置存放主题的文件夹。

5. 新建文章
-------

```
# 进入想要存放网站文件夹的目录
cd .\yang-blog
# 新建文章（yang-blog是名字）
hugo new post/Hugo搭建个人博客（Winsows版）.md
# 随后在 Hugo搭建个人博客（Winsows版）.md 中添加内容即可


```

注意：新创建的 **md** 文档需要将原来 **draft** 后的 **true** 改为如下所示的 **false** 才能在预览的时候加载出来。

![](https://i.loli.net/2020/04/12/85qYcsCxUaSMr9W.png)

6. 本地预览网站效果
-----------

```
# 启动 Hugo
hugo server -D
# 终止
Ctrl+C


```

浏览器中打开 http://localhost:1313 即可预览。

注意：须至少有一篇文章才能预览。

7. 构建 Hugo 网站
-------------

　　在 **yang-blog** 目录下执行 `hugo` 指令来构建你的 **Hugo** 网站，默认会将静态站点保存到 **public** 目录中。

8. 将网站文件夹转换为 Git 库
------------------

在 `/yang-blog/public` 目录下执行如下指令。

```
#
git init  
#
ls -a


```

9. 将 Git 本地库关联至远程库
------------------

在 `/yang-blog/public` 目录下执行如下指令。

```
git remote add origin git@github.com:pengpengyang94/pengpengyang94.github.io .git


```

注意：上面命令中的 "pengpengyang94/pengpengyang94.github.io .git” 含义是 “your-github-id/your-github-id.github.io.git”。

10. 提交修改至本地库
------------

在 `/yang-blog/public` 目录下执行如下指令。

```
git status  # 查看当前修改状态
git add .  # 添加所有修改过的文件
git commit -m "Add a new post"  # 引号内容是本次提交的说明


```

11. 将你的修改推至远程库
--------------

在 `/yang-blog/public` 目录下执行如下指令。

```
git push -u origin master


```

　　至此，就完成了整个 **blog** 的构建步骤，后面就可以愉快的在这更新文章了！！！

12. 日常编辑及上传文章流程
---------------

```
# ./yang-blog 目录下执行下面命令新建文章
hugo new post/paper.md
# 将更新的内容，保存到 public 目录下
hugo

# 编辑完成后，更新github上的内容
# /yang-blog/public 目录下
git status  # 查看当前修改状态
git add .  # 添加所有修改过的文件
git commit -m "Add a new post"  # 引号内容是本次提交的说明
git push -u origin master


```

* * *

**参考资料：**  
[1. 如何利用 GitHub Pages 和 Hugo 轻松搭建个人博客？](https://www.jianshu.com/p/ca04631f4438)  
[2. 用 Hugo 30 分钟搭建静态博客](https://linux.cn/article-10048-1.html)  
[3.HuGo+ github 个人博客搭建（步骤一：初始化一个 hugo 项目）](https://blog.csdn.net/u013233097/article/details/79780016)  
[4.hugo+github 博客搭建教程！](https://www.jianshu.com/p/68da4f350d97)  
[5.Hugo +github 简单快捷搭建完成个人博](https://www.jianshu.com/p/e57bb9cf0bc7)  
[6. 手把手教你从 0 开始搭建自己的个人博客 | 第二种姿势 | hugo](https://www.bilibili.com/video/BV1q4411i7gL?t=695)  
[7.HUGO](https://gohugo.io/)  
[8.HUGO 中文网](https://www.gohugo.cn/)
