java

这一年一直都学习前端,相对来说,底层的实现,或许好不太懂,但是基本可以完成前端遇到的问题,但是合肥这边后端基本都是java,没办法,只能学习java了

### java第一天

看的是毕向东的javase教程

怎么说呢,之前学过一点java,当时不感兴趣,就放弃了,加上写了很久的 web网盘项目,外加很久的前端,现在回头看java没啥压力,基本都懂,老师讲课不错,懂了一些原理,比如java classpath path java_home 环境变量的作用啊,以及命令行运行java程序

### java第二天

主要是学习,进制之间的转行

比如

**这是2进制转10进制**

  1  0  1  1

1\*2(3) + 0\*2(2) + 1\*2(1) + 1*2(0) = 11  

**10进制转2进制**

```  
10
  2|10
    2|5  0
      2|2 1
        2|1 0
          2|0 1
== 1010 
10的二进制为1010
```

#### java数据类型

基础数据类型  8个

数值-整数型 (byte short int long)

数值-浮点型 (float,double)

字符型 char

布尔型 boolean



引用数据类型 - 类 class

引用数据类型 - 接口 interface

引用数据类型 - 数组 []

####变量的类型转换

**自动类型**转换也叫隐式转换,指的是两个内息在转换过程中不需要显式的会进行声明,java要实现隐式转换,必须满足两个条件:

1. 两种数据类型彼此兼容'
2. 目标类型的取值范围大于源类型的取值范围

```
byte b = 3;
int a = b;    //程序把byte类型的变量b转换成int类型的a,这无需特殊声明
```

**强制类型转换**也叫显式类型转换,知道是两种数据类型之间的转换需要进行显式的声明

```
int a =4;
byte b = a;       //这里会报错 ,因为int类型强制转byte会损失进度
```

也有办法然后程序不报错

```
int a = 4;
byte b = (byte)a  //这就是显式转换
```

注意:

在运算的时候 byte类型会强制转化成为int,所以byte相加会报错

```
byte a = 1;
byte b = 2;
byte c = a + b;     //这里的a,b在相加的时候 提升成为int类型,所以byte 类型的c 储存int会报错
```

代码应该这么写

```
byte a = 1;
byte b = 2;
byte c = (byte)(a + b);
```

字符与数字相加

```
System.out.println('a' + 1);  //结果是98!! 因为 'a'对应ascii表是01100001 = 97 +1  = 98
```

####逻辑运算符

```
&  运算符 (解析代码的时候不管左边的代码结果如何 依旧检查右边的代码)
&& 运算符 (假如左边的是false,右边的不参与运算 直接出结果 )
|  运算符 (解析代码的时候不管左边的代码结果如何 依旧检查右边的代码)
|| 运算符 (假如左边的是true,右边的不参与运算 直接出结果 )
```

#### 移位运算符 - 左移

**System.out.println(3<<2); **

代表3的二进制左移2位

```
0011   -----    1100  3变成 12   3*2(2)
```

**System.out.println(3<<3);** 

代表3的二进制左移3位

```
0011   -----    1100  3变成 24  3*2(3)
```

位移几位就是该数据乘以2的几次方

#### 移位运算符 - 右移

**System.out.println(6<<1); **

```
0110  ----     0011   6变成3  3/2(1)  3
0110  ----     0001   6变成1  3/2(2)  1.5 小数点省略 变成1
```

位移几位就是该数据除以以2的几次方

对于高位出现的空位 原来是什么就用什么补什么

```
>>> 被移位的二进制 不管是 1还是0 都用0去补
```

#### if语句和switch的比较

if :

​	1.对区间的值进行判断

​	2.对区间判断

​	3.对运算结果是boolean 类型的表达式进行判断

switch: 

​	1.对具体的值进行判断

​	2.值的数量通常是固定的

对几个固定的值进行判断,建议使用switch ,因为switch语句会把具体代码都加载进入内存

效率高一点

#####while do-while

while 与 do-while 基本一样的 但是有一点,do-while至少执行一次,其他的基本一样的

#####while 与 for

基本上这两者可以互换

格式上面不一样,for不会有全局变量,但是假如,变量后面还要用,就使用while

无限循环

while(true)

for( ; ; )



\n 回车

\t 制表符

\b 退格

\r 按下回车键

windows里面回车符是由\r\n组成的,

linux里面是由\n 

在使用的时候要注意



continue 继续

作用: 结束本次循环,继续下次循环

continue 后面不能有代码	 

 

### 函数

定义函数的类型

修饰符  返回值类型  函数名 (参数类型 参数名,参数类型 参数名,.............){

 	执行语句;

​	return 返回值;

}

##### 函数的重载

1. 同一个类名
2. 参数个数不同 或者 参数类型不同
3. 函数的重载与返回值无关

感觉很..奇怪的方法



#####java的栈内存

储存的都是局部变量

并且变量所属的作用域一但结束,该变量就会释放

#####java的堆内存

储存的是数组和对象 (数组也是对象) 

特点:

1. 每个实体都有首地址值
2. 堆内存里的每个变量都会默认初始化,根据类型的不同而不同,整数为0 ,小数为0.0 等等
3. 自动的垃圾回收机制

#####java数组

格式1: 

​	int[] arr = new int[3]; 在堆内存里面储存一个长度为3的数组

格式2:

元素类型[] 数组名 = new 元素类型[]{元素,元素,元素}

​	int[] arr = new int[]{1,2,3,4,5};

​	int[] arr = {1,2,3,4,5};

**数组获取最大值:**

```java
 public static int getMax(int[] arr){
      int max = arr[0];
      for (int i = 1; i < arr.length; i++) {
        if (arr[i] > max) {
            max =arr[i]; 
        }
      }
      return max;
    }
```

**通过索引:**

