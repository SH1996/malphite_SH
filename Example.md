git命令：
=======

# 打印所有的子命令：
  git | git help -a
  
# 查看团队协作的提交：
  blame <file name> | blame -L 100,10 <file name>
  
# 清除git仓库档案：
  git clean -n(列出档案) | git clean -f(真正删除) | git clean -x(连gitignore中的档案也删除)
  
# 简短的信息；
  git status -sb
  
# 添加／删除／提交／坠下／移动改名
  git add || git commit -am "" || git rm || git vm
  
# 一个文件多个位置多次提交
  git add -p a.txt(基于这个命令可以说明：github是基于修改变更的来操作的，而不是基于文件的)
  输入s
  然后提示需要让入暂存区的修改输入y，不需要输入n
  git diff 查看变更
  最后全部提交：git add .
  
# [提交注解格式书写](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)
 
# 深入git查看信息：
  git status -sb 
  
  git log a.txt -10 查看全部提交列表前10条 
  
  过滤选择的查询提交信息： git log a.txt --grap 条件 
  
  git show HEAD 或者 git show 哈希值  -->查看每一个提交的信息内容 ，还可以，git show HEAD~1 ,表示最后一个提交的前一个提交的信息变更； 
  
# git diff操作： 
  diff是比较仓库中所有修改的变更（包括提交的和暂存区和工作区中的变更），具体比较如下：  
  git diff是比较工作区和暂存区的差距 
  git diff --cached是比较暂存区和提交仓库的差距 
  git diff HEAD是比较工作区和仓库之间的变更 
  git diff 哈希值 哈希值 是比较提交的两个变更之间的差距 
  如果是想在前面的基础之上比较暂存区和提交的某一条变更之间的差异，可以在提交的变更之上添加tag，git tag TTT HEAD~2,然后git diff --cached TTT, 
  那么这就表示暂存区和标记的那个提交变更之间的差异。 

# git reset的回撤 [直观](https://blog.csdn.net/qidi_huang/article/details/53839591)： 
  从提交回撤到暂存区：git reset --soft HEAD~1 
  从暂存区回撤到工作区：git reset HEAD 还有一个命令是回撤到工作区时抛弃工作区存在的文件 git checkout -- files; 
  从提交仓库回撤提交，直接删除：git reset --hard HEAD~1
  回撤远程仓库后强制推上：git push -f  其中-f就是-force（不建议使用，实际中会干扰分布式其他人的仓库混乱） 
  
# 变基操作 
  git rebase -i HEAD～3（其中HEAD～3表示最后提交的前三个提交历史，然后编辑文本变基，变基是更高级的修改提交的历史，可以任意合并提交历史） 
  
# Tag
  
  1.git tag 查看本地tag
  
  2.git tag TTT HEAD -m "message 可有可无"在当前分支添加标签
  
  3.git push origin --tags 推送全部标签
  
  4.git push origin TTT 推送一个标签
  
  5.git tag -d TTT 删除ttt标签
  
  6.git push origin :refs/tagss/TTT 推送删除后的标签，推送上去
  
  7.git tag 查看不到远程标签了
  

