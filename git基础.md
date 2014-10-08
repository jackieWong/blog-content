date: 2014/10/8
category: git


### Git基础
	git init
	git add xxx.txt		//start track, staging
	git commit -m "text file"	//put it in repository
	
	git log
	git status
	
Notice how Git says changes to be committed? The files listed here are in the Staging Area, and they are not in our repository yet. We could add or remove files from the stage before we store them in the repository.

	git add ocotcat.txt
在完成git add以后文件处于staging area



To store our staged changes we run the commit command with a message describing what we've changed. Let's do that now by typing:

git commit -m "Add cute octocat story"

在完成git commit 以后，文件被加入了repository

	git add '*.txt'
使用引号的原因

Wildcards:
We need quotes so that Git will receive the wildcard before our shell can interfere with it. Without quotes our shell will only execute the wildcard search within the current directory. Git will receive the list of files the shell found instead of the wildcard and it will not be able to add the files inside of the octofamily directory.


## Real git codeschool
卡在了 css/目录下地所有文件
git add 'css/*' 不行
使用的命令是 git add css

### git 配置
git config --global user.name jackie
git config --global user.email wstnap@gmail.com
git config --global credential.helper osxkeychain

### 在github上创建自己的库

https://github.com/jackieWong/test.git
git remote add origin https://github.com/jackieWong/test.git

### 推荐在自己的每个库都包含README, LICENSE, and gitignore
