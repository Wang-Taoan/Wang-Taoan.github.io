# git版本控制

> 参考文档：<https://www.liaoxuefeng.com/wiki/896043488029600>

命令：

* commit：提交，将本地文件和版本信息保存到本地仓库
* push：推送，将本地仓库文件和版本信息上传到远程仓库
* pull：拉取，将远程仓库文件和版本信息下载到本地仓库

## 全局设置
设置用户信息
```shell
git config --global user.name "xxx"
git config --global user.email "xxx@qq.com"

```

查看配置信息
```shell
git config --list
```

## 时光穿梭

* 本地初始化git仓库(不常用)
```shell
git init
```

* 远程克隆仓库
```shell
git clone "url"
```

* 添加文件到Git仓库，分两步:
```shell
git add <file> 注意，可反复多次使用，添加多个文件；把文件修改添加到暂存区；

git commit -m <message> 把暂存区的所有内容提交到当前分支。
```

* 查看仓库当前状态
```shell
git status 告诉你有文件被修改过

git diff 可以查看修改内容。
```

* 版本回退
```shell
git log 显示从最近到最远的提交日志

git reset --hard "commit_id "  回退指定版本。

这个版本号不需要写全，输入前面几位就可以自动找到

git reflog 用来记录你的每一次commit和reset操作的版本号
```

* 撤销修改
```shell
场景1:当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令
git checkout -- file

场景2:当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步。
第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
```

* 删除文件
```shell
一般情况下，你通常直接在文件管理器中把没用的文件删了，或者用`rm`命令删了

这个时候，Git知道你删除了文件，因此，工作区和版本库就不一致了，`git status`命令会立刻告诉你哪些文件被删除了

现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`

另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：

git checkout -- test.txt

git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

```

* 远程仓库操作
```shell
git remote 查看远程仓库

git remote add <name> url 添加远程仓库

git clone 从远程仓库克隆

git pull  从远程仓库获取最新版本并合并到本地仓库


git push [remote-name] [branch-name] 本地仓库文件推送到远程仓库
> remote-name 是关联到远程仓库时候，给指定的名字
```

## 远程仓库

* 添加关联到远程库


```shell
git remote add origin git@github.com:wangtaoan/learngit.git
```

```shell
git push -u origin master  远程库名 分支

```

由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；

```shell
git push origin master
```

* 从远程库克隆
要克隆一个仓库，首先必须知道仓库的地址，然后使用`git clone`命令克隆。

Git支持多种协议，包括`https`，但`ssh`协议速度最快。

```shell
git clone ssh/https
```

## 工作区、暂存区、版本库


* 工作区：包含`.git` 文件夹的目录就是工作区
* 暂存区：`.git`文件夹中有很多文件，其中就有一个index文件，里面是临时保存修改文件
* 版本库：前面看到的`.git`文件夹就是版本库。里面有日志文件、配置信息、文件版本等

工作区->暂存区->版本库

git add ->暂存区 git commit->版本库
