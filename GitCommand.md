#[链接](http://www.cnblogs.com/lixiaolun/p/4360732.html)

###1.本地创建git仓库:

    mkdir git-rep
    cd git-rep
    git init
    touch README.md
    git add README.md
    git commit -a -m "add README.md"
    git push -u origin master
    
###2.常用命令：

* ssh-keygen -t rsa -C "xxx"：生成一个SSH的公钥和秘钥对(可以自己指定名称)

* ssh-add xxx：配置xxx秘钥(在某个git仓库路径中)

* ssh-add -l :查看绑定的秘钥

* __git commit -a -m "xxx"__：提交全部修改文件

* __git commit -o xxxx__：提交指定目录的xxx文件

* __git push__：发布到远程库

* __git pull__：抓取远程库

* __git remote -v__：查看本地配置的origin信息

* __git push -u origin master__：绑定远程origin与本地仓库的关联关系

* __git status__: 查看本地分支与远程分支的差异

* __git branch -a__：查看所有的分支

* __git checkout xxx__：切换到xxx分支

* __git log__：查看所有提交日志

* __git log --pretty=oneling__：一行显示每一个提交的日志

* __git diff xxx__：查看xxx文件的修改比较

* __git reflog__：查看每一个git操作记录

* __git reset --hard xxx__：回退到用git reflog查出来的某一个命令，回退到某一次命令操作

* __git reset --hard HEAD^__：本地回退到上一个版本

* __git merge__: 从另外一个分支同步修改,比如Ａ和Ｂ分支同步，然后Ａ修改代码之后，Ｂ需要同步Ａ的修改，1.切换到Ｂ分支 git checkout B;2.同步代码 git merge A

* __git checkout -f__:强制切换到master，丢弃本地修改

>
Git必须知道当前版本是哪个版本，在Git中，用HEAD表示当前版本，也就是最新的提交xxx版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。

##3.解决冲突方法：

* Step 1: From your project repository, bring in the changes and test.  
  git fetch origin  
  git checkout -b Linux_Desktop origin/Linux_Desktop  
  git merge master  

* Step 2: Merge the changes and update on GitHub.  
  git checkout master   
  git merge --no-ff Linux_Desktop  
  git push origin master  

