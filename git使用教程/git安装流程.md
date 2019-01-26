### 1. Linux上安装
Git 的工作需要调用 curl，zlib，openssl，expat，libiconv 等库的代码，所以需要先安装这些依赖工具。

Debian/Ubuntu Git 安装命令为：  

	```
	$ apt-get install libcurl4-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev  
	$ apt-get install git  
	## 查看git版本  
	$ git --version  
	```

Centos/RedHat Git 安装命令为：

	```
	$ yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel  
	$ yum -y install git-core
	```

### 2. Mac上安装
下载官方维护的[Git OSX安装程序](https://git-scm.com/download/mac)，进行安装。

### 3. Windows上安装
下载git安装程序，点击安装，安装完成之后，会出现git相关工具： 
 
-	Git Bash： Linux风格命令行，可以使用Linux和windows命令，并且在Git CMD的基础上增添了一些新的功能与命令，一般操作使用Git Bash。  
-	Git CMD： windows风格的命令行，可以使用windows命令。  
-	Git GUI： 客户端风格，代替命令行。

### 参考来源
[1] [Git 安装配置](http://www.runoob.com/git/git-install-setup.html)  
[2] [安装 Git](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)  