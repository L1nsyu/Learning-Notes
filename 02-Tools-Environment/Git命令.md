# git

git 覆盖本地文件

如果你想将本地 Git 仓库中的所有文件都覆盖到本地文件系统中，可以使用以下命令：

```Plain Text
git checkout .
```

该命令会将 Git 仓库中的所有文件都还原到最近一次提交的状态，并覆盖本地文件系统中的文件。注意，这个命令会清除你在本地的所有未提交的更改，因此请谨慎使用。

如果你想将远程仓库完全覆盖本地 git 仓库，你可以使用 `git fetch --all` 命令从远程仓库获取所有分支的最新状态

然后使用 `git reset --hard origin/master `命令重置本地仓库到远程仓库的状态。

注意，这将丢失本地仓库中未提交的所有更改，因此请确保在执行此操作！

\================================================

下载git：

`sudo apt-get install git`

sudo chmod 600 \~/.ssh/id\_rsa

sudo chmod 755 \~/.ssh

ssh密钥生成`ssh-keygen`

共钥地址：

`cat ~/.ssh/id_rsa.pub `

配置git信息：

```bash
git config --global user.name Leivzy
git config --global user.email leivzy@163.com
git config --list

git config --global user.name Leivmox
git config --global user.email leivmox@gmail.com
git config --list

```

git仓库：

git@github.com:Leivzy/code\_2023.git

`git remote add origin` + ssh下载地址

```Plain Text
git remote add origin git@gitee.com:leivzy/code_2023.git
git remote add origin git@github.com:leivmox/code_2023.git

```

`git pull origin master`

git@github.com:Leivzy/code\_2023.git

关联本地master和远程master，简化命令：

`git branch --set-upstream-to=origin/master master`

`git branch --set-upstream-to=origin/main main`

如果本地默认分支是 `master` 而不是 `main`，可以将 `master` 分支改名为 `main`：

git branch -m master main





> \*\*\*\*\*\*\*\*\*\*\*\*git常用命令\*\*\*\*\*\*\*\*\*\*\*\*

> git init    #初始化仓库

> git clone + ssh路径/https路径   #拷贝一份远程仓库

> git add     #添加文件到暂存区

> git commit -m "备注"     #将暂存区提交至本地仓库

> git push origin master  #将本地分支推送到远程origin的master分支

> git pull  origin master  #从远程仓库拉取最新代码

> #\*\*\*\*\*\*\*\*\*\*\*

> git status             #查看当前仓库状态

> git branch         #查看本地所有分支

> git branch -r   #查看远程所有分支

> git branch -d <分支名>  #删除本地分支

> git branch    #创建分支

> #\*\*\*\*\*\*\*\*

> git checkout   #切换分支

> git merge              #合并分支

> git branch --set-upstream-to=origin/<远程分支名称> <本地分支名称>  #本地分支关联远程分支

> git config --list     #查看git配置信息

> #\*\*\*\*\*\*回滚操作\*\*\*\*\*

> git reset --hard        #已执行git add 但未执行git commit

> #\*\*\*\*\*\*\*\*已提交至本地仓库

> git reset --hard HEAD^   #上个版本回退，不加^是当前版本  执行git commit 未执行git push

> git reset --hard <commit\_id>   #指定版本回退

> #\*\*\*\*\*已git push情况

> git reset --hard HEAD^     #先在暂存区恢复上个版本

> git push -f           #在强制推送是远程仓库，覆盖之前版本

```Plain Text
echo "# ReadmeTest" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:Leivzy/ReadmeTest.git
git push -u origin main
```

* 将.ssh目录的权限设置为700：运行以下命令：`chmod 700 ~/.ssh`；
* 将私钥文件的权限设置为600：运行以下命令：`chmod 600 ~/.ssh/id_rsa`；
* 将公钥文件的权限设置为644：运行以下命令：`chmod 644 ~/.ssh/id_rsa.pub`



gitee:

#### 简易的命令行入门教程:

Git 全局设置:

```Plain Text
git config --global user.name "Leivzy"
git config --global user.email "leivzy@163.com"
```

创建 git 仓库:

```Plain Text
mkdir python
cd python
git init 
touch README.md
git add README.md
git commit -m "first commit"
git remote add origin https://gitee.com/leivzy/python.git
git push -u origin "master"
```

已有仓库?

```Plain Text
cd existing_git_repo
git remote add origin https://gitee.com/leivzy/python.git
git push -u origin "master"
```

git reflog

查看所有分支的所有操作记录

```Plain Text
git reset --hard <commit_hash>
git reset --hard head^
```

\==========================================

为了正确配置.ssh目录及其内涵的文件权限，可以按照以下步骤操作：

```Plain Text
将.ssh目录的权限设置为700：运行以下命令：chmod 700 ~/.ssh；
将私钥文件的权限设置为600：运行以下命令：chmod 600 ~/.ssh/id_rsa；
将公钥文件的权限设置为644：运行以下命令：chmod 644 ~/.ssh/id_rsa.pub。
```

这样做的目的是，只允许当前用户读写.ssh目录和私钥文件，而其他用户只能读取公钥文件，从而保证.ssh目录和密钥文件的安全性。
当然，你可以使用如下命令批量化的处理.ssh权限问题：

chmod 600 \~/.ssh/\* && chmod 644 \~/.ssh/\*.pub && chmod 700 \~/.ssh

————————————————

```Plain Text
                        版权声明：本文为博主原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接和本声明。
```

原文链接：https://blog.csdn.net/bigbaojian/article/details/130255339