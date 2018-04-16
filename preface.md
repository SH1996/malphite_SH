github的出现：版本管理系统，管理文件的更新和版本的控制，最早是由file-branch模式，转变到集中控制版本模式，直到接近现在的分布式模式，还有git和linux
的一个历史，简单的说，git是经典的版本控制软件，可以在很多网址搭建中央仓库（团队模式），分为一个本地仓库和一个中央仓库，创建本地仓库的工具有：git bash
，git GUI，git cmd，sourcesTree，Egit，中央仓库有：开源中国，github，coding等。。。。


github的配合：在github的传输仓库中有两个重要的文件，一个是.gitignore和另一个.gitconfig，分别作用是上传时忽略的文件（github上有非常的模版，很全的
通配符忽略文件的书写语法），和git仓库的配置（用户名和密码，换行警告，简化的别名，上传的凭证）

三个区，四个状态：
工作区，暂存区，本地仓库，
Staged（被暂存的），unTracked（没有被跟踪的），modify(修改的)，Unmodify（没有被修改的）
工作区中的数据有modify和untracked，暂存区中的状态是staged，本地仓库中的状态是unmodify
转换命令：add comit checkout
