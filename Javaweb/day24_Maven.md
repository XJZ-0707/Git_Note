# 第1章 Maven 介绍
## 1.1 什么是 Maven
### 1.1.1 什么是 Maven
* Maven 的正确发音是[ˈmevən]，而不是“马瘟”以及其他什么瘟。Maven 在美国是一个口语化的词语，代表专家、内行的意思。一个对 Maven 比较正式的定义是这么说的：Maven 是一个项目管理工具它包含了一个项目对象模型 (POM：Project Object Model)，一组标准集合，一个项目生命周期(Project Lifecycle)，一个依赖管理系统(Dependency Management System)，和用来运行定义在生命周期阶段(phase)中插件(plugin)目标(goal)的逻辑。
### 1.2.2 项目的一键构建
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven1-1569841287184.jpg)

# 第2章 Maven 的使用 
## 2.1 Maven 的安装
### 三级标题 2.1.1 Maven 软件的下载
* 去官网下载
### 2.1.2 Maven 软件的安装
* Maven 下载后，将 Maven 解压到一个没有中文没有空格的路径下，比如 D:\software\maven 下面。
解压后目录结构如下：
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven2-1569843137961.jpg)
bin:存放了 maven 的命令，比如我们前面用到的 mvn tomcat:run
boot:存放了一些 maven 本身的引导程序，如类加载器等
conf:存放了 maven 的一些配置文件，如 setting.xml 文件
lib:存放了 maven 本身运行所需的一些 jar 包至此我们的 maven 软件就可以使用了，前提是你的电脑上之前已经安装并配置好JDK。
### 2.1.4 Maven 及 JDK 配置
电脑上需安装 java 环境，安装 JDK1.7 + 版本（JAVA_HOME/bin 配置环境变量 path ），我们使用的是 JDK8 相关版本配置MAVEN_HOME ，变量值就是你的 maven 安装 的路径（bin 目录之前一级目录）
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven3-1569843278893.jpg)
上面配置了我们的 Maven 软件，注意这个目录就是之前你解压 maven 的压缩文件包在的的目录，最好不要有中文和空格。

### 2.1.5 Maven 软件版本测试
通过 mvn -v命令检查 maven 是否安装成功，看到 maven 的版本为 3.5.2 及 java 版本为 1.8 即为安装成功。
找开 cmd 命令，输入 mvn –v命令，如下图：
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven5-1569843383159.jpg)
## 2.2 Maven 仓库
### 2.2.1 Maven 仓库的分类
maven 的工作需要从仓库下载一些 jar 包，如下图所示，本地的项目 A、项目 B 等都会通过 maven软件从远程仓库（可以理解为互联网上的仓库）下载 jar 包并存在本地仓库，本地仓库 就是本地文件夹，当第二次需要此 jar 包时则不再从远程仓库下载，因为本地仓库已经存在了，可以将本地仓库理解为缓存，有了本地仓库就不用每次从远程仓库下载了。

* 本地仓库 ：用来存储从远程仓库或中央仓库下载的插件和 jar 包，项目使用一些插件或 jar 包，优先从本地仓库查找
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven6-1569844010436.jpg)

* 远程仓库：如果本地需要插件或者 jar 包，本地仓库没有，默认去远程仓库下载。远程仓库可以在互联网内也可以在局域网内。
* 中央仓库 ：在 maven 软件中内置一个远程仓库地址 http://repo1.maven.org/maven2 ，它是中央仓库，服务于整个互联网，它是由 Maven 团队自己维护，里面存储了非常全的 jar 包，它包含了世界上大部分流行的开源项目构件。
  
## 2.3 Maven 工程的认识

### 2.3.1 Maven 工程的目录结构
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven7-1569844181745.jpg)
* 作为一个 maven 工程，它的 src 目录和 pom.xml 是必备的。
进入 src 目录后，我们发现它里面的目录结构如下：
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven8-1569844362656.jpg)
* src/main/java —— 存放项目的.java 文件
src/main/resources —— 存放项目资源文件，如 spring, hibernate 配置文件
src/test/java —— 存放所有单元测试.java 文件，如 JUnit 测试类
src/test/resources —— 测试资源文件
target —— 项目输出位置，编译后的 class 文件会输出到此目录
pom.xml——maven 项目核心配置文件
注意：如果是普通的 java 项目，那么就没有 webapp 目录。
## 第3章 Maven 常用命令 
我们可以在 cmd 中通过一系列的 maven 命令来对我们的 maven-helloworld 工程进行编译、测试、运行、打包、安装、部署。

### 3.1.1 compile
* compile 是 maven 工程的编译命令，作用是将 src/main/java 下的文件编译为 class 文件输出到 target目录下。
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven9-1569844765904.jpg)