```java
public static int getMax(int[] arr){
      int max = 0;
      for (int i = 1; i < arr.length; i++) {
        if (arr[i] > arr[max]) {
            max = i; 
        }
      }
      return arr[max];
    }
```

**选择排序:**

```java
class demo
{
    public static void main(String[] args){
      int[] arr = {1,2,3,4,5,312,32131,-2};
      selectsort(arr);
      for (int i = 0; i < arr.length; i++) {
        System.out.println(arr[i]);
      }
    }
    public static void selectsort(int[] arr){
      for (int i = 0; i <arr.length-1 ; i++) {
        for (int f = i+1; f < arr.length; f++) {
          if(arr[f]>arr[i]){
            int temp = arr[f];
            arr[f] = arr[i];
            arr[i] = temp;
          }
        }
      }
    }
}
```

**冒泡排序**

```java
public static void msort(int[] arr){
      for (int i = arr.length-1; i >=0; i--) {
        for (int f = 0; f < i; f++) {
          if (arr[f]<arr[f+1]) {
            int temp = arr[f+1];
            arr[f+1] = arr[f];
            arr[f] = temp;
          }
        }
      }
    }
```

**通过内存排序**

```java
 public static void sort_2(int[] arr) {
      for (int i = 0; i < arr.length-1; i++) {
        int mun = arr[i];
        int index = i;
        for (int f = i+1; f < arr.length; f++) {
          if(mun < arr[f]){
            mun = arr[f];
            index = f;
          }
        }
        int temp = arr[index];
        arr[index] = arr[i];
        arr[i] = temp;
      }
    }
```



**有问题的 10进制 转 16进制**

```java
 public static void toHex(int num){
	      String score = " ";
	      for (int i = 0; i < 8; i++) {
	    	  int temp = num & 15;     // 意思就是 将前4个二进制数匹配出来    1111 $ 0011 = 0011
	        if(temp > 9){
	        	score += (char)(temp-10+'A'); //假如是16进制 大于10的数要转字母 
	        } else if(temp == 0){
	          //略过
	        } else {
	        	score+=temp;
	        }
	        num = num >>> 4;   //向右移动4位 也就是走转换过的16进制
	      }
	      System.out.println("score:"+score);
	    }
```

**10进制转16 但是没有去除空格**

```java
 public static void toHex(int num){
		 char[] chs = {'0','1','2','3','4','5','6','7','8','9','A','B','C','D','E','F'};
		 char[] pos = new char[8];
		 for (int i = 7; i >= 0; i--) {
			int temp = num & 15;
			if(temp == 0) {
				//跳过
			} else if(temp != 0) {
				pos[i] = chs[temp];
			}
			num = num >>> 4;
		}
		 for (int i = 0; i < pos.length; i++) {
				System.out.print(pos[i]);
		}
	}
```

10进制 转 4 8 16

```java
public class first {

	public static void main(String[] args) {
		sixteen(16);
	}
	
	public static void sixteen(int num) {     // 10转16
		trans(num, 15, 4);
	}
	public static void two(int num) {         // 10转2
		trans(num,1,1);
	}
	public static void eight(int num) {       // 10转8
		trans(num,7,3);
	}
	
	 public static void trans(int num,int base,int offset){
		 char[] chs = {'0','1','2','3','4','5','6','7','8','9','A','B','C','D','E','F'};
		 char[] pos = new char[8];
		 for (int i = 7; i >= 0; i--) {
			int temp = num & base;
				pos[i] = chs[temp];
			num = num >>> offset;
		}
		 for (int i = 0; i < pos.length; i++) {
			 if(pos[i] != '0') {
				 break;
			 }else {
				 pos[i] = '#';
				 
			 }
		 }
		 for (int i = 0; i < pos.length; i++) {
			if(pos[i] != '#') {
				System.out.print(pos[i]);
			}
		}
	 }
```

###面向对象

对象:该类事物实实在在存在的个体

类和对象的关系:

类:事物的描述

对象:该类事物的实例,在java里面通过new来创建

```java
public class catDemo {

	public static void main(String[] args) {
		car c = new car();  //在计算机里面创建一个car的实例.通过new关键字
		c.num=4;
		c.color="red";
		c.run();  //要使用对象的内容可以通过,对象.成员的方法去完成调用
	}

}

class car{
	int num;
	String color;
	void run() {
		
		System.out.println(num+"-----"+color);
	}
}

```

定义类就是定义类里面的成员  **成员变量 与 成员函数**

```
new 的时候会在堆内存开辟一点空间,并且分配内存,给new的变量
c.num 就会找到堆内存里面的变量并且给他赋值
```

成员变量与局部变量的区别

成员变量:

​	定义在类中,整个类都可以访问

​	存在于堆内存的对象里面

​	随着对象的创建而存在,随着对象的消失而消失

​	成员变量都有初始化值

局部变量:

​	定义在函数,语句,局部代码块里面,只在所属区域有效

​	存在与栈内存的方法里面

​	随着所属区域的执行而存在,随着所属区域的结束而释放(出栈)

​	局部变量没有初始化值

#####匿名对象

没有名字的对象 new car(); 

1. 对方法只有一次调用的时候可以简化成匿名函数
2. 匿名函数可以作为实际参数进行传递





##### 基本数据类型参数传递

```java
public class day6 {
	
	public static void main(String[] args) {
		int x = 3;
		show(x);
		System.out.println(x);
	}	
	
	public static void show(int x) {
		x = 4;
	}
}

```

基本类型弹出栈后 不会影响主函数的数值

##### 引用类型参数传递

```java
int x = 3;
	public static void main(String[] args) {
		day6 d = new day6();
		d.x = 9;
		show(d);
		System.out.println(d.x);
	}
	
	public static void show(day6 d) {
		d.x = 4;
	}
```

引用类型会因为引用地址的数值变化而变化

##### 封装

