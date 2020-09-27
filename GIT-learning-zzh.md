# **git**

#### **1**.mkdir file.name----------*create a file*

#### 2.cd file.name---------------*Open the file*
#### 3.qwd---------------------------Display the current directory* 
#### 4.git init------------------------*GIT can control the file*
#### 5.git add ; git commit ; 

![git-repo](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

#### 注意：git add 和git commit 要成对出现（一个添加，一个提交）;

***

####  6.git status(获得当前状态) ; git diff(display the difference,展示最近的变动) ；

#### 7.[git log (--pretty=oneline：只显示主要信息）]显示日志；

#### 8.git reset --hard HEAD~n (向前返回n个版本)；

#### 9.git reset --hard 10936(某个版本号)  ( 到达某个版本号(存在的都行) )   用git log 查看版本号；

#### 10.git reflog : 查看历史命令。

#### **11.git checkout --readme.txt:总之，就是让这个文件回到最近一次git commit或git add时的状态.**

>### 命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

#### 12.rm相当于手动删除文件，但是仓库里还有。 git rm 把这个删除提交上去，仓库里也没了，但可以通过命令返回到以前版本。

#### 13.要关联一个远程库，使用命令`git remote add origin git@server-name:path/origin.git`;关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；

> 我的：git remote add origin git@github.com:jijiuli/learngit.git

#### 14.git clone 用来克隆一个本地库 

> git clone git@github.com:jijiuli/gitskills.git

#### 15.Git鼓励大量使用分支：

**查看分支：`git branch`**

**创建分支：`git branch <name> `**

**切换分支：`git checkout <name> `或者`git switch <name> `**

**创建+切换分支：`git checkout -b <name> `或者`git switch -c <name> `**

**合并某分支到当前分支：`git merge <name> `**

**删除分支：`git branch -d**  <name>`

![GIT-picture](C:\Users\周志豪\Desktop\markdown-\GIT-picture.jpg)

# 如何快速关联/ 修改 Git 远程仓库地址

### [如何快速关联/ 修改 Git 远程仓库地址](https://blog.csdn.net/MLQ8087/article/details/81360025?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~first_rank_v2~rank_v25-1-81360025.nonecase&utm_term=git%E6%94%B9%E5%8F%98%E5%85%B3%E8%81%94%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93 "超链接")