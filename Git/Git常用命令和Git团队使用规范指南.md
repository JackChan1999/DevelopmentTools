

![git](https://i.v2ex.co/fAhm82RJ.png)

# 1. 前言
在2005年的某一天，Linux之父Linus Torvalds 发布了他的又一个里程碑作品——Git。它的出现改变了软件开发流程，大大地提高了开发流畅度，直到现在仍十分流行，完全没有衰退的迹象。其实一般情况下，只需要掌握git的几个常用命令即可，但是在使用的过程中难免会遇到各种复杂的需求，这时候经常需要搜索，非常麻烦，故总结了一下自己平常会用到的git操作。本文根据团队实践记录Git入门指南和Git常用命令，文章中不仅记录了Git的搭建和使用教程，还参考了大量Git团队使用规范上的经验，希望大家可以结合自己团队的实际应用场景让Git协作优雅的落地。

>Git是目前世界上最先进的分布式版本控制系统

# **2. 更新记录**
2016年04月22日 - 初稿
阅读原文 - http://wsgzao.github.io/post/git/

## **2.1 扩展阅读**
Git Book - https://git-scm.com/book/zh/
git简明指南 - http://rogerdudler.github.io/git-guide/index.zh.html
常用 Git 命令清单 - http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html
猴子都能懂的GIT入门 - http://backlogtool.com/git-guide/cn/
Git教程 - http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

# **3. SVN与Git的最主要的区别**
SVN是集中式版本控制系统，版本库是集中放在中央服务器的，而干活的时候，用的都是自己的电脑，所以首先要从中央服务器哪里得到最新的版本，然后干活，干完后，需要把自己做完的活推送到中央服务器。集中式版本控制系统是必须联网才能工作，如果在局域网还可以，带宽够大，速度够快，如果在互联网下，如果网速慢的话，就纳闷了。

Git是分布式版本控制系统，那么它就没有中央服务器的，每个人的电脑就是一个完整的版本库，这样，工作的时候就不需要联网了，因为版本都是在自己的电脑上。既然每个人的电脑都有一个完整的版本库，那多个人如何协作呢？比如说自己在电脑上改了文件A，其他人也在电脑上改了文件A，这时，你们两之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。

# **4. Git搭建和使用**
Git上手并不难，深入学习还是建议多实践，可以参考扩展阅读中廖雪峰的Git教程
Git服务端

服务端搭建Git很简单，有更多需求不妨试试Gogs和Gitlab
使用Gogs轻松搭建可能比GitLab更好用的Git服务平台 - http://wsgzao.github.io/post/gogs/

```
#安装git
sudo apt-get install git
yum install git

#创建一个git用户，用来运行git服务
sudo adduser git

#创建证书使用公钥免密码登录(可选)
ssh-keygen -t rsa
vi ~/.ssh/authorized_keys

#初始化Git仓库
sudo git init --bare sample.git
sudo chown -R git:git sample.git

#禁用shell登录
vi /etc/passwd
git:x:1001:1001:,,,:/home/git:/usr/bin/git-shell

#在客户端上克隆远程仓库
git clone git@server:/srv/sample.git
```

# 5. 管理公钥推荐使用Gitosis
Gitosis - https://github.com/res0nat0r/gitosis
Gitosis配置手记 - http://debugo.com/gitosis/
管理权限推荐使用Gitolite
Gitolite - https://github.com/sitaramc/gitolite

# **6. Git客户端**
Git客户端可以按个人习惯来选择，遵守团队协作中的Git规范标准才是更重要的
Git - https://git-scm.com/
TortoiseGit - https://tortoisegit.org/
SourceTree - https://www.sourcetreeapp.com/

```
#以最基本的Git命令行为例，先下载Git
https://git-scm.com/download/

#配置git提交用户名和邮箱，定义别名方便区分
git config --global user.name "你的姓名"
git config --global user.email "you@example.com"

#克隆仓库
git clone cap@172.28.70.243:/cap/cap.git

$ git clone cap@172.28.70.243:/cap/cap.git
Cloning into 'cap'...
warning: You appear to have cloned an empty repository.
Checking connectivity... done.

#测试推送
touch README
git add README
git commit -m "add readme"
git push origin master

Counting objects: 3, done.
Writing objects: 100% (3/3), 199 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To cap@172.28.70.243:/cap/cap.git
 * [new branch]      master -> master
```

# 7. Git常用命令
## 7.1 符号约定
<xxx> 自定义内容
[xxx] 可选内容
[<xxx>]自定义可选内容

```
#初始设置
git config --global user.name "<用户名>" #设置用户名
git config --global user.email "<电子邮件>" #设置电子邮件

#本地操作
git add [-i] #保存更新，-i为逐个确认。
git status #检查更新。
git commit [-a] -m "<更新说明>" #提交更新，-a为包含内容修改和增删，-m为说明信息，也可以使用 -am。

#远端操作
git clone <git地址> #克隆到本地。
git fetch #远端抓取。
git merge #与本地当前分支合并。
git pull [<远端别名>] [<远端branch>] #抓取并合并,相当于第2、3步
git push [-f] [<远端别名>] [<远端branch>] #推送到远端，-f为强制覆盖
git remote add <别名> <git地址> #设置远端别名
git remote [-v] #列出远端，-v为详细信息
git remote show <远端别名> #查看远端信息
git remote rename <远端别名> <新远端别名> #重命名远端
git remote rm <远端别名> #删除远端
git remote update [<远端别名>] #更新分支列表

#分支相关
git branch [-r] [-a] #列出分支，-r远端 ,-a全部
git branch <分支名> #新建分支
git branch -b <分支名> #新建并切换分支
git branch -d <分支名> #删除分支
git checkout <分支名> #切换到分支
git checkout -b <本地branch> [-t <远端别名>/<远端分支>] #-b新建本地分支并切换到分支, -t绑定远端分支
git merge <分支名> #合并某分支到当前分支
```

Git常用命令 - http://gityuan.com/2015/06/27/git-notes/

![git](http://gityuan.com/images/git/1.png)

- workspace: 本地的工作目录。（记作A）
- index：缓存区域，临时保存本地改动。（记作B）
- local repository: 本地仓库，只想最后一次提交HEAD。（记作C）
- remote repository：远程仓库。（记作D）

>以下所有的命令的功能说明，都采用上述的标记的A、B、C、D的方式来阐述。

```
#初始化
git init //创建
git clone /path/to/repository //检出
git config --global user.email "you@example.com" //配置email
git config --global user.name "Name" //配置用户名

#操作
git add <file> // 文件添加，A → B
git add . // 所有文件添加，A → B

git commit -m "代码提交信息" //文件提交，B → C
git commit --amend //与上次commit合并, *B → C

git push origin master //推送至master分支, C → D
git pull //更新本地仓库至最新改动， D → A
git fetch //抓取远程仓库更新， D → C

git log //查看提交记录
git status //查看修改状态
git diff//查看详细修改内容
git show//显示某次提交的内容

#撤销操作
git reset <file>//某个文件索引会回滚到最后一次提交， C → B
git reset//索引会回滚到最后一次提交， C → B
git reset --hard // 索引会回滚到最后一次提交， C → B → A

git checkout // 从index复制到workspace， B → A
git checkout -- files // 文件从index复制到workspace， B → A
git checkout HEAD -- files // 文件从local repository复制到workspace， C → A

#分支相关
git checkout -b branch_name //创建名叫“branch_name”的分支，并切换过去
git checkout master //切换回主分支
git branch -d branch_name // 删除名叫“branch_name”的分支
git push origin branch_name //推送分支到远端仓库
git merge branch_name // 合并分支branch_name到当前分支(如master)
git rebase //衍合，线性化的自动， D → A

#冲突处理
git diff //对比workspace与index
git diff HEAD //对于workspace与最后一次commit
git diff <source_branch> <target_branch> //对比差异
git add <filename> //修改完冲突，需要add以标记合并成功

#其他
gitk //开灯图形化git
git config color.ui true //彩色的 git 输出
git config format.pretty oneline //显示历史记录时，每个提交的信息只显示一行
git add -i //交互式添加文件到暂存区
```

# **8. Git使用规范**
Git 使用规范流程 - http://www.ruanyifeng.com/blog/2015/08/git-use-process.html
团队中的 Git 实践 - https://ourai.ws/posts/working-with-git-in-team/
构家网 git 团队协作使用规范 v2 - http://wenku.baidu.com/view/e1430d1b7f1922791788e81e

# **9. Git使用规范提醒**

- 使用Git过程中，必须通过创建分支进行开发，坚决禁止在主干分支上直接开发。review的同事有责任检查其他同事是否遵循分支规范。
- 在Git中，默认是不会提交空目录的，如果想提交某个空目录到版本库中，需要在该目录下新建一个 .gitignore 的空白文件，就可以提交了
- 把外部文件纳入到自己的 Git 分支来的时候一定要记得是先比对，确认所有修改都是自己修改的，然后再纳入。不然，容易出现代码回溯
- 多人协作时，不要各自在自己的 Git 分支开发，然后发文件合并。正确的方法应该是开一个远程分支，然后一起在远程分支里协作。不然，容易出现代码回溯（即别人的代码被覆盖的情况）
- 每个人提交代码是一定要 git diff 看提交的东西是不是都是自己修改的。如果有不是自己修改的内容，很可能就是代码回溯
- review 代码的时候如果看到有被删除掉的代码，一定要确实是否是写代码的同事自己删除的。如果不是，很可能就是代码回溯

原文链接：https://wsgzao.github.io/post/git/