指隐藏对象的属性和实现细节,仅对外提供公共访问方式

好处:

- 将变化隔离
- 提高安全性
- 提高复用性

封装的原则:

- 将不需要对外提供的内容都隐藏起来
- 把属性隐藏的同时,提供公共方法进行访问

private :私有 权限修饰符 用于修饰成员,私有的内容仅仅在本类里面有效

 ##### 二维数组

```java
public class twoArray {
	public static void main(String[] args) {
		int[][] arr = new int[2][3];
		//创建一个二维数组,有2个一维数组,每个一维数组里面有一个3个元素的数组
		System.out.println(arr);   			//二维数组 这里是地址
		System.out.println(arr[0]); 		//二维数组里面的第一个 数组是对象 是引用类型 所以依旧打印内存地址
		System.out.println(arr[0][0]);    	//二维数组里面的第一位里面的第一个
	}
}
```

也可以暂定二维数组的子数组不确定值,后面定义

```java
public class twoArray {
	public static void main(String[] args) {
		
		int[][] arr2 = new int[2][];
		arr2[1] = new int[3];
		arr2[1][2] = 20;
		System.out.println(arr2[1][2]);
	}
}
```

二维数组的第二种表现形式

```java
int[][] arr3 = {{1,2,3},{4,5,6},{7,8,9}};
```

遍历二维数组

```java
int[][] arr3 = {{1,2,3},{4,5,6},{7,8,9}};
for (int i = 0; i < arr3.length; i++) {
			for (int j = 0; j < arr3[i].length; j++) {
				System.out.print(arr3[i][j]);
			}
		}
```

#####构造函数

构建创造对象时调用的函数,作用 : 可以给对象进行初始化

特征:

- 方法名与类名相同
- 在方法名前面没有返回值类型
- 方法里面没有return

一个类如果没有定义构造函数,那么这么类里面会有默认的空参数的构造函数

如果指定了构造函数,就会覆盖默认的构造函数

**一般函数和构造函数什么区别?**

构造函数

- 对象创建时,就会调用与之对应的构造函数,对对象进行初始化
- 对象创建的时候,会调用 只调用一次

一般函数

- 对象创建后,需要函数功能才调用
- 对象创建后,可以被多次调用

#####构造函数- 重载

```java
public class staticClass {
	public static void main(String args[]) {
		Preson p = new Preson(10);
		p.look();
		Preson p1 = new Preson(10,"李四");
		p1.look();
		Preson p2 = new Preson("王二麻子",11);
		p2.look();
	}
}

class Preson{
	private int age;
	private String name;
	
	Preson(){
		name = "body";
		age = 1;
		System.out.println("name="+name+"  "+age);
	}
	
	Preson(int a){     //重载的形式去体现
		age = a;
	}
	Preson(int a,String n){
		age = a;
		name = n;
	}
	Preson(String n,int a){
		age = a;
		name = n;
	}
	void look() {
		System.out.println("name="+name+"  "+age);
	}
}
```

#### this

当成员变量和局部变量重命,可以用关键字this来区分

this就是所在函数所属对象的引用

简单说: 那个对象调用this所在的函数,this就代表那个对象

例如上面的代码

```java
Preson(int age,String name){
		this.age = age;
		this.name = name;
	}
```

this 也可以用于构造函数里面调用其他函数

注意: 只能定义在构造函数的第一行,因为初始化动作要先执行

```java
Preson(int age){
		this.age = age;
	}
	Preson(int age,String name){
		this(age);      //这里相当与再次调用构造函数,this及是本身 Preson 这里是 Preson(age)  就是上面的构造函数
		this.name = name;
	}
```

对this的应用

```java
public class comp {

	public static void main(String[] args) {
		compare p1 = new compare("张三", 20);
		compare p2 = new compare("李四", 20);
		p1.compAre(p2);
	}

}
class compare {
	private String name;
	private int age;
	
	compare(String name,int age) {
		this.name = name;
		this.age = age;
	}
	
	void compAre(compare p) {
		if(this.age == p.age) {   //this指本身
			System.out.println(this.name+"与"+p.name+"年龄相同");
		} else {
			System.out.println(this.name+"与"+p.name+"年龄不相同");
		}
	}
}

```

#### static

1. static是一个修饰符,用于修饰成员;
2. static修饰的成员,被所有对象所共享
3. static优先与对象存在,因为static的成员是随着类的加载就已经存在了
4. static修饰的成员多以一种调用方式, 可以不需要new 直接用类名调用
5. static修饰的数据是共享数据,对象中的储存的是特有数据

```java
public class staticDemo {
	
	public static void main(String[] args) {
		demo d = new demo();  
		d.show("张三");  
		System.out.println(demo.country);   //可以直接访问类里面的数据
	}
}

class demo {
	String name;   //成员变量 实例变量
	static String country = "CN";    //静态变量  类变量
	public void show(String name){
		this.name = name;
		System.out.println(country+":"+name);
	}
}

```

**成员变量与静态变量的区别**

1. 生命周期不同
   - 成员变量随着对象的创建而存在,随着对象的被回收而释放
   - 静态变量随着类的加载而存在,随着类的消失而消失
2. 调用方式不一样
   - 成员变量只能被对象调用
   - 静态变量可以被对象调用,还可以被**类名调用**
3. 别名不同
   - 成员变量也被称为实例变量
   - 静态变量被称为类变量
4.   数据储存位置不同
   - 成员变量数据储存在堆内存的对象中,所以也叫对象的特有数据
   - 静态变量数据储存在方法区(共享数据区)的静态区,所以也叫对象的共享数据

静态的使用的注意事项:

1. 静态方法只能访问静态成员. (非静态可以访问静态,也可以访问非静态)
2. 静态方法中不可以使用this或者super关键字
3. 主函数是静态的

