## 说明

用途：《如何使用Github进行在线协作？》研修课内容仓库

微课地址：<http://joinwee.com/lesson/108/>

更多详情，请点击上面的地址进行了解。最终，我们将形成一份如何使用github进行协作创作的[操作手册](git_guide.md)。

## 协作方法

- 注册一个[github](https://github.com)帐号。
- Fork [joinwee_l108][1]。
- Clone你Fork的仓库到你的电脑。
- 在你的电脑上修改`xiuyou.md`文件，并同步到github。
- Follow学友。点击`xiuyou.md`文件中的学友链接，击点右上的`Follow`相互关注。
- 修改并同步到你的github仓库中。
- 将你的内容合并到源库中来。

我们准备的[操作手册](git_guide.md)正是在讲如何使用Github进行合作的事，所以你可以一直关注这个手册的内容，当然你有想法，也可以更新进来。

## 推荐案例

关于如何在线协作，进行共创，我们收集到`anli.md`文件中，你可以在github上到处看看，找一些有意思的内容，交添加到这个文件中来。

## 简明教程

<http://rogerdudler.github.io/git-guide/index.zh.html>

## 小技巧

### 如何不用每次提交都要求输入帐号及密码？
A：当我们使用https协议时，每次更改都需要输入帐号及密码及进行验证。为了省略这个事，你可以输入下面的命令：

```
$git config --global credential.helper store
```

更详细说明，请看里：

<http://git.oschina.net/oschina/git-osc/issues/2586>

## 编辑工具

** Linux **

如果你使用的是Linux那你可以试用下Gedit，这个是很简单的文本编辑器，需果需要支持语法高亮的话，那你么需要Google一下，找找插件。

** Mac OS X **

如果你使用的是Mac OS X操作系统，你可以尝试使用一下`Mou`这个Markdown编辑器。

** Windows **

.md其实就是一个文本文件，只是内容里面使用了不一样的语法而已。如果你在Windows参与我们的研修课程，你就不得不自己准备一个编辑器了。因为Windows上常用的记事本或是Word类的工具是不适合编辑文本文件的。

这里我们为Windows学友们推荐使用`MarkdownPad 2`这个编辑器。你可以到这里去下载：

<http://markdownpad.com>

在Windows上，当你打开GitBash之后，默认工作路径是：

```
C:\Documents and Settings\USER_NAME
```

后面的`USER_NAME`为你的登录名，你可以在`C:\`目录中找到。

三个平台，你都可以使用一下`Sublime`这个软件，但如果你初次使用的话，可以会觉得有些太过于复杂了。


