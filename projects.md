1.eclipse环境下项目迁移问题：
  ```
  1.alt + enter 进入项目配置选项，
  2.查看Project Facets（文件配置）和java Compiler（本地机器配置）version是否一致，
  3.更改为一致
  
  ```
 2.不能获取资源配置：
   ```
   1.检查Build Path中是否存在目标资源
   2.检查Build Path中是否version正确
   
   ```
 3.maven创建项目报错：Classpath entry org.maven.eclipse.MAVEN2_CLASSPATH_CONTAINER will not be exported or published
 ```
 eclipse打开navigator，修改setting.xml文件内容，如下。
 <classpathentry kind="con" path="org.maven.ide.eclipse.MAVEN2_CLASSPATH_CONTAINER">  
    <attributes>  
        <attribute name="org.eclipse.jst.component.dependency" value="/WEB-INF/lib"/>  
    </attributes>  
	</classpathentry>
 然后可以在alt+enter中（java build path／deployed assembly）可以发现改变。
 ```
 ···后续
 
