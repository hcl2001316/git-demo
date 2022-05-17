[时光机穿梭 - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/896043488029600/896954074659008)

# 1 git用户签名

首次安装要写 为了区分是谁提交的代码 

```
$ git config --global user.name
Huang ChengLong

```

```
$ git config --global user.email
1774347909@qq.com

```

# 2.初始化本地库

```
$ git init
Initialized empty Git repository in D:/Git-Space/git-demo/.git/

```

# 3 查看本地库状态

git status

# 4 添加暂存区

git add 

```
$ git add hcl.txt
```

# 5 提交本地库

git commit -m 日志信息 file

```bash
$ git commit -m "测试的提交的版本" hcl.txt
```

git reflog

```bash
$ git reflog
bdbf93f (HEAD -> master) HEAD@{0}: commit (initial): 测试的提交的版本
```

git log

```bash
$ git log
commit bdbf93f63388e0e30f790a0fec8580d3cf16e1ed (HEAD -> master)
Author: Huang ChengLong <1774347909@qq.com>
Date:   Sun May 15 20:19:44 2022 +0800

    测试的提交的版本
```

# 6 修改文件

![1652617903243](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652617903243.png)

# 7 版本穿梭

git reset --hard 版本号

![1652618338358](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652618338358.png)

# 8 创建分支 切换分支 修改分支 查看分支 

```
$ git branch hot-fix        #创建分支
```

```
$ git branch -v               #查看分支
```

```
$ git checkout hot-fix      #切换分支
```

# 9 合并分支

git merge 分支名

![1652619589790](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652619589790.png)

# 10 分支冲突解决

如果两个分支修改了同一个文件 那么在合并的时候就发生冲突，需要手动去除文件中的乱七八糟的东西，然后再加入暂存区 提交本地库（注意这时候不能写名字）

![1652621276904](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652621276904.png)

# 11 远程库创建别名

```bash
黄小爷@▒Ƴ▒▒▒ MINGW64 /d/Git-Space/git-demo (master)
$ git remote add git-demo https://github.com/hcl2001316/git-demo.git
```

查看别名

git remote -v

# 12 推送本地库到远程库

将上面的分支推送到远程库 用的是别名 也可以直接写网址

```
$ git push git-demo
```

# 13 拉取远程库

```
$ git pull git-demo master
```

# 14 克隆远程库

```
$ git clone https://github.com/hcl2001316/git-demo.git
```

# 15 团队内协作

![1652692454468](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652692454468.png)

点击settings

![1652692565275](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652692565275.png)

点击add people然后输入加入人的名字，然后把一个链接发给加入人，加入人复制链接访问，同意就行了。

# 16 团队外协作

首先打开人家的代码 然后点击fork存到本地 然后修改后 pull request

别人就收到了 可以决定要不要留下来你的代码。

# 17 ssh免密登录

C:\Users\黄小爷

在这个目录下执行bash

```
$ ssh-keygen -t rsa -C hcl2001316
```

![1652701339345](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652701339345.png)

把这个id_rsa.pub打开复制到github setting 复制到sshkey里面。

# 18 idea集成git环境准备

C:\Users\黄小爷下面

创建git.ignore

```
/target/
*/target/
!.mvn/wrapper/maven-wrapper.jar

### STS ###
.apt_generated
.classpath
.factorypath
.project
.settings
.springBeans
.sts4-cache

### IntelliJ IDEA ###
.idea
*.iws
*.iml
*.ipr
.idea/workspace.xml
.idea/*
### NetBeans ###
/nbproject/private/
/build/
/nbbuild/
/dist/
/nbdist/
/.nb-gradle/

```

.gitconf

```
[user]
	name = Huang ChengLong
	email = 1774347909@qq.com
[http]
	proxy = http://127.0.0.1:31181
	sslVerify = false
[https]
	proxy = http://127.0.0.1:31181
[core]
	excludesfile=C:/Users/黄小爷/git.ignore
```

![1652702585084](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652702585084.png)

# 19 初始化

打开vsc创建一个本地库 默认是本项目

然后右键选择Git进行add  和commit操作

# 20 idea切换版本

![1652704662991](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652704662991.png)

# 21 创建分支 切换分支

![1652704879447](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652704879447.png)

![1652704889833](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652704889833.png)

# 22 合并分支 解决冲突

![1652705657246](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652705657246.png)

如果发生冲突 手动修改

# 23 项目分享到github

![1652706053521](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652706053521.png)

# 24 Push到远程库

![1652706512371](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652706512371.png)

点击这个切换为ssh

![1652706540464](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652706540464.png)

![1652706554085](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652706554085.png)

复制ssh 放进去 选它 点push

# 25 拉取代码

直接pull

# 26 克隆代码

![1652706948453](C:\Users\黄小爷\AppData\Roaming\Typora\typora-user-images\1652706948453.png)

# 27 github项目复制到gitee

在gitee上导入 傻瓜式操作就行了。

# 完结撒花

