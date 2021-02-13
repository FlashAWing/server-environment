# Git-learn

## Git教程

[廖雪峰](https://www.liaoxuefeng.com/wiki/896043488029600)

## 安装之后的设置

全局设置：

```shell
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
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

#HEAD表示当前版本，上一个版本是HEAD^
#回退到上一版本
git reset --hard HEAD^
#指定某一版本
git reset --hard <commit id>

#记录每一次操作
git reflog
```

https://www.liaoxuefeng.com/wiki/896043488029600/897271968352576