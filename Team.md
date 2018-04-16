GITHUB协议(上传和下载)
======
# 1.本地协议：

    1).克隆本地仓库：/c/wd/test.git
    2).克隆本地仓库，不建议使用file：／／／ git clone file:///c/wd/test.git
    3).添加远程仓库的链接：git remote add origin /c/wd/test.git
    
# 2.GIT协议：
    
    1).git clone git://server_ip/test.git
    2).git remote add origin git://server_ip/test.git
    3).git一般只读，不能写，速度最全，一般配合其他协议使用，一般开通防火墙9418端口。
    
# 3.HTTP协议：
    
    1).和本地协议使用方式一样
    2).每次输入账号密码，开放的80的端口，效率低，公司配置这个协议比较困难。
    
# 4.SSH协议：   

    1).克隆远程仓库：
      git clone ssh://git@github.com/user/test.git
      git clone git@github.com:user/test.git
      
    2).添加远程仓库的链接：
      git remote add origin git@github.com:user/test.git
      
    3).生成RSA密钥对：
      1.ssh-Keygen -t rsa -C "you email";
      2.在github网站添加公钥；
      3.使用SSH协议，克隆仓库，或者添加远程链接
      
# 另加一个命令： git remote -v      
      
