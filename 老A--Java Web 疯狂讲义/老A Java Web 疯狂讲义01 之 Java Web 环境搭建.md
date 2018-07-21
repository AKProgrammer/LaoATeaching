# 《老 "A" -- JAVA WEB 疯狂讲义》

# Java Web 环境搭建

## 一、环境配置

### 1. 相关工具下载

- JDK下载 ： [JDK 官网地址 - http://www.oracle.com](http://www.oracle.com)
- Tomcat下载 ： [Tomcat 官网地址 - http://tomcat.apache.org](http://tomcat.apache.org)
- Eclipse下载 ： [Eclipse 官网地址 - https://www.eclipse.org](https://www.eclipse.org)
- 注 ： 由于网站不定期改版、关于工具下载不在这里做详细介绍，根据自己的需求选在对应的版本下载即可。

### 2. 环境安装

#### JDK 安装与配置
- JDK 环境安装 ： 按照正常安装软件方法安装即可（记住程序安装路径，该路径需配置环境变量，重要！！！）
- JDK 环境变量配置 ： 
	- 向系统环境变量中添加 JAVA_HOME 项，并将变量值设置为JDK安装目录，如：```C:\Program Files\Java\jdk1.8.0_172```
	- 编辑系统或当前用户环境变量 PATH 如果没有则新建，值设置为 "%JAVA_HOME%\bin"
- ***注：由于系统版本不同（Win7、Win8、Win18、Linux、Ubuntu、Uinux、MacOS（OSX）），进入环境变量设置页面的方法也有所不同，所以在此不做详细记录，在这里只需要记录环境变量名称和对应值的设置，具体根据不同系统版本的这是方法，通过百度可以找到对应的答案。***
- JDK 环境测试
	- 开始 >> 运行 >> 输入 cmd >> 回车 （进入命令行模式）
		 在命令行输入 ```java 	-version``` 查看 JDK 版本，运行结果如下图
	![](./images/01/1.png)
	- 在命令行输入 ```javac``` 查看命令执行结果，运行结果如下图
	![](./images/01/2.png)
	- 开始 >> 运行 >> 输入 jmc >> 回车 ， 进入管理工具，运行结果如下图所示
	![](./images/01/3.png)
- ***注：若测试一次出现以上结果，说明 JDK 环境配置成功。另有些书籍中提到需要配置 CLASSPATH 环境变量，在此强调在 1.5 版本以后的 JDK 都不需要再进行配置该环境变量了。网上的资料还有一些出版书籍中依然保留，个人考虑有一下两点原因，原因一：有可能是考虑到有版本向下兼容问题。原因二：很多出版物并非专业技术人会员编写，大多数以抄袭为主，如果是抄袭的话，至今的出版物当中依然保留着该部分内容也就能够得到合理的解释了。个人认为后者的可能性更大一些。在这里对 CLASSPATH 变量的设置则不进行描述，需要使用老版本 JDK 的可以自行百度。至该讲义编写时，JDK版本已经更新到10.1，这里采用的是JDK8版本，如果想要体验新版的，可根据需求自行下载。***

#### Tomcat 安装与配置
- Tomcat 环境安装 与 配置： 按照正常安装软件方法安装即可（需要注意一下几点）
	1. 在 Choose Components 页面选择必要的组件，除 Examples 选项其他选项全选（所有选项全选也可）
	![](./images/01/6.png)
	2. 在Configuration 页面中，前三项端口号为默认值（8005、8080、8009），如果有冲突可以自行修改，若无冲突，不建议修改，在该页面设置用户名和密码，User Name 设置为 “admin”， Password 这是为 “admin”（该用户名、密码可以自定义设置，“admin” 是我的个人习惯，只要你设置的你自己能记得住就 OK ！）
	![](./images/01/7.png)
	3. 在 Java Virtual Machine 页面选择 Java 虚拟机路径，注意这里选择的是 Java 虚拟机的路径，即 jre 的安装目录，并非 jdk 的安装目录。默认情况下 jre 安装目录 与 jdk 安装目录 处于同层级目录下，自行选择即可 如： ```C:\Program Files\Java\jre1.8.0_172``` 这是我的安装路径。
	![](./images/01/8.png)
	4. 在 Choose Install Location 页面记住自己 Tomcat 的安装目录，使用默认即可，该路径后面在配置环境中会用到。
	![](./images/01/9.png)
- Tomcat 环境测试
	1. 启动 Tomcat。在开始菜单中找到 Apache Tomcat X.X Tomcat X 目录中的 Monitor Tomcat 命令启动 Tomcat程序。
	2. 启动成功之后在右下角的系统托盘中将会出现一个 ![](./images/01/4.png) 图标。表示启动成功。
	3. 打开任意浏览器，在地址栏当中输入 “http://localhost:8080” 并进入该地址若出现下图，则说明Tomcat安装成功。
	![](./images/01/5.png)
- ***注 ： 至该讲义编写位置 Tomcat 已经 更新至 9.0 ， 在本讲义中使用的是相对最成熟稳定的 7.0 版本。大家可根据环境需要在官网上下载安装对应的版本。***

#### Eclipse 安装与配置
- Eclipse 安装 ： 将下载好的zip格式压缩包解压缩后存放到自己喜欢的目的地即可。
    - 为了使用方便，可将 eclipse.exe 发送快捷方式到桌面上。
- Eclipse 环境测试 ： 
    1. 双击 eclipse.exe 源文件或之前创建的快捷方式启动 eclipse，如下图所示
    ![](./images/01/10.png)
    2. 选择工作目录后，点击 Launch 进入 Eclipse 主程序，并显示欢迎页面，如下图所示
    ![](./images/01/11.png)
    3. 进入 Eclipse 后，创建 Java 工程项目，依次选择 File >> New >> Project， 如下图所示
    ![](./images/01/12.png)
    4. 进入项目类型选择页面，选择 Java 项目，然后点击下一步，如下图所示
    ![](./images/01/13.png)
    5. 进入项目创建页面，为项目起名，其他使用默认选项即可
    ![](./images/01/14.png)
    6. 创建 Java 项目成功，提示你是否切换视图， 用 Java 视图来替换 当前视图。选择哪个按钮都无所谓，如下图所示
    ![](./images/01/15.png)
    7. 查看已经创建好的项目，如下图所示
    ![](./images/01/16.png)
    8. 在刚刚创建好的项目中新建一个类，如下图所示
    ![](./images/01/17.png)
    9. 完成创建新类的配置，如下图所示
    ![](./images/01/18.png)
    10. 编写测试代码，在主方法中添加 ```System.out.println("Hello Java world!~");``` 并运行查看结果，如下图所示
    ![](./images/01/19.png)
    ***注：查到运行结果为 “Hello Java world！~”，说明 Java 以及 Eclipse 环境配置正确。***

## 二、Java Web 环境测试
- 在保证 JDK、Tomcat 和 Eclipse 全部安装正确的前提下进行以下测试
    1. 确保 Tomcat 服务没有被启动，即右下角托盘出没有 ![](./images/01/4.png) 图标显示，若已经启动先在该图标上点击右键选择 ```stop service``` 选项来停止服务，然后退出 Tomcat，如下图所示
    ![](./images/01/21.png)
    2. 创建基于 Web 的 Java 项目（```Dynamic Web Project```），如下图所示
    ![](./images/01/22.png)
    3. 配置项目，如下图所示
    ![](./images/01/23.png)
    ![](./images/01/24.png)
    ![](./images/01/25.png)
    ![](./images/01/26.png)
    4. 在项目中的 ```Web Content``` 节点中新建 jsp 文件，并命名为 ```index.jsp```,如下图所示
    ![](./images/01/27.png)
    ![](./images/01/28.png)
    5. 在 JSP 文件中编辑代码，在 ```<body></body>``` 标签中添加 ```<center>Hello Java Web world!~</center>```，如下图所示
    ![](./images/01/29.png)
    6. 测试运行环境，如下图所示
    ![](./images/01/30.png)
    ![](./images/01/31.png)
    7. 查看测试成功结果，如下图所示
    ![](./images/01/32.png)

### 环境配置搭建以及测试大功告成
*以上为 Windows 系统中环境搭建与测试方法，Unix/Linux类操作系统中方法不另做介绍，若想了解，可关注本人 Linux 相关课程。或直接联系本人。老邪很乐意为正在努力的你答疑解惑……*
    