```java
public class staticDemo2 {

	public static void main(String[] args) {
		//show();   //这相当与 在静态方法里面调用非静态 会报错
		new staticDemo2().show();    //但是可以通过new 自身去调用非静态方法
	}
	
	int num = 4;
	public void show() {
		System.out.println(num);
	}
}
```

**静态什么时候用?**

1. 静态变量

   - 当分析对象中所具有的成员变量都是相同的时候,这时候可以被静态修饰
   - 只要数据在对象中是不同的,就是对象的特有属性,必须储存在对象中,是非静态
   - 如果是相同的数据,对象不需要修改,只需要使用,不需要储存对象,定义成静态的

2. 静态函数

   - 函数时候用静态修饰,参考一点,就是函数功能是否有访问到对象中的特有数据

     假如是静态的成员变量,就用静态函数,,也可以定义非静态 

     非静态可以访问静态 静态函数不可以访问非静态成员变量

     假如是非静态变量,就定义非静态函数

##### 静态代码块

随着类的加载而执行,而且只执行一次,因为new的时候 内存已经加载  再new 内存已经存在静态代码块,所以不管new几次都只执行一次

作用

​	给类,静态变量进行初始化 构造函数是给成员变量进行初始化 

```java
public class staticDemo2 {

	public static void main(String[] args) {
		score s = new score();
		score s1 = new score();
		score s2 = new score();
	}
}

class score{
	static String num;
	static {
		num = "一";
		System.out.println("我只执行"+num+"次");
	}
}
```

#### main函数解析

主函数特殊之处:

1. 格式固定
2. 被jvm虚拟机所识别 调用

public:             因为权限必须最大

static:		不需要对象所属类名调用即可

void:		主函数没有具体返回值

main: 		函数名 ,是jvm识别的固定函数名

String[]  args:主函数的参数列表,是一个数组类型的参数,而且元素都是字符串类型

可以在命令框里面 给args传值

```
java demo a a a a a  //给args数组传值 
```

#### 继承

提高代码复用性

让类与类之间产生关系,给第三特征多态提供前提

```java
public class jichen {
	public static void main(String[] args) {
		Student s = new Student();
		s.study(18, "小明");
		Worker w = new Worker();
		w.work(29, "张三");
	}
}


class Presons {
	int age;
	String name;
}

class Student extends Presons {
	void study (int age,String name) {
		System.out.println("name:"+name+"学生--age:"+age);
	}
}

class Worker extends Presons {
	void work (int age,String name) {
		this.age = age;
		this.name = name;
		System.out.println("name:"+name+"工人--age:"+age);
	}
}
```

java中支持单继承,不直接支持多继承,但是对c++中的多继承机制进行改良

单继承: 一个子类只有一个父类

多继承: 一个子类可以有多个直接父类(java不允许,因为会产生调用的不确定性)

java支持多层继承 (c 继承 b  b 继承 a )

当要使用一个继承体系的时候

1. 查看该体系的顶层类,了解该体系的基本功能
2. 创建体系中的最子类对象,完成功能的使用

##### super关键字

```java
class Fu{
	private int a = 1;
	void geta() {
		System.out.println(a);
	}
}

class Zi extends Fu{
	int a = 2;
	Zi (){
		//System.out.println(super.a);   //私有化的将无法super去继承
		super.geta();
	}
}

class Zii extends Zi {
	int a = 3;
	Zii () {
		System.out.println("父类的a="+super.a);
		
	}
}
```

this与super的用法很相似

this: 代表一个本类对象的引用

super: 代表一个父类空间 因为没有new 父类

##### 继承 - 覆盖

当子父类中出现成员函数一模一样的情况,会运行子类的函数

这种现象,称为覆盖操作,这是函数在子父类里面的特征

```java
public class superdemo {
	public static void main(String[] args) {
		Zi z = new Zi();
		z.geta();
	}
}


class Fu{
	void geta() {
		System.out.println("我是父类");
	}
}

class Zi extends Fu{
	void geta() {
		System.out.println("我是子类");
	}
}
```

函数的两大特性:

1. 重载 在同一个类中的
2. 覆盖,子类覆盖父类,覆盖也称为重写,覆写

注意事项

1. 子类方法覆盖父类方法时,子类权限必须大于等于父类权限
2. 静态只能覆盖静态,或者被静态覆盖

什么时候使用覆盖操作?

当对一个类进行子类的拓展的时候,子类需要保留父类的功能声明

但是要定义子类中该功能的特有内容时,就要使用覆盖操作去完成

#####子父类的构造函数的问题

特点: 在子类构造对象的时候,发现,访问子类构造对象时,父类也运行了

原因: 在子类中所有的构造对象中的第一行都有隐式语句 spuer(),因为父类初始化动作必须第一行

子类的实例化过程: 子类中所有的构造函数默认都会访问父类中的空参数的构造函数

因为子类继承父类,获取到了父类内容,所以在使用父类之前,要先看父类是如何对自己的内容进行初始化的



子类构造函数中如果this调用了本类构造函数时,那么super就没用了,因为super和this都只能定义在第一行,所以只能有一个

```java
public class shilihua {

	public static void main(String[] args) {
		Zilei z = new Zilei();
		z.show();
	}

}

class Fuqin {
	Fuqin () {
		show();
	}
	void show() {
		System.out.println("this is fu");
	}
}

class Zilei extends Fuqin {
	int num;
	Zilei () {
		super();
		//这里的this 指向子类 子类的对象变量没有初始化,等super()父类初始化完毕后,才会进行子类的成员变量初始化
		num = 8;
	}
	void show () {
		System.out.println("this is"+ num);
	}
}


```

一个对象的实例化过程

