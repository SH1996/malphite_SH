GIT_NEXT:
========

[git_graph](./git_graph.png)
=============================

  1).git graph: 
  
     a.git -- 三个区，四个状态，本地和远程，仓库，暂存和工作区，HEAD含义，分支和提交记录的图形关系，版本使用和Tag 
     
     b.operations -- add ， commit ， checkout ， reset ， pull ， push ， branch ， tag ， clone ， fetch ， rebase ，show ，merge
     
     c.记忆图：上图超链接
     
     d.DEMO_:
           
           1.首先git clone https://git@github.com/SH5511/TEST克隆一个简单仓库, 
           2.然后cd 到 TEST目录,
           3.echo "111" >> a.txt , git add a.txt , git commit -m "docs(master):initalizate a.txt",
           4.再echo "222" >> a.txt , git add a.txt ,
           5.再echo "333" >> a.txt
           6.此时，通过git status（三个区和四个状态的说明） , git log（提交日志） , git diff（比较三个区差异）【有参数后面说明】可以证明三个工作区和四个状态 ,
           7.git checkout HEAD~1 , git diff , git diff --cached ,git HEAD , git log --pretty=oneline , git reset --hard 第三条的哈希值，
           8.git reset --soft HEAD~1 ,git log --pretty=oneline , git reset --hard 第三条的哈希值  , 
           9.git checkout -b dev , git checkout master , git branch -d dev , git tag TTT HEAD~1 , git show TTT
           10.说明以上操作：只要目的是比较git checkout 和 git reset 之间的差异，为了比较这两个命令行，整合过程几乎使用到了大多数本地操作，一个实例，
           可以说明对git内部结构的认识，过程，含义
           11.重点说明（对以上不了解的地方将会明朗）: 
               ..
               ..一个仓库每一次提交获得的哈希值都是唯一值的，可以通过这一点来回撤到任何想要回撤的位置，没有不可能
               ..
               ..HEAD是当前分支的最新位置，每提交一次或者合并时都会更新HEAD的位置
               ..
               ..每一个命令都是一种含义，后面参数只是细微的区别不同，但还是前面的大含义，比如：git reset --cached 和 git reset HEAD就是回撤后文件在
               暂存区和工作区是否存在，这个reset回撤主要针对commit而言的
               ..
               ..不同种命令后面参数很多，但是很像英语语法，命令有语法结构，参数有不同含义，大致：git <大命令> --参数 <哈希值等代表提交位置的信息> 
               ..
               ..图解 Git：http://marklodato.github.io/visual-git-guide/index-zh-cn.html
               
           
        
     
     
     
     
     
