# 用Github进行协作的指导手册

## 目录

* [引言](#引言)
* [准备工作](#准备工作)
* [git与github](#git与github)
* [安装及配置](#安装及配置)
* [fork及同步](#fork及同步)
* [编辑并提交修改](#编辑并提交修改)
* [请求与源仓库合并](#请求与源仓库合并)
* [研修资料](#研修资料)

----

## 引言

可能git或是github这些名词出现在我们普通人眼中的时候，觉得这些内容都只是属于程序员们的，而对我们来说，我只需要能拿着鼠标浏览一些内容，再使用Word之类打点字，排个版，输入点内容就成了。没有必要搞这些看似很Geeker的内容。

而git除了是一种很棒的技术之外，更重要的是的理念。可能我们习惯了，一个中心，然后所有内容都围绕这个中心进行的习惯，而git告诉我们，世界其实不应该是这样的，我们每个个体都是特别的、独一无二的，消除中心，让我们每个人都成为网的中心。然后再将我们所有的个体力量进行彼此集中，从而增强我们每个个体的力量。

有一个关于git的TED视频，推荐大家学习，或许通过学习之后，能引发你不一样的思考：

* [Further reading in GitHub, from Clay Shirky](http://blog.ted.com/2012/09/25/further-reading-in-github/)

## git与github

简单来说，git是一种分布式的代码管理工具，而github则是用于提借专门的网络服务来进行git仓库托管的公司。

> **git 简史** (内容来自[《Pro Git》](http://iissnan.com/progit/html/zh/ch1_2.html))

> 同生活中的许多伟大事件一样，Git 诞生于一个极富纷争大举创新的年代。Linux 内核开源项目有着为数众广的参与者。绝大多数的 Linux 内核维护工作都花在了提交补丁和保存归档的繁琐事务上（1991－2002年间）。到 2002 年，整个项目组开始启用分布式版本控制系统 BitKeeper 来管理和维护代码。

> 到了 2005 年，开发 BitKeeper 的商业公司同 Linux 内核开源社区的合作关系结束，他们收回了免费使用 BitKeeper 的权力。这就迫使 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds ）不得不吸取教训，只有开发一套属于自己的版本控制系统才不至于重蹈覆辙。他们对新的系统制订了若干目标：

> - 速度
> - 简单的设计
> - 对非线性开发模式的强力支持（允许上千个并行开发的分支）
> - 完全分布式
> - 有能力高效管理类似 Linux 内核一样的超大规模项目（速度和数据量）

> 自诞生于 2005 年以来，Git 日臻成熟完善，在高度易用的同时，仍然保留着初期设定的目标。它的速度飞快，极其适合管理大项目，它还有着令人难以置信的非线性分支管理系统（见第三章），可以应付各种复杂的项目开发需求。

国内类似的git托管服务有：[gitcaft](http://gitcafe.com)、[git.oschina](http://git.oschina.net)等。

## 准备工作

为了顺利的参与合作，你需要事先准备一下，具体分为;

### 技能准备

- 熟悉电脑操作，如文字输入、文件管理、使用浏览器进行浏览。
- 需要掌握一些基本的Linux操作命令，如：ls, cd, mv, cp, mkdir等。
- 会进得程序的安装与调试。
- 会使用网络搜索引擎，我们推荐你使用[Google](http://www.google.com)。

### 工具准备

- 拥有一个github.com的帐号。
- 安装上git。

```bash
# Ubuntu
$ sudo apt-get install git
# Mac
$ brew install git
# Windows 安装`msysgit`这个软件。
```

- 一个支持Markdown讲法的文本编辑器，如果是Ubuntu，我们推荐你直接使用gedit，如果是Mac，我们推荐你使用Mou或是Sublime，如果是windows，我们推荐你使用`Markdownpad`。

### 心理准备

不错，你现在看到的许多内容，都不是仅通过鼠标点击一下，就能做成的，绝大多数的内容，需要你一字一字的输入，而这些输入的命令，又全是英文字符，可能初次看到的时候，你会有些头皮发麻，觉得太难以理解，但我们认为，这其实都不是问题，问题是你有没有信心大胆尝试一把。相信你会有收获的。

## 安装及配置

**安装**

由于git就是为Linux而出生的，所以如果你还在使用Windows的话，那么你可以尝试一下Linux，比如[Ubuntu](http://www.ubuntu.com)或是国人作品[Deepin Linux](http://www.linuxdeepin.com/index.cn.html)，当然还有其它的不一样的Linux发行版，你可以Google一下。

如果你使用的是Linux或是Mac OS的话，那么在安装和设置上都会省下不少的时间。具体的安装，可以参照这里进行：

* 如何将git安装到你的电脑上: <http://joinwee.com/lesson/107/>

**设置**

如果你以前从来没有使用过Git，那么需要设置一下你的用户名和Email，这个信息，在你提交代码的时候，会一并提交到Git仓库里，这样就能让其他人看到，是由谁作出的更新了。设置方法,进行终端，如果是Windows用户，运行“git bash”即可：

```bash
$ git config --global user.name "YOUR_NAME"
$ git config --global user.email "YOUR_EMAIL"
```

通过上面两个命令，你就设置好了你的git信息，只需要设置一次，以后就可以不管了－－除非你重装了系统，或是删除了`.gitconfig`配置文件。可以使用下面的命令来查看下你的git设置：

```bash
$ git config -l
```

## fork及同步

经过前面的一些准备之后，我们就可以上路了。相信通过以上内容的学习，你也不是那么担心自己不能掌握这些内容了。下面我们就开始进行具体的操作步骤。

协作的过程大致是这样的：

> 1. fork别人的仓库
> 2. clone fork过来的仓库内容
> 3. 进行修改编辑
> 4. 提交更改到自己的仓库
> 5. 申请与原库合并
> 6. 重复3～5

这里我们以[joinwee_l108](https://github.com/wwq0327/joinwee_l108)为例来说明这是个怎么的过程。

**Fork**

一般情况下我们在进行合作的时候，如果你是发起人，当然就需要创建一个仓库，如果你与他人合作的时候，就不需要再从零开始，fork已经将已存在的仓库，变成自己的仓库。

点击页面右上方的“Fork”按钮，就会得到一个github仓库：

![](http://ww1.sinaimg.cn/large/603daed6gw1efjqwqfod7j20b401q746.jpg)

**Clone**

Clone就是克隆自己的仓库到你的电脑上来：

```bash
$ git clone https://github.com/YOUR_NAME/joinwee_l108.git
```

将链接中的“YOUR_NAME”换成你的用户名。

**配置远程仓库**

上面所clone过来的仓库，仅存你自己的内容，但有可能存在这样的情况，你fork过来之后，暂时没有作修改，而源仓库内容有了新的变化，这时你的仓库内容就得同步到源仓库之后，再进行编辑修改。因此你需要配置一下，让你的仓库跟上源仓库的节奏：

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
upstream 	https://github.com/wwq0327/joinwee_l108.git (fetch)
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

- 将你本地内容push到你的github仓库里。

```bash
$ git push origin master
```

> 我们建议：

> 每次你在开始更新你仓库内容的时候，都先执行一下第2，3两步，这样保证你的内容是与源库一样的。

这步操作之后，你本地仓库内容就和源仓库一个样了。这步部份操作，你也可以阅读下github上关于fork的帮助：<https://help.github.com/articles/fork-a-repo>

## 编辑并提交修改

得到内容之后，你就可以在本地进行内容的编辑了。编辑完成之后，你可以使用以下命令将内容同步到你的仓库里：

在提交之前，你可以检查下当前仓库的状态：

```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md
	modified:   git_guide.md

no changes added to commit (use "git add" and/or "git commit -a")
```

如果你看到类似内容的话，表示你现在的修改还没有提交到仓库中来。你可以使用`git diff`这个仓库查看下，你到底进行了一些什么样的修改：

```bash
$ git diff
diff --git a/README.md b/README.md
index 57ae86d..78c78fd 100644
--- a/README.md
+++ b/README.md
@@ -12,6 +12,9 @@
 - Fork [joinwee_l108][1]。
 - Clone你Fork的仓库到你的电脑。
 - 在你的电脑上修改`xiuyou.md`文件，并同步到github。
+- Follow学友。点击`xiuyou.md`文件中的学友链接，击点右上的`Follow`相互关注。
+- 修改并同步到你的github仓库中。
+- 将你的内容合并到源库中来。
...
```

开头部份大致类似，这里会将你作的修改全部显示出来。事实事，git会详细的记录下我们每次的修改，也正因为这样，我们总到回到我们想回到的地方去。

如果没有问题了，你就进行下面的操作，将内容提交到仓库。

```bash
$ git add .
# 把所有新增加的文件添加到仓库
$ git commit -m '一些修改说明'
# 提交更改以仓库
$ git push origin master
# 推到github
```

这里你再次查看仓库状态时，会这样显示：

```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

nothing to commit, working directory clean
```

这表示你的仓库没有作任何修改，或是内容已完全提交了。而你的每次修改与提交，github都会为你记录下来，如：

![](http://ww4.sinaimg.cn/large/603daed6gw1efjsgiza2rj20m806xwf8.jpg)

其中红色部份为修改之前的内容，绿色部份为修改后的内容。具体样式，可以看看[这里](https://github.com/wwq0327/joinwee_l108/commit/6ee7b4705198f1c198298445e2bd2997d7db0c2c)。

但如果你发现有个文件内容你改错了，想反悔了，怎么办呢？你不去跑回去再把文件内容改过来，只需这样作就成了，比如我们想把READMD.md这个文件恢复到未修改之前的状态：

```bash
$ git chechout -- README.md
```

> 我们建议，你每作一次修改，你就可以停下来，`git add .`和`git commit -m "f"`一次，这样保证你能回到任何一个你之前修改的地方。

## 请求与源仓库合并

这些修改只是同步到了你的仓库里，但如果要将修改提交到[源仓库](https://github.com/wwq0327/joinwee_l108)这个源仓库怎么办呢？

首先，你需要回到github上你Fork的仓库里，在右边栏，你可以看到`Pull Requests`字样，点击进去，再点击`New pull request`，如果你是作了修改的，那么，填写上相应内容，点击提交就成了。这时，源仓库的创建者就会收到你发出的合并请求。

当你的请求被通过之后，在源仓库中全将贡献者作一个简单的列表，大致是：

![](http://ww1.sinaimg.cn/large/603daed6gw1efjsyvk9q4j20m8044jrr.jpg)

## 研修资料
- [《Pro Git](http://iissnan.com/progit/index.html)》

## 交流反馈
你可以到本微课的讨论区进行问题的交流与讨论，地址在：

<http://joinwee.com/lesson/108/discuss/>