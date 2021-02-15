# Git-learn

## Git教程

[廖雪峰](https://www.liaoxuefeng.com/wiki/896043488029600)



[可视化工具](https://www.sourcetreeapp.com/)



## 安装之后的设置

全局设置：

```shell
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
git config --global color.ui true #设置带颜色
git config --global alias.st status #别名设置，global为全局，不加为当前仓库
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit" #彩色日志
```

## 忽略特殊文件

[忽略特殊文件](https://www.liaoxuefeng.com/wiki/896043488029600/900004590234208)



[.gitignore模板](https://github.com/github/gitignore)



```shell
# 排除所有.class文件:
*.class

# 不排除.gitignore和App.class:
!.gitignore
!App.class
```





## 常用命令

```shell
#目录变仓库
git init 

#添加文件
git add <file> 

#提交更改
git commit -m "message" 

#查看当前信息
git status

#查看历史记录
git log
git log --pretty=oneline #一行输出
git log --graph --pretty=oneline --abbrev-commit #带有分支图的信息

#HEAD表示当前版本，上一个版本是HEAD^
#回退到上一版本
git reset --hard HEAD^
#指定某一版本
git reset --hard <commit id>

#记录每一次操作
git reflog

#丢弃工作区修改，用版本库中的文件替换工作区文件
git checkout -- <file>

#撤销暂存区修改，删除在寄存区的修改，常与checkout连用
git reset HEAD <file>

#删除文件
git rm <file>

#储藏当前正在进行的更改
git stash
#查看储藏历史
git stash list
#恢复，不删除储藏区
git stash apply
#恢复删除储藏区
git stash pop
#恢复指定储藏
git stash apply stash@{0}

#提交特定更改到当前分支
git cherry-pick <commitID>



```



## 远程

```shell
#添加ssh密钥
ssh-keygen -t rsa -C "youremail@example.com"

#本地第一次链接远程仓库
git remote add <远程库名> <链接>
#例子
git remote add origin git@github.com:michaelliao/learngit.git
#本地第一次推送，并绑定master分支
git push -u <远程库名> <分支>
#例子
git push -u origin master
#以后的提交命令
git push origin master

#删除远程库
git remote rm origin

#克隆远程库
git clone <链接>

#查看远程库信息
git remote
git remote -v #详细

#绑定远程dev分支和本地dev
git branch --set-upstream-to=origin/dev dev



```



## 分支管理

```shell
#创建dev分支
git branch dev

#创建并切换
git checkout -b <beanch>
git checkout -b dev

#查看分支
git branch

#切换分支
git checkout dev

#合并dev分支到当前分支
git merge dev
#非快速合并，保留分支信息
git merge --no-ff -m "message" <branchID>

#变基合并
git rebase -i #交互式变基


#删除dev分支
git branch -d dev

#创建并切换
git switch -c dev
#切换
git switch master


```



## 标签管理

```shell
#打一个标签
git tag v1.0
git tag v0.9 commitID

#展示标签信息
git show v0.9

#指定标签名
git tag -a v0.1 -m "version 0.1 released" 1094adb

#删除
git tag -d v0.1

#推送一个标签到远程
git push origin v1.0
#推送所有标签到远程
git push origin --tags

#远程删除步骤
git tag -d v0.9
git push origin :refs/tags/v0.9



```