1. jvm会读取指定的路径下的person.class文件,并加载进内存,并会先加载Person的父类
2. 在堆内存中开辟空间,分配地址
3. 并在对象空间中,对对象中的属性进行初始化
4. 调用对应的构造函数进行函数的初始化
5. 在构造函数中,第一行会先调用父类中的构造函数进行初始化
6. 父类初始化后,会对子类的属性进行显式初始化
7. 在进行子类构造函数的特定初始化
8. 初始化完毕后,将地址复制给引用变量



#### 设计模式

单例设计模式

​	解决的问题: 可以保证一个类在内存里面的唯一性

比如对于多个程序使用统一配置信息对象的时候,需要保证对象的唯一性

如何保证对象的唯一性?

1. 不允许其他对象new 创建该对象
2. 在该类里面创建自己的实例
3. 对外提供方法让其他程序可以获取该对象

 步骤:

1. 私有化对对象的构造函数
2. 通过new  创建本类对象
3. 定义一个共有方法,将创建的对象返回

````java
public class shejimoshi {

	public static void main(String[] args) {
//		test test1 = new test();    //会报错
//		test test2 = new test();
		test test1 = test.getInstance();
		test test2 = test.getInstance();
		test1.setnum(10);
		test2.setnum(20);
		System.out.println(test1.getnum());	
		System.out.println(test2.getnum());
	}

}

class test {
	private int num;
	
	//这几行代码完成了要求
	private test () {}  //被new 内存就没办法保持引用类型的一致
	private static test s = new test();     //为了保持内存的一致性 在内部new 自己 并且为了外部可以引用 改为静态
	
	public static test getInstance() {  //因为不可以new 了 所以是能通过static的形式去让外部调用
		return s;
	}
	
	public  void setnum (int num) {
		this.num = num;
	}
	public int getnum() {
		return num;
	}
}

````

饿汉式 ---- 类一加载,对象就存在了

```java
class Single{
	private Single () {}   //防止new 
 	private static Single s = new Single();     // 将对象静态化  
   	public static Single getInstance(){       // 返回静态化的方法地址 这样 不管谁引用,都是一个地址
    	return s;
    }
}
```

懒汉式  ---- 类加载进来,没有对象 只有调用了getInstance方法时候,才会创建对象

```java
class Single{
	private Single () {}   //防止new 
 	private static Single s = null;     // 将对象静态化  
   	public static Single getInstance(){       // 返回静态化的方法地址 这样 不管谁引用,都是一个地址
    	if(s == null){
            s = new Single();
            return s;
    	}
    }
}
```

#### final

1. final可以修饰变量 类
2. final 修饰的类无法被继承
3. final 修饰的方法不可以被覆盖
4. final修饰的变量是一个常量,只能赋值一次          
5. final 不会默认初始化

为什么使用final修饰变量?

​	因为程序如果一个数据是固定的,那么直接使用这个数据是固定的,那么直接使用这个数据就可以了

但是直接使用阅读性差,所以给该变量起个名字,而且这个变量的值不能变化,所以加上final

写法规范: 常量所有字母都大写,多个单词,中间用_连接

修饰符: 

public: 全局访问

private: 私有修饰符 只能在本类中被使用

static: 静态 通过类名直接访问

final: 将变量修饰为常量的修饰符 

#### 抽象类

不具体即为抽象

特点:

1. 方法只有声明没有实现的时候,该方法就是抽象方法,需要被abstract修饰
2. 抽象类无法被实例化,因为调用抽象对象没有意义
3. 抽象类必须有其子类覆盖了所有的抽象方法,该子类才可以实例化,否则,子类也是抽象类

抽象类的问题:

1. 抽象类有构造函数吗?

    有,用于给子类对象进行实例化

2. 抽象类可以不定义抽象方法吗?

   可以,但是很少见,主要用于不让该类创建对象

3. 抽象类关键字不可以个那些关键字共存

   private	因为私有化 子类无法覆盖

   static 	不可以 因为可以直接使用类名调用, 没有意义

   final    	abstract 与 final 的意义相反 一个是必须覆盖,final是一定不可以覆盖

4. 抽象类和一般类的异同点

   - 相同点: 抽象类和一般类都是用来描述事物的,都在内部定义成员
   - 不同点
     - 一般类有足够的信息描述事物
     - 抽象类描述事物的信息不足
     - 一般类中不能定义抽象方法,只能定义非抽象方法
     - 抽象类里面可以定义抽象方法,也可以定义非抽象方法
     - 一般类可以被实例化
     - 抽象类不可以被实例化

5. 抽象类一定是父类吗?

   是的 因为抽象类不可直接使用,所以一定有子类 才 可以使用

```java
public class jiekou {

	public static void main(String[] args) {	
		b b = new b();
		b.show();
		b.data();
	}
}


abstract class a {                   //abstract 创建抽象类
	public abstract void show();
	void data() {
		System.out.println("这里是data");
	}
}

interface c {                        //创建一个接口
	public abstract void show();
}

interface MM extends c {   //接口接口之间是继承关系
	public abstract void ss();
}

class b extends a implements MM {
	public void show() {
		System.out.println("haha");
	}

	public void ss() {
		System.err.println("抽象类必须重写");		
	}
}

```

####接口

定义接口的关键字不是class 是interface

对于接口当中常见的成员 - 这些成员都有固定的修饰符

1. 全局变量 public static final
2. 抽象对象 public abstract

由此可以看出接口中的成员都是公共权限

类继承接口是implements

```java
public class jiekou {

	public static void main(String[] args) {	
		b b = new b();
		b.show();
	}

}


interface a {
	public abstract void show();
}

class b implements a {
	public void show() {
		System.out.println("haha");
	}
}
```

java的接口可以多实现

接口的特点:

- 接口是对外暴露的规则
- 接口是程序的功能拓展
- 接口的出现 降低了耦合性
- 接口实现了多实现
- 类和接口之间是实现关系,而且类可以继承一个类的同时实现多个接口
- 接口接口之间可以是继承关系

