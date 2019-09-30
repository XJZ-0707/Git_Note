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
lib:存放了 maven 本身运行所需的一些 jar 包
至此我们的 maven 软件就可以使用了，前提是你的电脑上之前已经安装并配置好了 JDK。
### 2.1.4 Maven 及 JDK 配置
电脑上需安装 java 环境，安装 JDK1.7 + 版本（JAVA_HOME/bin 配置环境变量 path ），我们使用的是 JDK8 相关版本
配置 MAVEN_HOME ，变量值就是你的 maven 安装 的路径（bin 目录之前一级目录）
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven3-1569843278893.jpg)
上面配置了我们的 Maven 软件，注意这个目录就是之前你解压 maven 的压缩文件包在的的目录，最好不要有中文和空格。

### 2.1.5 Maven 软件版本测试
通过 mvn -v命令检查 maven 是否安装成功，看到 maven 的版本为 3.5.2 及 java 版本为 1.8 即为安装成功。
找开 cmd 命令，输入 mvn –v命令，如下图：
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/30/maven5-1569843383159.jpg)
## 2.2 Maven 仓库
### 2.2.1 Maven 仓库的分类
maven 的工作需要从仓库下载一些 jar 包，如下图所示，本地的项目 A、项目 B 等都会通过 maven软件从远程仓库（可以理解为互联网上的仓库）下载 jar 包并存在本地仓库，本地仓库 就是本地文
件夹，当第二次需要此 jar 包时则不再从远程仓库下载，因为本地仓库已经存在了，可以将本地仓库理解为缓存，有了本地仓库就不用每次从远程仓库下载了。


