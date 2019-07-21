---
layout: post
title:  "Training One: Shell"
date: 2019-07-20 23:33:33 +0800
categories: Training
description: 这是一份正经培训教程
---

# 前言

> UNIX操作系统最早由KenThompson、Dennis Ritchie和Douglas McIlroy于1969年在AT&T的贝尔实验室开发的多用户、多任务、支持多种处理器架构的分时操作系统（分时操作系统将系统处理机时间与内存空间按一定的时间间隔，轮流地切换给各终端用户的程序使用）。

> Shell是用户与内核进行交互的命令解释器。

当你搜索“Shell教程”，万能的搜索引擎将指引你通往知识的海洋，网上的大神们已经为你精心准备了各式套餐，さあ、勉強しましょう！（现在一起学习吧！）  
  
那么问题来了，为何才疏学浅的我又要写这么一个教程呢？的确，那么多Shell教程随便一份拿来给新人看不就好了，何必花这些时间写自己的Shell教程。然而我想说，就当是自己的一种尝试，希望能通过不一样表达方式将Shell更容易地被学习和理解。  
  
看看标题后的两个词条，显然是从什么地方复制过来的，一上来就一堆专业名词，这和别的教程有啥区别，ちょっと待って（且慢），这是前言怎么也得装的专业一点啊！  
  
本教程纯属虚构，如有雷同，纯属巧合=。=

# 来自神秘总部的邮件

> 小白同学，邀请你参加来自总部的审核任务，请访问远程服务器（ACCOUNT:shiro, IP:233.233.233.233, PWD:GeniusCannotSeeThePassword）以获得更多的资讯。

咳咳咳，一大早就收到这种邮件，不知道是什么样的心情，虽然我是姓白，一上来就叫我小白是几个意思！emm，大概是我简历信息填写的名字是しろちゃん（白酱）。

首先让我看看这神秘的总部服务器上给我准备了什么任务。

```Bash
shiro@ubuntu:~$ssh shiro@233.233.233.233
shiro@233.233.233.233's password
...
...
...
shiro@233.233.233.233:~$ls -l
total 0
```

这是和我开玩笑呢，说好的更多资讯到哪里去了？让我试试显示隐藏内容。

```Bash
shiro@233.233.233.233:~$ls -al
total 12
drwxr-xr-x 2 shiro shiro 4096 Jul 20 23:33 .
drwxr-xr-x 2 shiro shiro 4096 Jul 20 23:33 ..
drwxr-xr-x 2 shiro shiro 4096 Jul 20 23:33 .mission
```

还是被我发现了吧，搞个隐藏目录就以为我找不到吗？真以为我是小白啊。

```Bash
shiro@233.233.233.233:~$cd .mission
shiro@233.233.233.233:~/.mission$ls
mission0
shiro@233.233.233.233:~/.mission$cat mission0
小白同学，不错哟，居然被你发现了。
恭喜发现mission0，下一个任务是mission1，快去寻找吧~
```

原来是闯关游戏，那就奉陪到底。

```Bash
shiro@233.233.233.233:~/.mission$sudo find / -name *mission1*
/YouGotIt/mission1
shiro@233.233.233.233:~/.mission$cat /YouGotIt/mission1
小白同学，请将这个任务文件移动到上一条线索所在目录，并将包含该文件的文件夹删除。
```

小菜一碟，让我先看看这目录下到底还有些啥。

```Bash
shiro@233.233.233.233:~/.mission$ls /tmp/YouGotIt/
mission1  mission2
shiro@233.233.233.233:~/.mission$mv /tmp/YouGotIt/* .
shiro@233.233.233.233:~/.mission$rm -fr /tmp/YouGotIt/
```

还好小心驶得万年船，没有一股脑把文件夹删除，一开始就感受到满满的恶意。

```Bash
shiro@233.233.233.233:~/.mission$cat mission2
小白同学，居然没有把我删掉，看好你哦~
请创建~/.mission/info/system目录，将/proc/cpuinfo复制到该目录下；
获取“model name”，将重复的信息过滤后输出到~/.mission/info/system/modelinfo文件中。

本次任务结束，等待后续邮件吧~
```

先完成任务吧，不知道这个总部想玩啥花样。

```Bash
shiro@233.233.233.233:~/.mission$mkdir -p info/system
shiro@233.233.233.233:~/.mission$cp /proc/cpuinfo ./info/system
shiro@233.233.233.233:~/.mission$cat info/system/cpuinfo | grep 'model name' | uniq > info/system/modelinfo
shiro@233.233.233.233:~/.mission$exit
```

未完待续……
