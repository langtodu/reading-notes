### 1. git简介  
git是Linux开源社区在2005年基于Linux内核开发的一个开源的分布式版本控制系统<sup>[1]</sup>（Distributed Version Control System，简称 DVCS），版本控制是一种记录一个或若干个文件内容变化，以便将来查阅特定版本修订情况的系统。在分布式版本控制系统中，客户端并不只提取最新版本的文件快照，而是把代码仓库完整地镜像下来。 这么一来，任何一处协同工作用的服务器发生故障，事后都可以用任何一个镜像出来的本地仓库恢复。 因为每一次的克隆操作，实际上都是一次对代码仓库的完整备份。这种方式避免了集中版本控制系统因单点故障而造成的无法提供服务的问题。

<center>![](https://images2015.cnblogs.com/blog/1098543/201701/1098543-20170123152215831-1107675805.jpg)</center>
<center> 分布式版本控制<sup>[2]</sup></center>

### 2. git工作流程
基本概念：  

-	工作区：本地的目录文件。
-	暂存区（缓存区）：一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
-	版本库：工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。

<center>![](http://www.worldhello.net/wpfiles/2010/11/git-stage.png)</center>
<center> 各区的工作关系<sup>[3]</sup></center>


工作区、暂存区、版本区的图解：

-	新建文件--->Untracked
-	使用add命令将新建的文件加入到暂存区--->Staged
-	使用commit命令将暂存区的文件提交到本地仓库--->Unmodified
-	如果对Unmodified状态的文件进行修改---> modified
-	如果对Unmodified状态的文件进行remove操作--->Untracked

### 参考来源
[1] [关于版本控制](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%85%B3%E4%BA%8E%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6)  
[2] [git分布式版本控制系统](https://blog.csdn.net/umke888/article/details/54767243)
[3] [git 工作区 暂存区 版本区](https://www.cnblogs.com/qdhxhz/p/9757390.html)  