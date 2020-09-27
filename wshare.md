版本回退：

$git log:用于查看版本历史（$git log --pretty=oneline）

HEAD:表示当前版本，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。



$git reset --hard HEAD^:返回上一个版本

$git reset --hard 1094a：返回版本“1094a”

所以你让`HEAD`指向哪个版本号，你就把当前版本定位在哪。

问题：`--hard`参数有啥意义？

当不知版号时：可以利用$git reflog查看版号



撤销修改：

命令`git checkout -- readme.txt`意思就是，把`readme.txt`文件在工作区的修改全部撤销，这里有两种情况：

一种是`readme.txt`自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是`readme.txt`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次`git commit`或`git add`时的状态。

注：`git checkout -- file`命令中的`--`很重要。



$git reset第二个作用：可以把暂存区修改撤回退到工作区，

如：$git reset HEAD readme.txt



删除文件：

前提：文件已加入版本库

用`rm`命令删除文件（）后：

1.可用命令`git rm`将其在版本库中删掉，并且`git commit`。

2.`git checkout`其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

所以若已经将版本库中的文件删除，git checkout将无法恢复。这是可以利用“git reset”返回删除前的版本。



添加远程库：

要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`；

关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容。



从远程库克隆：

```
$ git clone git@github.com:michaelliao/gitskills.git
```

要克隆一个仓库，首先必须知道仓库的地址，然后使用`git clone`命令克隆。

Git支持多种协议，包括`https`，但`ssh`协议速度最快。



创建&合并分支：

```
$ git checkout -b dev// $ git switch -c dev
Switched to a new branch 'dev'
```

`git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

```
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
```

git branch:查看当前分支

git checkout master：切换回`master`分支//git switch

git merge dev:合并分支

git  branch -d dev：删除“dev”分支

git branch -D dev 



分支管理策略：

合并分支时，如果可能，Git会用`Fast forward`模式，但这种模式下，删除分支后，会丢掉分支信息。

如果要强制禁用`Fast forward`模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

```
$ git merge --no-ff -m "merge with no-ff" dev
```

（dev前切记加空格）

```
$ git log --graph
```

可以更直观查看分支



的利用分支去除BUG：

若在“dev”分支，可用命令“git stash”保存工作。

之后确定在哪个分支修改BUG。假定需要在`master`分支上修复，就从`master`创建临时分支
