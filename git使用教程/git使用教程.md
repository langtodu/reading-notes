### 1. 初始配置
在完成Git安装后，在正式使用前需要对git进行配置，一般只需要配置一次即可。常用的配置如下：

-	配置用户名称和电子邮件地址，以下配置用于所有的仓库，属于全局配置。更改的配置文件位于用户主目录下，以后所有的项目都会默认使用这里的配置。如果在特定的目录中使用其他名字或电子邮件，只需要去掉--global选项重新配置即可，新的配置保存在当前项目的.git/config文件里。    

		```   
		$ git config --global user.name "[name]"	  
		$ git config --global user.email "[email address]"  
		 ##查看配置信息  
		$ git config --list  
		```
	
-	其他配置 

		``` 
	     ##设置git默认使用的文本编辑器，如vi、vim、emacs等  
		$ git config --global core.editor emacs  
		 ##设置差分分析工具，如vimdiff、tkdiff、gvimdiff等  
		$ git config --global merge.tool vimdiff  
		```

### 2. 创建仓库（选择GitHub作为远程仓库）
#### （1） 通过在本地初始化一个仓库
git init用于在本地初始化一个git仓库，Git 的很多命令都需要在 Git 的仓库中运行，所以 git init 是使用 Git 的第一个命令。每创建一个仓库就需要执行一次该命令。

##### 使用方法
使用当前目录作为git仓库，只需要直接执行下面命令。执行后Git仓库会生成一个.git目录，该目录包含了资源的所有元数据，其他的项目目录保持不变。

```
$ git init
```

使用指定目录作为git仓库，执行下面命令，会在reponame目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。

```
$ git init reponame
```

#### （2） 通过克隆已有的仓库来作为一个仓库
如以下命令，git会在当前目录下创建一个名为libgit2的目录，并在里面初始化.git文件夹，并从远程仓库拉取所有的数据放在.git文件夹内，然后从中读取最新版本的文件的拷贝。 如果你进入到这个新建的 libgit2 文件夹，你会发现所有的项目文件已经在里面了，准备就绪等待后续的开发和使用。

```
$ git clone https://github.com/libgit2/libgit2
```
执行下面的命令会与上面的命令产生相同的效果，不过在本地创建的仓库名字变为 mylibgit。

```
$ git clone https://github.com/libgit2/libgit2 mylibgit
```

### 3. 使用仓库（选择GitHub作为远程仓库）
#### （1） 使本地仓库与远程仓库建立连接
当创建的仓库为空时，需要添加一些内容然后才能上传到远程仓库，否则报错。注：远程仓库的名称一般默认为origin。

	```
	echo "# reading-notes" >> README.md   
	git add README.md
	git commit -m "first commit"
	git remote add origin git@github.com:*.git
	git push -u origin master
	```

### 4. git常用命令详解
#### git remote
	```
	作用：关联远程仓库。
	用法： 
	-	查看关联的远程仓库的名称： git remote  
	-	添加远程仓库的关联： git remote add origin <url>  
	-	删除远程仓库的关联： git remote remove <name>
	-	修改远程仓库的关联： git remote set-url origin <newurl>
	```
#### git status
	```
	作用：查看在上次提交之后仓库是否有修改。
	用法： git status
	```
#### git diff
	```
	作用：查看执行 git status 的结果的详细信息。 git diff 命令显示已写入缓存与已修改但尚未写入缓存的改动的区别。
	用法： 
		-	尚未缓存的改动：git diff
		-	查看已缓存的改动： git diff --cached
		-	查看已缓存的与未缓存的所有改动：git diff HEAD
		-	显示摘要而非整个 diff：git diff --stat
	```
#### git add
	```
	作用：用于将该文件添加到缓存。  
	用法： git add filename
	```
#### git commit
	```
	作用：用于将缓存区内容添加到仓库中。  
	用法： git add filename
	```
#### git push
	```
	作用：用于将本地库中的最新信息发送给远程库。  
	用法： git push -u origin 远程分支名
	```
#### git pull
	```
	作用：用于将从远程获取最新版本到本地，并自动merge。  
	用法： git pull 链接
	```
#### git fetch
	```
	作用：用于将从远程获取最新版本到本地，不会自动merge。  
	用法： git fetch <repository>
	```
#### git merge
	```
	作用：用于从指定的commit(s)合并到当前分支，用来合并两个分支。  
	用法： git merge branchname
	```
#### git reset
	```
	作用：用于撤销提交。  
	用法： 
	-	回退一个版本,且会将暂存区的内容和本地已提交的内容全部恢复到未暂存的状态,不影响原来本地文件： git reset (–mixed) HEAD~1 
	-	回退一个版本,不清空暂存区,将已提交的内容恢复到暂存区,不影响原来本地的文件： git reset –soft HEAD~1   
	-	回退一个版本,清空暂存区,将已提交的内容的版本恢复到本地,本地的文件也将被恢复的版本替换： git reset –hard HEAD~1 
	```
#### git rm
	```
	作用：从工作目录中手工删除文件。  
	用法： 
	-	从Git中移除某个文件，并且是从已跟踪文件清单中移除，然后提交： git rm filename
	-	如果删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项 -f： git rm -f filename
	-	如果把文件从暂存区域移除，但仍然希望保留在当前工作目录中，换句话说，仅是从跟踪清单中删除： git rm --cached filename
	```
#### git branch
	```
	用作用：分支命令。  
	用法： 
	-	查看分支： git branch
	-	创建分支： git branch branchname
	-	删除分支： git branch -d branchname
	```
#### git checkout
	```
	用作用：切换分支。  
	用法： git checkout branchname
	```

### 参考来源
[1] [git-菜鸟教程](http://www.runoob.com/git/git-tutorial.html)  
[2] [git教程](https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E8%8E%B7%E5%8F%96-Git-%E4%BB%93%E5%BA%93)  
[3] [Github 简明教程](http://www.runoob.com/manual/github-git-cheat-sheet.pdf)  
  