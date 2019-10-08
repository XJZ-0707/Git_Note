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


# 11-2 Collection接口方法
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/collection01-1570440575748.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/collection03-1570440741328.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/collection02-1570440707669.jpg)

## 11.1~11.2代码示例一：
```java
package com_2.day05.java2;

import org.junit.Test;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Date;


 * 一、集合框架的概述
 *
 * 1.集合、数组都是对多个数据进行存储操作的结构，简称Java容器。
 *  说明：此时的存储，主要指的是内存层面的存储，不涉及到持久化的存储（.txt,.jpg,.avi，数据库中）
 *
 * 2.1 数组在存储多个数据方面的特点：
 *      > 一旦初始化以后，其长度就确定了。
 *      > 数组一旦定义好，其元素的类型也就确定了。我们也就只能操作指定类型的数据了。
 *       比如：String[] arr;int[] arr1;Object[] arr2;
 * 2.2 数组在存储多个数据方面的缺点：
 *      > 一旦初始化以后，其长度就不可修改。
 *      > 数组中提供的方法非常有限，对于添加、删除、插入数据等操作，非常不便，同时效率不高。
 *      > 获取数组中实际元素的个数的需求，数组没有现成的属性或方法可用
 *      > 数组存储数据的特点：有序、可重复。对于无序、不可重复的需求，不能满足。
 *
 * 二、集合框架
 *      |----Collection接口：单列集合，用来存储一个一个的对象
 *          |----List接口：存储有序的、可重复的数据。  -->“动态”数组
 *              |----ArrayList、LinkedList、Vector
 *
 *          |----Set接口：存储无序的、不可重复的数据   -->高中讲的“集合”
 *              |----HashSet、LinkedHashSet、TreeSet
 *
 *      |----Map接口：双列集合，用来存储一对(key - value)一对的数据   -->高中函数：y = f(x)
 *              |----HashMap、LinkedHashMap、TreeMap、Hashtable、Properties
 *
 *
 * 三、Collection接口中的方法的使用
 *
 * @author shkstart
 * @create 2019 下午 4:08


public class CollectionTest {

    @Test
    public void test1(){
        Collection coll = new ArrayList();

        //add(Object e):将元素e添加到集合coll中
        coll.add("AA");
        coll.add("BB");
        coll.add(123);//自动装箱
        coll.add(new Date());

        //size():获取添加的元素的个数
        System.out.println(coll.size());//4

        //addAll(Collection coll1):将coll1集合中的元素添加到当前的集合中
        Collection coll1 = new ArrayList();
        coll1.add(456);
        coll1.add("CC");
        coll.addAll(coll1);

        System.out.println(coll.size());//6
        System.out.println(coll);

        //clear():清空集合元素
        coll.clear();

        //isEmpty():判断当前集合是否为空
        System.out.println(coll.isEmpty());

    }

}

```

## 11.1~11.2代码示例二：

```java
package com_2.day06.java;

import org.junit.Test;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collection;
import java.util.List;

/**
 * Collection接口中声明的方法的测试
 *
 * 结论：
 * 向Collection接口的实现类的对象中添加数据obj时，要求obj所在类要重写equals().
 *
 * @author shkstart
 * @create 2019 上午 10:04
 */
public class CollectionTest {


    @Test
    public void test1(){
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
//        Person p = new Person("Jerry",20);
//        coll.add(p);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);
        //1.contains(Object obj):判断当前集合中是否包含obj
        //我们在判断时会调用obj对象所在类的equals()。
        boolean contains = coll.contains(123);
        System.out.println(contains);
        System.out.println(coll.contains(new String("Tom")));
//        System.out.println(coll.contains(p));//true
        System.out.println(coll.contains(new Person("Jerry",20)));//false -->true

        //2.containsAll(Collection coll1):判断形参coll1中的所有元素是否都存在于当前集合中。
        Collection coll1 = Arrays.asList(123,4567);
        System.out.println(coll.containsAll(coll1));
    }

    @Test
    public void test2(){
        //3.remove(Object obj):从当前集合中移除obj元素。
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);

        coll.remove(1234);
        System.out.println(coll);

        coll.remove(new Person("Jerry",20));
        System.out.println(coll);

        //4. removeAll(Collection coll1):差集：从当前集合中移除coll1中所有的元素。
        Collection coll1 = Arrays.asList(123,456);
        coll.removeAll(coll1);
        System.out.println(coll);


    }

    @Test
    public void test3(){
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);

        //5.retainAll(Collection coll1):交集：获取当前集合和coll1集合的交集，并返回给当前集合
//        Collection coll1 = Arrays.asList(123,456,789);
//        coll.retainAll(coll1);
//        System.out.println(coll);

        //6.equals(Object obj):要想返回true，需要当前集合和形参集合的元素都相同。
        Collection coll1 = new ArrayList();
        coll1.add(456);
        coll1.add(123);
        coll1.add(new Person("Jerry",20));
        coll1.add(new String("Tom"));
        coll1.add(false);

        System.out.println(coll.equals(coll1));


    }

    @Test
    public void test4(){
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);

        //7.hashCode():返回当前对象的哈希值
        System.out.println(coll.hashCode());

        //8.集合 --->数组：toArray()
        Object[] arr = coll.toArray();
        for(int i = 0;i < arr.length;i++){
            System.out.println(arr[i]);
        }

        //拓展：数组 --->集合:调用Arrays类的静态方法asList()
        List<String> list = Arrays.asList(new String[]{"AA", "BB", "CC"});
        System.out.println(list);

        List arr1 = Arrays.asList(new int[]{123, 456});
        System.out.println(arr1.size());//1

        List arr2 = Arrays.asList(new Integer[]{123, 456});
        System.out.println(arr2.size());//2

        //9.iterator():返回Iterator接口的实例，用于遍历集合元素。放在IteratorTest.java中测试

    }
}



******
如下是Person类，配合上面的CollectionTest.java
package com_2.day06.java;

import java.util.Objects;

/**
 * @author shkstart
 * @create 2019 上午 10:06
 */
public class Person {

    private String name;
    private int age;

    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }

    @Override
    public boolean equals(Object o) {
        System.out.println("Person equals()....");
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Person person = (Person) o;
        return age == person.age &&
                Objects.equals(name, person.name);
    }

    @Override
    public int hashCode() {

        return Objects.hash(name, age);
    }
}


```

