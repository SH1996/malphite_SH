maven.org(联通网络下不能访问)：
==========================
```
maven联通网络下中央仓库不能访问的解决办法
2012年07月08日 15:59:32
阅读数：62004
最近刚开始学习maven工具，下载解压完毕，环境变量配置完毕，运行如下命令尝试快速构建一个maven项目：

mvn archetype:generate

结果就有问题：

[INFO] Scanning for projects...
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.4.1/maven-clean-plugin-2.4.1.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-clean-plugin:2.4.1: Plugin org.apache.maven.plugins:maven-clean-plugin:2.4.1 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-clean-plugin:jar:2.4.1
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-install-plugin/2.3.1/maven-install-plugin-2.3.1.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-install-plugin:2.3.1: Plugin org.apache.maven.plugins:maven-install-plugin:2.3.1 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-install-plugin:jar:2.3.1
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-deploy-plugin/2.5/maven-deploy-plugin-2.5.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-deploy-plugin:2.5: Plugin org.apache.maven.plugins:maven-deploy-plugin:2.5 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-deploy-plugin:jar:2.5
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-site-plugin/2.0.1/maven-site-plugin-2.0.1.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-site-plugin:2.0.1: Plugin org.apache.maven.plugins:maven-site-plugin:2.0.1 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-site-plugin:jar:2.0.1
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-antrun-plugin/1.3/maven-antrun-plugin-1.3.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-antrun-plugin:1.3: Plugin org.apache.maven.plugins:maven-antrun-plugin:1.3 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-antrun-plugin:jar:1.3
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-assembly-plugin/2.2-beta-5/maven-assembly-plugin-2.2-beta-5.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-assembly-plugin:2.2-beta-5: Plugin org.apache.maven.plugins:maven-assembly-plugin:2.2-beta-5 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-assembly-plugin:jar:2.2-beta-5
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.1/maven-dependency-plugin-2.1.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-dependency-plugin:2.1: Plugin org.apache.maven.plugins:maven-dependency-plugin:2.1 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-dependency-plugin:jar:2.1
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-release-plugin/2.0/maven-release-plugin-2.0.pom
[WARNING] Failed to retrieve plugin descriptor for org.apache.maven.plugins:maven-release-plugin:2.0: Plugin org.apache.maven.plugins:maven-release-plugin:2.0 or one of its dependencies could not be resolved: Failed to read artifact descriptor for org.apache.maven.plugins:maven-release-plugin:jar:2.0
Downloading: http://repo1.maven.org/maven2/org/codehaus/mojo/maven-metadata.xml
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-metadata.xml
[WARNING] Could not transfer metadata org.apache.maven.plugins/maven-metadata.xml from/to central (http://repo1.maven.org/maven2): Error transferring file: Connection timed out: connect
[WARNING] Could not transfer metadata org.codehaus.mojo/maven-metadata.xml from/to central (http://repo1.maven.org/maven2): Error transferring file: Connection timed out: connect
Downloading: http://repo1.maven.org/maven2/org/codehaus/mojo/maven-metadata.xml
Downloading: http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-metadata.xml
[WARNING] Could not transfer metadata org.apache.maven.plugins/maven-metadata.xml from/to central (http://repo1.maven.org/maven2): Error transferring file: Connection timed out: connect
[WARNING] Could not transfer metadata org.codehaus.mojo/maven-metadata.xml from/to central (http://repo1.maven.org/maven2): Error transferring file: Connection timed out: connect
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 3:30.786s
[INFO] Finished at: Sun Jul 08 15:55:29 CST 2012
[INFO] Final Memory: 2M/121M
[INFO] ------------------------------------------------------------------------
[ERROR] No plugin found for prefix 'archetype' in the current project and in the plugin groups [org.apache.maven.plugins, org.codehaus.mojo] available from the repositories [local (D:\project\.mave_repo\repo), central (http://repo1.maven.org/maven2)] -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/NoPluginFoundForPrefixException

 

这种hello world级别的操作出错，就怀疑是网络问题，于是让其他同事帮我尝试访问http://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.4.1/maven-clean-plugin-2.4.1.pom地址，发现完全没问题，感觉异常郁闷。后来网上查了一下，发现是因为联通网络下，无法访问maven.org网站。解决此问题理论上有两个办法，一个是在maven的配置文件中设置代理，另一个是在maven的配置文件中设置联通网络下，能够访问的中央仓库的mirrors。因为也不好找稳定的代理，我就在网上搜索了两个可用的mirror站点，配置方式如下：

1、打开maven配置文件(maven安装目录下的conf目录下的settings.xml文件)

2、搜索mirrors关键字，如果注释说明的下方没有  <mirrors>节点，则建立mirrors节点，带mirrors节点的所有配置如下(复制下面的内容，粘贴到配置文件中即可)：

   <mirrors>
    <!-- mirror
     | Specifies a repository mirror site to use instead of a given repository. The repository that
     | this mirror serves has an ID that matches the mirrorOf element of this mirror. IDs are used
     | for inheritance and direct lookup purposes, and must be unique across the set of mirrors.
     |
    <mirror>
      <id>mirrorId</id>
      <mirrorOf>repositoryId</mirrorOf>
      <name>Human Readable Name for this Mirror.</name>
      <url>http://my.repository.com/repo/path</url>
    </mirror>
    -->
     <mirror> 
           <id>ibiblio.org</id> 
           <name>ibiblio Mirror of http://repo1.maven.org/maven2/</name> 
           <url>http://mirrors.ibiblio.org/pub/mirrors/maven2</url> 
           <mirrorOf>central</mirrorOf> 
           <!-- United States, North Carolina --> 
     </mirror>
     <mirror>  
         <id>jboss-public-repository-group</id>  
         <mirrorOf>central</mirrorOf>  
         <name>JBoss Public Repository Group</name>  
         <url>http://repository.jboss.org/nexus/content/groups/public</url>  
     </mirror>  
        
  </mirrors>
```
