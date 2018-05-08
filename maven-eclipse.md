main:use maven error with eclipse:
=================================
1.发生项目：spring——boot

2.项目描述：运行spring-boot-web：error

3.error：（）

4.诊断：maven导入工程，已经熟悉pom.xml配置文件，但是发现错误的不能加载spring-boot的一个模版，模版解析RquestMapping（），发现是jar包错误，

确定maven仓库是jar包下载问题，重新下载，建议不要代理，在进行sha1校验。

5.从中新接触：看一个项目的配置，首先alt+enter进入，可以看一些版本或结构（project facetd／project assembly等），然后是view（navigate），

帮助看项目的最终出来的模型，那么里面有一个文件.classpath，用于文件的路径配置，这个和path build config结合配置或检查，ex：

修改此处：

  <classpathentry exported="true" kind="con" path="org.eclipse.m2e.MAVEN2_CLASSPATH_CONTAINER">
		<attributes>
			<attribute name="maven.pomderived" value="true"/>
			<attribute name="org.eclipse.jst.component.dependency" value="/WEB-INF/lib"/>
		</attributes>
	</classpathentry>

不难看出：

文件的配置信息，可以最后修改，但是不能update maven 或者 maven clean，否者文件配置或路径文件内容会重新定义。

6.新想法，如果要导入自己有的jar包到maven中，可以build path中配置（先添加，在order and exports，最后看navigate）

