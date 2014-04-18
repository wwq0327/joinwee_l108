# 用Github进行协作的指导手册

## 目录

* [引言](#引言)
* [安装及配置](#安装及配置)

----

## 引言

可能git或是github这些名词出现在我们普通人眼中的时候，觉得这些内容都只是属于程序员们的，而对我们来说，我只需要能拿着鼠标浏览一些内容，再使用Word之类打点字，排个版，出点内容就成了。没有必要搞这些看似很Geeker的内容。

而git除了是一种很棒的技术之外，更重要的是的理念。可能我们习惯了，一个中心，然后所有内容都围绕这个中心进行的习惯，而git告诉我们，世界其实不应该是这样的，我们每个个体都是特别的、独一无二的，消除中心，让我们每个人都成为网的中心。然后再将我们所有的个体力量进行彼此集中，从而增强我们每个个体的力量。

有一个关于git的TED视频，推荐大家学习，或许通过学习之后，能引发你不一样的思考：

* [Further reading in GitHub, from Clay Shirky](http://blog.ted.com/2012/09/25/further-reading-in-github/)

## git与github

简单来说，git是一种分布式的代码管理工具，而github则是用于提借专门的网络服务来进行git仓库托管的公司。国内类似的git托管服务有：[gitcaft](http://gitcafe.com)、[git.oschina](http://git.oschina.net)等。

## 技能准备

为了顺利的参与合作，你需要具备以下的技能：

- 熟悉电脑操作，如文字输入、文件管理、使用浏览器进行浏览。
- 需要掌握一些基本的Linux操作命令，如：ls, cd, mv, cp, mkdir等。
- 会进得程序的安装与调试。
- 会使用网络搜索引擎，我们推荐你使用[Google](http://www.google.com)。

## 工具准备

- 拥有一个github.com的帐号。
- 安装上git。Ubuntu，可使用`sudo apt-get install git`进行安装，Mac使用`brew install git`，如果是Windows，那会麻烦一点，你需要安装`msysgit`这个软件。
- 一个支持Markdown讲法的文本编辑器，如果是Ubuntu，我们推荐你直接使用gedit，如果是Mac，我们推荐你使用Mou或是Sublime，如果是windows，我们推荐你使用`Markdownpad`。

由于git就是为Linux而出生的，所以如果你还在使用Windows的话，那么你可以尝试一下Linux，比如Ubuntu或是国人作品Deepin Linux。

## 安装及配置

## fork 及同步

点击右上的Fork之后，你会得到一个和这个仓库一样的仓库。然后使用clone仓库，可以将内容clone到本地：

`git clone https://github.com/YOUR_NAME/joinwee_l108.git`

得到内容之后，你就可以在本地进行内容的编辑了。

编辑完成之后，你可以使用以下命令将内容同步到你的仓库里：

```bash
$ git add .
$ git commit -m '一些修改说明'
$ git push origin master
```

这些修改只是同步到了你的仓库里，但如果要将修改提交到[wwq0327/joinwee_l108](https://github.com/wwq0327/joinwee_l108)这个源仓库怎么办呢？

首先，你需要回到github上你Fork的仓库里，在右边栏，你可以看到“Pull Requests”字样，点击进去，再点击“New pull request”，如果你是作了修改的，那么，填写上相应内容，点击提交就成了。这时，源仓库的创建者就会收到你发出的合并请求。

你对frok仓库所作的修改，仅限于在你自己的仓库里，但同时，源仓库也在作修改，如何将原仓库的内容同步到你的仓库呢？

步骤如下：

- 添加源仓库作为你的第二仓库：

```bash
$ git remote add upstream https://github.com/wwq0327/joinwee_l108.git
```

添加成功后，你可以查看下仓库情况：

```bash
$ git remote -v
origin	https://github.com/vole2014/joinwee_l108.git (fetch)
origin	https://github.com/vole2014/joinwee_l108.git (push)
upstream	https://github.com/wwq0327/joinwee_l108.git (fetch)
upstream	https://github.com/wwq0327/joinwee_l108.git (push)
```

- 更新到本地：

```bash
$ git fetch upstream
```

- 与你的仓库进行合并：

```bash
$ git merge  upstream/master
```

这步操作之后，你本地仓库内容就和源仓库一个样了。

- 将你本地内容push到你的github仓库里。

```bash
$ git push origin master
```

> 我们建议：

> 每次你在开始更新你仓库内容的时候，都先执行一下第2，3两步，这样保证你的内容是与源库一样的。

## 案例学习

## 扩展学习
