##     								Java必备知识点总结

### **1、Java的基本程序设计结构**

#### 	**1.1	一个简单的Java应用程序**

```java
public class FirstSample{
    public static void main(String[] args){
        System.out.println("we will not use 'Hello world!'");
    }
}
```

<font color="red">注意：</font>源代码的文件名必须与公共类的名字相同，类名以大写字母开头，以.Java作为扩展名

#### 	1.2	注释

```java
/**
*	注释的代码规范   
*/
//	单行注释
```

#### 	1.3数据类型

&emsp; Java是一种强类型语言。必须为每一个变量声明一种类型。在Java中一共有8中基本类型，其中有4中整型、2种浮点类型。

<font color=grap>注释：</font>Java有一个能够表示任意精度的算术包，通常称为“大数值”（big number）是一种Java对象

##### 		1.3.1	整型

***

​				类型													存储需求													取值范围

***

​				int														4字节												-2147483~2147483

​			  short													 2字节												-32768~32767

​			   long													  8字节			    -9223372036854775808~-9223372036854775807

​			   byte													  1字节    												-128~127

***

##### 		1.3.2	浮点类型

&emsp; 浮点类型用于表示小数部分的数值。在Java中有两种浮点类型。float和double。绝大部分采用double类型（有效值6~7位），float类型（有效位数为15位）的精度很难满足需求。

##### 		1.3.3	char类型

&emsp;char类型用于表示单个字符。通常用来表示字符常量。

##### 		<font color="red">&#9733;1.3.4	boolean类型</font>

&emsp;boolean(布尔)类型有两个值：false和true，用来判定逻辑条件。

&emsp;<font color="red">注意：</font>整型值和布尔值之间不能进行相互转换。

#### 	1.4	变量

&emsp;在Java中，每一个变量属于一种类型（type）。在生命变量时，变量所属的类型位于变量名之前。

```java
double salary;
int vacationDays;
long earthPopulation;
boolean done;
```

##### 			1.4.1	变量初始化

&emsp;声明一个变量之后，必须要进行赋值语句对变量进行显示初始化。

```java
int vacationDays;
vacationDays=12;
```

##### 			1.4.2	常量

&emsp;在Java中，利用关键字final指示常量。

```java
public class Constants{
    public static void man(String[] args){
        final double CM_PER_INCH = 2.54;
        double paperWidth = 8.5;
        double parperHeight = 11;
        System.out.println("Paper size in centimeters: "+paperWidth*CM_PER_INCH+"by"+paperHeight*CM_PER_INCH);
    }
}
```

&emsp;关键字final表示这个变量只能被赋值一次。一旦被赋值就不能再修改了。通常希望某个常量在一个类中的多个方法中使用，通常将这些常量称为类常量。

```java
public static fianl double CM_PER_INCH = 2.54
```

#### 			1.5 运算符

&emsp;在Java中，使用+、-、*、/表示加、减、乘、除运算。当参与/运算的两个操作数都是整数时，表示整数除法；否则表示浮点除法。

```
x + = 4;
x = x + 4;
```

##### 				1.5.1	自增运算符与自减运算符

```java
int m = 7;
int n = 7;
int a = 2 * ++m;	//a=16  m=8    前缀是先进行加1
int b = 2 * n++;	//a=14  m=8	   后缀是使用变量原来的值
```

##### 				1.5.2	关系运算符与boolean运算符

```java
x!=0&&1/x>x+y  // &&和||按照”短路“的方式求值，如果第一个操作数已经能够确定表达式的值了，第二哥操作数就不必计算了
condition?expression1:expression2 //当条件为真时，计算第1表达式，否则计算第2个表达式
```

##### 				<font color="red">&#9733;1.5.3	位运算符</font>

&emsp;在处理整型数值时，可以直接对组成整型数值的各个位进行操作。位运算符包括：&（”与“）、|（”或“）、^（”异或“）、~（”非“）。

```java
int n=ob0110;
int fourth=(n & ob1000) / ob1000;
```

&emsp;另外，”>>“和”<<“运算符将二进制位进行右移或左移操作。

```java
int n = ob0011;
int fourth = (n & (1 << 3)) >> 3;
```

##### 				1.5.4	数学函数与常量

```java
double x = 4;
double y = Math.sqrt(x);
System.out.println(y);
public static final double a =Math.PI;
final double a = Math.e;
```

##### 				<font color="red">&#9733;1.5.5	数值类型之间的转换</font>

&emsp;在程序运行时，经常需要将一种数值类型转换位另一种数值类型。如图1.1给出了数值类型之间的合法转换。

![1566381498096](C:\Users\20190712158\AppData\Roaming\Typora\typora-user-images\1566381498096.png)

&emsp;虚箭头表示可能有精度损失的转换当使用上面两个数字进行二元操作时，先要将两个操作数转换位同一种类型，然后再进行计算。

* 如果两个操作数中有一个是double类型，另一个操作数就会转换位double类型。
* 否则，如果其中一个操作数是float类型，另一个操作数将会转换位float类型。
* 否则，如果其中一个操作数是long类型，另一个操作数将会转换位long类型。
* 否则，两个操作数都将被转换为int类型。

​				<font color="red">&#9733;1.5.6	强制类型转换</font>

&emsp;在必要的时候，int类型的值将会自动转换为double类型。但另一方面，有时也需要将double转换成int类型。在Java中，允许进行数值之间的类型转换。

```java
double x = 9.997;
int y = (int)x;
```

