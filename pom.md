Pom:
===
1.maven is build multi-models of instruction project,has three part,such as jar,war,pom.so,overview pom.xml file--
  
  parent :继承，复用。 
  
  dependencies :依赖其它项目。
   
  dependenciesManagement :依赖管理，一般用于pom项目，默认使用版本。
   
  repositorcies:用来配置maven的远程仓库的信息。
  
  modules :聚合模块
   
  properties :用于简介表示pom文件元素标签的信息，ex：{project.version}表示项目的版本。
  
  import : 用于dependenciesManagement下面，表示引入其它pom的dependenciesManagement的配置。
  
