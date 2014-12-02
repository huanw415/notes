版本控制系统  

解决的问题: 多个人同时操作一个file, 可以check, 然后把几个file给merge成一个.  
          他就像一个time capsule, 有它的改变日志, 包括改变的内容和改变的原因, 你可以在版本控制中看到不同的版本.  



Git 是由 Linus 发明的, 是一个DVCS(Distributed Version Control System).

`centralized repository: 当几个人同时进行工作时, 任何一个人改变内容, 添加注释, 或者存储时, 都会改变中心仓库.`  

`distributed repository: 每个人都从仓库复制了一份文件, 有助于快速commit, 并且如果其中一个人的文件破坏后, 可以重新copy一份
  从repository.`

你可以从[Git官方网站](http://git-scm.com/)下载Git.

#### command line

##### help system: git help  得到一系列的指令
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
