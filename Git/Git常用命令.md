## 设置用户名和邮箱

```
# 设置用户名
git config --global user.name 'AllenIverson'

# 设置用户名邮箱
git config --global user.email '619888095@qq.com'

# 初始化仓库
git init

# 查看设置
git config --list
```
## 常见操作
```
git status
git log
git reflog
git clone

# 查看标签
git tag
# 切换标签
git checkout v1.0

git show

# 推送
git push origin master 

# 拉取
git pull origin master = git fetch & git merge

# 抓取你还没有的数据
git fetch <name>

git add <filename>
git add *
git rm test.java
git commit -m '提交描述'
git commit -a -m '提交描述'

# 没有commit的文件的difference
git diff

# 版本回退，版本号没必要写全，前几位就可以了
git reset --hard commit_id

# 回退到上一个版本，HEAD^上一个版本，HEAD^^上上一个版本
git reset --hard HEAD^

# 命令记录
git reflog
```
## 远程分支

```
git remote 
git remote add <name> <url>
git remote remove <name> <url>

# 查看我们当前项目有哪些远程仓库
git remote -v

git remote show origin 
git remote rename
git remote rm
```

## Git 别名

```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
$ git config --global alias.last 'log -1 HEAD'
$ git config --global alias.psm 'push origin master'
$ git config --global alias.plm 'pull origin master'
```
## 分支branch

```
# 创建分支
git branch <branch_name>

# 删除分支
git branch -d <branch_name>
git branch -D 

#查看分支
git branch

# 创建并切换到该分支
git checkout -b <branch_name>

# 切换分支
git checkout <branch_name>

# 撤销修改
git checkout -- readme.txt

# git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区
git reset HEAD readme.txt

git push origin --delete

# 合并分支
git merge 
git rebase master

```
## stash

```
# 把没有commit的代码暂存起来
git stash

git stash list

# 还原代码
git stash apply

# 删除stash记录
git stash drop

# 还原代码以及删除stash记录
git stash pop

# 清空所有暂存区的记录
git stash clear
```

- master 保留完全稳定的代码
- develop
- hotfix
- bugfix
- release

## 使用Git遇到的问题

### refusing to merge unrelated histories

```bash
# 在命令后面加上 --allow-unrelated-histories
git pull origin master --allow-unrelated-histories
```

### 解决git push错误

The requested URL returned error: 403 Forbidden while accessing

答案：私有项目，没有权限，输入用户名密码，或者远程地址采用这种类型：

vi .git/config # 将[remote "origin"]      url = https://github.com/用户名/仓库名.git

修改为：[remote "origin"]    url = https://用户名:密码@github.com/用户名/仓库名.git

### 中文显示为数字的解决方法

```bash
git config --global core.quotepath false
```

