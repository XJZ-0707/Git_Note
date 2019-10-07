# 11-1 Java集合框架概述
## 11.1 Java 集合框架概述
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/%E9%9B%86%E5%90%8801-1570437104798.jpg)
## 11.1 Java 集合框架概述：集合的使用场景
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/%E9%9B%86%E5%90%8802-1570437162647.jpg)
## 11.1 Java 集合框架概述
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/%E9%9B%86%E5%90%8803-1570437236503.jpg)

## 11.1 Java 集合框架概述：Collection接口继承树
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/%E9%9B%86%E5%90%8804-1570437296842.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/%E9%9B%86%E5%90%8805-1570439757008.jpg)


## 11-2 Collection接口方法
```java

Collection 接口
* Collection 接口是 List、Set 和 Queue 接口的父接口，该接口里定义的方法
既可用于操作 Set 集合，也可用于操作 List 和 Queue 集合。
JDK不提供此接口的任何直接实现，而是提供更具体的子接口(如：Set和List)
实现。
在 Java5 之前，Java 集合会丢失容器中所有对象的数据类型，把所有对象都
当成 Object 类型处理；从 JDK 5.0 增加了泛型以后，Java 集合可以记住容
器中对象的数据类型。

```




