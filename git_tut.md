# git基本操作

## 配置

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

1. 添加源仓库作为你的第二仓库：

`$ git remote add upstream https://github.com/wwq0327/joinwee_l108.git`

添加成功后，你可以查看下仓库情况：

![](http://ww3.sinaimg.cn/large/603daed6gw1efijw7tiyvj20bo01rt8u.jpg)

2. 更新到本地：`git fetch upstream`

3. 与你的仓库进行合并：`git merge  upstream/master`

这步操作之后，你本地仓库内容就和源仓库一个样了。

4. 将你本地内容push到你的github仓库里。

```
$ git push origin master
```

** 我们建议：每次你在开始更新你仓库内容的时候，都先执行一下第2，3两步，这样保证你的内容是与源库一样的。**


