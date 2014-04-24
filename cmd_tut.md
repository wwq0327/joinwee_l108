Linux 常用命令
=============

在使用Git过程中，我们一般都是通过命令行进行操作的，这里需要我们掌握一些基本的Linux操作命令，基本的操作为文件的操作，含文件的拷贝、移动、删除之类的。这里我们只介绍几个最基本的操作命令就行了：

> `ls` `cd` `cp` `mv` `rm` `cat` `touch` `mkdir` `tree`

## 使用演示

这里我们通过具体事例来进行。

当你进行终端之后，在Linux/Mac中有一个名为`终端`的程序，在Windows中，你可以直接打开`Git Bash`。这里我以Mac下的终端为例，界面是这样的：

![](http://ww4.sinaimg.cn/large/603daed6gw1efqht3a8k9j20p60hs75e.jpg)

**ls查看当前目录下的文件及文件夹**

`ls`用于查看文件及文件平的，比如：

```bash
wyattdeMacBook-Pro:~ wyatt$ ls
Applications   Movies         VirtualBox VMs hello.md       src
Desktop        Music          baidupan       joinwee.com    tmp
```

一般情况下，你可以根据颜色来区别显示出来的内容是一个文件还是一个文件夹，其实在*nix中，所有内容都是当作文件来对待的。

**mkdir 创建一个目录**

使用`mkdir`可能创建一个空目录，文件：`mkdir 名称`，这里我们创建一个用于尝试的文件夹：

```bash
$ mkdir tut
$ cd tut
$ ls
```

这里你发现里面什么都有。上面用到了`cd`，这是一个进入目录的操作，类似于在图形界面中双击一个文件夹一样。

然后我们再在这个目录里面创建两个目录，一个`a`，一个`b`：

```bash
wyattdeMacBook-Pro:tut wyatt$ mkdir a
wyattdeMacBook-Pro:tut wyatt$ mkdir b
wyattdeMacBook-Pro:tut wyatt$ ls
a b
```

这里我们发现，输入查看命令之后，就会有a、b这两个目录了。

**touch和cat**

`touch`用于创建一个空白文件：

```bash
$ touch hello.md
$ ls
a        b        hello.md
```

显后我们可以开始命令这个文件了，使用你喜欢的文件编辑器写上内容，然后你可以使用`cat`这个命令来显示文件内容：

```bash
$ cat hello.md 
Hello, world!

```

**cp、mv、rm**

我们再在当前目录中创建三个文件，分别为`file1.md`、`file2.md`和`file3.md`进行这三个命令的操作:

```bash
$ touch file1.md file2.md file3.md
$ ls
a        b        file1.md file2.md file3 hello.md
```

后我们进行拷贝的演示：

```bash
wyattdeMacBook-Pro:tut wyatt$ cp file1.md a
wyattdeMacBook-Pro:tut wyatt$ cp file2.md b
wyattdeMacBook-Pro:tut wyatt$ ls
a        b        file1.md file2.md file3.md hello.md
wyattdeMacBook-Pro:tut wyatt$ ls a
file1.md
wyattdeMacBook-Pro:tut wyatt$ ls b
file2.md
```

你也可以使用`tree`这个命令来查看目录树：

```bash
wyattdeMacBook-Pro:tut wyatt$ tree
.
├── a
│   └── file1.md
├── b
│   └── file2.md
├── file1.md
├── file2.md
├── file3.md
└── hello.md

2 directories, 6 files
```

然后我们把`file3.md`这个文件移动到目录`b`：

```bash
wyattdeMacBook-Pro:tut wyatt$ mv file3.md b
wyattdeMacBook-Pro:tut wyatt$ tree
.
├── a
│   └── file1.md
├── b
│   ├── file2.md
│   └── file3.md
├── file1.md
├── file2.md
└── hello.md

2 directories, 6 files
```

然后我们把当前目录的`file1.md` `file2.md` 删除掉：

```bash
wyattdeMacBook-Pro:tut wyatt$ rm file1.md 
wyattdeMacBook-Pro:tut wyatt$ rm file2.md 
wyattdeMacBook-Pro:tut wyatt$ tree
.
├── a
│   └── file1.md
├── b
│   ├── file2.md
│   └── file3.md
└── hello.md

2 directories, 4 files
```

这里你可以看到当前目录中的这两个文件不见了。然后我们再把`./a/file1.md`移动到当前目录来，再删除掉目录`a`:

```bash
wyattdeMacBook-Pro:tut wyatt$ mv a/file1.md . #这里.表示你当前所在的位置
wyattdeMacBook-Pro:tut wyatt$ tree
.
├── a
├── b
│   ├── file2.md
│   └── file3.md
├── file1.md
└── hello.md

2 directories, 4 files
wyattdeMacBook-Pro:tut wyatt$ rm -r a # 与文件操作类似，但对于目录的删除，需要使用－r参数
wyattdeMacBook-Pro:tut wyatt$ tree
.
├── b
│   ├── file2.md
│   └── file3.md
├── file1.md
└── hello.md

1 directory, 4 files
```

> 需要提醒的是，在执行删除的时候，是没有提示的，所以删除前请作好确认。

最好，我们把这个`tut`的演示目录一起删除掉，但你现在正处在这个目录里，所以你先得退出来再进行删除，退出当前目录的操作是：

```bash
$ cd ..
```

`..`表示当前目录的上一级目录，有时你不知道自己在哪里的时候，你可以使用`pwd`来确认下位置。最后删除：

```bash
$ rm -r tut
```

基本的命令就说完了，初次使用可能仍有些难度，但一些时间的使用之后，你会爱上的。

## 推荐阅读

上面只是常用的几个，如果你想学习下Linux的使用，推荐你可以去读一读《[鸟哥的 Linux 私房菜 -- 基础学习篇](http://vbird.dic.ksu.edu.tw/linux_basic/linux_basic.php)》。

