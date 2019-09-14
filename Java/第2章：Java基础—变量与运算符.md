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
## Java 基本数据类型(8种)

Java语言提供了八种基本类型。六种数字类型（四个整数型，两个浮点型），一种字符类型，还有一种布尔型。

* byte：
byte 数据类型是8位、有符号的，以二进制补码表示的整数；
最小值是 -128（-2^7）；
最大值是 127（2^7-1）；
默认值是 0；
byte 类型用在大型数组中节约空间，主要代替整数，因为 byte 变量占用的空间只有 int 类型的四分之一；
例子：byte a = 100，byte b = -50。
* short：
short 数据类型是 16 位、有符号的以二进制补码表示的整数
最小值是 -32768（-2^15）；
最大值是 32767（2^15 - 1）；
Short 数据类型也可以像 byte 那样节省空间。一个short变量是int型变量所占空间的二分之一；
默认值是 0；
例子：short s = 1000，short r = -20000。
* int：
int 数据类型是32位、有符号的以二进制补码表示的整数；
最小值是 -2,147,483,648（-2^31）；
最大值是 2,147,483,647（2^31 - 1）；
一般地整型变量默认为 int 类型；
默认值是 0 ；
例子：int a = 100000, int b = -200000。
* long：
long 数据类型是 64 位、有符号的以二进制补码表示的整数；
最小值是 -9,223,372,036,854,775,808（-2^63）；
最大值是 9,223,372,036,854,775,807（2^63 -1）；
这种类型主要使用在需要比较大整数的系统上；
默认值是 0L；
例子： long a = 100000L，Long b = -200000L。
"L"理论上不分大小写，但是若写成"l"容易与数字"1"混淆，不容易分辩。所以最好大写。
* float：
float 数据类型是单精度、32位、符合IEEE 754标准的浮点数；
float 在储存大型浮点数组的时候可节省内存空间；
默认值是 0.0f；
浮点数不能用来表示精确的值，如货币；
例子：float f1 = 234.5f。
* double：
double 数据类型是双精度、64 位、符合IEEE 754标准的浮点数；
浮点数的默认类型为double类型；
double类型同样不能表示精确的值，如货币；
默认值是 0.0d；
例子：double d1 = 123.4。
* boolean：
boolean数据类型表示一位的信息；
只有两个取值：true 和 false；
这种类型只作为一种标志来记录 true/false 情况；
默认值是 false；
例子：boolean one = true。
* char：
char类型是一个单一的 16 位 Unicode 字符；
最小值是 \u0000（即为0）；
最大值是 \uffff（即为65,535）；
char 数据类型可以储存任何字符；
例子：char letter = 'A';。

	
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B-1568379167832.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/datatype-1568379261451.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%95%B4%E6%95%B0%E7%B1%BB%E5%9E%8B-1568379501112.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%B5%AE%E7%82%B9%E7%B1%BB%E5%9E%8B-1568379571841.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E5%AD%97%E7%AC%A6%E7%B1%BB%E5%9E%8B-1568379634837.jpg)

![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/Boolean-1568379774693.jpg)
# 2-4 运算符
* 算数运算符
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E7%AE%97%E6%9C%AF%E8%BF%90%E7%AE%97%E7%AC%A6-1568384345017.jpg)

* 比较运算符
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E6%AF%94%E8%BE%83%E8%BF%90%E7%AE%97%E7%AC%A6-1568384461665.jpg)
* 位运算符
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E4%BD%8D%E8%BF%90%E7%AE%97%E7%AC%A6-1568384816221.jpg)
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E4%BD%8D%E8%BF%90%E7%AE%97%E7%AC%A62-1568384900750.jpg)
* 逻辑运算符
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E9%80%BB%E8%BE%91%E8%BF%90%E7%AE%97%E7%AC%A6-1568386768805.jpg)
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/13/%E9%80%BB%E8%BE%91%E8%BF%90%E7%AE%97%E7%AC%A62-1568386810564.jpg)
* 三元运算符
![title](https://raw.githubusercontent.com/XJZ-0707/imge/master/gitnote/2019/09/14/%E4%B8%89%E5%85%83%E8%BF%90%E7%AE%97%E7%AC%A6-1568427413167.jpg)

