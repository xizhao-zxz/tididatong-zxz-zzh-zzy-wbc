# 基础命令

```git
$mkdir leargit                                       创建文件夹   
$cd leargint                                         进入文件夹
$pwd                                                 显示所在目录
$git init                                            初始化文件夹作为git仓库
$git add <file>                                      把file添加到暂存区
$git add -A                                          将除了clone所有文件加到暂存区
$git commit -m"revise"                               存档，注释revise
$git status                                          显示当前工作区状态
$git diff readme.txt                                 对比当前文件
$git log                                             显示版本历史
$git reset --hard <edition>                          返回edition版本
$git reflog                                          显示历史存档改变记录
$git checkout -- <file>                              撤销更改
$git reset HEAD readme.txt                           返回存档
$rm <file>                                           删除文件夹中文件
$git rm <file>                                       删除存档中文件
```

# 与Github链接推送的命令

```
$git remote add origin git@github.com:michaelliao/learngit.git
与远程仓库origin建立链接
$git remote -v
查看远程库的信息
$git push -u origin master
把本地master分支提交到远程空仓库
$git push -u origin master -f
强制把本地仓库提交到远程空仓库
$git clone git@github.com:HAPPYyear2030/qwqw.git
克隆下来一个本地库


```



# 分支命令

``` 
$git checkout -b dev                                创建名称为dev的分支并切换分支
$git branch dev                                     创建分支，名称为dev
$git checkout dev                                   切换到dev分支
$git switch dev                                     切换到dev分支【常用】
$git branch                                         查看当前分支
$git merge dev                                      合并dev至当前分支
$git merge dev --no-ff -m"         "                禁用Fast forward模式进行合并
$git branch -d dev                                  删除dev分支
$git log --graph                                    查看历史【带分支图】
$git stash                                          储存当前工作现场
$git stash list                                     查看保存的工作现场
$git stash apply stash@[0]                          恢复指定的工作现场
$git cherry-pick 4c805e2                            在当前分支上重复4c805e2进行的修改
$git branch -D <name>                               强制删除name分支
$git rebase                                         将版本历史中原来的分支合并起来
```

# 标签管理

``` 
$git tag                                            查看所有标签
$git tag <name>                                     为目前commit添加上name标签
$git tag <name> <edition>                           为版本贴上标签
$git tag -a <tagname> -m"" <edition>                创建一个带有说明的标签       
$git tag -d <tagname>                               删除标签
$git push origin :refs/tags/v0.9                    从远程删除标签
$git push origin <tagname>                          推送标签到远程
$git push origin --tags                             一次性推送尚未推送的标签
$git show <tagname>                                 查看标签信息
```



