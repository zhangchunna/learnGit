#### Git配置

```
$ git config --global user.name  "Your Name"

$ git config --global user.email "xxx@xx.com"
```
> 注意 git config 命令的 --global 参数,用了这个参数,表明你这台机器长的所有Git仓库都会使用这个配置
#### 创建版本库
##### 在当前的目录下创建Git仓库
```
$ git init
```
##### 文件添加到仓库

```
$ git add xxx.txt
$ git commit -m '提交说明'
```
>Git commit -m后面输入的是本次提交的说明,可以输入任何内容,这样就可以冲历史记录方面找到改动记录

>add提交不同文件
然后通过commit把不同的文件一次提交


##### 掌握工作区的状态
```
$ git status
```
##### 查看文件修改内容
```
$ git diff
```
##### 版本回退
```
$ git reset --hard HEAD^
```
- HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id
- 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本
- 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本


### 远程仓库
> 本地Git仓库跟Github仓库之前的传输是通过SSH加密的
1. 创建SSH Key
看看在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash）

```
$ ssh-keygen -t rsa -C "xxx@xxx.com"
```
2.登录Github,打开Account settings,SSH Keys 点击点Add SSH Key，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容 

##### 关联远程仓库
```
$ git remote add origin git@github.com:zhangchunna/learngit.git
```
##### 推送到远程仓库上
```
$ git push -u origin master
```
- 把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程
- 由于远程库是空的，我们第一次推送master分支时，加上了-u参数在以后的推送或者拉取时就可以简化命令
##### 从远程克隆
```
$ git clone git@github.com:zhangchunna/learngit.git
```
