1.gitignore文件简介：
  
  通常由于系统会生成一些自定义文件，但是对于我们并不需要，为了简化每次都要删除的任务，感觉麻烦，事先定义好这些要忽略的文件会省很多事情，上传时不用在关心
  这个问题 
  
2[.gitignore文件模版](https://github.com/github/gitignore)

3.gitconfig文件简介：

  git软件初次创建本地仓库会默认生成一个gitconfig的配置文件（但是分全局和单个），这个文件中会有一些默认的配置参数随初始化而生成，这些参数是可能根据电脑系统的信号自动生成的，重要的是有些很友好的配置参数我们需要知道，其中有：消除换行警告，简化bash命令中的复杂命令，设置别名代替，不在重复登陆用户的凭证
  
  1).换行：对于window系统是需要使用这个命令配置下载文件参数：
  
      git config --global core.autocrlf true（widnow默认）
      git config --global core.safecrlf false（window需要添加的）
      
      解释：cr 回车 ／r --> return 
           lf 换行 ／n --> newline
           
           linux 中使用git只需要 ／n
           window 只需要 ／r/n
           mac OS 只需要 ／r
  
  2).别名：例如使用这个命令：
  
      git config --global alias.co commit(以前打git commit -m “”现在只需要打 git co -m “”)            
      log的别名设置：log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
      同样我们找到gitconfig文件进行vim写入来设置也是可以的
      
  3).凭证：使用这个命令：
      
      git config --global credential.helper wincred
      
