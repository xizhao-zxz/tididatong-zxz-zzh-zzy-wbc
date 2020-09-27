

# GITJICAO

midir <file>

cd <file>

pwd 



## git init :

把一个目录变成可以被git管理的仓库

会生成一个隐藏目录  .git（可在查找中显示隐藏目录）

### git add <文件名>：{

将文件添加到暂存区
}

### git commit -m"本次提交的说明"：{

一次性把暂存区的所有内容提交到当前分支。
}
添加文件需要 git add和 git commit -m"..."两个文件
可以多次运行 git add 然后用git commit ....

## git status :

返回工作区状态

{

Changes not staged for commit:
Changes to be committed:
nothing to commit, working tree clean
}

### git diff : 

查看修改了什么内容{

在执行 git add 之后 git diff 就不返回东西了
计算机中 删除和添加是分两步完成的，即我只在Word前写了+  但计算机认为是删除word 再写入+word
}

### git diff <file name> 

看的是工作区该文件与版本库中当前分支上该文件的差异

## git log:

查看每次提交的历史记录{

author xizhao-zxz <i826994865@qq.com>
这里不知道为什么邮箱是i826994865@qq.com
并且我不能继续用全局配置改名了，暂无大碍以后查一下
}

### git log --pretty=oneline:

简略查看提交历史

git reset --hard <commit_id>
                        HEAD^
{
HEAD表示当前版本， HEAD^表示上一个版本， HEAD^^表示上两个版本。HEAD~x表示往上x个版本
指针形式移动，即返回上一个版本是内部存储的上一个版本不是刚刚操作的上一个版本。

}

### git reflog:

查看每一次命令{

上箭头可以快速呼出git reflog{好像不是这个效果，以后研究一下}
}

HAED是一个指向master的一个指针



## git reset --hard commit_id:

回到某一个版本

git reset --hard HEAD^：回到上一个版本。

git reset --hard HEAD~n :回到前n个版本。

 ### git chechout -- <file>:

让工作区文件回到最近一次 git add或git commit 时的状态{

删除和增添都可以，回到...时的状态

2.23版中引入了新命令git switch和git restore, 用以代替现在的 git checkout --<file>

}





假如已经放到了暂存区，我们可以

### git reset HEAD<file>:

把暂存区的修改撤掉（unstage）重新放回到工作区{

或许我可以理解为释放当前版本的文件
}



## rm <文件名>  ：

删除一个文件，可用 git restore <文件名> 和 git checkout -- <文件名> 来恢复

这个好像和手动删除效果差不多，因为在文件管理器里删除也可以用git restore 和 git checkout 来恢复。

用 git status 查看

### git rm <file>:

提交 删除一个文件 和 git add效果差不多。 

刚刚试了下，甚至效果是一样的。

之后可以用 git commit提交更改到版本库。



## git --help

呼出git指令 。 直接敲 git 也是这个效果。

# GIT YUANCHENCANGKU

## GitHub SSH Key:

在用户主目录下打开 git Bash    输入   $ ssh-keygen -t rsa -C "youremail@example.com"

### git remote add origin git@github.com:<github账户名>/<库名>：

假如关联错误

[https://blog.csdn.net/MLQ8087/article/details/81360025?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~first_rank_v2~rank_v25-1-81360025.nonecase&utm_term=git%E6%94%B9%E5%8F%98%E5%85%B3%E8%81%94%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93](https://blog.csdn.net/MLQ8087/article/details/81360025?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~first_rank_v2~rank_v25-1-81360025.nonecase&utm_term=git改变关联远程仓库)

自己用的：进入.git目录 在git bash 下git remote 查看远程库名称

git remote rm <远程库名称>：删除当前关联的远程仓库

### git push -u origin master

git push -u <远程库名称> master

git push origin master: 以后就用这个就可以了

### git clone git@github.com:<github账户名>/<库名> ：

克隆一份到本地

## git checkout -b dev:

创建dev分支

以上命令相当于

### git branch git

### git checkout dev

### git branch:

列出所有分支，在当前分支上有*号

### git checkout <分支名称>：

切换到某个分支

### git merge <分支名称>：

合并指令分支到当前分支

会显示：快进合并 --  Fast-forward 即直接把当前分支指向指令分支。

### git branch -d <分支名>：

删除指令分支。 应该是删除指针。

因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在`master`分支上工作效果是一样的，但过程更安全。

## git switch

git switch -c <分支名>：创建并切换到新分支

git switch <分支名>：切换分支 和 git checkout <分支名称> 效果一致

//对于所有分支而言， 工作区和暂存区是公共的。
