接口是抽象类的异同点

相同点: 

​	都是向上抽取出来的

不同点:

​	抽象类需要被继承,而且只能单继承

​	接口需要被实现,而且可以多实现

​	抽象类中可以定义抽象方法和费抽象方法,子类继承后,可以直接使用非抽象方法

​	接口中只能定义抽象方法,必须由子类去实现

​	抽象类的继承 是基本保持共性的

​	接口的实现是 定义体系外的额外功能

```java
//接口的使用
public class bookPc {

	public static void main(String[] args) {
		Upan u = new Upan();  //功能拓展
		useUsb(u);
		useclose(u);
	}	
	//使用规则
	public static void useUsb(USB u) {    //接口类型的引用 用于接收(指向)接口的子类对象
		u.open();
	}
	public static void useclose(USB u) {
		u.close();
	}
}

//暴露的规则
interface USB {                 
	public void open();
	public void close();
}
//实现规则
class Upan implements USB {
	public void open (){
		System.out.println("U盘打开");
	}
	public void close () {
		System.out.println("U盘关闭");
	}
}

```

#### 多态

```java
public class duotai1 {

	public static void main(String[] args) {
		donwu a = new cat();    //自动类型提升 猫对象提升为动物 但是特有供能无法访问
        //作用是限制对特有功能的访问
		cat b = new cat();
		// 一个对象 两种形态
		//猫种类事物即具猫类,又具备dongwu的形态 这就是对象的多态性
		//简单说就是一个对象对应着不同的类型
		//多态在代码上的体现: 父类或者接口的引用指向子类的对象
		
	}

}

class donwu {
	donwu () {
		System.out.println("我是A");
	}
}

class cat extends donwu {
	cat () {
		System.out.println("我是B");
	}
}
```

多态的优点:

- 提高了代码的拓展性,前期定义的代码可以使用后期内容

多态的弊端:

- 前期定义的内容不能使用(调用)后期子类的特有内容

多态的前提:

- 必须有关系,继承 实现
- 要有覆盖

```java
public class duotai2 {
	public static void main(String[] args) {
		method(new Cat());  //自动类型提升 猫对象提升为动物 但是特有供能无法访问
        //作用是限制对特有功能的访问
		method(new Dog());
	}
	public static void method(Animal a1) {
//		Cat a = (Cat)a1;    //如果还想具体动物的猫的特有功能,你可以将该对象进行向下转型,这样就可以使用子类的方法
//		//对于转型,自始至终都是子类对象在做类型的转换
//		a.eat();
//		a.Mouse();
		
		if(a1 instanceof Cat) {    //用于判断对象的具体类型 instanceof 在向下转型前用于健壮性的判断
			Cat a = (Cat)a1;       //向下转型
			a.eat();
			a.Mouse();
		} else if(a1 instanceof Dog) {
			Dog a = (Dog)a1;
			a.eat();
			a.home();
		}
	}
}

abstract class Animal {   //创建抽象类
	abstract void eat();  //抽象方法
}

class Cat extends Animal {
	void eat() {
		System.out.println("猫粮");
	}
	void Mouse() {
		System.out.println("抓老鼠");
	}
}

class Dog extends Animal {
	void eat() {
		System.out.println("狗粮");
	}
	void home() {
		System.out.println("看家");
	}
}
```



多态时成员的特点:

- 成员变量

  - 编译时: 参考引用型变量所属的类是否有调用的成员变量,有,编译通过,没有 编译失败
  - 运行时: 参考引用型变量所属的类是否有调用的成员变量,并运行该所属类中的成员

  编译和运行都参考等号的左边

- 成员函数

  - 编译时: 参考引用型变量所属的类中的是否有调用的数,有 编译通过 没有 编译失败
  - 运行时: 参考的是对象那个所属的类是否有调动的函数

  简单来说,编译看左边 运行看右边

- 静态函数

  - 编译时: 参考引用型变量所属的类是否有调用的静态方法
  - 运行时: 参考引用型变量所属的类是否有调用的静态方法

其实对于静态方法 是不需要对象的,直接用类名调用

#### 内部类

1. 内部类可以直接访问外部类的成员
2. 外部类要访问内部类,必须建立内部类的对象

分析事物 发现该事物描述中还是有事物,而且这个事物还在访问被描述事物的内容 这就要用内部类

在外部 进行内部类的访问 

```java
Wai.Lei li = new Wai().new Lei();
```

内部类 访问 外部变量 以及内部变量

```java
public class leibulei2 {
	public static void main(String[] args) {
		fuqin.erzi e = new fuqin().new erzi();
		e.show();
	}
}
class fuqin {
	int a = 1;
	class erzi {
		int a = 2;
		void show () {
			int a = 3;
			System.out.println(a);                      //3 在栈里面找
			System.out.println(this.a);                 //2 在erzi里面找
			System.out.println(fuqin.this.a);           //1 在父类里面找
		}
	}
}

```

###### 匿名内部类

就是内部类的简写

必要的前提: 内部类必须继承或者实现一个外部类或者接口

匿名内部类: 其实就是一个匿名的子类对象

格式 new父类/接口 (){.......}.方法();

````java
public class limin {

	public static void main(String[] args) {
		one one = new one();
		one.show();
	}

}

//匿名内部类 可以匿名实现接口
 abstract class Demo {
	 abstract void show();
 }

 class one {
	 public void show() {
		 new Demo() {
			void show() {     
				System.out.println("这是匿名内部类");
			}
		}.show();
	 }
 }
````

接口

```java
public class limin {

	public static void main(String[] args) {
		three t = new three();
		t.show();
	}

}

 interface jiekou {
	 void show();
 }
 
 class three {
	 void show() {
		 new jiekou() {
			 public void show () {
				 System.out.println("匿名内部类实现接口");
			 }
		 }.show();
	 }
 }

```

