版本控制系统  

解决的问题: 多个人同时操作一个file, 可以check, 然后把几个file给merge成一个.  
          他就像一个time capsule, 有它的改变日志, 包括改变的内容和改变的原因, 你可以在版本控制中看到不同的版本.  



Git 是由 Linus 发明的, 是一个DVCS(Distributed Version Control System).

`centralized repository: 当几个人同时进行工作时, 任何一个人改变内容, 添加注释, 或者存储时, 都会改变中心仓库.`  

`distributed repository: 每个人都从仓库复制了一份文件, 有助于快速commit, 并且如果其中一个人的文件破坏后, 可以重新copy一份
  从repository.`

你可以从[Git官方网站](http://git-scm.com/)下载Git.

#### command line

##### git help  得到一系列的指令
    usage: git [--version] [--help] [-C <path>] [-c name=value]  
               [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]  
               [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]  
               [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]  
               <command> [<args>]  

    The most commonly used git commands are:  
       add        Add file contents to the index  
       bisect     Find by binary search the change that introduced a bug  
       branch     List, create, or delete branches  
       checkout   Checkout a branch or paths to the working tree  
       clone      Clone a repository into a new directory  
       commit     Record changes to the repository  
       diff       Show changes between commits, commit and working tree, etc  
       fetch      Download objects and refs from another repository  
       grep       Print lines matching a pattern  
       init       Create an empty Git repository or reinitialize an existing one  
       log        Show commit logs  
       merge      Join two or more development histories together  
       mv         Move or rename a file, a directory, or a symlink  
       pull       Fetch from and integrate with another repository or a local branch  
       push       Update remote refs along with associated objects  
       rebase     Forward-port local commits to the updated upstream head  
       reset      Reset current HEAD to the specified state  
       rm         Remove files from the working tree and from the index  
       show       Show various types of objects  
       status     Show the working tree status  
       tag        Create, list, delete or verify a tag object signed with GPG  

    'git help -a' and 'git help -g' lists available subcommands and some  
    concept guides. See 'git help <command>' or 'git help <concept>'  
    to read about a specific subcommand or concept.  

##### git help config  可以得到更加详细的文档
安装好Git 后的第一件事情就是设置一些基本配置.  
  `git config --global user.name "user_name"`  
  `git config --global user.email "user_email@outlook.com"`
  `git config --global color.ui true`

##### git init 创建一个本地的Git仓库
此时会在当前文件夹下生成一个.git的隐藏文件夹, 这个即是本地的仓库, 用来存储.  

##### git status 告诉我们从上一次commit结束后, 哪些文件发生了变化

##### git add 将未追踪的文件添加到staged area

  `git add <文件列表>`  
  `git add --all 添加所有发生变化的文件到staged area`  
  `git add . 添加所有发生变化的文件到staged area`  
  `git add *.txt 添加当前文件夹下所有发生变化的.txt类型文件`  
  `git add docs/*.txt 添加docs文件夹下所有发生变化的.txt文件`  
  `git add docs/ 添加docs文件夹下所有发生变化的文件`  
  `git add "*.txt" 添加整个工程中发生变化的.txt文件`  

##### git commit -m "descriptions of changes" 描述什么发生了变化
  commit的内容应该使用一般现在时, 而不是过去时,例如:  
  `应为create readme file, 而不是created readme file`  

##### git log 查看日志, 包括Author, Date, Commit

##### git diff 列出相比于commit之后没有stage的文件发生了什么变化
(-)红色的表示删除的内容  
(+)绿色表示增加的内容  

*git diff --staged  可以查看staged的文件发生了什么变化*

##### git reset HEAD file名字 把file变成unstaged
HEAD可以找到我们当前分支上的最近一次commit的地方  

##### git reset --soft HEAD^ 返回到staged状态

##### git reset --hard HEAD^ 取消上次的commit和所有的变化  
git reset --hard HEAD^^ 取消上两次的commit和所有的变化

##### git checkout file名字 可将file恢复到上次commit后的状态

##### git commit --amend -m "descriptions of changes"  将new commit message添加到上一次的commit

##### git remote add origin URL  URL是GitHub给我们的仓库的地址, origin是给它起的名字(第一次创建仓库的时候使用)  

##### git remote -v 展示远端的仓库

##### git push -u origin master (master->local brach to push, oringin->远端仓库的名字)

##### git clone URL 文件夹名称(例: demo)  将URL下的内容克隆到本地的文件夹(demo)中

##### 分支操作

1. git brach 分支名称(例: cat) 创建分支(cat)  
2. git branch 查看分支情况(`*为当前所在分支`)  
3. git branch -r 查看remote端分支情况  
4. git remote show origin(remote端的名字)  展示local branch, 以及remote端的合并情况  
5. git checkout 分支名称(例: cat) 跳转到此分支(cat)上  
`在当前分支上创建的文件不会在另一个分支上显示`  
6. git merge 分支名称(例: cat) 将当前分支和选择的分支(cat)合并  
7. git checkout -b 新分支名称(cat) 创建新分支(cat),并跳转到该分支上
8. git push origin(remote URL的名字) 新分支名称(cat)  将新分支cat push到了github上, 然后就可以track cat分支  
9. git push origin(remote端名称) :想要删除的分支名称(cat) 将删除remote端的这个分支(cat)  
10. git branch -d 分支名称(cat) 删除本地的此分支(cat)  
`-D 如果此分支还没有合并, 需要强制删除时使用`  
11. git remote prune origin 清除已经被在remote端删除的分支  
12. git fetch copy remote端的branch  

##### tag操作(**tag大部分情况被用于标记发布版本**)
1. git tag 查看所有的版本情况  
2. git checkout 版本名称 checkout此版本到commit  
3. git tag -a 版本名称 -m "commit内容"
4. git push --tag push这个tag到remote端  
