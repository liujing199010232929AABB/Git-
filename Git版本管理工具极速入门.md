# Git版本管理工具极速入门

## Git的介绍以及安装 

### 1.Git的介绍

#### 1.1git是什么

git是一种版本控制器

一个快速的分布式版本控制系统（工具），支持该工具的网站有Github等。

更直白说，团队开发时，管理代码的软件

面试容易被问到的一个东西

#### 1.2安装

git在Linux,Mac,Win下都可以安装

Window环境：

到https://git-for-windows github.io/下载软件，双击一路"Next"安装完毕

Linux环境安装git:

```git
#ubuntu.debian#
$sudo apt-get install git
```

centos.redhat系统

```
#yum install git
```

#### 1.3自报家门

人在江湖岂能没有名号

开源教主Richard Mathew Stailman的江湖名号RMS

在你用git之前，要先报家门，否则代码不能提交

```
$ git config -- global user.name #你是谁
$ git config -- global user.email #怎么联系你
$ git confit -- list
```

#### 1.4代码管理

##### 1.4.1创建版本库

```git
$ cd D:/
$ mkdir test
$ git init
```

注意：

不要把仓库建在中文目录下，可能出问题

.git是个隐藏目录，不要乱碰(你的每一次修改代码修改它能帮你记录着)

##### 1.4.2

添加文件在D:/test 目录下，用你喜欢的编辑器(sublime/phpstrom等)

开发你的程序，比如：index.php

```php
echo "PHP中文网！真好！"
```

编辑PHP文件后#git status,查看仓库状态

实例如下：

```
$ git status
```

可见此时git发现有一个新文件，但并没有把此文件纳入管理，我们需要两步让git仓库管理index.php

```
$ git add index.php
$ #把index.php提交到暂存区
$ git commit -m "新建index.php"
$ #把index.php提交到版本库
```

实例如下：

```
$ git add index.php
$ git commit -m "新建index.php"
```

##### 1.4.3修改文件

如果修改了文件，也不要忘记提交版本库

这个过程和添加文件是一样的一样是需要两步，让git仓库记录此次

实例如下：

```
$ git add index.php
$ #把index.php提交到暂存区
$ git commit -m "改了第2行"
$ #把index.php提交到版本库
```

##### 1.4.4删除文件

用rm命令删除文件，并直接commit提交到版本库 例如：先创建一个foo.php供练习删除用

实例如下：

```
$ touch foo.php #创建foo.php
$ git add foo.php
$ git commit -m "练习使用"
$ ls
foo.php index.php

#开始删除
$ git rm foo.php
rm 'foo.php'

$ git commit -m "删除foo.php"
[master e4dc37c]删除foo.php
1 file changed,0 insertions(+),0 deletions(-)
delete mode 100644 foo.php

$ ls
index.php
```

#### 1.5远程仓库

经过前面的练习，我们在本地的仓库管理代码已经比较熟练了

但如果是团队开发如何配合起来呢？

我们可以把版本仓库放在互联网上

开发者把自己最新的版本推到线上仓库

同时，把线上仓库的最新代码，拉到自己本地

这样，就可以配合工作了

##### 1.5.1注册git在线仓库的账号

国外：http://www.github.com

国内：http://git.oschina.net

github.com也是目前程序员的装备利器，在github上挂个项目，逼格瞬间就提升两三倍

不过由于国外网站，速度不咋样

处于学习方便，我在oschina.net给大家演示

##### 1.5.2创建项目

在oschina注册后，"新建项目"，我们先建一个测试项目叫test

oschina为此项目提供的仓库地址有2个

http地址：https://gitee.com/lge244/lianxi.git

ssh地址：git@gitee.com lge244/xianxi.git

##### 1.5.3把代码推到远程仓库

推 push

- 为本地库添加远程库

  ​	$ git remode add origin 地址--

  ​	意思是添加1个远程库，代号是origin地址是https://...test.git

  ​	origin是别名的意思

- push退代码

  ​	$ git push origin master

  ​	意思是把本地的版本(默认是master)推到代号为origin的远程库区

  ​	这个过程会让你输入用户名密码，即你注册时的账户密码

#### 2.1工作区和版本库

如果你想更清晰的学习git,你必须要了解3个重要区域

- 工作区，即开发者的工作目录
- 暂存区，修改已被记录，但尚未录入版本库的区域
- 版本库，存储变化日志及版本信息