匿名内部类的细节

```java
public class leibulei3 {

	class one {
		void show () {
			new Object() {  // 这里相当于  class a extends Object  
				void zz () {
					System.out.println("这是继承了Object的匿名内部类");
				}
			}.zz();
			//o.show();    //这里,没办法进行show的直接调用  因为 show 这和方法已经向上转型 无法通过变量调用
		}
	}
	
	public static void main(String[] args) {
		//one a = new one();   在主函数里面因为是静态的,所以没办法去new 非静态的内部类
		new leibulei3().score();
	}
	
	public void score () {
		one o = new one();
		o.show();
	} 
}
```

####对象的初始化过程

1. 进入子类构造函数
2. 父类构造函数初始化
3. 执行父类构造函数的方法
4. 显式初始化 
5. 运行构造代码块

```java
public class chushuhua {

	public static void main(String[] args) {
		Zi z = new Zi();
		z.show();
	}
}

class Fu {
	Fu () {
		System.out.println("父类初始化");
		show();
	}
	void show () {
		System.out.println("haha");
	}
}

class Zi extends Fu {
	int num = 1;
	{
		System.out.println("局部代码块"+num);
	}
	Zi () {
		super();   /*	--(1).进入子类构造函数,(2)父类构造函数初始化  Fu构造函数执行
						-- show()执行(3) 但是 子类super没执行完之前 num没有完成初始化  所以是 0
						这时候 (4)--显示初始化--
						--(5)构造代码块
						--子类构造函数初始化完成
		 			*/
		System.out.println("子类初始化");
	}
	void show () {
		System.out.println("num="+num);
	}
}
```

### 异常

运行时期发生的不正常情况

在java中用类的形式对不正常情况进行描述和封装对象,描述不正常的类,也被称为异常类

将正常流程代码和问题处理代码结合

不同的问题用不同的类进行描述,比如角标越界,空指针等等

最终(不正常情况)就分成两大类

Throwable  无论是errot 还是 Exception 都抛出 让调用者知道并且处理  也只有Throwable可以抛出

​				//该体系的特点就是Throwable及其所有的子类都具有可抛性

​				通过关键字throw throws 凡是通过这两个关键字所调用的类和对对象都具有可抛性

- 不可处理的 Errot    --- 由jvm抛出的严重性问题,不针对处理 直接修改程序
- 可以处理的 Exception

子类的后缀名 都是用其父类名作为后缀,阅读性很强

**自定义异常**

```java
public class one {
	public static void main(String[] args) throws Exception {
		int[] arr  = new int[3];
		Demo d = new Demo();
		System.out.println(d.method(arr,-1));
	}
}

class Demo {
	public int method(int arr[],int index) throws Exception {  //为什么要 throws Exception 因为声明函数
		if (arr == null) {
			throw new NullPointerException("引用对象不可以为空");
		} else if (index>=arr.length) {
			throw new ArrayIndexOutOfBoundsException("角标越界");
		} else if (index<0) {
			throw new FushuIndexException("角标变成负数了");
		}
		return arr[index];
	}
}

class FushuIndexException extends Exception {   //自定义异常要继承异常类 添加构造函数
	public FushuIndexException(String msg) {
		super(msg);   //这里不需要打印 因为 exception 这和类已经把方法写好了 所以直接传就行了
	}
}


//异常最后报错 说明 语法已经是没有错误的了
```

异常的分类:

1. 编译时被检测的异常,也就是EXception和其子类都是,除了特殊子类RuntimeException 体系

   - 这种问题一旦出现,希望在编译时就进行检测,让这种问题有对应的处理方式,这样的问题就可以针对性的解决

2. 编译时不检测异常,也就是exception中的runtimeException和其子类 

   - 这种问题的发生,无法让功能继续,运算无法进行,更多是因为调用者的原因导致的而或者引发了内部状态的改变导致的,那么这样的问题一般不处理,直接编译通过,在运行时候,让调用者调用时程序停止,对代码进行修正

   比如程序没错 但是参数错的 这样的错误不会被检测,或者只有运行的时候才能看到错

```java
class FushuIndexException extends RuntimeException {   //改成Runtime 就无需声明异常了
	public FushuIndexException(String msg) {
		super(msg);   //这里不需要打印 因为 exception 这和类已经把方法写好了 所以直接传就行了
	}
}
```



自定义异常的时候 要么继承 Exception 要么继承 RuntimeException

throws 使用在函数上,抛出异常类,可以一次抛出多个,用逗号隔开

throw   抛出的是异常对象

#####try catch

​	对异常情况的针对性处理方式

try {

​	需要被检测的代码

} catch ( 异常类 变量 ) {     该变量用于接受发生的异常对象

​	处理异常的代码

} finally {

​	无论代码时候正常都运行的代码

}

```java
package Exception;

public class one {
	public static void main(String[] args) throws FushuIndexException {
		int[] arr  = new int[3];
		Demo d = new Demo();
		try {                                     //可以解决就try 不能解决就抛出
			int num = d.method(arr,-1);
			System.out.println(num);
		} catch (FushuIndexException e) {   //FushuIndexException e = new FushuIndexException()  相当于这样
			System.out.println(e.getMessage());
			e.printStackTrace();  //jvm默认的异常处理机制 就是调用printStackTrace 
		} catch (NullPointerException e) {
			System.out.println(e.toString());
		} catch (Exception e) {    //以上catch 会捕捉上面catch 没有的情况  多catch 父类catch放在最下面
			e.printStackTrace();
		}
	}
}

class Demo {
	public int method(int arr[],int index) throws FushuIndexException {  //为什么要 throws Exception 因为声明函数
		if (arr == null) {
			throw new NullPointerException("引用对象不可以为空");
		} else if (index>=arr.length) {
			throw new ArrayIndexOutOfBoundsException("角标越界");
		} else if (index<0) {
			throw new FushuIndexException("角标变成负数了");
		}
		return arr[index];
	}
}

class FushuIndexException extends Exception {   //自定义异常要继承异常类 添加构造函数
	public FushuIndexException(String msg) {
		super(msg);   //这里不需要打印 因为 exception 这和类已经把方法写好了 所以直接传就行了
	}
}


//异常最后报错 说明 语法已经是没有错误的了
```

