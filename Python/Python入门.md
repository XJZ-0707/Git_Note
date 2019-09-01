# Python入门
## 配置环境变量
1. 在计算机环境变量下配置 D:\python（这是我的		Python3.7的安装目录）
2. 创建python项目	
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/01/python%E9%A1%B9%E7%9B%AE%E5%88%9B%E5%BB%BA-1567327350471.jpg)
## 注释 
1. 单行注释
*  #注释的内容 如：#print("hello python!")

2. 多行注释（两种）
* 第一种（三个双引号）
 """
第一行注释
第二行注释
第三行注释
"""
* 第二种（三个单引号）
'''
第一行注释
第二行注释
第三行注释
'''
	
## 变量
1. 同Java的变量命名规则
如：my_name = “tom” print(my_name)
2. 特点：

## 认识数据类型
* 数据类型如下：
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/01/python%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B-1567327399671.jpg) 	
* 数据类型代码示例：
```language
num = 1
print(type(num)) # <class 'int'> int 类型
num1 = 2.2
print(type(num1)) # <class 'float'> float 类型
str = '你好啊'
print(type(str))  # <class 'str'> str 类型
bo = True #或者 False
print(type(bo)) # <class 'bool'> boolean 类型
list = [1,2,3]
print(type(list)) # <class 'list'> list 列表
tu = (1,2,3)
print(type(tu)) # <class 'tuple'> tuple 元组
se = {1,2,3}
print(type(se)) # <class 'set'> set 集合
dic = {"name": 'Tom',"age" : 18}
print(type(dic)) # <class 'dict'> dic 字典 键值对
```


* 变量总结 
![python变量.jpg](1)
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/01/python%E5%8F%98%E9%87%8F-1567327418576.jpg)
## 格式化符号
* 格式化符号表

![python格式化符号.jpg](3)
![python字符.jpg](4)

* 代码示例
```language
age = 18
name = 'Tom'
weight = 73.2
stu_id = 1
# 1.整数 %d
print('今年我的年龄是%d' %age)
# 2.字符串 %s
print('我的名字是%s' %name)
# 3.浮点数 %f
print('我的体重是 %.3f' % weight)
# 4.
print('我的学号是%d' %stu_id)
# 4.1
print('我的学号是%03d' %stu_id)
# 5.
print('我是名字是%s,今年%d岁了' %(name,age))
print('我是名字是%s,明年%d岁了' %(name,age + 1))
# 6.语法 f'{表达式}
print(f'我的名字是{name}，今年{age +2}岁了')

输出：
今年我的年龄是18
我的名字是Tom
我的体重是 73.200
我的学号是1
我的学号是001
我是名字是Tom,今年18岁了
我是名字是Tom,明年19岁了
我是名字是Tom,明年20岁了

```
![python f表达式.jpg](5)
* 转义字符
	* ![python转义字符.jpg](6)
	* 示例代码：
```language
	print('hello word')
	print('hello\nPython')
	print('\tabcd')
	
	输出
	hello word
	hello
	Python
	    abcd
```
* 结束符
```language
print('hello',end="\n")
print('word',end="\t")
print('hello',end="....")
print('Python')

输出：
hello
word	hello....Python
```
![python结束符.jpg](7)
* 总结
![python格式化总结.jpg](8)

## 输入
* 输入的语法
```
input （"提示信息"）
```

* 输入的特点
![python input输入.jpg](9)

* 代码示例
```
password = input('请输入密码：')
print(f'您输入的密码是{password}')
print(type(password))

输出：
请输入密码：123
您输入的密码是123
<class 'str'>

```
## 转换数据类型
* 转换数据类型的作用
![python 转换数据类型作用.jpg](10)

* 数据类型转换表
![python数据类型转换.jpg](11)


![python项目创建.jpg](0)
	


