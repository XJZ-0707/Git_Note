# 2.1 关键字与保留字
 * 关键字(keyword)的定义和特点
	* 定义：被Java语言赋予了特殊含义，用做专门用途的字符串（单词）
	* 特点：关键字中所有字母都为小写
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E5%85%B3%E9%94%AE%E5%AD%97-1568373577494.jpg)

		![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E5%85%B3%E9%94%AE%E5%AD%972-1568373621049.jpg)

# 2.2 标识符(Identifier)
## 标识符：
    * Java 对各种变量、方法和类等要素命名时使用的字符序列称为标识符
    * 技巧：凡是自己可以起名字的地方都叫标识符。
## 定义合法标识符规则：
	*  由26个英文字母大小写，0-9 ，_或 $ 组成
	*  数字不可以开头。
	*  不可以使用关键字和保留字，但能包含关键字和保留字。
	*  Java中严格区分大小写，长度无限制。
	*  标识符不能包含空格。

# 2-3 变量
## 变量的概念：
    * 内存中的一个存储区域
    * 该区域的数据可以在同一类型范围内不断变化
    *变量是程序中最基本的存储单元。包含变量类型、变量名和存储的值
## 变量的作用：
	* 用于在内存中保存数据
	
## 使用变量注意：
	Java中每个变量必须先声明，后使用
	使用变量名来访问这块区域的数据
	变量的作用域：其定义所在的一对{ }内
	变量只有在其作用域内才有效
	同一个作用域内，不能定义重名的变量
	
	* 声明变量：
		 语法：<数据类型> <变量名称>
		 例如：int var;  
	* 变量的赋值
		 语法：<变量名称> = <值>
		 例如：var = 10;
	* 声明和赋值变量
		 语法： <数据类型> <变量名> = <初始化值>
		 例如：int var = 10;
	
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B-1568379167832.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/datatype-1568379261451.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%95%B4%E6%95%B0%E7%B1%BB%E5%9E%8B-1568379501112.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%B5%AE%E7%82%B9%E7%B1%BB%E5%9E%8B-1568379571841.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E5%AD%97%E7%AC%A6%E7%B1%BB%E5%9E%8B-1568379634837.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/Boolean-1568379774693.jpg)