# 11-3 Iterator迭代器接口
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/Iterator01-1570459302392.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/Iterator02-1570459422175.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/Iterator03-1570459471661.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/Iterator04-1570459499459.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/Iterator05-1570459521998.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/Iterator06-1570459552862.jpg)
## 示例代码：
```java
package com_2.day06.java;
import org.junit.Test;
import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;


 * 集合元素的遍历操作，使用迭代器Iterator接口
 * 1.内部的方法：hasNext() 和  next()
 * 2.集合对象每次调用iterator()方法都得到一个全新的迭代器对象，
 * 默认游标都在集合的第一个元素之前。
 * 3.内部定义了remove(),可以在遍历的时候，删除集合中的元素。此方法不同于集合直接调用remove()
 *
 * @author shkstart
 * @create 2019 上午 10:44


public class IteratorTest {

    @Test
    public void test1(){
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);

        Iterator iterator = coll.iterator();
        //方式一：
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
//        System.out.println(iterator.next());
//        //报异常：NoSuchElementException
//        System.out.println(iterator.next());

        //方式二：不推荐
//        for(int i = 0;i < coll.size();i++){
//            System.out.println(iterator.next());
//        }

        //方式三：推荐
        ////hasNext():判断是否还有下一个元素
        while(iterator.hasNext()){
            //next():①指针下移 ②将下移以后集合位置上的元素返回
            System.out.println(iterator.next());
        }

    }

    @Test
    public void test2(){

        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);

        //错误方式一：
//        Iterator iterator = coll.iterator();
//        while((iterator.next()) != null){
//            System.out.println(iterator.next());
//        }

        //错误方式二：
        //集合对象每次调用iterator()方法都得到一个全新的迭代器对象，默认游标都在集合的第一个元素之前。
        while (coll.iterator().hasNext()){
            System.out.println(coll.iterator().next());
        }


    }

    //测试Iterator中的remove()
    //如果还未调用next()或在上一次调用 next 方法之后已经调用了 remove 方法，
    // 再调用remove都会报IllegalStateException。
    @Test
    public void test3(){
        Collection coll = new ArrayList();
        coll.add(123);
        coll.add(456);
        coll.add(new Person("Jerry",20));
        coll.add(new String("Tom"));
        coll.add(false);

        //删除集合中"Tom"
        Iterator iterator = coll.iterator();
        while (iterator.hasNext()){
//            iterator.remove();
            Object obj = iterator.next();
            if("Tom".equals(obj)){
                iterator.remove();
//                iterator.remove();
            }

        }
        //遍历集合
        iterator = coll.iterator();
        while (iterator.hasNext()){
            System.out.println(iterator.next());
        }
    }
}

```


# 11-4 Collection子接口之一：List接口

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list01-1570459641998.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list02-1570459663259.jpg)
## List实现类之一：ArrayList
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list03-1570459697341.jpg)

## List实现类之二：LinkedList
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list04-1570459769451.jpg)
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list05-1570459793983.jpg)

## List 实现类之三：Vector
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list06-1570459837475.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/list07-1570459868333.jpg)

## 11-5 Collection子接口之二：Set接口
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/set01-1570459914894.jpg)

### Set实现类之一：HashSet
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/set02-1570459982846.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/set03-1570460004925.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/10/07/set04-1570460024609.jpg)