### 3.1.2 test
* test 是 maven 工程的测试命令 mvn test，会执行src/test/java 下的单元测试类。
cmd 执行 mvn test 执行 src/test/java 下单元测试类，下图为测试结果，运行 1 个测试用例，全部成功
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven10-1569844844978.jpg)

### 3.1.3 clean
* clean 是 maven 工程的清理命令，执行 clean 会删除 target 目录及内容。
### 3.1.4 package
* package 是 maven 工程的打包命令，对于 java 工程执行 package 打成 jar 包，对于 web 工程打成 war包。

### 3.1.5 install
* install 是 maven 工程的安装命令，执行 install 将 maven 打成 jar 包或 war 包发布到本地仓库。
从运行结果中，可以看出：
当后面的命令执行时，前面的操作过程也都会自动执行，

## 3.2 idea 开发 maven 项目

### 3.2.1 idea 的 maven 配置
#### 3.2.1.1 打开->File->Settings 配置 maven
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven11-1569846099937.jpg)
3.2.2 idea 中创建一个 maven 的 web 工程
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven12-1569851010218.jpg)
........省略一些步骤
* 点击 Finish 后开始创建工程，耐心等待，直到出现如下界面。
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven13-1569851104333.jpg)
* 手动添加 src/main/java 目录，如下图右键 main 文件夹->New-->Directory
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven14-1569851159780.jpg)
* 点击 OK 后，在新的文件夹 java 上右键-->Make Directory as-->Sources Root
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven15-1569851227770.jpg)
### 3.2.2.1 创建一个 Servlet
* src/java/main 创建了一个 Servlet，但报错
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven16-1569851289545.jpg)
### 3.2.2.2 在 pom.xml 文件添加坐标
* 直接打开 hello_maven 工程的 pom.xml 文件，再添加坐标
	* 添加 jar 包的坐标时，还可以指定这个 jar 包将来的作用范围。每个 maven 工程都需要定义本工程的坐标，坐标是 maven 对 jar 包的身份定义，比如：入门程序的坐标定义如下：
```java
<!--项目名称，定义为组织名+项目名，类似包名-->
<groupId>com.itheima</groupId>
<!-- 模块名称 -->
<artifactId>hello_maven</artifactId>
<!-- 当前项目版本号，snapshot 为快照版本即非正式版本，release 为正式发布版本 -->
<version>0.0.1-SNAPSHOT</version>
<packaging > ：打包类型
jar：执行 package 会打成 jar 包
war：执行 package 会打成 war 包
pom ：用于 maven 工程的继承，通常父工程设置为 pom
```
### 3.2.2.3 坐标的来源方式
* 添加依赖需要指定依赖 jar 包的坐标，但是很多情况我们是不知道 jar 包的的坐标，可以通过如下方式查询：
#### 3.2.2.3.1 从互联网搜索
* http://search.maven.org/
http://mvnrepository.com/
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven17-1569851465978.jpg)
### 3.2.3 依赖范围
* A 依赖 B，需要在 A 的 pom.xml 文件中添加 B 的坐标，添加坐标时需要指定依赖范围，依赖范围包括：
	* compile：编译范围，指 A 在编译时依赖 B，此范围为默认依赖范围。编译范围的依赖会用在编译、测试、运行，由于运行时需要所以编译范围的依赖会被打包。
	* provided：provided 依赖只有在当 JDK 或者一个容器已提供该依赖之后才使用， provided 依赖在编译和测试时需要，在运行时不需要，比如：servlet api 被 tomcat 容器提供。
	* runtime：runtime 依赖在运行和测试系统的时候需要，但在编译的时候不需要。比如：jdbc的驱动包。由于运行时需要所以 runtime 范围的依赖会被打包。
	* test：test 范围依赖 在编译和运行时都不需要，它们只有在测试编译和测试运行阶段可用，比如：junit。由于运行时不需要所以 test范围依赖不会被打包。
	* system：system 范围依赖与 provided 类似，但是你必须显式的提供一个对于本地系统中 JAR文件的路径，需要指定systemPath 磁盘路径，system依赖不推荐使用。
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven18-1569851734634.jpg)
在 maven-web 工程中测试各各 scop。
测试总结：
	*  默认引入 的 jar 包 ------- compile 【默认范围 可以不写】（编译、测试、运行 都有效 ）
	*  servlet-api 、jsp-api ------- provided （编译、测试 有效， 运行时无效 防止和 tomcat 下 jar 冲突）
	*  jdbc 驱动 jar 包 ---- runtime （测试、运行 有效 ）
	*  junit ----- test （测试有效）
依赖范围由强到弱的顺序是：compile>provided>runtime>test

### 3.2.4 项目中添加的坐标
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven19-1569851884085.jpg)