异常函数处理原则

1. 函数内容如果抛出需要检测的异常,那么函数上必须要声明,或者在函数内部进行try catch 捕捉 ,否则编译失败

2. 如果调用到了声明异常的函数,要么 try catch 要么 抛出(throws) 否则编译失败

3. 什么时候catch 什么时候 throws ? 

   功能内容可以解决 用catch;

    解决不了的 用throws告诉调用者

4. 一个功能如果抛出多个异常,那么调用时,必须有对应多个catch进行针对性的处理

   内部有几个需要检测的异常,就抛出几个异常,抛出几个,就catch几个

finally 就算try catch里面return 也依旧会执行finally里面的代码

只有一种情况使得finally不执行 System.exit();

可以有try finally 这样的组合,但是要抛出

异常的应用

```java
public class two {

	public static void main(String[] args) throws NanpinException,Senbinexception {
		Teacher t = new Teacher("毕老师");
		try {
			t.shangle();
		} catch (NoplanException e) {
			System.out.println("学校表示:..............换老师");
		}
		
	}
}



class Teacher {
	private String name;
	private Comp comp = new Comp();
	public Teacher(String name){
		this.name = name;
	}
	public void shangle () throws NanpinException,Senbinexception, NoplanException  {
		try {    //检查电脑时候有问题
			
			comp.comp();   
			System.out.println(name+"开始上课");
			
		} catch (NanpinException e) {
			
			System.out.println(e.getMessage());
			reset();
			shangle();
		} catch (Senbinexception e) {
			System.out.println(e.getMessage());
			throw new NoplanException();        //捕获错误 同时抛出另外的错误
		}
	}
	public void reset(){
		comp.reset();
	}
}


class Comp {
	int num = 2;
	public void comp () throws NanpinException,Senbinexception {
		if(num == 0) {
			System.out.println("电脑运行");
		}else if(num == 1) {
			throw new NanpinException("电脑蓝屏了!!");
		}else if(num == 2) {
			throw new Senbinexception("老师生病了!!");
		}
	}
	
	public void reset () {
		num = 0;
		System.out.println("电脑重启");
	}
}

class NanpinException extends Exception {
	public NanpinException(String msg) {
		super(msg);
	}
}

class Senbinexception extends Exception {
	public Senbinexception (String msg) {
		super(msg);
	}
}
class NoplanException extends Exception {
	public NoplanException () {}
}

```

异常的注意事项

1. 子类在覆盖父类方法的时候,父类方法如果抛出异常,那么子类的方法只能抛出父类的异常或者该异常的子类
2. 如果父类抛出多个异常,那么子类只能抛出父类的异常的子集

简单说     子类覆盖父类只能抛出父类的异常或者子集

​		如果父类的方法没有抛出异常,那么子类覆盖时绝对不能抛,只能try

####Object类的方法

所有类的上帝 Object是不断抽取而来,所有对象都有的共性内容

#####equals hashCode getClass toString 

```java
package ss;

public class Object1 {

	public static void main(String[] args) {
		Person p1 = new Person(20);
		Person p2 = new Person(20);
		Person p3 = p1;
		System.out.println(p1.equals(p3));  //比较的是内存地址
		System.out.println(Integer.toHexString(p1.hashCode()));    
		//hashCode 获取对象的在内存里面的hashCode值
		System.out.println(p1.getClass().getName());  //获取   
		System.out.println(p1.getClass().getName()+"$"+Integer.toHexString(p1.hashCode()));  //内存地址
	}

}
class Person extends Object {
	private int age;
	public Person(int age) {
		this.age = age;
	}
	public boolean equals(Object age) {   //重写equals 方法 
		if(!(age instanceof Person)) {
			throw new NomanException("不是数字");    //自定义异常
		}
		Person p = (Person)age;
		return this.age == p.age;
	}
//	public int hashCode () {          	  //重写 hashCode方法,意味着对象的内存地址发生变化
//		return age;
//	}
	public String toString () {           //重写toString   原本是返回该对象的字符串表示
		return "Person"+age;
	}
}

class NomanException extends RuntimeException {
	NomanException (String msg) {
		super(msg);
	}
}

```


#### 面向对象 - 包

package 包名所有字母都小写

-d <目录>                    指定放置生成的类文件的位置

```
package mypackage        //定义包名  在文件系统里面即使文件夹名
```

javac -d  .one.java    这样class 文件就会生成到当前目录里面去

运行的时候 就是 java mypackage.one



包与包的访问

 包与包之间的类进行访问,被访问的包必须是public的,被访问的包中的类的方法也必须是public 

```
public		最高权限 包 类 子类 不同的包都可以访问到
protected 	可以在同一个包 同一个类 子类里面访问 但是 不可以在不同的包里面访问
default  	可以在同一个类里面 也可以在同一个包里面访问 但是 在子类 以及不同的包里面无法访问
private 	只能在同一个类里面访问
```



import

```java
package ss;

import score.*;   //导入score包里面的Superdemo类   * 是导入所有类
//导包的原则 用到那个类 就导入那个类  import 就是为了简化类名的书写

public class Object2 extends score.Superdemo {

	public static void main(String[] args) {
		new Object2().geta();
		Superdemo s = new Superdemo();   //这种情况下 protected 属性 只能在被继承的时候 使用
		s.geta();
	}
	
}

```

jar 包就是压缩后的class包