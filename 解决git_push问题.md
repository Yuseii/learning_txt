### Linux git push问题
error: The requested URL returned error: 403 Forbidden while accessing https://github.com/Yuseii/AndroidLesson.git/info/refs

fatal: HTTP request failed  
  
#### 解决办法  
1.打开git配置文件
 
	vim .git/config 
配置文件如下  

	[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
	[remote "origin"]
	    fetch = +refs/heads/*:refs/remotes/origin/*
	    url = https://github.com/Yuseii/AndroidLesson.git
	[branch "master"]
	    remote = origin
	    merge = refs/heads/master

2.把remote "origin"的url  
  
	[remote "origin"]
    fetch = +refs/heads/*:refs/remotes/origin/*
    url = https://github.com/Yuseii/AndroidLesson.git  
改为  

	[remote "origin"]
    fetch = +refs/heads/*:refs/remotes/origin/*
    url = https://Yuseii@github.com/Yuseii/AndroidLesson.git

也就是说，在url中添加 userid@  

	

	