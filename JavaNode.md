# Java基础学习



[TOC]



## 1 Java提前知识

### 1.1CMD

图形化界面的缺点：消耗更多的内存，运行速度没有命令方式快

CMD：利用命令行的方式操作计算机

**打开CMD窗口**

- win+r 出现运行窗口
- 在运行窗口输入cmd回车

**常见的CMD命令**

- 切换盘符：盘符+冒号（e:）

- 查看当前目录下内容：dir 
- 进入（单/多级）文件：cd 目录/目录 /文件
- 回退到上一目录：cd .. 
- 回退到盘符目录：cd \ 

- 清屏：cls 
- 退出窗口：exit 
- 打开文件：文件名+后缀
- 删除文件夹：rd 文件夹/s
- 删除文件：del 文件名+后缀

### 1.2 环境变量

**环境变量（Environment variables）**：一般是指在操作系统中用来**指定操作系统运行环境的一些参数**

如：临时文件夹位置和系统文件夹位置等

**Java配置Path环境变量的目的**

java每次需要调用jdk目录下的javac以及java程序，而调用需要每次输入绝对路径，为了方便我们调用，配置Path环境变量

**如何找回误删的环境变量呢？**

- 打开注册表（win+r 输入regedit）
- 查找path（计算机\HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\Session Manager\Environment）
- 查询path的值

### 1.3 IDEA中内容的辅助键和快捷键

- 快速生成语句：

​	**快速生成main()方法：psvm，回车**

​	**快速生成输出语句：sout，回车**

- 内容辅助键：

​	**ctrl+alt+space ：内容提示，代码补全**

- 快捷键：

​	**注释：**

​		单行：选中代码，ctrl+/,再来一次取消

​		多行：选中代码，ctrl+shift+/,再来一次取消

​	**格式化**：ctrl+alt+l

### 1.4 HelloWorld分析java编译解析过程

.java文件  被javac 编译为.class字节文件

.class文件 被java  解释到窗口显示

### 1.5 解决Bug

要具备识别以及解决Bug的能力

例如：

​	错误：非法字符 --中文字符

​				system无法识别---System首字母大写

### 1.6 注释

- 单行注释		格式：//注释信息
- 多行注释        格式：/*注释信息*/
- 文档注释         格式：/**注释信息**/

### 1.7 关键字

- 关键字开头**首字母小写**
- 常用代码编辑器对关键字进行颜色标记，直观

例如：public，class等

## 2 基础知识

### 2.1 常量

- 字符串常量：用双引号括起来的内容，如：“helloworld”
- 整数常量：不带小数的数字，如：666
- 小数常量：带小数的数字，如：3.14
- 字符常量：用单引号括起来的内容，如：‘A’
- 布尔常量：bool值表示真假，true或false
- 空常量：空值，null

### 2.2 数据类型

- 计算机最小的**存储**单元：字节B（byte）
- 计算机最小的**信息**单元：位b（bit）

1B = 8bit ，1KB = 1024B

1MB = 1024KB ，1GB = 1024 MB ,1TB = 1024GB

![](C:\Users\Asinil\Desktop\学习\Java\2.2.PNG)

| 数据类型 |    关键字    | 内存占用 |   取值范围   |
| :------: | :----------: | :------: | :----------: |
|   整数   |     byte     |    1     |   -128~127   |
|          |    short     |    2     | -2^15~2^15-1 |
|          |  int(默认)   |    4     | -2^31~2^31-1 |
|          |     long     |    8     | -2^63~2^63-1 |
|  浮点数  |    float     |    4     |              |
|          | double(默认) |    8     |              |
|   字符   |     char     |    2     |   0-2^16-1   |
|   bool   |   boolean    |    1     |  true/false  |

### 2.3 变量

**变量定义：**

​	数据类型 变量名 = 变量值

**定义变量注意事项：**

- 定义变量名不能重复
- 未赋值的变量名不能使用
- <u>定义long类型时，变量值是整数时默认int类型，整数太大超过int取值范围不会报错，须在变量值后加l/L</u>
- <u>定义float类型时，变量值是浮点数时默认double类型，防止类型不兼容，须在变量值后加f/F</u>

### 2.4 标识符

标识符定义规则：

- 由数字，字母，下划线，美元符组成
- 不能以数字开头
- 不能是关键字
- 区分大小写

**常见的命名约定：**

（**小驼峰命名法：针对方法，变量**）

1. 标识符是一个单词时，首字母小写，例如：name
2. 标识符由多个单词组成时，首单词首字母小写，其他单词首字母大写，例如：firstName

（**大驼峰命名法：针对类**）

1. 标识符是一个单词时，首字母大写，例如：Name
2. 标识符由多个单词组成时，每个单词首字母大写，例如：FirstName

### 2.5 类型转换

自动类型转换：把一个**数据范围小**的数值或变量赋值给另一个**范围大**的变量

例如：double d = 10(int);

![](C:\Users\Asinil\Desktop\学习\Java\2.5.PNG)

**byte，short无法直接转换类型为char**

强制类型转换：把一个大范围的数值或变量赋值给另一个范围小的变量

格式：
```java
原数据类型 变量名 = （目标数据类型）变量/值
```

例如：int k = (int)88.88;

### 2.6 算术运算符

运算符：对常量或变量进行操作的符号，例如：“+”，“-”，“*”，“/”

表达式：用运算符把常量或者变量连接起来符合java语法的式子，例如：a+b

### 2.7 自增自减运算符

自增自减运算符有：++，--

- 单数使用，++/--写在钱前面或者后面都是一样的
- ++i和i++在运算中效果可能相同也可能不同

i++和++i的区别：

```java
//i = 10
int a = i++;
int b = ++i;
//a和b的结果不一样，第一个是i的值先赋值给a，在进行++操作，第二个是先进行++操作，在将i的值赋给b
System.out.println(a);
System.out.println(b);
//a = 10,b = 12
```

### 2.8 字符的+操作

- A：65 A-Z是连续的
- a：97 a-z是连续的
- 0：49 0-9是连续的

算数表达式包含**多个基本数据类型**的值时，整个表达式的类型都会**自动进行提升**

- byte，short类型和char类型将被提升到int类型

- 整个表达式的类型提升到表达式中最高等级操作数同样的类型

  等级顺序：byte，short，char -> int -> long ->float ->double

### 2.9 字符串的+操作

+操作出现字符串，+相当于连接符，对字符串进行拼接多个+操作时，拼接顺序从左至右

### 2.10 赋值运算符

赋值运算符：=，+=，-=，*=，/=，%=

**a=a+b在一定程度上等于a+=b但不完全等于，因为类型可能不匹配**

扩展的赋值运算符隐含了强制类型转换

### 2.11 关系运算符

| 符号 |                        说明                        |
| :--: | :------------------------------------------------: |
|  ==  |  a==b,判断a,b是否相等，成立为true，不成立为false   |
| ！=  | a！=b,判断a,b是否不相等，成立为true，不成立为false |
|  >   |   a>b,判断a是否大于b，成立为true，不成立为false    |
|  >=  | a>=b,判断a是否大于等于b，成立为true，不成立为false |
|  <   |   a<b,判断a是否小于b，成立为true，不成立为false    |
|  <=  | a<=b,判断a是否小于等于b，成立为true，不成立为false |

**如果将==写为=，则表示将右边的值或变量赋予给左边然后输出**

### 2.12 逻辑运算符

| 符号 |   说明   |             作用             |
| :--: | :------: | :--------------------------: |
|  &   |  逻辑与  |        有false则false        |
|  \|  |  逻辑或  |         有true则true         |
|  ^   | 逻辑异或 |   相同为false，不同为true    |
|  !   |  逻辑非  | 非true为false，非false为true |

### 2.13 短路逻辑运算符

| 符号 |  说明  |             作用             |
| :--: | :----: | :--------------------------: |
|  &&  | 短路与 | 作用与&相同，但具有短路效果  |
| \|\| | 短路或 | 作用与\|相同，但具有短路效果 |

- &和&&的区别:当左边一个判定为false时，&&不在执行右边二个判定，而&还会执行
- |和||的区别:当左边一个判定为false时，&&不在执行右边二个判定，而&还会执行

### 2.14 三元运算符

格式：
```java
关系表达式？表达式1：表达式2
```

例如：a>b?a:b;

计算规则：

​	首先计算关系表达式的值

- ​	如果值为true，表达式1的值就是运算结果
- ​	如果值为false，表达式2的值就是运算结果

**例题：两只老虎：有两只老虎，m体重180，n体重200，用程序判断两只老虎体重是否相同？**

```java
int m = 180;
int n = 200;
boolean res = m==n?true:false;
System.out.println(res);
```

**例题：三个和尚：三个和尚的身高分别为150cm，165cm，210cm，用程序失效获取三个和尚的最高身高？**

```java
int h1 = 150;
int h2 = 165;
int h3 = 210;
int temph = h1>h2?h1:h2;
int maxh = temph>h3?temph:h3;
System.out.println("最高身高："+maxh);
```

## 3 流程控制

### 3.1数据输入 Scanner API

数据输入必须用到Scanner类，以下是使用的基本步骤：

- 导包

```java
	import java.utill.Scanner;
```

​	导包的动作必须出现在类定义的上面

- 创建对象

```java
	Scanner sc = new Scanner (System.in);
```

​	上面这个格式里面sc是变量名，可以变动，其他不可以

- 接收数据

```java
	int i = sc.nextInt();
```

​	上面这个格式里面i,sc是变量名，可以变动，其他不可以

### 3.2 顺序结构

按代码顺序依次执行，从上到下，从开始到结束

### 3.3 if语句

#### 3.3.1 if……else结构

格式1：

```java
if（关系表达式）{
	语句体
}
```

执行流程：

1. 计算关系表达式的值
2. 如果关系表达式为true，则执行语句体，为false则不执行
3. 继续执行后续语句

格式2：

```java
if（关系表达式）{
		语句体1
	}else{
		语句体2
	}
```

执行流程：

1. 计算关系表达式的值
2. 如果关系表达式为true，则执行语句体1，为false则执行语句体2
3. 继续执行后续语句

**例题：三个和尚plus：三个和尚未知，测量后比较三个和尚得出最高身高？**

```java
Scanner sc = new Scanner(System.in);
System.out.println("请输入第一个和尚身高： ");
int hight1 = sc.nextInt();
System.out.println("请输入第一个和尚身高： ");
int hight2 = sc.nextInt();
System.out.println("请输入第一个和尚身高： ");
int hight3 = sc.nextInt();
int temp = hight1>hight2?hight1:hight2;
int max = temp>hight3?temp:hight3;
System.out.println("三个和尚最高身高： "+max+"cm");
```

**综合例题：任意给出一个整数，判断该整数是奇数还是偶数？**

```java
Scanner sc = new Scanner(System.in);
System.out.println("任意给出一个属： ");
int i = sc.nextInt();
if(i%2 == 0){
System.out.println(i+"是偶数");
}else{
System.out.println(i+"是奇数");
}
```

#### 3.3.2 if……else if……结构

```java
    if（关系表达式1）{
        语句体1
     }else if(关系表达式2){
        语句体2
     }esle{
        语句体3
     }
```

**例题：**

​	**考试奖励：期末考试了，小明爸爸根据小明考试成绩给予他奖励，100~95得到自行车，90~94可以去游乐园玩，80~89得到汽车人玩具，80分以下被爸爸揍一顿？**

```java
Scanner sc = new Scanner(System.in);
System.out.println("输入小明成绩： ");
int i = sc.nextInt();
if(i>=95 &&i<= 100){
    System.out.println("自行车奖励");
}else if(i<95 && i>= 90){
    System.out.println("去游乐园");
}else if(i >= 80 && i<90){
    System.out.println("玩具模型");
}else if(i <80){
    System.out.println("被胖揍");
}else {
    System.out.println("分数输入错误");
}
```

测试数据：**正确数据，边界数据，错误数据**

### 3.4 switch语句

格式；

```java
	switch(表达式){
		case 值1：
					语句体1;
					break;
		case 值2：
					语句体2;
					break;
		……
		default:
					语句体n+1;
					[break;]
	}
```

格式说明：

- 表达式：取值为byte，short，int，char，JDK5之后可以枚举，JDK7之后可以String
- case：后面跟的值要和表达式结果进行比较
- break：表示中断，结束switch
- default：表示所有类型不匹配时，就执行此处内容

执行流程：

1. 先计算表达式的值
2. 依次和case后的值进行比较，如果有对应的值，执行相应的程序后break结束
3. 如果和所有值不匹配，执行default的语句体，然后程序结束掉

**switch例题：春夏秋冬：一年由12个月分别属于春夏秋冬，键盘输入一个月份，用程序判断该月份属于那个月份并输出**

常规编写：

```java
Scanner sc = new Scanner(System.in);
System.out.println("输入一个月份（1~12）： ");
int i = sc.nextInt();
switch (i){
    case 1:
        System.out.println("春季");
        break;
    case 2:
        System.out.println("春季");
        break;
    case 3:
        System.out.println("春季");
        break;
    case 4:
        System.out.println("夏季");
        break;
    case 5:
        System.out.println("夏季");
        break;
    case 6:
        System.out.println("夏季");
        break;
    case 7:
        System.out.println("秋季");
        break;
    case 8:
        System.out.println("秋季");
        break;
    case 9:
        System.out.println("秋季");
        break;
    case 10:
        System.out.println("冬季");
        break;
    case 11:
        System.out.println("冬季");
        break;
    case 12:
        System.out.println("冬季");
        break;
    default:
        System.out.println("输入错误");
```

你会觉得switch程序太过于臃肿，这时候我们需要利用到case的另外一个特性：

​	**case穿透**：如果在case控制的语句体后面不写break，将出现穿透现象，在**不判断case值的情况下向下运行**，直到**遇到break或者整体switch语句结束**；

改进编程：

```java
switch (i){
            case 1:
            case 2:
            case 3:
                System.out.println("春季");
                break;
            case 4:
            case 5:
            case 6:
                System.out.println("夏季");
                break;
            case 7:
            case 8:
            case 9:
                System.out.println("秋季");
                break;
            case 10:
            case 11:
            case 12:
                System.out.println("冬季");
                break;
            default:
                System.out.println("输入错误");
}
```

### 3.5 for循环语句

循环结构的组成：

- 初始化语句：表示循环开启时的起始状态,这些语句完成初始化操作
- 条件判断语句：表示循环反复进行的条件，使用一个结果值为boolean类型的表达式
- 循环体语句：表示循环反复执行的内容
- 条件控制语句：表示循环执行中每次变化的内容，达到控制循环是否继续向下执行的效果，类似i++

for循环格式：

```java
for(初始化语句;条件判断语句;条件控制语句){
	循环体语句;
}
```

执行流程：

1. 执行初始化语句

2. 执行条件判断语句，看其结果时true还是false

   如果是false，循环结束

   如果是true，循环继续

3. <u>执行循环体语句</u>

4. <u>执行条件控制语句</u>

5. 回到步骤2继续

**例题1：输出数据：输出1~10和10~1的数据**

```java
//1~10
for(int i = 1; i <= 10; i++){
	System.out.println(i);
}
```

```java
//10~1
for(int i = 10; i > 0; i--){
	System.out.println(i);
}
```

**例题2：求和：求1~10的数据和**

```java
int sum = 0;
for(int i = 1;i <= 10;i++){
    sum += i;
}
System.out.println(sum);
```

**例题3：求1~100的所有偶数和**

```java
int sum = 0;
for(int i = 1;i <= 100;i++){
    if(i%2 == 0){
        sum += i;
    }   
}
System.out.println(sum);
```

**例题4：在控制台输出所有”水仙花数“**

​	**水仙花数：**

**1.水仙花数是个三位数**

**2.水仙花数的各位的立方和等于原数 例如 xyz = x^3+y^3+z^3**

```java
for (int i = 100;i <1000;i++){
            int z = i%10;
            int y = (i/10)%10;
            int x = i/100;
            int sum = x*x*x+y*y*y+z*z*z;
            if(sum == i){
                System.out.println(i);
            }
        }
```

### 3.6 while循环语句

循环语句格式:

```java
初始化语句;
while(条件判断语句){
    循环体语句;
    条件控制语句；
}
```

执行流程：(和for循环流程相同)

1. 执行初始化语句

2. 执行条件判断语句，看其结果时true还是false

   如果是false，循环结束

   如果是true，循环继续

3. 执行循环体语句

4. 执行条件控制语句

5. 回到步骤2继续

**例子：珠穆朗玛峰：珠穆朗玛峰高度为（8844.43米=8844430毫米），如我有一张足够大的纸张，它的厚度为0.1毫米，需要折叠多少次达到珠穆朗玛峰高度？**

```java
double h = 0.1;
int count = 0;
while(h < 8844430.0){
     h *= 2;
     count ++;
}
System.out.println("需要折叠： "+count+"次");
```

### 3.7 do……while循环语句

循环语句格式:

```java
初始化语句;
do{
    循环体语句;
    条件控制语句；
}while(条件判断语句);
```

执行流程：

1. 执行初始化语句

2. 执行循环体语句

3. 执行条件控制语句

4. 执行条件判断语句，看其结果时true还是false

   如果是false，循环结束

   如果是true，循环继续

5. 回到步骤2继续

### 3.8 三种循环的区别

#### 3.8.1 三种循环的区别:

- for和while循环都是先判断执行条件，后进行循环体
- dowhile循环是先进行一次循环体再判断执行条件

```java
//        for循环：
        for(int i = 2; i<2;i++){
            System.out.println("for循环");
        }
//        while循环
        int j = 2;
        while(j<2){
            System.out.println("while循环");
        }
//        do while循环
        int k = 2;
        do {
            System.out.println("dowhile循环");
        }while(k<2);
```

输出：dowhile循环

#### 3.8.2 for和while的区别

- 条件控制语句所控制的自增变量，因为归属for循环语法结构中，在for循环结束后，就不能被再次访问
- 条件控制语句所控制的自增变量，对于while循环来说不归属其语法结构中，在while循环结束后，该变量还能被再次访问

for循环，while循环，dowhile循环的三种死循环格式:

```java
//for
	for(;;){}
//while
	while(true){}
//dowhile
	do{
        
	}while(true);
```

其中，**while死循环**是最常用的，命令提示窗口中的ctrl+c能结束死循环

### 3.9 跳转控制语句

**跳过某次循环体内容的执行：countinue**（注意：使用基于条件控制的）

**终止循环内容的执行：break**（注意：使用基于条件控制的）

```java
//        跳转控制语句
        for(int i = 0;i<10;i++){
            if(i%2 == 0){
//                跳过执行循环体
                continue;
            }
            if (i>8){
//                终止循环
                break;
            }
            System.out.println(i);
        }
```

### 3.10 循环嵌套

语句结构：

- 顺序语句：以分号结尾，表示一句话的结束

- 分支语句：

​	一对大括号表示if的整体结构，整体描述一个完整的if语句

​	一对大括号表示switch的整体结构，整体描述一个完整的switch语句

- 循环语句：

​	一对大括号表示while的整体结构，整体描述一个完整的while语句

​	一对大括号表示do……while的整体结构，整体描述一个完整的do……while语句

任何语句对外都可以看成一句话，一句代码。例如：for(){},if(){}

分支中包含分支被称为**分支嵌套**

循环中包含循环被称为**循环嵌套**

**例如：输出一天的小时和分钟**

```java
for(int hour = 0;hour < 24;hour++){
    for(int minute = 0;minute<60;minute++){
        System.out.println(hour+"时"+minute+"分");
    }
    System.out,println("---------");
}
```

外循环控制小时数，内循环控制分钟数

### 3.11 Random API

Random的作用和使用步骤：

​	作用：产生一个随机数

​	使用步骤：

​		导包

```java
import java.util.Random;
```

​		创建对象

```java
Random r = new Random();
```

​		获取随机数

```java
int number = r.nextInt(10);//获取随机数的范围[0,10),包括0不包括10
```

**例子：程序自动生成1~100之间的数字，实用程序猜出这个数字是多少？**

**当猜错时更具不同情况给出相应的提示：**

​	**如果才的数字比真实数字大，提示猜大了**

​	**如果才的数字比真实数字小，提示猜小了**

​	**如果才的数字比真实数字相等，提示猜中了**

```java
		Random r = new Random();
        Scanner sc = new Scanner(System.in);
        int count = 1;
        int number = r.nextInt(100)+1;
        while(count < 11){
            System.out.println("你只有10次猜的机会，现在是第"+count+"次");
            System.out.println("给出你猜的数字： ");
            int num = sc.nextInt();
            count++;
            if (num == number){
                System.out.println("恭喜你猜对了");
                break;
            }else if (num > number){
                System.out.println("你猜大了");
            }else if (num < number){
                System.out.println("你猜小了");
            }
        }
```

## 4 数组

### 4.1数组定义格式

需求：一次性定义大量同类型数据				结果：定义数组

**数组：**是一种用于存储**多个**<u>同类型数据</u>的存储模型

**格式1：数据类型[] 变量名**（推荐）

例如：int[] arr

含义：定义了一个int类型的数组，数组名时arr

**格式2：数据类型 变量名[]**

例如：int arr[]

含义：定义了一个int类型的变量，变量名是arr数组

### 4.2数组初始化之动态初始化

java中的数组必须先初始化才能使用

**初始化**：为数组中的数组元素分配内存空间，并为每个数组元素赋值

- **动态初始化：**初始化时只指定数组长度，由系为数组分配从初始值

​		格式：数据类型[] 变量名 = new 数据类型[数组长度];

​		例如：int[] arr = new int[10];

### 4.3数组元素访问

- 数组变量的访问模式

​	格式：数组名

- 数组内部保存数据的访问方式

​	格式：数组名[索引]

- 索引：索引是数组在数据的编号方式，从0开始，连续逐级加1的

​	作用：索引用于访问数组中数据使用，数组名[索引]等同于变量名，是一种特殊的变量名

### 4.4 内存分配

#### 4.4.1 Java数组中内存分配

Java程序在运行时，需要在内存中分配存储空间，为了提高运算效率，就对空间进行了不同区域的划分因为每一片区域都有特定的是处理数据方式和内存管理方式

![](C:\Users\Asinil\Desktop\学习\Java\4.4.1.PNG)

左边的存储空间:**栈内存**   

​	存储对象：存储局部变量

​	特点：定义在方法中的变量，例如：arr，使用完毕后立即消失

右边的存储空间:**堆内存**	

​	存储对象：存储new出来的内容（实体，对象）

​	**数组在初始化时，会将存储空间添加默认值:**

- 整数默认值：0 
- 浮点数默认值：0.0
-  布尔默认值：false
-  字符默认值：空字符 
- 引用数据类型：null

​	每一个new出来的东西都有一地址值（如：001），使用完毕后会在垃圾回器空闲时被回收

#### 4.4.2 多个数组指向相同

![](C:\Users\Asinil\Desktop\学习\Java\4.4.2.PNG)

**当两个数组指向相同时，修改任意个数组，都会改变两个数组的值**

### 4.5 数组初始化之静态初始化

静态初始化：初始化时指定每个数组元素的初始值，由系统决定数组长度

- 格式：数据类型[] 变量名 = new 数据类型[]{数据1，数据2，数据3……};

​	例如： int[]  arr = new int[]{1,2,3};

- 简化格式：数据类型[] 变量名 = {数据1，数据2，数据3……};

​	例如： int[]  arr = {1,2,3};

### 4.6 数组操作的两个常见小问题

#### 4.6.1索引越界

例如：

```java
int[] arr = new int[3];
System.out.println(arr[3]);
```

**索引越界**：访问了数组中不存在的索引对应的元素，造成的索引越界问题

代码报错提示：**ArrayIndexOutOfBoundsException**

#### 4.6.2空指针异常

例如：

```java
int[] arr = new int[3];
arr = null;
System.out.println(arr[0]);
```

数组arr指向的地址值已经被修改为null，无法再通过arr访问到原来的arr[0]

**空指针异常**：访问的数组已经不再指向堆内存的数据，造成空指针异常

代码报错提示：**NullPointerException**

null：空值，引用数据类型的默认值，表示不指向任何有效的对象

### 4.7数组常见操作

#### 4.7.1遍历

常用方法：利用循环进行遍历数组

已知数组长度

​	例如：

```java
int[] arr = {11,22,33,44,55,66};
for(int i = 0;i<6;i++){
	System.out.println(arr[i]);
}
```

**如果未知数组长度呢？**

引入获取元素数量:

​	格式：数组名.length

​	例如：arr.length

```java
int[] arr = {……};
for(int i = 0;i<arr.lenht;i++){
	System.out.println(arr[i]);
}
```

遍历通用格式：

```java
int[] arr = {……};
for(int i = 0;i<arr.lenht;i++){
	arr[i]//对arr[i]进行操作
}
```

#### 4.7.2获取最值

```java
int[] arr = {12,15,11,10,16,19,14,8};
```

思路;

- 定义一个变量，用于保存最大值/最小值

```java
int max;
```

- 取数组中第一个数据作为变量初始值

```java
int max = arr[0];
```

- 与数组中各个数据逐一比对，每次将大的数据保存到变量中

```java
for(int i = 1;i<arr.length;i++){
    if(arr[i]>max){
        max = arr[i];
    }
}
```

- 循环结束后，打印变量的值

```
System.out.println(max);
```

## 5 方法

### 5.1方法概述

![](C:\Users\Asinil\Desktop\学习\Java\5.1.PNG)

图中每一个步骤都相当于一个个代码块，将他们全部打包为一个整体，就是刷牙过程，也就是刷牙方法

**方法**：将具有独立功能的**代码块**组织成为一个整体，使其具有特殊功能的**代码集**

注意：

- 方法必须先创建才可以使用，该过程被称为**方法定义**
- 方法创建后，并不是直接运行的，需要手动使用后才执行，该过程被称为**方法调用**

### 5.2方法定义和方法调用

#### 5.2.1  方法定义

格式：

```java
public static void 方法名(){
	//方法体
}
public void 方法名(){
    //方法体
}
```

例如;

```java
public static void isEvenNumber(){
	//方法体
}
```

#### 5.2.2方法调用

格式：

```java
方法名();
```

例如：

```java
isEvenNumber();
```

#### 5.2.3方法练习

**需求：设计一个方法用于打印两个数在的较大数**

```java
public static void getMax(int x,int y){
        int max = x>y?x:y;
        System.out.println("两个数中较大的是："+max);
    }
```

```java
public static void getMax(){
        int a = 10;
        int b = 20
        if(a>b){
        	System.out.println(a);
        }else{
        	System.out.println(b);
        }
        
    }
```

### 5.3 形参和实参

形参：方法定义中的参数

​	等同于变量定义格式，例如;int number

实参：方法调用中的参数

​	等同于使用变量或者常量，例如 10    number

```java
public class demo06 {
    public static void main(String[] args) {
        getMax(10,15);  //实参      
    }
public static void getMax(int x,int y){//xy形参
        int max = x>y?x:y;
        System.out.println("两个书中较大的是："+max);
    }    
```

代码例子中的调用getMax方法，传输的10，15是实参

定义的getMax方法中int x，int y 则是形参

### 5.4 带参数方法的定义和调用

**带参数方法定义：**

```java
public static void 方法名(参数){
	//方法体
}
```

格式（多个参数）：

```java
public static void 方法名(参数类型 变量名1，参数类型 变量名2……){
	//方法体
}
```

注意：

- 方法定义时，参数中的数据类型与变量名都不能缺少，缺少任意一个程序出错
- 定义方法时，多个参数之间使用（，）分隔

带参数方法调用：

```java
方法名(参数);
```

格式（多参数）：

```java
方法名(变量名1/常量1,变量名2/常量2);
```

注意：

- 方法调用时，参数的数量和类型必须与定义方法中的设置匹配，否则程序出错

### 5.5 带返回值方法的定义和调用

定义格式：

```java
public static 数据类型 方法名(参数类型 参数名){
	return 返回值;
}
```

- 注意：方法定义时return后面的返回值与方法定义的数据类型要匹配，否则程序包出错

调用格式1：

```java
方法名(参数);
getMax(5);
```

调用格式2：

```java
数据类型 变量名 = 方法名(参数);
boolean flag = isEvenNumber(5);
```

- 注意：方法的返回值要用一个数据类型匹配的变量来接收，否则返回值无效

**需求：获取两个数的较大数，数据来自参数**

```java
public class demo06 {
    public static void main(String[] args) {
        int m = getMax(10,15);  
        System.out.println("较大值为："+m);
        //System.out.println("较大值为："+getMax(10,15));  这种也行
    }
public static int getMax(int x,int y){
        int max = x>y?x:y;
        return max;
    }  
```

### 5.6 方法的注意事项

1. 方法不能嵌套定义
2. void表示无返回值，可以省略ruturn，也可以写return，但是不用加返回值

```java
//错误示例：不能嵌套
public static void methodOne(){
	public static void methodTwo(){
	}
}
//省略return
public static void methonOne(){
    return;
}
```

  3.方法的通用格式

```java
public static 返回值类型 方法名(参数){
	方法体;
	return 数据
}
```

|     部分      |                          作用                          |
| :-----------: | :----------------------------------------------------: |
| public static |                修饰符，目前记住这个格式                |
|  返回值类型   | 方法操作完毕之后的数据返回类型，void类型一般不写return |
|    方法名     |                  调用方法时使用的标识                  |
|     参数      |     由数据类型和变量名组成，多个参数之间用逗号隔开     |
|    方法体     |                    完成功能的代码块                    |
|    return     |  如果方法操作完毕，有数据返回，用于把数据返回给调用者  |

定义方法时，做到两个明确：

- ​	明确返回值类型：主要是明确方法操作完毕之后是否有返回值，如果没有写void，如果有写对应的数据类型
- ​	明确参数：明确参数的类型和数量

调用方法时

- ​	void方法直接调用
- ​	非void方法，推荐用变量接收调用

### 5.7 方法重载

方法重载：是指**同一个类中定义**的多个方法之间的关系，满足**下列条件的多个方法**相互构成重载

- **多个方法在同一个类中**
- **多个方法具有相同的方法名**
- 多个方法的参数不相同**，类型不同或者数量不同**

重载特点：

- 重载仅对应方法的定义，与方法的调用无关，调用方式参照标准格式
- 重载仅针对同一个类中方法的名称与参数进行识别，与返回值无关，换句话说不能通过返回值来判定两个方法是否相互构成重载

需求：求两个int，double，三个int类型的方法

```java
public class MethodDemo{
	public static void main(String[] arges){
		int res1 = sun(10,20);
        System.out.println(res3);
		double res2 = sun(10.0,20.0);
        System.out.println(res3);
		int res3 = sum(10,20,30);
        System.out.println(res3);
	}
	public static int sum(int a,int b){
		return a+b;
	}
	public static double sum(double a,double b){
		return a+b;
	}
	public static int sum(int a,int b,int c){
		return a+b+c;
	}
}
```

### 5.8 方法参数传递

![](C:\Users\Asinil\Desktop\java基础\Java\2.2.PNG)

#### 5.8.1方法参数传递（基本类型）

```java
public class demo06 {
    public static void main(String[] args) {
//        方法参数的传递
        int number = 10;
        System.out.println(number);
        change(number);//传入实参
        System.out.println(number);
    }
    public static void change(int num){//int num = number;
        num = 20;//改变形参
    }
}
```

调用change方法流程图：

![](C:\Users\Asinil\Desktop\学习\Java\5.8.1.PNG)

**change方法改变的是传递过来number的值（形参），对于main方法中的number的值没有做出任何改变，而change方法结束后，形参在栈内存中消失对实参无影响**

结论：**对于基本类型的参数，形参的改变，不会影响实参的值**

#### 5.8.2方法参数的传递（引用类型）

```java
public class demo06 {
    public static void main(String[] args) {
//        方法参数的传递
        int[] arr = {10,20,30};
        System.out.println(arr[1]);
        change(arr);
        System.out.println(arr[1]);
    }
    public static void change(int[] arr){//int[] arr = arr;将arr的地址赋值给新定义的arr
        arr[1] = 200;
    }
}
```

调用change方法流程图：

![](C:\Users\Asinil\Desktop\学习\Java\5.8.2.PNG)

**执行change(arr)，进入方法change中，由于传递的arr是存储数组的堆内存地址，通过内存地址找到数组对arr[1]进行修改，进而影响到了实际参数的值**

结论：**对于引用类型的参数，形参的改变，影响实参的值**

### 5.9方法参数传递例题

需求1：设计一个方法用于数组遍历，要求遍历输出结果是在一行上的，例如：[11,22,33,44,55]

思路：要求输出在一行上，用到一个新的输出语句system.out.print(“内容”);

- ​	System.out.println("内容"); 输出内容换行
- ​	System.out.print("内容");输出内容不换行

```java
public class demo06 {
    public static void main(String[] args) {
		int[] arr = {11,22,33,44,55};
        allPrint(arr);
    }
    public static void allPrint(int[] arr){
        System.out.print("[");
        for (int i = 0;i< arr.length;i++){
            if (i == arr.length - 1){
                System.out.print(arr[i]);
            }else{
                System.out.print(arr[i]+",");
            }
        }
        System.out.print("]");
    }
}
```

需求2：设计一个方法用于获取数组中元素的最大值，调用方法并输出结果

```java
public class demo06 {
    public static void main(String[] args) {
		int[] arr = {1,9,8,6,2,3,5,4};
        int maxArr = getArrMax(arr);
        System.out.println("数组中最大值为："+maxArr);
    }
    public static int getArrMax(int[] arr){  
        int max = arr[0];
        for (int i = 1;i< arr.length;i++){
   			if(arr[i] > max){
                max = arr[i];
            }       
        }
        return max;
    }
}
```

### 5.10 Debug调试

Debug：是供程序员代码调试工具，用于查看程序执行流程，也可以追踪程序过程来调试程序

debug调试：又称断点调试

​	断点是一个标记，告诉我们从哪里开始查看

注意事项：如果数据来自键盘输入，一定要记得输入数据，不然debug无法继续进行下去

## 6 类

### 6.1 类和对象

类是对现实生活中具有共同属性和行为的事物的抽象

**类的特点**：

- 类是对象的数据类型
- 类是具有相同属性和行为的一组对象集合

**对象的属性**：对象具有的各种特征，每个对象的每个属性都拥有特定的值

**对象的行为**：对象能够执行的操作

**类和对象的关系**：

类只是现实生活中一类具有共同属性和行为的事物的抽象

对象则是将抽象具体化，是摸得着看得见的实体

即：**类是对象的抽象，对象是类的实体**

### 6.2 类的定义和使用

类的组成：

**属性**：在类中通过成员变量来体现

**行为**：在类中通过成员方法来体现

类的定义：

```java
public class 类名{
	//成员变量
	数据类型 变量名;
	//成员方法
	方法();
}
```

创建对象：

格式：类名 对象名  = new 类名()；

使用对象：

- 使用成员变量：对象名.变量名

- 使用成员方法：对象名.方法名();

### 6.3 对象内存图

####  多个对象指向相同的内存图

![](C:\Users\Asinil\Desktop\学习\Java\6.3.1.PNG)

**当多个对象的指向相同后，指向的对象地址也是相同的，因此和数组一样，有一个对象数据改变，其他所有指向相同的对象数据也会改变**

### 6.4 成员变量和局部变量

成员变量：在类中方法外的变量

局部变量：在方法中的变量

|     区别     |                  成员变量                  |                    局部变量                    |
| :----------: | :----------------------------------------: | :--------------------------------------------: |
| 类中位置不同 |                 类中方法外                 |              方法内或者方法声明上              |
| 内存位置不同 |                   堆内存                   |                     栈内存                     |
| 生命周期不同 | 随着对象的存在而存在，随着对象的消失而消失 | 随着对象的调用而存在，随着对象的调用结束而消失 |
| 初始化值不同 |             **有默认的初始值**             |   **没有默认的初始值，须先定义赋值才能使用**   |

### 6.5 封装

#### 6.5.1 private关键字

**private**:是一个权限修饰符，可以修饰成员（成员变量或成员方法）

**作用**：保护成员不被别的类使用，被private修饰的成员只有在本类中才能访问

针对private修饰的成员变量，如果需要被其他类使用，提供相应的操作：

- 提供”get变量名()“方法，用于获取成员变量的值，方法用public修饰

- 提供“set变量名(参数)”方法，用于设置成员变量的值，方法用public修饰

#### 6.5.2 this关键字

this修饰的变量用于指代成员变量

- 方法的形参如果和成员变量同名，不带this修饰的变量指的是形参，而不是成员变量

- 方法的形参如果没与成员变量同名，不带this修饰的变量指的是成员变量

```java
public class Student{
	private String name;
	public String getName(){
		return name;
	}
	public void setName(String name){
		this.name = name;
	}
}
```

使用this修饰符的时机：**解决局部变量隐藏成员变量时**

this：代表所在类的对象引用

- 注意：方法被哪个对象引用，this就代表那个对象

#### 6.5.3 程序封装

**封装概述**：

是面向对象三大特征之一（**封装，继承，多态**）

是面向对象编程语言对客观世界的模拟，客观世界里成员变量都是隐藏在对象内部的，外界是无法直接操作的

**封装原则**：

将类的某些信息隐藏在类的内部，不允许外部程序直接访问，而是通过该类提供的方法来实现对隐藏信息的操作和访问

成员变量private，提供的对应的getXX()/setXX()方法

**封装的好处**：

通过控制成员变量的操作，提高代码的**安全性**，

把代码用方法进行封装，提高代码的**复用性**

### 6.6构造方法

构造方法是一种特殊的方法，作用是构造对象，完成初始化

格式：

```java
public class 类名{
	修饰符 类名(参数){}
}
```

**注意事项**：

- 如果没有定义构造方法，系统会给一个默认无参构造方法
- 如果给了一个构造方法，系统将不会给其他构造方法，只能按照定义的构造方法进行对象初始化

#### 6.6.1构造方法的重载：

如果自定义了一个构造方法，还要使用无参构造方法，就必须再写一个无参构造方法

推荐：无论是否使用，都手工写一个无参构造方法

#### 6.6.2 标准类的制作

- 成员变量：

​		使用private修饰

- 构造方法：

​		提供一个无参构造方法

​		提供一个带参数的构造方法

- 成员方法：

​		提供成员变量对应的get/set方法

​		提供显示一个对象的show方法

- 创建对象并给对象成员变量赋值

​		无参构造方法后set方法赋值

​		有参构造方法直接创建带有属性值的对象

### 6.7API

**API（Application Programming Interface）**应用程序编程接口

JavaAPI :指的是jdk中提供的各种功能的Java类

调用接口有返回值，可以自己手动写，也可以**ctrl+alt+v**自动生成接受数据的变量

### 6.8 String API

String 类在**java.lang**包下，不需要进行导包操作

String类代表字符串类，Java程序在所有字符串文字（例如：“abc”）都被实现为此类的实例

即：**java程序中所有双引号的字符串，都是String的对象**

字符串的特点：

- 字符串不可变，他们的值在创建后不能被更改
- 虽然String的值是不可变的，但是他们可以被共享
- 字符串效果上相当于字符串数组char[]（**JDK8及以前是字符串数组，JDK9及以后是字节数组**），但底层原理是字节数组byte[]

#### 6.8.1 String构造方法

|          方法名           |                  说明                   |
| :-----------------------: | :-------------------------------------: |
|      public String()      | 创建一个空白字符串对象，不含有任何内容  |
| public String(cahr[] chs) |  根据字符数组的内容，来创建字符串对象   |
| public String(byte[] bys) |  根据字节数组的内容，来创建字节串对象   |
|     String s = "abc"      | 直接赋值的方式创建字符串对象，内容位abc |

**推荐使用直接赋值的方式得到字符串对象**

#### 6.8.2 String对象的特点

- 通过new创建的字符串对象，每一次new都会申请一个内存空间，虽然内容相同，但是地址值不同
- 以""方式给出的字符串，只要字符序列相同（大小写顺序），无论在程序代码中出现几次，JVM都只会建立一个String对象，并在字符串池中维护

```java
String s3 = "abc";
String s4 = "abc";
```

上面代码中，针对第一行代码，JVM会在堆内存中建立一个String对象放在字符串池中，并给s3参考；

第二行则让s4直接参考字符串池中的String对象，本质上是同一个数

![](C:\Users\Asinil\Desktop\学习\Java\6.8.2.PNG)

#### 6.8.3字符串的比较

使用==作比较

- 基本类型：比较的是**数据值**是否相同
- 引用类型：比较的是**地址值**是否相同

字符串是对象，它比较内容是否相同，通过方法**equals()**实现

- public boolean **equals(Object anObject)**：将此字符串与指定对象进行比较，由于比较的是字符串对象，所以参数传递的是字符串

**需求：键盘录入一个字符串，使用程序实现在控制台遍历该字符串**

思路：

键盘录入，Scanner实现

遍历字符串，首先获取到每一个字符串在的每一个字符，使用charAt()方法实现

- ​	**public char charAt(int index);**返回指定索引处的char值，字符串也是从0开始的

遍历字符串，其次能获取字符串长度，使用length()方法实现

- ​	**public int length();**返回字符串长度

**通用字符串遍历格式**：

```java
for(int i=0;i<s.length();i++){
	s.charAt(i);
}
```

#### 6.8.4常用的String方法

|              方法名               |              说明              |
| :-------------------------------: | :----------------------------: |
| public bollean equals(Object obj) | 比较字符串内容，严格区分大小写 |
|   public char charAt(int index)   |       返回索引处的char值       |
|        public int length()        |         返回字符串长度         |

### 6.9 StringBuilder API

![](C:\Users\Asinil\Desktop\学习\Java\6.9.PNG)

分析：如果对字符串进行拼接操作，每次拼接都会构建一个新的String对象，**既耗时又浪费内存空间**，而且这种模式还不可避免。

**通过Java提供的StringBuilder类来解决这个问题**

StringBuilder是一个可变的字符串类，我们可以把它看作一个容器。这里的可变指的是StringBuilder对象中的内容是可变的

**String和StringBuilder的区别**：

String不可变，StringBuilder可变

#### 6.9.1 如何理解String的不可变性

String类使用的final修饰符，保证该类不会被继承和修改

```java
String str = "abc";
str = "123";
System.out.println(str);//123
```

- 上述代码看似改变了字符串str的内容，但实际上只是将变量str指向的地址由"abc"改为了"123"，常量池中"abc"依然存在，不可被改变

- 对于String提供的trim，replace等修改字符串字面值的方法也是同理，都是创建一个新的字符串赋值给它，并没有修改原有字符

#### 6.9.2 StringBuilder构造方法

|               方法名               |                     说明                     |
| :--------------------------------: | :------------------------------------------: |
|       public StringBuilder()       | 创建一个空白可变字符串对象，初始大小为16字符 |
|  public StringBilder(String str)   |     根据字符串内容，来创建可变字符串对象     |
| puublic StringBilder(int capacity) |  创建一个空白可变字符串对象，大小为capacity  |

#### 6.9.3 StringBuilder的添加和反转方法

|                方法名                 |          说明          |
| :-----------------------------------: | :--------------------: |
| public StringBuilder append(任意类型) | 添加数据，返回对象本身 |
|    public StringBuilder reverse()     |   放回相反的字符序列   |

sb.append整体是一个对象，那么可以调用方法

链式编程;

```java
sb.append("hello").append(100).revese();
```

#### 6.9.4 StringBuilder和String相互转换

**StringBuilder 转换为 String**

public String toString():通过toString()方法就可以实现

**String 转换为StringBuilder**

public StringBuilder(String s):通过构造方法就可以实现把String转换为StringBuilder

**需求：定义一个方法，输入一个String字符串abc，返回cba**

```java
public static  void main(String[] args){
    Scanner sc = new Scanner(System.in);
    System.out.println("输入一个字符串");
    String line = sc.nextLine();
    Srting s = stringToReverse(line);
    System.out.println("s:"+s);   
}
public static String stringToReverse(String line){
    return new StringBuilder(line).reverse().toString();
}
```

## 7 集合基础

### 7.1集合基础知识

编程时如果要存储多个数据，使用长度固定的数组存储格式，不一定满足我们的需求，更加适应不了需求的变化，那么如何选择呢？

**集合类特点**：提供一种存储空间可变的存储模型，存储的数据容量可以发生改变

集合类有很多，目前学习一个：**ArrayList**



**ArratList<E>:**

- 底层为可调整大小的数组实现
- <E>是存储的一种特殊的数据类型，**泛型**

例如：ArrayList<String>,ArrayList<Student>等

### 7.2ArrayList构造方法和添加方法

|                方法名                |                  说明                  |
| :----------------------------------: | :------------------------------------: |
|          public ArrayList()          | 创建一个空的集合对象，初始容量为10可变 |
|       public boolean  add(E e)       |     将指定元素追加到此集合**末尾**     |
| public void add(int index,E element) |    在此集合在的指定位置插入指定元素    |
|    public ArrayList(int capacity)    |      创建一个capacity长度的空集合      |

### 7.3ArrayList集合的常用方法

|              方法名               |                   说明                   |
| :-------------------------------: | :--------------------------------------: |
|  public boolean remove(object o)  |    删除指定元素，**返回删除是否成功**    |
|    public E remove(int index)     |  删除指定索引处元素，**返回被删除元素**  |
| public E set(int index,E element) | 修改指定索引处的元素，**返回被修改元素** |
|      public E get(int index)      |            返回指定索引处元素            |
|         public int size()         |            返回集合中元素个数            |

需求：对字符串集合进行进行遍历操作

```java
public static void main(String[] args){
    ArrayList<String> array = new Array<>();
    array.add("zhangsan");
    array.add("lisi");
    array.add("wangwu");
    
    for(int i = 0;i<array.size();i++){
        System.out.println(array.get(i));
    }
}
```

**遍历集合通用格式:**

```java
for(int i = 0;i<array.size();i++){
    String s = get(i);
    System.out.println(s);
}
```

## 8 继承

### 8.1继承概述

**继承**是面向对象三大特征之一（封装，继承，多态），可以使得子类具有父类的属性和方法，还可以在子类中重新定义，追加属性和方法

继承格式：

```java
public class 子类名 extends 父类名{
}
```

父类：也被称为基类，超类

子类：也被称为派生类

**继承中子类特点**：子类有自己的内容，也可以使用父类的内容

### 8.2 继承的好处和弊端

继承好处：

- 提高了代码**复用性**，多个类相同的成员可以放到同一个类中
- 提高了代码的**维护性**，如果方法代码需要修改，修改一处即可

继承弊端：

- 继承让类与类之间产生了关系，类的耦合性增强了，当父类发生变化时，子类实现也不得不跟着变化，削弱了子类的独立性

**那什么时候使用继承呢**？

- 继承体现的关系：**is a**（什么是什么的一种）
- **假设法**：如果有两个类A，B，如果他们满足A是B的一种，或者B是A的一种，就说明他们存在在继承关系，这个时候就可以考虑使用继承来体现，否则不能滥用继承

例如：水果和苹果，动物和狗，猫和狗（不用继承）等

### 8.3 继承中访问变量的特点

在子类方法中访问一个变量：

1. 在子类局部范围找（方法内）
2. 子类成员变量范围找
3. 父类成员变量范围找
4. 如果都没有就报错

### 8.4 super关键字

```java
public class Fu(){
    public int age = 40;
}

public class Zi extends Fu(){
    public int age = 30;
    
    public void show(){
        int age = 20;
        System.out.println(age);//age = 20
    }
}
```

那么如果需要显示age是子类成员变量的呢?要显示父类age呢？

- 显示子类成员变量age：this.age
- 显示父类成员变量age：super.age

**super关键字用法**

super关键字用法和this关键字用法相似：

- this：代表本类对象的引用
- super：代表父类存储空间的标识（可以理解为父类对象引用）

| 关键字 |    访问成员变量    | 访问构造方法 |      访问成员方法      |
| :----: | :----------------: | :----------: | :--------------------: |
|  this  | this.本类成员变量  |   this(……)   | this.本类成员方法(……)  |
| super  | super.父类成员变量 |  super(……)   | super.父类成员方法(……) |

### 8.5继承中构造方法的访问特点

```java
public class Fu(){
    public Fu(){
        System.out.println("Fu类无参构造方法被调用");
    }
    public Fu(int age){
        System.out.println("Fu类带参构造方法被调用");
    }
}

public class Zi extends Fu(){
   public Zi(){
        System.out.println("Zi类无参构造方法被调用");
    }
    public Zi(int age){
        System.out.println("Zi类带参构造方法被调用");
    }
}

public class ExtendsDemo (){
    public static void main(String[] args){
        Zi z = new Zi();
    	Zi z1 = new Zi(20);
    	/*输出结果：
    		Fu类无参构造方法被调用
			Zi类无参构造方法被调用
            Fu类带参构造方法被调用
            Zi类带参构造方法被调用
    	*/
    }
}
```

**子类中所有的构造方法默认都会访问父类中无参的构造方法**

为什么呢？

- 因为子类会继承父类中的数据，可能还会使用父类的数据，所以**子类初始化之前，一定要先完成父类数据的初始化**
- 每一个子类构造方法的第一条默认都是：**super()**

如果父类中只有带参构造方法没有无参构造方法，该怎么办呢？

- 通过super关键字去显示的调用父类带参构造方法
- 在父类在自己提供一个无参构造方法

推荐：自己给出无参构造方法

### 8.6 继承中成员方法的访问特点

通过子类对象中访问一个方法：

1. 子类成员方法范围找
2. 父类成员方法范围找
3. 如果都没有就报错

### 8.7 方法重写

方法重写概述：子类中出现了和父类中一模一样的方法声明

方法重写的应用：

- 当子类需要父类功能，而功能主体子类有自己特有内容时，可以重写父类方法，这样即沿袭了父类的功能有定义了子类特有的内容

```java
//父类
public class Phone(){
    public void call(String name){
    	System.out.println("给"+name+"打电话");
    }
}
//子类
public class NewPhone extends Phone(String names){
    public void call(String name){
    	System.out.println("开启视频功能");
    	super.call();
    }
}
//测试类
public class ExtendsDemo (){
    public static void main(String[] args){
        NewPhone np = new NewPhone();
        np.call("张三");
    	/*输出结果：
    		开启视频功能
    		给张三打电话
    	*/
    }
}

```

如果有时候怕子类重写父类方法时声明写错了，就在前面加一个注解***@Override***，表面后面方法是重写父类方法

```java
//父类
public class Fu(){
    public void show(){
    }
}
//子类
public class Zi extends Fu(){
    @Override//报错：提示下面重写方法声明在父类中未找到
   public void shov(){}
}
```

***@Override***

- 是一个注解（后面会学习到注解开发）
- 可以帮助我们检查重写方法的方法声明正确性

**方法重写的注意事项：**

- 私有方法不能被重写（父类私有成员，子类无法被继承）
- 子类方法访问权限不能更低（public>默认>private）

**类继承的注意事项**：

- Java类只支持单继承，不支持一个类继承多个类
- Java类支持多层继承

### 8.8 package

**包**其实就是文件夹，作用是对类进行分类管理

包的定义格式：

```java
package 包名;(多级包用.分开)
```

例如：package com.javaCode;

带包的java类编译和执行：

- 手动建包：
  - 按照以前的格式编译java文件            javac Helloworld.java
  - 手动建包                                              在工作盘建立文件夹com,然后在com下建立文件夹javaCode
  - 把class文件放到包里面                      把helloworld.class文件放到javaCode文件里面
  - 带包执行                                              java com.javaCode.Helloworld

- 自动建包
  - 按照自动建包格式编译java文件        javac -d . Helloworld.java
  - 带包执行                                              java com.javaCode.Helloworld                                            

### 8.9 导包

使用不同包下的类时，使用的时候要写类的全路径，这样写起来太麻烦了

为了简化带包操作，Java就提供了导包功能

格式：

```java
import 包名;
```

例如：import com.javaCode.Teacher;

### 8.10 权限修饰符

#### private，默认default，protected，public访问权限

|  修饰符\类  |  父类   | 同包子类 | 同包其他类 | 不同包子类 | 不同包其他类 |
| :---------: | :-----: | :------: | :--------: | :--------: | :----------: |
|   private   | **yes** |          |            |            |              |
| 默认default | **yes** | **yes**  |  **yes**   |            |              |
|  protected  | **yes** | **yes**  |  **yes**   |  **yes**   |              |
|   public    | **yes** | **yes**  |  **yes**   |  **yes**   |   **yes**    |

### 8.11 状态修饰符

- final（最终态）
- static（静态）

#### 8.11.1 final

**final**关键字是最终的意思，可以修饰**成员方法，成员变量，类**

**final修饰特点：**

- 修饰方法：表示该方法是最终方法，不能被重写
- 修饰变量：表示该变量是常量，不能被再次赋值
- 修饰类：表示该类是最终类，不能被继承

**final修饰局部变量**

final修饰基本类型变量：基本类型的**数据值**不可变

final修饰引用类型变量：引用类型的**地址值**不能改变，地址内容可以改变

#### 8.11.2 static

**static**关键字是静态的意思，可以修饰**成员方法，成员变量**

**static修饰特点:**

- static修饰成员变量将被类的所有对象共享

  这也是我们判断是否使用静态关键字的条件，推荐使用类名调用

**static访问特点：**

非静态的成员方法

- 能访问静态的成员变量
- 能访问非静态的成员变量
- 能访问静态的成员方法
- 能访问非静态的成员方法

静态的成员方法

- 能访问静态成员变量
- 能访问静态成员方法

**总结：静态成员方法只能访问静态成员**

## 9多态

### 9.1多态描述

**多态**指的是同一个对象，在不同时刻表现出来的不同形态

举例：猫🐱

我们可以说：**猫 cat =  new 猫（）；**

我们也可以说猫是动物：**动物 animal = new 猫（）；**

在这里猫体现了在不同时刻表现出来的不同形态，即是多态

#### 多态的前提和体现

- 有继承/实现关系（实现在后面学到）
- 有方法重写
- 有父类引用指向子类对象

### 9.2多态中成员访问特点

- ***成员变量*：编译看左边，执行看左边**
- ***成员方法*：编译看左边，执行看右边**

为什么成员方法和成员变量的访问不一样呢？

因为成员方法有重写，而成员变量没有

### 9.3多态的好处和弊端

```java
public class Animal{
    public void eat(){
        System.out.println("吃东西");
    }
}
public class Cat extends Animal{
    public void eat(){
        System.out.println("猫吃鱼");
    }
}
public class Dog extends Animal{
    public void eat(){
        System.out.println("狗吃肉");
    }
}
public class AnimalOperator{//Cat c = new Cat();
    public void useAnimal(Cat c){
        c.eat();
    }
     public void useAnimal(Dog d){//Dog d = new Dog();
        d.eat();
    }
}
public class AnimalDemo{
    public static void main(String[] args){
        AnimalOperator ao = new AnimalOperator();
        Cat c = new Cat();
        ao.useAnimal(c);
        Dog d = new Dog();
        ao.useAnimal(d);
    }
}
```

上述代码弊端就是每添加一个动物类，就需要在动物操作类中添加方法，太过于复杂麻烦

用多态进行改进：

```java
public class Animal{
    public void eat(){
        System.out.println("吃东西");
    }
}
public class Cat extends Animal{
    public void eat(){
        System.out.println("猫吃鱼");
    }
}
public class Dog extends Animal{
    public void eat(){
        System.out.println("狗吃肉");
    }
}
public class AnimalOperator{
    public void useAnimal(Animal a){//利用多态减少代码编写
        a.eat();
    }   
}
public class AnimalDemo{
    public static void main(String[] args){
        AnimalOperator ao = new AnimalOperator();
        Animal c = new Cat();
        ao.useAnimal(c);
        Animal d = new Dog();
        ao.useAnimal(d);
    }
}
```

**好处：提高了程序的拓展性**

​	具体体现：定义方法的时候，使用父类作为参数，将来在使用的时候，使用具体的子类型参与操作

**弊端：不能使用子类的特有功能**

### 9.4多态的转型

- **向上转型（多态）**

  从子到父，父类引用指向子类对象

- **向下转型（强制转换）**

  从父到子，父类引用转为子类对象

```java
public class Animal{
    public void eat(){
        System.out.println("吃东西");
    }
}
public class Cat extends Animal{
    public void eat(){
        System.out.println("猫吃鱼");
    }
    public void play(){
        System.out.println("猫抓老鼠");
    }
}
public class AnimalDemo{
    public static void main(String[] args){    
        //向上转型
        Animal a = new Cat();
        a.eat();
        //a.play();  报错：无法使用子类特有方法
        
        //向下转型,将Animal强转为Cat对象
		Cat c = (Cat)a;
        c.eat();
		c.play();
    }
}
```

### 9.5 抽象类

在Java中，一个**没有方法体**的方法应该被定义为**抽象方法**，而类中如果有抽象方法，该类必须被定义为**抽象类**

***abstract关键字***：用于声明抽象方法和抽象类

#### 9.5.1抽象类特点

- 抽象类和抽象方法必须使用abstract关键字修饰
  - public **abstract** class 类名{}
  - public **abstract** 返回类型 方法名(参数){}

- 抽象类中不一定有抽象方法，抽象方法的类一定是抽象类

- 抽象类不能直接实例化
  - 如何实例化？参照多态的方式，通过子类对象实例化，这叫抽象类多态

- 抽象类的子类
  - 要么重写抽象类中所有抽象方法
  - 要么是抽象类

#### 9.5.2抽象类的成员特点

- 成员变量
  - 可以是变量
  - 也可以是常量

- 构造方法
  - 可以有构造方法，但是**不能直接实例化**
  - 构造方法的作用：用于子类访问父类数据的初始化

- 成员方法
  - 可以有抽象方法：限定子类必须完成某些动作
  - 也可以有非抽象方法，提高代码复用性

### 9.6接口

**接口**就是一种**公共的规范标准**，只要符合规范标准，大家都可以通用

Java中的接口更多体现在**对行为的抽象**

#### 9.6.1接口的特点

- 接口用关键字***interface***修饰

  public **interface** 接口名{}

- 类实现接口用***implements***表示

  public class 类名 **implements** 接口名{}

- 接口不能直接实例化

  接口如何实例化？参照多态的方式，通过实现类对象实例化，这叫**接口多态**

  多态的形式：具体类多态，**抽象类多态**，**接口多态**

  多态的前提：有继承或者实现关系；有方法重写；有父（类/接口）引用指向（子/实现）类对象

- 接口的实现类

  要么重写接口中的所有抽象方法

  要么是抽象类，但之后继承该抽象类依旧需要重写接口方法

#### 9.6.2 接口的成员特点

- 成员变量

  - 只能是常量

    默认修饰符：public static final

- 构造方法
  - 接口没有构造方法，因为接口主要是对行为进行抽象的，是没有具体存在
  - 一个类如果没有父类，默认继承自Object根类

- 成员方法
  - 只能是抽象方法
  - 默认修饰符：public abstract

关于接口中的方法，JDK8和JDK9中有些新特性

- JDK8：

  - 默认方法：用default修饰，不可省略，供子类调用或者重写，默认修饰权限符public

    ```java
    default 返回类型 方法名(参数){}
    ```

  - 静态方法：用static修饰，供接口直接调用，不用于使用子类对象间调用，修饰符可以是public private，因为private只供自身默认/静态方法使用，更安全

    ```java
    public static 返回类型 方法名(参数){}
    ```

- JDK9

  - 私有方法：用private修饰，只供接口中默认方法，或者静态方法使用

    ```java
    private 返回类型 方法名(参数){}
    ```

#### 9.6.3 类和接口的关系

- **类和类的关系**

  **继承关系**，只能单继承但是可以继承很多层

- **类和接口的关系**

  **实现关系**，可以单实现，还可以在继承一个类的同时实现多个接口

- **接口和接口的关系**

  **继承关系**，可以单继承也可以多继承

#### 9.6.4 抽象类和接口的区别

- 成员区别

  抽象类					变量，常量；有构造方法；有抽象方法；也有非抽象方法

  接口						常量；抽象方法

- 关系区别

  类与类                     继承，单继承

  类与接口                 实现，可以单实现，也可以多实现

  接口与接口              继承，单继承，多继承

- 设计理念区别

  抽象类                      对类抽象，包括属性，行为

  接口                          行为抽象，主要是行为

例如：门和报警（门有开关动作，不一定有报警动作）

```java
//将功能都放在抽象类中，让子类继承
//抽象类
public abstract class door{
    public abstract void open();
    public abstract void close();
    public abstract void alarm();
} 
//或者这样写，将功能都放在接口中，让子类实现
//接口
public interface door{
    void open();
    void close();
    void alarm();
}
```

上面这两种方法都不好，有的门没报警功能，有的报警但不是门，下面进行优化

```java
//抽象类
public abstract class Door{
    public abstract void open();
    public abstract void close();
} 
//接口
public interface Alarm{
    void alarm();
}
public class AlarmDoor extends Door implements Alarm{
}
```

### 9.7 形参和返回值

#### 9.7.1类名作为形参和返回值

- 方法的形参是类名，其实需要的是该类的对象

```java
public void useCat(Cat c){
 	//Cat c = new Cat();
}
```

- 方法的返回值是类名，其实返回的是该类的对象

```java
public Cat getCat(){
    Cat c = new Cat();
    return c;
    //return new Cat();
}
```

#### 9.7.2抽象类名作为形参和返回值

- 方法的形参是类名，其实需要的是该类子类的对象，抽象类不能直接实例化，通过子类实例化

```java
public void useAnimal(Animal a){
 	//Animal a = new Cat();
}
```

- 方法的返回值是类名，其实返回的是该类子类的对象

```java
public Animal getAnimal(){
    Animal a = new Cat();
    return a;
    //return new Cat();
}
```

#### 9.7.3接口作为形参和返回值

- 方法的形参是接口，其实需要的是该接口的实现类对象，接口不能直接实例化，通过类实现接口

```java
public void useJump(Jump j){
 	//Jump j = new Cat();
}
```

- 方法的返回值是接口，其实返回的是该接口的实现类对象

```java
public Jump getJump(){
    Jump a = new Cat();
    return a;
    //return new Cat();
}
```

## 10 内部类

#### 10.1内部类概述

**内部类**：就是在一个类中定义一个类

**定义格式**：

```java
public class 类名{
    修饰符 class 类名{
        
    }
}
```

**内部类的访问特点**

- 内部类可以直接访问外部类的成员，包括私有

- 外部类要访问内部类的成员，必须创建对象

#### 10.2成员内部类

按照内部类在类中定义的位置不同，可分为如下两种形式：

- 在类的成员位置：**成员内部类**
- 在类的局部位置：**局部内部类**

成员内部类，外界如何创建对象使用呢？

**格式：外部类.内部类 对象名 = 外部类对象.内部类对象;**

```java
Outer.Inner oi = new Outer().new Inner();
```

正确使用方法：内部类权限修饰private，使用外部类方法调用内部类方法

```java
//外部类
public class Outer{
    private int num = 10;
    //内部类
    private class Inner{
        //内部成员方法，访问外部成员变量
        public void show(){
			System.out.println(num);
        }
    }
    //外部成员方法，调用内部类方法
    public void method(){
        Inner i = new Inner();
        i.show();
    }
}
```

#### 10.3局部内部类

**局部内部类**是在***方法中定义的类***，所以外界是**无法直接使用**，需要在方法内部创建对象使用

**权限**：该类可以直接访问外部类的成员，也可以访问方法内的局部变量

```java
//外部类
public class Outer{
    private int num = 10;
 
    //外部成员方法，调用内部类方法
    public void method(){
        int num2 = 10;
        //内部类
        private class Inner{
            //内部成员方法，访问外部成员变量
            public void show(){
                System.out.println(num);
                System.out.println(num2);
            }
        }
        
        Inner i = new Inner();
        i.show();
    }
}
```

#### 10.4匿名内部类

前提：存在一个类或者接口，这里的类是可以是具体类也可以是抽象类

**格式**：

```java
new 类名或者接口名(){
    重写方法;
};
```

例如：

```java
//整体是个对象
new Inter(){
    //重写方法或实现接口
    public void show(){
    }
};
```

本质：是一个继承了该类或者实现了该接口的子类匿名***对象***

```java
//外部类
public class Outer {
    //    外部成员方法
    public void method() {
//        匿名内部类(对象)
        /*new Inter(){
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        };*/
//        创建并调用方法
        /*new Inter(){
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        }.show();*/
//        多次调用方法，太过于麻烦,接口多态的形式将接口引用指向对象
        Inter i = new Inter() {
            @Override
            public void show() {
                System.out.println("匿名内部类");
            }
        };
        i.show();
    }
}
```

相当于：另类的局部内部类（内部类是抽象类的继承类或者接口的实现类）

```java
//创建一个接口
public interface Jump{
    void jump();
}
//创建一个操作接口类
public class JumpOperator{
    public void method(Jump j){//相当于传递接口实现类对象。这时候就可以使用匿名内部类
 		j.jump();
    }
}
//测试类
public  class JumpDemo{
    JumpOperator jo = new JumpOperator();
    jo.method(new Jump{//匿名内部类完成对接口方法实现，不需要Cat类
        public void jump(){
            System.out.println("猫可以跳高了");
        }
    });
}
```



## 11.常用API

### 11.1 Math

Math包含执行基本数字运算的方法

**没有构造方法，如何使用类中的成员呢？**

看类的成员是否都是静态的，如果是，通过类名就可以直接调用

#### Math类的常用方法

|                   方法名                    |                      说明                      |
| :-----------------------------------------: | :--------------------------------------------: |
|        public static int abs(int a)         |                 返回参数绝对值                 |
|     public static double ceil(double a)     | 返回大于或等于参数的最小double值，等于一个整数 |
|    public static double floor(double a)     | 返回小于或等于参数的最大double值，等于一个整数 |
|      public static int round(float a)       |        按照四舍五入返回最接近参数的int         |
|     public static int max(int a,int b)      |            返回两个int值中的较大值             |
|     public static int min(int a,int b)      |            返回两个int值中的较小值             |
| public static double pow(double a,double b) |                返回a的b次幂的值                |
|        public static double random()        |    随机数，返回值为double的正值，[0.0,1.0)     |

### 11.2 System

System包含几个有用的类字段和方法，它不能被实例化

#### System的常用方法

|                方法名                 |                    说明                    |
| :-----------------------------------: | :----------------------------------------: |
|  public static void exit(int status)  | 终止当前运行的Java虚拟机，非零表示异常终止 |
| public static long currentTimeMilis() |        返回当前时间（以毫秒为单位）        |

**正确使用currentTimeMilis方法**

计算程序的运行时长：

```java
		long start = System.currentTimeMillis();
        for (int i = 0; i < 10000; i++) {
            System.out.println(i);
        }
        long end = System.currentTimeMillis();
        System.out.println("程序耗时："+(end-start)+"毫秒");
```

### 11.3 Object

Object是类层次结构的根，每个类都可以将Object作为超类，所有类都直接或者间接的继承自该类

构造方法：public Object()

**回想面对对象中，为什么说子类的构造方法默认访问的是父类的无参构造方法？**

因为他们的顶级父类只有无参构造方法

|             方法名              |                            说明                            |
| :-----------------------------: | :--------------------------------------------------------: |
|    public String toString()     | 返回对象的字符串表示形式，建议所有子类重写该方法，自动生成 |
| public boolean equals(Object o) | 比较对象是否相同，默认比较地址，重写可以比较内容，自动生成 |

### 11.4 Arrays（数组操作类）

#### 11.4.1冒泡排序

**冒泡排序**：排序的一种方式，对要进行排序的数据在相邻的数据进行两两比较，将较大的数据放在后面依次对所有的数据进行操作，直至所有数据按要求完成排序

- 如果有n个数据进行排序，总共需要比较n-1次

- 每一次比较完毕，下一次的比较就会少一个数据参与

```java
for (int i = 0; i < arr.length-1; i++) {
            for (int j = 0; j < arr.length-i-1; j++) {
                if(arr[j]>arr[j+1]){
                    int temp = arr[j+1];
                    arr[j+1] = arr[j];
                    arr[j] = temp;
                }
            }
        }
```

#### 11.4.2Arrays

Arrays类包含用于操作数组的各种方法

**Arrays类的常用方法**

|                 方法名                 |                说明                |
| :------------------------------------: | :--------------------------------: |
| public static String toString(int[] a) | 返回指定数组的内容的字符串表示形式 |
|    public static void sort(int[] a)    |     按照数字顺序排列指定的数组     |

工具类的设计思想：（Arrays，Math，System等）

- 构造方法用private修饰（让人只能通过类名访问，无法创建对象）
- 成员用public static修饰

### 11.5 基本类型包装类

将基本数据类型封装成对象的好处在于可以在对象中定义更多的功能方法操作该数据

常用的操作之一：用于基本数据类型与字符串之间的转换

| 基本数据类型 |    包装类     |
| :----------: | :-----------: |
|     byte     |     Byte      |
|    short     |     Short     |
|     int      |  **Integer**  |
|     long     |     Long      |
|    float     |     Float     |
|    double    |    Double     |
|     char     | **Character** |
|   boolean    |    Boolean    |

#### 11.5.1Integer类的概述和使用

Integer:包装一个对象中的原始类型int的值

|                 方法名                  |                 说明                  |
| :-------------------------------------: | :-----------------------------------: |
|     ~~public Integer (int value)~~      |   （过时）根据int值创建Integer对象    |
|      ~~public Integer(String s)~~       |  （过时）根据String值创建Integer对象  |
|  public static Integer valueOf(int i)   |   返回表示指定的int值的integer实例    |
| public static Integer valueOf(String s) | 返回一个保存指定值的integer对象String |

#### 11.5.2int和String的相互转换

前提：String字符串必须是数字字符串，不然报错NumberFormatException数字解析错误

- **Integer转int**

**public int intValue()**

返回int类型，该方法是Integer类的方法

- **int转Integer**

**public static Integer valueOf(int i)**

- **int转换String**

**public static String valueOf(int i)**

返回int参数的字符串表示形式，该方法是String类中的方法

- **String转换为int**

**public static int parseInt(String s)**

将字符串解析（parse）为int类型，该方法是Integer类中的方法

**案例：有一个字符串“91 27 46 38 50”输出结果“27 38 46 50 91”**

```java
public class IntgeterDome{
    public static void main(String[] args){
        String s1 = "91 27 46 38 50";
//       split： 以regex为分隔符号，将字符串分割为字符串数组
        String[] s = s1.split(" ");
        int[] arr = new int[s.length];
//        arr = Integer.parseInt(s);报错：不能这样用
        for (int i = 0; i < s.length; i++) {
            arr[i] = Integer.parseInt(s[i]);
        }
        Arrays.sort(arr);
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < arr.length-1; i++) {
            if(i == arr.length-1){
                sb.append(arr[i]);
            }else{
                sb.append(arr[i]).append(" ");
            }
        }
        String s2 = sb.toString();
        System.out.println(s2);        
    }
}
```

**public String[] split(String regex)方法**

将String字符串以String regex为分隔符，分为String[]数组

#### 11.5.3自动装箱和拆箱

- 装箱：把基本数据类型转换为对应的包装类类型（例如：int --Integer）

- 拆箱：把包装类类型转换为对应的基本数据类型（例如：Integer--int）

```java
Integer i = 100;//自动装箱：Integer i = Integer.valueOf(100);
i += 100;		//i = i+100; i.intValue()+100自动拆箱  i = i+100;自动装箱
```

**注意**：在使用包装类类型时，如果做操作，最好先判断是否为null

我么推荐的是：**只要是对象，在使用前就必须进行不为null的判断**

### 11.6日期类（三种）

#### 11.6.1Date类概述和构造方法

Date代表了一个特定的事件，精确到毫秒

**构造方法**

|         方法名         |                             说明                             |
| :--------------------: | :----------------------------------------------------------: |
|     public Date()      |    分配一个Date对象，并初始化，默认是现在时间，精确到毫秒    |
| public Date(long date) | 分配一个Date对象，并将其初始化，表示从标准基准时间（1970年1月1日零时）起过去的毫秒数 |

#### 11.6.2Date类的常用方法

|             方法名              |                      说明                      |
| :-----------------------------: | :--------------------------------------------: |
|      public long getTime()      | 获取的日期对象从1970年1月1日零时到现在的毫秒值 |
| public void  setTime(long time) |      过去了多长时间，设置时间给的是毫秒值      |

#### 11.6.3 SimpleDateFormat类概述（SimpleDateFormat是一个对Date进行操作的工具类）

***SimpleDateformat***是一个具体的类，用于以区域设置敏感的方式格式虎啊和解析日期，我们重点学习**日期格式化和解析**

- 日期和时间格式由***日期和时间模式*字符串**指定。  在日期和时间模式字符串中，从`'A'`到`'Z'`以及从`'a'`到`'z'`引号的字母被解释为表示日期或时间字符串的组件的模式字母。 
- 可以使用单引号（ `'` ）引用文本，以避免解释。  `"''"`代表单引号。 所有其他字符不被解释;  在格式化过程中，它们只是复制到输出字符串中，或者在解析过程中与输入字符串匹配。 

**常用的模式字母以及对应关系**

| 字母 | 对应 |
| :--: | :--: |
|  y   |  年  |
|  M   |  月  |
|  d   |  日  |
|  H   |  时  |
|  m   |  分  |
|  s   |  秒  |

**构造方法**

|                   方法                   |                          说明                          |
| :--------------------------------------: | :----------------------------------------------------: |
|        public  SimpleDateFormat()        |    构造一个SimpleDateFormat，使用默认模式和日期格式    |
| public SimpleDateFormat(String  pattern) | 构造一个SimpleDateFormat使用给定的模式和默认的日期格式 |

**SimpleDateFormat格式化和解析日期**

- **格式化（从Date 到String）**

public final String **format(Date date**):将日期格式化成日期/事件字符串

- **解析（从String到Date）**

public Date **parse(String source)**:从给定字符串的开始解析文本以生成日期

```java
public class SimpleDateFormateDome {
    public static void main(String[] args) throws ParseException {
//        格式化:从Date到String
        Date d = new Date();
//        SimpleDateFormat sd = new SimpleDateFormat();默认模式
        SimpleDateFormat sd = new SimpleDateFormat("yyyy年MM月dd日 HH：mm：ss");
        String s = sd.format(d);
        System.out.println(s);
        System.out.println("--------------");
//        解析：从String到Date
        String str = "2023-09-16 23：19：57";
//      SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH：mm：ss");
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH：mm：ss");
        //需要进行异常抛出throw ParseException
        Date date = sdf.parse(str);
        //ParseException解析异常：给定的字符串时间格式和SimpleDateFormat构造格式不一致
        System.out.println(date);
    }
}
```

### 11.6.4 Calendar类概述

**Calendar类**：也被称为日历类

**Calendar** 为某一时刻和某一组日历字段之间的转换提供了方法，并为操作日历字段提供了一些方法

**Calendar**提供了一个类方法getInstance用于获取Calendar对象，其日历字段已使用当前日期和时间初始化：

- Calendar rightNow = Calendar.getInstance();



#### Calendar的常用方法

|                      方法名                       |                          说明                          |
| :-----------------------------------------------: | :----------------------------------------------------: |
|             public int get(int field)             | 返回给定日历字段的值（常见字段：**YEAR,MONTH,DATE**）  |
|  public abstract void add(int field,int amount)   | 根据日历的规则，将指定的时间量添加或减去给定的日历字符 |
| public final void set(int year,int month,int day) |                  设置当前日历的年月日                  |

**需求：获取任意一年二月有多少天**

思路：

1. 键盘录入任意年份

2. 设置日历对象年月日

   1. 年：来自于键盘录入
   2. 月：设置为3月，月份从0开始，所以设置的值为2
   3. 日设置为1日

3. 3月1日往前推一天，二月最后一天

4. 输出这一天

   ```java
   public class CalendarTest {
       public static void main(String[] args) {
           Calendar c = Calendar.getInstance();
           Scanner sc = new Scanner(System.in);
           System.out.println("输入任意年份：");
           int y = sc.nextInt();
           c.set(y,2,1);//月份是从0开始计算的
           c.add(Calendar.DATE,-1);
           int m = c.get(Calendar.MONTH);
           int d = c.get(Calendar.DATE);
           System.out.println(y+"年"+m+"月有"+d+"天");
       }
   }
   ```

   

## 12异常

### 12.1异常描述

异常：就是程序出现了不正常的情况

![](C:\Users\Asinil\Desktop\学习\Java\12.1.png)

**Error**：严重问题，不需要处理

**Exception**：成为异常类，表示程序本省可以处理的问题

- RuntimeException：在编译期间是不检查的，出现问题后，需要我们回来修改代码
- **非RuntimeException**：编译期间就必须处理，否则程序无法通过编译，就更不能正常运行了

### 12.2 JVM的默认处理方案

如果程序出现了问题，我们没有做任何处理，最终JVM会做默认的处理

- **把异常的名称，异常原因以及异常出现的代码位置等信息输出在控制台**
- **程序停止执行后续代码**

### 12.3 异常处理

如果程序出现问题，我们需要自己来处理，有两种方案：

1. **try……catch……**
2. **throws**

#### 12.3.1 异常处理之try……catch

**格式**：

```java
try{
	可能出现异常的代码;
}catch(异常类名 变量){
	异常处理代码;
}
```

**执行流程**：

1. 程序从try里面代码开始执行
2. 出现异常，会自动生成一个异常对象，该异常对象将被提交给Java运行时系统
3. 当Java运行时系统接收到异常对象时，会到catch中去找匹配的异常类，找到后进行异常处理
4. 执行完毕之后，程序还可以继续向下执行

```java
public class ExceptionDemo01 {
    public static void main(String[] args) {
        System.out.println("开始");
        method();
        System.out.println("结束");
    }
    public static void method(){
        try{
            int arr[] = {1,2,3};
            System.out.println(arr[3]);//new ArrayIndexOutOfBoundsException();
        }catch (ArrayIndexOutOfBoundsException e){
//            System.out.println("你访问的数组索引不存在");
            e.printStackTrace();
        }
    }
}
/*
开始
结束
java.lang.ArrayIndexOutOfBoundsException: 3
	at javademo.passage12.test02.ExceptionDemo01.method(ExceptionDemo01.java:19)
	at javademo.passage12.test02.ExceptionDemo01.main(ExceptionDemo01.java:13)
*/
```

ArrayIndexOutOfBoundsException类的printStackTrace()方法能够将异常输出，但又不影响程序继续执行

#### 12.3.2 异常处理之throws

虽然能通过try……catch对异常进行处理，但不是所有的异常我们都有权限进行异常处理，也就是说，有些时候可能出现的异常是我们处理不的，这时候该怎么办？

针对这种情况，Java提供了throws的处理方案

**格式**：

```Java
throws 异常类名;
```

注意：这个格式是跟在方法后面的

- **编译时异常必须要进行异常处理**，两种方案：try…catch…或者throws，如果使用throws这种方案，将来谁调用谁处理（意思时：throws不能进行直接处理，而是将异常抛出方法，最后处理还得try…catch…解决）

- 运行时异常可以不处理，出现问题后，需要我们回来修改代码



### 12.4 Throwable的成员方法

Throwable类是所有异常和错误的超类

|            方法名             |              说明               |
| :---------------------------: | :-----------------------------: |
|  public String getMessage()   | 返回此throwable的详细消息字符串 |
|   public String toString()    |     返回此可抛出的简短描述      |
| public void printStackTrace() |  把异常的错误信息输出在控制台   |

```java
public class ExceptionDemo01 {
    public static void main(String[] args) {
        System.out.println("开始");
        method();
        System.out.println("结束");
    }
    public static void method(){
        try{
            int arr[] = {1,2,3};
            //异常：new ArrayIndexOutOfBoundsException("xxx");带参构造
            System.out.println(arr[3]);
        }catch (ArrayIndexOutOfBoundsException e){
//            e.printStackTrace();

//            public String getMessage()  返回此throwable的详细消息字符串
//            System.out.println(e.getMessage());
//            输出：3          只包含了异常原因

//            public String toString()   返回此可抛出的简短描述
//            System.out.println(e.toString());
//            输出：java.lang.ArrayIndexOutOfBoundsException: 3  包含了异常类名以及原因
            
//            public void printStackTrace()   把异常的错误信息输出在控制台
            e.printStackTrace();
//            输出包含异常类名异常信息以及异常位置
        }
    }
}
/*异常构造对象，使用的是带参构造方法
    public class Throwable{
        public static detailMessage;
        public Throwable(String meaasge){
            detailMessage = meaasge;
        }
        public String getMessage() {
            return detailMessage;
        }
    }
 */
```

### 12.5编译时异常和运行时异常的区别

Java中异常被分为两大类：**编译时异常**和**运行时异常**，也被称为**受检异常**和**非受检异常**

**所有RuntimeException类及其子类被称为运行时异常，其他的异常都是编译时异常**

- **编译时异常**：必须显示处理，否则程序就会发生错误，无法通过编译

- **运行时异常**：无需显示处理，也可以和编译时异常一样处理

**如何判断运行时异常和编译时异常：**

在编写代码时工具提醒你未进行异常处理的异常都是编译时异常

或者在运行报错后，在JDK文档中查看异常原因，是否是RuntimeException的子类

- 是子类则是运行时异常

- 不是子类则是编译时异常

### 12.6 自定义异常

异常类继承Exception或者RuntimeException类即可成为自定义异常

格式：

```java
public class 异常类名 extends Exception{
    无参构造;
    有参构造;
}
```

#### 12.6.1自定义编译时异常extends Exception

```java
//自定义异常类
public class ScoreException extends Exception{
    public ScoreException() {
    }
    public ScoreException(String message) {
        super(message);
    }
}
//老师对象类
public class Teacher {
    public void  checkScore(int score) throws ScoreException{//方法需要抛出异常类，调用者需要进行异常处理
        if(score<0||score>100){
//            使用无参构造方法抛出异常对象，在使用时没有输出异常原因
//            throw new ScoreException();
            throw new ScoreException("你给的分数有误");
        }else{
            System.out.println("分数正常");
        }
    }
}
//测试类
public class TeacherTest {
    public static void main(String[] args) {
        Teacher t = new Teacher();
        System.out.println("请输入分数：");
        Scanner sc = new Scanner(System.in);
        int i = sc.nextInt();
//        编译时异常必须处理异常
        try {
            t.checkScore(i);
        } catch (ScoreException e) {
            e.printStackTrace();
        }
    }
}
```

#### 12.6.2自定义运行时异常extends RuntimeException

```java
//自定义异常类
public class ScoreException extends RuntimeException{
    public ScoreException() {
    }
    public ScoreException(String message) {
        super(message);
    }
}
//老师对象类
public class Teacher {
    public void  checkScore(int score){//异常类可抛出也可以不抛
        if(score<0||score>100){
//            使用无参构造方法抛出异常对象，在使用时没有输出异常原因
//            throw new ScoreException();
            throw new ScoreException("你给的分数有误");
        }else{
            System.out.println("分数正常");
        }
    }
}
//测试类
public class TeacherTest {
    public static void main(String[] args) {
        Teacher t = new Teacher();
        System.out.println("请输入分数：");
        Scanner sc = new Scanner(System.in);
        int i = sc.nextInt();
//        编译时异常必须处理异常
        try {
            t.checkScore(i);
        } catch (ScoreException e) {
            e.printStackTrace();
        }
    }
}
```

#### 12.6.3throws和throw的区别

|                      throws                      |               throw                |
| :----------------------------------------------: | :--------------------------------: |
|         用在方法声明后面，跟的是异常类名         |  用在方法体内部，跟的是异常对象名  |
|        表示抛出异常，由该方法调用者来处理        | 表示抛出异常，由方法体内的语句处理 |
| 表示出现异常的一种可能性，并不一定会发生这种异常 |    执行throw一定抛出了某种异常     |



## 13集合进阶

### 13.1Collection

#### 13.1.1集合的基础知识回顾

**集合类特点**：提供一种存储空间可变的存储模型，存储的数据容量可以发生改变

#### 13.1.2集合类体系结构

![](C:\Users\Asinil\Desktop\学习\Java\13.2.png)

#### 13.1.3Collection集合概述和使用

Collection集合概述：

- 是单例集合的顶层接口，他表示一组对象，这些对象也成为Collection的元素
- JDK不提供此接口的任何直接实现，他提供更具体的子接口（如：set和List）实现

创建Collection集合对象

- 多态的方式
- 具体的实现类ArrayList

#### 13.1.4Collection集合常用方法

|           方法名           |             说明             |
| :------------------------: | :--------------------------: |
|      boolean add(E e)      |           添加元素           |
|  boolean remove(Object o)  |     从集合中移除指定元素     |
|        void clear()        |         清空集合元素         |
| boolean contains(Object o) |   判断集合是否存在指定元素   |
|     boolean isEmpty()      |       判断集合是否为空       |
|         int size()         | 集合长度，也就是集合元素个数 |

#### 13.1.5Collection集合的遍历

**Iterator**：迭代器，集合的专用遍历方式

- **Iterator<E> iterator():返回此集合中元素的迭代器，通过集合的iterator()方法得到**
- 迭代器是通过集合的iterator()方法得到的，所以我们说它是依赖于集合而存在的

**Iterator中常用方法**

|      方法名       |                说明                |
| :---------------: | :--------------------------------: |
|     E next()      |      返回迭代器中的下一个元素      |
| boolean hasNext() | 如果迭代器具有更多元素，则返回true |

```java
    public static void main(String[] args) {
        Collection<String> c = new ArrayList<String>();
//        添加元素
        c.add("java");
        c.add("hello");
        c.add("world");

//        返回此集合中的迭代器
        Iterator<String> it = c.iterator();
        /*ArrayList类中实现接口方法：
        * public Iterator<E> iterator() {
        return new Itr();
        *
        *  private class Itr implements Iterator<E> {
        * ……
        * }
    }*/
        /*System.out.println(it.next());
        System.out.println(it.next());
        System.out.println(it.next());
        System.out.println(it.next());//        报错：NoSuchElementException*/

//        boolean hasNext() :如果迭代器具有更多元素，则返回true
       /* if(it.hasNext()){
            System.out.println(it.next());
        }
        if(it.hasNext()){
            System.out.println(it.next());
        }
        if(it.hasNext()){
            System.out.println(it.next());
        }
        if(it.hasNext()){
            System.out.println(it.next());
        }*/

//        while循环改进
        while(it.hasNext()){
//            System.out.println(it.next());
            String s = it.next();
            System.out.println(s);
        }
    }
}
```

#### 13.1.6Collection集合的使用步骤

1. 创建集合对象：Collection<E> c = new ArrayList<E>();
2. 添加元素：add()；
   1. 创建元素
   2. 添加到元素集合
3. 遍历集合
   1. 通过集合对象获取迭代器对象：Iterator()方法
   2. 通过迭代器对象的hasNext()方法判断是否还有元素
   3. 通过迭代器对象的next()方法获取下一个元素

**需求：创建一个存储学生对象的集合，存储三个学生对象，使用程序实现在控制台遍历**

```java
//学生类
public class Student {
    private String name;
    private int age;
    private long id;
//  构造函数
    public Student() {
    }
    public Student(String name, int age, long id) {
        this.name = name;
        this.age = age;
        this.id = id;
    }
//    get/set方法
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
    public long getId() {
        return id;
    }
    public void setId(long id) {
        this.id = id;
    }
//    重写toString方法
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", id=" + id +
                '}';
    }
}

//测试类
public class StudentDemo {
    public static void main(String[] args) {
//        创建集合对象
        Collection<Student> c = new ArrayList<Student>();
//        创建集合元素
        Student s1 = new Student();
        s1.setId(2004241001);
        s1.setName("张三丰");
        s1.setAge(43);
        Student s2 = new Student("风清扬",41,2004241002);
        Student s3 = new Student("令狐冲",25,2004241003);
//        将元素存储进集合中
        c.add(s1);
        c.add(s2);
        c.add(s3);
//        获取集合迭代器
        Iterator<Student> it = c.iterator();
//        对集合进行遍历
        while(it.hasNext()){
            System.out.println(it.next());
//            it.next().toString();
        }
    }
}
```



### 13.2List

#### 13.2.1List集合概述

- 有序集合（也被称为序列），用户可以精确控制列表中每个元素的插入位置。用户可以通过整数索引访问元素，并搜索元素中的元素
- 与Set集合不同，列表通常允许重复元素

List集合特点

- 有序：存储和取出的元素顺序一致
- 可重复：存储的元素可以重复

#### 13.2.2List集合特有方法（ArrayList中学习过）

|            方法名             |                 说明                 |
| :---------------------------: | :----------------------------------: |
| void add(int index,E element) |    在此集合的指定位置插入指定元素    |
|      E remove(int index)      | 删除指定索引处的元素，返回被删除元素 |
|  E set(int index,E element)   | 修改指定索引处的元素，返回被修改元素 |
|       E get(int index)        |         返回指定索引处的元素         |

需求：使用List集合存储学生对象并遍历

```java
//学生类
public class Student {
    private String name;
    private int age;
    private long id;
//  构造函数
    public Student() {
    }
    public Student(String name, int age, long id) {
        this.name = name;
        this.age = age;
        this.id = id;
    }
//    get/set方法
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
    public long getId() {
        return id;
    }
    public void setId(long id) {
        this.id = id;
    }
//    重写toString方法
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", id=" + id +
                '}';
    }
}
//测试类
public class StudentDemo {
    public static void main(String[] args) {
//        创建集合对象
        List<Student> l = new ArrayList<Student>();
//        创建集合元素
        Student s1 = new Student();
        s1.setId(2004241001);
        s1.setName("张三丰");
        s1.setAge(43);
        Student s2 = new Student("风清扬",41,2004241002);
        Student s3 = new Student("令狐冲",25,2004241003);
//        将元素存储进集合中
        l.add(s1);
        l.add(s2);
        l.add(s3);
//        迭代器遍历方法
        Iterator<Student> it = c.iterator();
//        对集合进行遍历
        while(it.hasNext()){
            System.out.println(it.next());
        }
        System.out.println("-------------");
        //for循环get方法遍历
        for (int i = 0; i < l.size(); i++) {
            System.out.println(l.get(i));
        }     
    }
}
```

#### 13.2.3并发修改异常

**ConcurrentModificationException**：当不允许这样的修改时，可以通过检测到对象的并发修改的方法来抛出此异常。

**迭代器并发修改异常原因：**

- ​    在调用Iterator迭代器进行遍历时，预期修改集合次数expectedModCount == 实际修改集合次数ModCount
- ​    但是在循环过程中，使用add方法，使得ModCount++
- ​    而expectedModCount没有变化，导致运行next方法时检测expectedModCount ！= ModCount，抛出ConcurrentModificationException异常

**get方法没有并发异常原因：**

- ​    没有对修改次数进行判断，直接返回索引处的值

**解决方案**：

- 使用普通for循环遍历list.size()，返回用集合对象操作即可

#### 13.2.4ListIterator

ListIterator：列表迭代器

- 通过**List集合**的listIsterator()方法得到，所以说他是List集合特有的迭代器

- 用于允许程序员从任一方向遍历列表的列表迭代器，在迭代期间修改列表，并获取列表中迭代器的当前位置



**ListIterator中的常用方法**

| 方法名                | 说明                                                 |
| --------------------- | ---------------------------------------------------- |
| E next()              | 返回迭代器中的下一个元素                             |
| boolean hasNext()     | 如果迭代器具有更多元素，返回true                     |
| E previous()          | 返回列表中上一个元素                                 |
| boolean hasPrevious() | 如果迭代器在相反方向遍历列表时具有更多元素，返回true |
| void add(E e)         | 将指定元素插入列表                                   |

**ListIerator中add方法不会导致并发修改异常的原因**

```java
//listIerator：
	public void add(E e) {
            checkForComodification();//判断expectedModCount = modCount?
            try {
                int i = cursor;
                ArrayList.this.add(i, e);
                cursor = i + 1;
                lastRet = -1;
                expectedModCount = modCount;//实际修改值赋值给预期修改值，所以不会出现并发修改异常
            } catch (IndexOutOfBoundsException ex) {
                throw new ConcurrentModificationException();
            }
        }             
```

#### 13.2.5增强for循环

增强for：简化数组和Collection集合的遍历

- 实现Iterable接口的类允许其对象称为增强型for语句的目标
- 它是JDK5之后出现的，内部原理是一个Iterator迭代器

**增强for的格式**

```java
for(元素数据类型  变量名：数组或者Collection集合){
    //在此处使用变量即可，该变量是元素
}
```

例如：

```java
int[] arr = {1,2,3,4};
for(int i: arr){
    System.out.println(i);
}
```

**如何判断内部原理是一个Iterator迭代器？**

```java
//        内部原理是一个Iterator迭代器：抛出ConcurrentModificationException并发修改异常
	 List<String> list = new ArrayList<String>();
     list.add("张三");
     list.add("李四");
     list.add("王五");
	 for(String l:list){
         if(l.equals("张三")){
             list.add("javaee");
         }
    }   
```

#### 13.2.6数据结构

##### 1.常见数据结构之栈（一端开口一端闭口）

栈模型特点：

- 数据进入栈模型的过程为：**压/进栈**
- 数据进出栈模型的过程为：**弹/出栈**

**栈**是一种数据**先进后出**模型

进栈顺序：123		出栈顺序：321

##### 2.常见数据结构之队列（两端开口）

队列模型特点：

- 数据从**后端**进入队列模型的过程称为：**入队列**

- 数据从**前端**进入队列模型的过程称为：**出队列**

**队列**是一种数据**先进先出**模型

入队列顺序：123		出队列顺序：123

##### 3.常见数据类型之数组

数组模型特点：

- 查询数据时通过索引定位，查询任意数据耗时相同，**查询速度快**

- 删除数据时，要将原始数据删除，同时后面每个数据前移，**删除效率低**

- 添加数据时，要将添加位置后每个数据后移，在添加元素，**添加效率极低**

**数组**是一种**查询快，增删慢**的模型

##### 4.常见数据类型之链表

**链表**的每个元素称为**结点**

节点所包含的内容：

- **结点的存储位置（地址）**
- **存储具体的数据**
- **下一个结点的地址**

![](C:\Users\Asinil\Desktop\学习\Java\13.2.6png.png)

**在链表中，如何添加元素呢？（例如AC间添加B元素）**

1. 数据B对应的下一个数据地址指向C数据
2. 数据A对应的下一个数据地址指向B数据

![](C:\Users\Asinil\Desktop\学习\Java\13.2.6_2.png)

**在链表中，如何删除元素呢？（例如BCD间删除C元素）**

1. 数据B对应的下一个数据地址指向D数据
2. 删除C数据

**在链表中，如何查询数据？**

链表查询任一元素，必须从头（head）开始查询

**链表特点：**

- 链表是一种**增删快**的模型（对比数组）

- 链表是一种**查询慢**的模型（对比数组）

#### 13.2.7List集合子类特点

List集合常用子类：ArrayList，LinkedList

- ArrayList：底层数据结构是**数组**，查询快，增删慢
- LinkedList：底层数据结构时**链表**，查询慢，增删快

需求：分别使用ArrayList和LinkedList完成存储字符串并遍历

```java
//ArrayList和LinkedList实现存储和遍历
public class LinkedListDemo {
    public static void main(String[] args) {
/*//        ArrayList实现存储和遍历
//        创建集合对象
        List<String> list = new ArrayList<String>();
//        添加集合元素
        list.add("java");
        list.add("is");
        list.add("the");
        list.add("best");
        list.add("language");
//        增强for遍历，还有两种就不写了
        for (String s:list) {
            System.out.println(s);
        }*/
//        LinkedList实现存储和遍历
//        创建集合对象
        List<String> list = new LinkedList<String>();
//        添加集合元素
        list.add("java");
        list.add("is");
        list.add("the");
        list.add("best");
        list.add("language");
//        迭代器遍历，还有两种就不写了
        Iterator<String> it = list.iterator();
        while(it.hasNext()){
            String s = it.next();
            System.out.println(s);
        }

    }
}
```

#### 13.2.8LinkedList集合类的特有方法

|          方法名           |                   说明                   |
| :-----------------------: | :--------------------------------------: |
| public void addFirst(E e) |         在该列表开头插入指定元素         |
| public void addLast(E e)  |       将指定元素追加到此列表的末尾       |
|    public E getFirst()    |         返回此列表中的第一个元素         |
|    public E getLast()     |         返回此列表中最后一个元素         |
|  public E removeFirst()   |  从此列表中删除第一个元素，并返回该元素  |
|   public E removeLast()   | 从此列表中删除最后一个元素，并返回该元素 |

### 13.3Set

#### 13.3.1Set集合概述和特点

Set集合特点

- 不包含重复元素的集合
- 没有带索引的方法，所以不能使用普通for循环进行遍历

需求：使用Set集合存储字符串并遍历

#### 13.3.2哈希值

哈希值：是JDK根据对象的**地址**或者**字符串**或者**数字**算出来的int类型的数值

object类中有一个方法可以获取**对象的哈希值**

- 方法：public int hashCode（）返回对象的哈希码值



**对象的哈希值特点**

- 同一个对象多次调用hashCode()方法返回的哈希值是相同的
- 默认情况下，不同对象的哈希值是不同的，而重写hashCode()方法可以实现让不同对象的哈希值相同
- 不同集合存储相同对象
  - 存储一种相同对象，不同集合返回的哈希值为存储对象的哈希值
  - 存储多种相同对象，不同集合返回的哈希值相同

#### 13.3.3HashSet集合概述和特点

**HashSet集合特点**

- 底层数据结构是哈希表
- 对集合的迭代顺序不做任何保证，也就是说**不保证存储顺序和取出顺序一致**
- 没有带索引的方法，所以不能使用普通for循环进行遍历，只能使用迭代器和增强for循环遍历
- 由于是Set集合，所以是不包含重复元素的集合

需求：使用HashSet集合存储字符串并遍历

```java
public class HashSetDemo02 {
    public static void main(String[] args) {
//        创建Set集合对象
        HashSet<String> set = new HashSet<String>();
//        给集合添加元素
        set.add("java");
        set.add("is the best language");
        set.add("python");
//        使用迭代器进行遍历,没有出现并发修改异常
        Iterator<String> it = set.iterator();
        while(it.hasNext()){
            if(it.next().equals("java"))
                set.add("javaee");
        }
//        增强for循环遍历
        for (String s:set) {
            System.out.println(s);
        }
    }
}
```

#### 13.3.4HashSet集合保证元素唯一性源码分析

**HashSet集合添加一个元素的过程**

![](C:\Users\Asinil\Desktop\学习\Java\13.3.4.png)

**源码分析**

```java
public class HashSet<E>
{
    public boolean add(E e) {
            return map.put(e, PRESENT)==null;
        }
}
public class HashMap<K,V>  {
   		public V put(K key, V value) {
                return putVal(hash(key), key, value, false, true);
            }
        //通过传递元素得到元素哈希值
        static final int hash(Object key) {
                int h;
                return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
            }
        //hash为元素哈希值，key为元素本身
        final V putVal(int hash, K key, V value, boolean onlyIfAbsent,
                           boolean evict) {
                Node<K,V>[] tab; Node<K,V> p; int n, i;
                //如果哈希表未初始化，则进行初始化操作
                if ((tab = table) == null || (n = tab.length) == 0)
                    n = (tab = resize()).length;

                //根据对象的哈希值计算对象的存储位置，如果位置没有元素，就存储元素
                if ((p = tab[i = (n - 1) & hash]) == null)
                    tab[i] = newNode(hash, key, value, null);
                else {
                    Node<K,V> e; K k;
                    /*
                        存入元素和以前的元素比较哈希值
                            如果哈希值不同，继续向下执行，把元素添加到集合中
                            如果哈希值相同，会调用对象的equals方法比较
                                如果返回false，会向下执行添加到集合
                                如果返回true，元素重复不添加
                    */
                    if (p.hash == hash &&
                        ((k = p.key) == key || (key != null && key.equals(k))))
                        e = p;
                    else {
                        for (int binCount = 0; ; ++binCount) {
                            if ((e = p.next) == null) {
                            //建立一个新的结点存储元素
                                p.next = newNode(hash, key, value, null);
                                if (binCount >= TREEIFY_THRESHOLD - 1) // -1 for 1st
                                    treeifyBin(tab, hash);
                                break;
                            }
                            if (e.hash == hash &&
                                ((k = e.key) == key || (key != null && key.equals(k))))
                                break;
                            p = e;
                        }
                    }
                    if (e != null) { // existing mapping for key
                        V oldValue = e.value;
                        if (!onlyIfAbsent || oldValue == null)
                            e.value = value;
                        afterNodeAccess(e);
                        return oldValue;
                    }
                }
                ++modCount;
                if (++size > threshold)
                    resize();
                afterNodeInsertion(evict);
                return null;
            }
    }
```

HashSet集合存储元素

- 要保证元素唯一性，需要重写hashCode()和equals()

#### 13.3.5常见数据结构之哈希表

**哈希表**

- JDK8之前，底层采用**数组+链表**实现，可以说是一个元素为链表的数组
- JDK8以后，在长度比较长的时候，底层实现了优化

**HashSet集合**

- HashSet():无参构造，默认大小为16
- HashSet(int capacity):带参构造，可以指定大小

**哈希表的存储过程**

1. 先获取元素的哈希值，并将哈希值取余哈希表大小（例如：11111111%16）得到在哈希表中**数组存储位置**

2. 若数组存储位置没有元素，则直接添加进去

   若数组存储位置有元素，则将添加元素和以获取元素进行比较

   - 先比较双方哈希值，若相同再比较元素内容，再相同则为相同元素，
   - 若比较的哈希值不同或后面内容不同则为不同元素，直接添加在后面，以**链表形式**

![](C:\Users\Asinil\Desktop\学习\Java\13.3.5.png)

需求：使用HashSet集合创建一个存储学生对象的集合，存储多个学生对象，使用程序实现并遍历

```java
//学生类
public class Student {
    private String name;
    private int age;
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public Student() {
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
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Student student = (Student) o;
        if (age != student.age) return false;
        return name != null ? name.equals(student.name) : student.name == null;
    }
//      保证数据唯一性
    @Override
    public int hashCode() {
        int result = name != null ? name.hashCode() : 0;
        result = 31 * result + age;
        return result;
    }
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
//测试类
//需求：使用HashSet集合创建一个存储学生对象的集合，存储多个学生对象，使用程序实现并遍历
public class HashSetDemo03 {
    public static void main(String[] args) {
//        创建集合对象
        HashSet<Student> hset = new HashSet<Student>();
//        创建学生对象
        Student s1 = new Student("张三",18);
        Student s2 = new Student("李四",19);
        Student s3 = new Student("王五",20);
        Student s4 = new Student("张三",18);
//        添加到哈希表中,Student类重写hashcode方法和equals方法才能保证数据唯一性
        hset.add(s1);
        hset.add(s2);
        hset.add(s3);
        hset.add(s4);
//        迭代器遍历
        Iterator<Student> it = hset.iterator();
        while(it.hasNext()){
            System.out.println(it.next());
        }
        System.out.println("----------------");
//        增强for循环
        for (Student  s: hset
             ) {
            System.out.println(s);
        }

    }
}
```

**为保证数据唯一性，需要在Student类中重写equals方法和hashCode方法，equals和hashCode方法自动生成即可**

#### 13.3.6LinkedHashSet集合概述和特点

**LinkedHashSet集合特点**

- 哈希表和链表实现的Set接口，具有可预测的迭代次序
- **以链表保证元素有序，也就是说元素存储和取出顺序一致**
- 有哈希表保证元素唯一性，也就是说没有重复元素

需求：使用LinkHashSet集合完成字符串的存储和遍历

```java
public class LinkedHashSetDemo {
    public static void main(String[] args) {
//        创建元素对象
        LinkedHashSet<String> lhset = new LinkedHashSet<String>();
//        添加对象到集合
        lhset.add("java");
        lhset.add("hello");
        lhset.add("world");
        lhset.add("java");
//        增强for遍历
        for(String s:lhset){
            System.out.println(s);
        }
    }
}
```

#### 13.3.7TreeSet集合概述和特点

##### TreeSet集合特点

- 元素有序，这里的顺序不是指存储和取出的顺序，而是**按照一定的规则进行排序，具体方式取决于构造方法**
  - TreeSet()：根据其元素的自然排序进行排序
  - TreeSet(Comparator comparator)：根据指定的比较器进行排序
- 没有带索引的方法，不能使用普通for循环遍历
- 由于是Set集合，所以不包含重复元素

**需求：使用TreeSet集合完成整数的存储和遍历**

```java
public class TreeSetDemo {
    public static void main(String[] args) {
//        创建元素对象，这里<>里面填写的基本类型的引用类型，所以为包装类型
        TreeSet<Integer> tset = new TreeSet<Integer>();
//        添加对象到集合，这里直接填写10，因为可以自动装箱
        tset.add(10);
        tset.add(20);
        tset.add(50);
        tset.add(30);
        tset.add(20);
//        增强for遍历
        for(int s:tset){
            System.out.println(s);
        }
    }
}
```

##### 自然排序Comparable的使用

案例：

- 存储学生对象并遍历，创建TreeSet集合使用**无参构造方法**
- 按照年龄从小到大排序，如果年龄相同，则按照名字字母排序

```java
public class Student implements Comparable<Student> {
    private String name;
    private int age;
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public Student() {
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
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Student student = (Student) o;

        if (age != student.age) return false;
        return name != null ? name.equals(student.name) : student.name == null;
    }
    //      保证数据唯一性
    @Override
    public int hashCode() {
        int result = name != null ? name.hashCode() : 0;
        result = 31 * result + age;
        return result;
    }
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
    @Override
    public int compareTo(Student o) {
//        返回值为0，表示元素重复，不进行添加
//        return 0;
//        返回值为1，表示元素2比元素1大，排序在后面
//        return 1;
//        返回值为-1，表示元素1比元素2大，排序在前面
//        return -1;
//        按照年龄从小到大排序
        /*int num = this.age - o.age;
        if (num > 0) {
            return 1;
        } else if (num < 0) {
            return -1;
        } else {
            int num2 = this.name.compareTo(o.name);
            if (num > 0) {
                return 1;
            } else if ((num2 < 0)) {
                return -1;
            } else {
                return 0;
            }
        }*/
//        简化
        int num1 = this.age - o.age;
        int num2 = num1 == 0?this.name.compareTo(o.name):num1;
        return num2;
    }
}
//测试类
public class ComparableDemo {
    public static void main(String[] args) {
        TreeSet<Student> ts = new TreeSet<Student>();
        Student s1 = new Student("张三",18);
        Student s2 = new Student("李四",19);
        Student s3 = new Student("王五",20);
        Student s4 = new Student("刘六",18);
        ts.add(s1);
        ts.add(s2);
        ts.add(s3);
        ts.add(s4);
        for (Student  s: ts
        ) {
            System.out.println(s);
        }
    }
}
```

结论：

- 用TreeSet集合存储自定义对象，无参构造方法使用的是自然排序对元素进行排序的
- 自然排序就是让元素所属的类**实现Comparable接口**，**重写ConpareTo方法**
- 重写方法时，一定要注意排序规则必须按照要求的主要条件和次要条件来写

##### 比较器排序Comparator的使用

- 存储学生对象并遍历，创建TreeSet集合使用带参构造方法
- 要求：按照年龄从小到大排序，如果年龄相同，则按照名字字母排序

```java
public class ComparatorDemo {
    public static void main(String[] args) {
//        匿名内部类来传递接口实现类
        TreeSet<Student> ts = new TreeSet<>(new Comparator<Student>() {
            @Override
            public int compare(Student s1, Student s2) {
                int num1 = s1.getAge() - s2.getAge();
                int num2 = num1 == 0?s1.getName().compareTo(s2.getName()):num1;
                return num2;
            }
        });
        Student s1 = new Student("张三",18);
        Student s2 = new Student("李四",19);
        Student s3 = new Student("王五",20);
        Student s4 = new Student("刘六",18);
        ts.add(s1);
        ts.add(s2);
        ts.add(s3);
        ts.add(s4);
        for (Student  s: ts
        ) {
            System.out.println(s);
        }
    }
}
```

结论：

- 用TreeSet集合存储自定义对象，无参构造方法使用的是**比较器排序**对元素进行排序的
- 比较器排序，就是让**集合构造方法接收Comparable接口的实现类对象（可以使用匿名内部类），重写Conpare（T o1,T o2）方法**
- 重写方法时，一定要注意排序规则必须按照要求的主要条件和次要条件来写

### 13.4泛型

#### 13.4.1泛型概述

**泛型**：泛型是JDK5中引入的特性，它提供了编译时类型安全检测机制，该机制允许在编译时检测到非法类型

它本质是**参数化类型**，也就是说所操纵的数据类型被指定为一个参数

一提到参数，最熟悉的就是定义方法时有形参，然后调用方法时传递实参，那么参数化类型怎么理解呢？

顾名思义，就是**将类型由原来的具体的类型参数化，然后在使用/调用时传入具体的类型**

这种参数类型可以用在类，方法，接口中，分别被称为泛型类，泛型方法，泛型接口

**泛型的定义格式**

- <类型>：指定一种类型的格式，这里的类型可以看成形参
- <类型1,类型2>：指定多种类型格式，多种类型之间用逗号分开，这里的类型可以看成是形参
- 将来具体调用时给定的类型可以看成是实参，且实参的类型只能说引用数据类型（例如：Integer）

**泛型的好处**

- 将运行时的问题提前到了编译期
- 避免强制类型转换

#### 13.4.2泛型类

**泛型类的定义格式**

- 修饰符 class 类名<类型>{ }

- 范例：public class Generic<T>{ }

  此处**T**可以随便写为任意标识符，常见的如**T，E，K，V**等形式的参数常用于表示泛型

#### 13.4.3泛型方法 

**泛型方法定义格式**

- 修饰符 <类型>返回类型 方法名(类型 变量名){}
- 范例：Public<T>  void show（T t）{}

#### 13.4.4泛型接口

**泛型接口定义格式**

- 修饰符 interface 接口名<类型>{}
- 范例：public interface Generic <T>{}

#### 13.4.5类型通配符

为表示各种泛型List的父类，可以使用**类型通配符**

- 类型通配符：**<?>**
- List<?>：表示元素类型位置的List，它的元素可以匹配**任何类型**
- 这种带通配符的List仅表示它是各种泛型List的父类，并不能把元素添加到其中

如果我们不希望List<?>是任何泛型List的父类，只希望它代表某一类泛型List的父类，可以使用**类型通配符上限**

- 类型通配符上限：**<? extends 类型>**
- **List<? extends Number>**：表示的类型是**Number或者其子类型**

除了可以指定类型通配符上限，还可以指定类型通配符下限

- 类型通配符上限：**<? super类型>**
- **List<? super Number>**：表示的类型是**Number或者其父类型**

```java
public class GenericDemo03 {
    public static void main(String[] args) {
//        类型通配符
        List<?> list1 =new ArrayList<Object>();
        List<?> list2 =new ArrayList<Number>();
        List<?> list3 =new ArrayList<Integer>();

//        类型通配符上限
//        List<?extends Number> list4 =new ArrayList<Object>();//Object是Number的父类不能使用，已经限制上线为Number
        List<?extends Number> list4 =new ArrayList<Number>();
        List<?extends Number> list5 =new ArrayList<Integer>();

//        类型通配符下限
        List<?super Number> list6 =new ArrayList<Number>();
        List<?super Number> list7 =new ArrayList<Object>();
//        List<?super Number> list8 =new ArrayList<Integer>();//Integer是Number的子类，已经限制下线为Number
    }
}
```

#### 13.4.6可变参数

**可变参数**：又称参数个数可变，用作方法的形参出现，那么方法参数个数就是可变的

- 格式：修饰符 返回类型 方法名（数据类型…变量名）{}
- 例如：public static int sum(int...a){}

```java
public class ArgsDemo01 {
    public static void main(String[] args) {
        System.out.println(sum(10, 20));
        System.out.println(sum(10, 20, 30));
        System.out.println(sum(10, 20, 30, 40));
        System.out.println("------------------");
        System.out.println(sumStr("zhangsan",10, 20));
        System.out.println(sumStr("lisi",10, 20, 30));
        System.out.println(sumStr("wangwu",10, 20, 30, 40));
    }
    //    public static int sum(int a,int b){
//        return a+b;
//    }
//    public static int sum(int a,int b,int c){
//        return a+b+c;
//    }
//    public static int sum(int a,int b,int c,int d){
//        return a+b+c+d;
//    }
//    可变参数进行优化
    public static int sum(int... a) {
//        System.out.println(a);//可变参数将形参封装到一个int类型数组中了
        int sum = 0;
        for (int i : a) {
            sum += i;
        }
        return sum;
    }

//    如果一个方法由多个参数，可变参数放在后面
    public static int sumStr(String s,int...a){
        int sum = 0;
        for (int i : a) {
            sum += i;
        }
        return sum;
    }
}
```

**可变参数的注意事项**

- 这里的变量其实是一个数组
- 如果方法有多个参数，包含可变参数，**可变参数放最后面**



#### 13.4.7可变参数的使用

**Arrays工具类中有一个静态方法：**

- public static <T>   List<T>   asList(T...a)：返回由指定数组支持的固定大小列表
- 注意：返回的集合不能做增删操作，可以修改

**List接口中有一个静态方法（JDK9）：**

- public static<E>    List<E>   of(E...e)：返回包含任意数量元素的不可变列表
- 注意：不能做增删改操作

**Set接口中有一个静态方法（JDK9）：**

- public static<E>  Set<E>  of(E...e)：返回包含任意数量元素的不可变集合
- 注意：
  - 不能做增删操作，没有修改方法
  - 给元素返回集合时，不能给重复元素

```java
public class ArgsDemo02 {
    public static void main(String[] args) {
//         public static <T> List<T> asList(T...a)：返回由指定数组支持的固定大小列表
        List<String> list = Arrays.asList("hello","world","java");
//        list.add("javaee");//.UnsupportedOperationException不支持的操作异常
//        list.remove("world");//.UnsupportedOperationException不支持的操作异常
//        set方法没有修改集合大小可以使用
//        list.set(1,"javaee");

//        - public static<E>List<E> of(E...e)：返回包含任意数量元素的不可变列表
//        List.of方法在JDK9才可以使用
//        List<String> list = List.of("hello","world","java");
//        list.add("javaee");//.UnsupportedOperationException不支持的操作异常
//        list.remove("java");//.UnsupportedOperationException不支持的操作异常
//        list.set(1,"javaee");//.UnsupportedOperationException不支持的操作异常

//        - public static<E>Set<E> of(E...e)：返回包含任意数量元素的不可变集合*/
//        Set.of方法在JDK9才可以使用
//        Set<String> list = Set.of("hello","world","java");
//        Set<String> list = Set.of("hello","world","java","world");//IllegalArugmentEception非法或不正确的参数：因为有重复元素
//        list.add("javaee");//.UnsupportedOperationException不支持的操作异常
//        list.remove("java");//.UnsupportedOperationException不支持的操作异常
        System.out.println(list);
    }
}
```

### 13.5Map集合

#### 13.5.1Map集合的概述和特点

**Map集合概述**

- Interface Map<K,V>  

  K：键的类型

  V：值的类型

- 将键映射到值的对象；不能包含重复的键，每个键可以映射到最多一个值

- 例如：学生的学号和姓名

  2004241001	林青霞

  2004241002	张曼玉

**创建Map集合对象**

- 采用多态的方式
- 具体的实现类HashMap

#### 13.5.2Map集合的基本功能

|               方法名                |                  说明                  |
| :---------------------------------: | :------------------------------------: |
|        V put(K key,V value)         |                添加元素                |
|        V remove(Object key)         |          根据键删除键值对元素          |
|            void clear()             |           移除所有键值对元素           |
|   bollean containsKey(Object key)   |      判断集合中是否包含所指定的键      |
| bollean containsValue(Object value) |      判断集合中是否包含所指定的值      |
|          boolean isEmpty()          |            判断集合是否为空            |
|             int size()              | 返回集合长度，也就是集合中简直对的个数 |

#### 13.5.3Map集合的获取功能

|               方法名               |             说明             |
| :--------------------------------: | :--------------------------: |
|         V get(Object key)          |         根据键获取值         |
|          Set<K> keySet()           |       获取所有键的集合       |
|       Collection<V> value()        |       获取所有值的集合       |
| **Set<Map.Entry<K,V>> entrySet()** | **获取所有键值对对象的集合** |

```java
public class MapDemo03 {
    public static void main(String[] args) {
        //        创建集合对象
        Map<String,String> map = new HashMap<String,String>();
//        添加元素
        map.put("郭靖","黄蓉");
        map.put("杨过","小龙女");
        map.put("萧峰","阿朱");
        map.put("段誉","王语嫣");
        System.out.println(map);
        System.out.println("------------");

//        |         V get(Object key)          |         根据键获取值         |
        System.out.println(map.get("杨过"));
        System.out.println(map.get("杨不悔"));//不存在的输出null
        System.out.println("------------");
//        |          Set<K> keySet()           |       获取所有键的集合       |
        Set<String> set = map.keySet();
        for(String s :set){
            System.out.println(s);
        }
        System.out.println("------------");
//      |       Collection<V> value()        |       获取所有值的集合       |
        Collection<String> c = map.values();
        for(String s :c){
            System.out.println(s);
        }
        System.out.println("------------");
//        | **Set<Map.Entry<K,V>> entrySet()** | **获取所有键值对对象的集合** |
        Set<Map.Entry<String,String>> entryset = map.entrySet();
        System.out.println(entryset);
        System.out.println("------------");
    }
}
```

#### 13.5.4Map集合的遍历方式（方式一）

我们刚才存储的元素都是成对出现的，我们可以把Map看成是一对夫妻对的集合

遍历思路：

- 把所有丈夫集中起来
- 遍历丈夫集合，获取到每一个丈夫
- 根据丈夫去找妻子

转换为Map集合中的操作

- 获取所有键的集合，使用keySet方法实现
- 遍历键的集合，获取每一个键，用增强for实现
- 根据键去找值，使用get方法实现

#### 13.5.4Map集合的遍历方式（方式二）

我们刚才存储的元素都是成对出现的，我们可以把Map看成是一对夫妻对的集合

遍历思路：

- 获取所有结婚证的集合
- 遍历结婚证的集合，得到每一个结婚证
- 证据结婚证获取丈夫和妻子

转换为Map集合中的操作

- 获取所有键值对对象的集合，使用**Set<Map.Entry<K,V>> entrySet()**  **（获取所有键值对对象的集合）**方法实现
- 遍历键值对对象的集合，获取每一个键值对对象，用增强for实现
- 根据键值对对象去找键和值，使用getKey方法和getValue方法实现

```java
public class MapDemo04 {
    public static void main(String[] args) {
        //        创建集合对象
        Map<String,String> map = new HashMap<String,String>();
//        添加元素
        map.put("郭靖","黄蓉");
        map.put("杨过","小龙女");
        map.put("萧峰","阿朱");
        map.put("段誉","王语嫣");
        map.put("杨康","穆念慈");
        map.put("张无忌","赵敏");
        map.put("段正淳","白刀凤");
//        System.out.println(map);
//        System.out.println("------------");

/*//        遍历操作1：
//        获取所有键的集合，使用keySet方法实现
        Set<String> keyset = map.keySet();
//        遍历键的集合，获取每一个键，用增强for实现
        for(String s: keyset){
//            根据键去找值，使用get方法实现
            String value = map.get(s);
            System.out.println(s+","+value);
        }*/

//        遍历操作2：
//        获取所有键值对对象的集合，使用**Set<Map.Entry<K,V>> entrySet()**  **（获取所有键值对对象的集合）**方法实现
        Set<Map.Entry<String,String>> mapEntry = map.entrySet();
//        遍历键值对对象的集合，获取每一个键值对对象，用增强for实现
        for(Map.Entry<String,String> s :mapEntry){
//            根据键值对对象去找键和值，使用getKey方法和getValue方法实现
            String key = s.getKey();
            String value = s.getValue();
            System.out.println(key+","+value);
        }
    }
}
```

#### 13.5.5集合案例

1.分别以Student为键，String为值和Student为值，String为键创建HashMap集合，并遍历

```java
//学生类
public class Student {
    private String name;
    private int age;
    public Student() {
    }
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;

        Student student = (Student) o;

        if (age != student.age) return false;
        return name != null ? name.equals(student.name) : student.name == null;
    }
    @Override
    public int hashCode() {
        int result = name != null ? name.hashCode() : 0;
        result = 31 * result + age;
        return result;
    }
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
//学生测试类
public class StudentMapDemo {
    public static void main(String[] args) {
//        创建map集合对象
//        Map<String,Student> m = new HashMap<String,Student>();
        Map<Student,String> m = new HashMap<Student,String>();
//        创建学生对象
        Student s1 = new Student("杨过",32);
        Student s2 = new Student("郭靖",29);
        Student s3 = new Student("黄蓉",25);
        Student s4 = new Student("郭靖",29);
//        键为String值为Student对象
      /*  m.put("2004241001",s1);
        m.put("2004241002",s2);
        m.put("2004241003",s3);*/
//        键为Student值为String
        m.put(s1,"湖北");
        m.put(s2,"北京");
        m.put(s3,"上海");
        m.put(s4,"上海");//s4和s2的键是一样的，于是将s2的put方法覆盖了
//       遍历方法一
        /*Set<Map.Entry<String,Student>> entrymap = m.entrySet();
        for(Map.Entry<String,Student> s:entrymap){
            String key = s.getKey();
            Student value = s.getValue();
            System.out.println(key+","+value);
        }*/
        Set<Map.Entry<Student,String>> netrySet = m.entrySet();
        for(Map.Entry<Student,String> s:netrySet){
            Student key = s.getKey();
            String value = s.getValue();
            System.out.println(key+","+value);
        }
        System.out.println("-----------------------");
//       遍历方法二
        /*Set<String> set = m.keySet();
        for(String s:set){
            Student value = m.get(s);
            System.out.println(s+","+value);
        }*/
    }
}
```

HashMap底层为哈希表，需要重写学生类的equals和hashCode方法，保证键的唯一性：**学生对象的成员变量值相同就认为是同一个对象**

2.集合嵌套案例

需求1：创建一个ArrayList集合，存储三个元素，每个元素都是HashMap，每一个HashMap的键和值都是String，并遍历

```java
//集合嵌套：创建一个ArrayList集合，存储三个元素，每个元素都是HashMap，每一个HashMap的键和值都是String，并遍历
public class ArrayListIncludeHashMapDemo {
    public static void main(String[] args) {
//        创建ArrayList集合对象
        ArrayList<HashMap<String,String>> array = new ArrayList<HashMap<String,String>>();
//        创建HashMap对象
        HashMap<String,String> map1 = new HashMap<String,String>();
        HashMap<String,String> map2 = new HashMap<String,String>();
        HashMap<String,String> map3 = new HashMap<String,String>();
//        在三个hashmap中存入数据
        map1.put("郭靖","黄蓉");
        map1.put("杨过","小龙女");
        map1.put("萧峰","阿朱");
        map2.put("段誉","王语嫣");
        map2.put("杨康","穆念慈");
        map3.put("张无忌","赵敏");
        map3.put("段正淳","白刀凤");
//        将HashMap存入ArrayList集合里面
        array.add(map1);
        array.add(map2);
        array.add(map3);
//        增强for遍历
        for(HashMap<String,String> map :array){
            Set<Map.Entry<String,String>> set = map.entrySet();
            for(Map.Entry<String,String> me:set){
                String key = me.getKey();
                String value = me.getValue();
                System.out.println(key+","+value);
            }
        }
    }
}
```

需求2:创建一个HashMap集合，存储三个元素，每个元素HashMap的键是String，值为ArrayList，ArrayList存储string，并遍历

```java
//创建一个HashMap集合，存储三个元素，每个元素HashMap的键是String，值为ArrayList，ArrayList存储string，并遍历
public class HashMapIncludeArrayListDemo {
    public static void main(String[] args) {
//        创建HashMap对象
        HashMap<String,ArrayList<String>> map = new HashMap<String,ArrayList<String>>();
//        创建ArrayList集合3对象
        ArrayList<String> array1 = new ArrayList<String>();
        ArrayList<String> array2 = new ArrayList<String>();
        ArrayList<String> array3 = new ArrayList<String>();
//        在三个ArrayList中存入数据
        array1.add("令狐冲");
        array1.add("林平之");
        array2.add("岳灵珊");
        array2.add("东方不败");
        array3.add("任盈盈");
        array3.add("任我行");
//        将ArrayList存入HashMap集合里面
        map.put("情敌",array1);
        map.put("配角",array2);
        map.put("父女",array3);
//        遍历
        Set<Map.Entry<String, ArrayList<String>>> entryMaap = map.entrySet();
        for(Map.Entry<String, ArrayList<String>> me :entryMaap){
            String key = me.getKey();
            ArrayList<String> value = me.getValue();
            for(String s:value){
                System.out.println(key+","+s);
            }
        }
    }
}
```

需求3：统计字符串中每个字符出现的次数

例如：键盘录入：“aaabbbcccddd”			在控制台输出：“a(3)b(3)c(3)d(3)”

分析：

1. 我们可以把结果分为几个部分来看a(3),b(3)……

2. 每个部分可以看成：字符和字符对应的次数组成

3. 这样的数据我们可以通过HashMap集合来进行存储，健是字符，值是字符出现的次数

   注意：健是字符，类型应该是Character；值是字符出现次数，类型应该是Integer

```java
public class HashMapDemo05 {
    public static void main(String[] args) {
//        从键盘录入一个字符串
        Scanner sc = new Scanner(System.in);
        System.out.println("输入一个字符串：");
        String s = sc.nextLine();
//        创建HashMap集合对象，HashMap没有对键进行排序功能，所以可以使用TreeMap
//        Map<Character,Integer> map = new HashMap<Character,Integer>();
         Map<Character,Integer> map = new TreeMap<Character,Integer>();
//        字符串遍历得到每一个字符
        for (int i = 0; i < s.length(); i++) {
            char key = s.charAt(i);
//            拿得到的每一个字符作为键到hashMap集合中去找对应的值，看其返回值
            Integer value = map.get(key);
            if(value == null){
//                若果返回值是null，说明该字符不存在，就把该字符作为键，1为存储值
                map.put(key,1);
            }else{
//                若果返回值不是null，说明该字符存在，把存储值value++
                value++;
                map.put(key,value);
            }
        }
//          对集合进行遍历，并按要求对字符串进行拼接操作
        StringBuilder sb = new StringBuilder();
        Set<Map.Entry<Character, Integer>> entrySet = map.entrySet();
        for(Map.Entry<Character, Integer> me :entrySet){
            Character key = me.getKey();
            Integer value = me.getValue();
            sb.append(key).append("(").append(value).append(")");
        }
        String s1 = sb.toString();
        System.out.println(s1);
    }
}

```

### 13.6 Collections概述和使用

Collections类的概述

- **是针对集合的工具类**

Collections类的常用方法

|                            方法名                            |                说明                |
| :----------------------------------------------------------: | :--------------------------------: |
| public static<T extends Comparable<? super T>> void sort(List<T> list) | 将指定的列表按升序排列（自然排序） |
|           public static void reverse(List<?> list)           |      反转指定列表中元素的顺序      |
|           pubic static void shuffle(List<?> list)            |  使用默认的随机源随机排列指定列表  |
| public static<T> void sort(List<T> list，Comparable<? super T>  c) |      按指定规则对列表进行排列      |

需求1：ArrayList集合存储学生对象，使用Collections对ArrayList集合进行排序

```java
//ArrayList集合存储学生对象，使用Collections对ArrayList集合进行排序
public class CollectionsDemo02 {
    public static void main(String[] args) {
        ArrayList<Student> array = new ArrayList<Student>();
        Student s1 =new Student("zhangsan",19);
        Student s2 =new Student("lisi",18);
        Student s3 =new Student("wangwu",20);
        Student s4 =new Student("liuwu",18);
        array.add(s1);
        array.add(s2);
        array.add(s3);
        array.add(s4);
//         自然排序需要在Student类中实现Comparable接口
//        Collections.sort(array);
//        sort(List<T> list, Comparator<? super T> c) 根据指定的比较器引起的顺序对指定的列表进行排序
//        自定义排序
        Collections.sort(array, new Comparator<Student>() {
            @Override
            public int compare(Student s1, Student s2) {
                int num1 = s1.getAge() - s2.getAge();
                int num2 = num1 == 0? s1.getName().compareTo(s2.getName()):num1;
                return num2;
            }
        });
        for(Student s:array){
            System.out.println(s);
        }
    }
}
```

需求2：通过程序实现斗地主过程中的洗牌发牌和看牌

```java
//模拟发牌洗牌看牌过程
public class PokerDemo {
    public static void main(String[] args) {
//        创建一个牌盒
        ArrayList<String> array = new ArrayList<String>();
//        向牌盒中添加牌
//        定义花色数组
        String[] colors = {"♠", "♣", "♦", "♥"};
//        定义点数数组
        String[] number = {"2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A"};
//        嵌套循环存储进集合中
        for (String color : colors) {
            for (String num : number) {
                StringBuilder sb = new StringBuilder();
                sb.append(color).append(num);
                String s = sb.toString();
                array.add(s);
            }
        }
        array.add("小王");
        array.add("大王");
//        洗牌
        Collections.shuffle(array);
//        发牌给三个玩家
        ArrayList<String> arr1 = new ArrayList<String>();
        ArrayList<String> arr2 = new ArrayList<String>();
        ArrayList<String> arr3 = new ArrayList<String>();
        ArrayList<String> button = new ArrayList<String>();

        for (int i = 0; i< array.size();i++) {
            if (i < array.size()-3){
                if(i%3 == 0){
                    arr1.add(array.get(i));
                }
                if(i%3 == 1){
                    arr2.add(array.get(i));
                }
                if(i%3 == 2){
                    arr3.add(array.get(i));
                }
            }else{
                button.add(array.get(i));
            }
        }
//        看牌
        show(arr1);
        show(arr2);
        show(arr3);
        show(button);
    }
//    看牌方法
    public static void show(ArrayList<String> arr){
        for (String s:arr
             ) {
            System.out.print(s+"\t");
        }
        System.out.println();
    }
}
```

需求3：对需求2中的案例进行排序

```java
public class PokerPlusDemo {
    public static void main(String[] args) {
        HashMap<Integer, String> hmap = new HashMap<>();
//        向牌盒中添加牌
//        定义index数组
        ArrayList<Integer> arr = new ArrayList<Integer>();
//        定义花色数组
        String[] colors = {"♠", "♥", "♣", "♦"};
//        定义点数数组
        String[] number = {"3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A", "2"};
//        嵌套循环存储进集合中
        int index = 0;
        for (String num :number) {
            for (String color : colors) {
                StringBuilder sb = new StringBuilder();
                sb.append(color).append(num);
                String s = sb.toString();
                arr.add(index);
                hmap.put(index, s);
                index++;
            }
        }
        arr.add(index);
        hmap.put(index++, "小王");
        arr.add(index);
        hmap.put(index, "大王");
//        将索引洗牌
        Collections.shuffle(arr);
//        发牌
        TreeSet<Integer> set1 = new TreeSet<Integer>();
        TreeSet<Integer> set2 = new TreeSet<Integer>();
        TreeSet<Integer> set3 = new TreeSet<Integer>();
        TreeSet<Integer> button = new TreeSet<Integer>();
        for (int i = 0; i< arr.size();i++) {
            if (i < arr.size()-3){
                if(i%3 == 0){
                    set1.add(arr.get(i));
                }
                if(i%3 == 1){
                    set2.add(arr.get(i));
                }
                if(i%3 == 2){
                    set3.add(arr.get(i));
                }
            }else{
                button.add(arr.get(i));
            }
        }
        show(hmap,set1);
        show(hmap,set2);
        show(hmap,set3);
        show(hmap,button);
    }
    //看牌方法
    public static void show(HashMap<Integer, String> map,TreeSet<Integer> set){
        for (Integer me:set){
            String value = map.get(me);
            System.out.print(value+"\t");
        }
        System.out.println();
    }
}
```

## 14 IO流

### 14.1File类

#### File类概述

**File：它是文件和目录路径名的抽象表示**

- 文件和目录是可以通过File封装成对象的
- 对于File来说，其封装的并不是一个真正存在的文件，仅仅是一个路径名而已。他是可以存在的，也可以是不存在的。将来要通过具体的操作把这个路径的内容转换为具体存在的

**构造方法**

|                方法名                 |                           说明                           |
| :-----------------------------------: | :------------------------------------------------------: |
|       **File(String pathname)**       | 通过将给定的路径字符串转换为抽象路径名来创建新的File实例 |
| **File(String  parent,String child)** |       从父路径名字符串和子路径名字符串创建File实例       |
|    File(File parent,String child)     |      从父抽象路径名和子路径名字符串创建新的File实例      |

**注意：构造方法抽象化路径名来构造File实例，并没有要求路径名是否正确/存在**

**File类的创建功能**

|            方法名             |                             说明                             |
| :---------------------------: | :----------------------------------------------------------: |
| public boolean creatNewFile() | 当具有该名称的文件不存在时，创建一个由该抽象路径名命名的新的空文件 |
|    public boolean mkdir()     |                创建由此该抽象路径名命名的目录                |
|    public boolean mkdirs()    | 创建由此该抽象路径名命名的目录，巴奥括任何必须但不存在的父目录 |

**FIle类判断和获取功能**

|              方法名              |                            说明                            |
| :------------------------------: | :--------------------------------------------------------: |
| **public boolean isDirectory()** |            测试此抽象路径名表示的File是否为目录            |
|     public boolean isFile()      |            测试此抽象路径名表示的File是否为文件            |
|   **public boolean exists()**    |             测试此抽象路径名表示的File是否存在             |
| public String getAbsolutePath()  |           返回此抽象路径名的**绝对路径名**字符串           |
|     public String getPath()      |              将此抽象路径名转换为路径名字符串              |
|   **public String getName()**    |          返回由此抽象路径名表示的文件/目录的名称           |
|      public String[] list()      | 返回由此抽象路径名表示的目录中的文件和目录的名称字符串数组 |
|   **public File[] listFile()**   |  返回此抽象路径名表示的目录中的文件和目录的File[]对象数组  |

**File类的删除功能**

- **public boolean delete()**		删除此抽象路径名表示的文件或者目录

**注意：删除时目录下有内容（目录或文件），不能直接删除，应该先删除掉目录的内容，最后才能删除掉目录**



**绝对路径**：*完整的路径名*，不需要任何其他信息就可以定位他所表示的文件，例如：E:\\JavaDate\\test01\\java.txt

**相对路径**：必须使用取自其他路径名信息进行解释，例如：src\\\passage10\\java.txt



### 14.2递归

**递归概述**：已编程的角度看，递归是指**方法定义中调用方法本身**的现象

**递归解决问题思路**

把一个复杂问题层层转化为一个与**原问题相似的规模较小**的问题来求解

递归测略只需**少量的程序**就可以描述出解决问题过程所需的多次重复计算

```java
public class DiGuiDemo {
    public static void main(String[] args) {
        /*不死神兔
        每个月兔子对数：1，1，2，3，5，8，13……
        */
        System.out.println(f(20));
    }
    /*递归解决问题：先定义一个方法
        定义一个方法f(n),表示第n个月兔子个数
        那么第n-1个月为，f(n-1)
        第n-2个月为，f(n-2)
     */
//StackOverflowError:递归太深报错，没有出口
    public  static int f(int n){
        if(n ==1||n==2) {
            return 1;
        }else {
            return f(n - 1) + f(n - 2);
        }
    }
}
```

**递归解决问题要找到的两个内容**

- 递归出口：否则会出现内存溢出
- 递归规则：与原问题相似的规模较小的问题

**案例:遍历目录**

需求：给定一个路径，请通过递归完成遍历该目录下所有的内容，并把所有文件的绝地路径输出在控制台

```java
//需求：给定一个路径，请通过递归完成遍历该目录下所有的内容，并把所有u文件的绝地路径输出在控制台
public class FileDiGuiDemo {
    public static void main(String[] args) {
//        定义一个路径对象
        File file = new File("src\\hello.java");
        FileBianLi(file);

    }
    public static void FileBianLi(File file){
        if(file.isDirectory()){
            File[] files = file.listFiles();
            if(files != null){
                for(File f :files){
                    FileBianLi(f);
                }
            }
        }else{
            System.out.println(file.getAbsolutePath());
        }
    }
}
```

### 14.3字节流

**IO流概述和分类**

IO概述

- IO：输入/输出（Input/Output）

- 流：是一种抽象概念，是对数据传输的总称。也即是说数据在设备间的传输称为流，流的本质是数据传输

- IO流就是用来处理设备间数据传输问题的

  ​	常用的应用：文件复制，文件上传，文件下载

IO流分类

- 按照数据流向
  - 输入流：读取数据
  - 输出流：写入数据

- 按照数据类型分类
  - 字节流：字节输入流，字节输出流
  - 字符流：字符输入流，字符输出流

一般来说，我们说IO流的分类是按照**数据类型**来分的

**什么情况使用什么流呢？**

- 如果数据通过Windows自带的记事本软件打开，我们可以读懂里面的内容，就使用字符流，否则使用字节流
- 如果实在不知道该用哪种类型的流，就使用字节流（万能流）

### 14.4字节流写数据

**字节流抽象基类**

- **InputStream**：这个抽象类表示字节输入流所有的超类
- **OutputStream**：这个抽象类表示字节输出流所有的超类
- 子类特点：子类名称都是以其父类名作为子类名后缀



**FileOutputStream：文件输出流用于将数据写入File**

- FileOutputStream（String name）：创建文件输出流以指定的名称写入文件
- FileOutputStream（File file）：创建文件输出流以指定File对象写入文件



**使用字节输出流写数据的步骤**

1. 创建字节输出流对象（**调用系统功能创建文件，创建字节输出流对象，将字节输出流对象指向目标文件**）
2. 调用字节输出流对象的写数据方法
3. 释放资源（**关闭此文件输出流并释放与此相关联的任何系统资源**）



**字节输出流写数据的三种方式**

|                方法名                |                             说明                             |
| :----------------------------------: | :----------------------------------------------------------: |
|          void write(int b)           |       将指定的字节写入此文件输出流，一次写一个字节数据       |
|         void write(byte[] b)         | 将b.length字节从指定的字节数组写入此文件输出流，一次写一个字节数组数据 |
| void write(byte[] b,int off,int len) | 将len字节从指定的字节数组开始，从偏移量off开始写入此文件输出流，一次写一个字节数组的部分数据 |

**String类中方法 byte[] getBytes()返回字符串的字节数组**



**字节流写数据的两个小问题**

- 字节流如何实现换行？

  - 不同操作系统识别换行符不同：
    - Windows：/r/n
    - linuux:/n
    - mac:/r

- 字节流如何实现追加写入数据？

  - **public FileOutputStream(String name,boolean append)**

    创建文件输出流以指定的名称写入文件。 如果第二个参数为true ，则字节将写入文件的末尾而不是开头



### 14.5字节流写数据加异常处理

**finally**：在异常处理时提供finally块来执行所有清除操作，比如说：IO流在的释放资源

**特点：被finally控制的语句一定会执行，除非JVM退出**

```
try{
	可能出现异常的代码
}catch(异常类名 变量名){
	异常处理代码
}finally{
	执行所有清除操作
}
```

```java
public class FileOutputStreamDemo03 {
    public static void main(String[] args) {
        FileOutputStream fos = null;
        try {
//            FileNotFoundException文件路径不存在
//            fos = new FileOutputStream("V:\\src\\javademo\\passage14\\test03\\fos.txt");
            fos = new FileOutputStream("src\\javademo\\passage14\\test03\\fos.txt");
            fos.write("hello".getBytes());
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            if(fos != null) {
                try {
//                NullPointerException空指针异常，需要进行if判断
                    fos.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }

    }
}
```



### 14.6字节流读数据

**FileInputStream**：字节输入流，从文件系统中的文件获取输入字节

**构造方法**

- FileInputStream(String name)：通过打开与实际文件的链接来创建一个FileInputStream，该文件由文件系统中的路径名name命名
- FileInputStream(File file)：通过打开与实际文件的链接来创建一个FileInputStream，该文件由文件系统中的路径名的File对象命名



**使用字节流读数据的步骤**

1. 创建字节输入流对象（**调用系统功能创建文件，创建字节输入流对象，将字节输入流对象指向目标文件**）
2. 调用字节输入流对象的读取数据方法
3. 释放资源（**关闭此文件输入流并释放与此相关联的任何系统资源**）

**字节流读取数据的三种方法**

|               方法名               |                            说明                             |
| :--------------------------------: | :---------------------------------------------------------: |
|             int read()             |                从该输入流读取一个字节的数据                 |
|         int read(byte[] b)         |    从该输入流读取最多 b.length个字节的数据到一个字节数组    |
| int read(byte[] b,int off,int len) | 从偏移量off开始从该输入流读取最多 len个字节的数据到字节数组 |

案例：复制文本文件

需求：把"E:\\JavaDate\\test\\小说文本.txt"复制到模块目录下"小说文本.txt"

```java
public class FileInputStreamDemo02 {
    public static void main(String[] args) throws IOException {
//        创建字节输入流对象
        FileInputStream fis = new FileInputStream("E:\\JavaDate\\test\\小说文本.txt");
//        创建输出流对象
        FileOutputStream fos = new FileOutputStream("src\\javademo\\passage14\\test04\\小说文本.txt");

//        将数据源的内容读取出来,并写入文件
        int  by;
        while ((by = fis.read()) != -1){
//            fos = new FileOutputStream("src\\javademo\\passage14\\test04\\小说文本.txt",true);
            fos.write(by);
        }
//        释放资源
        fis.close();
        fos.close();
    }
}
```

需求：将fis.txt的内容读取出来在控制台输出

```java
public class FileInputStreamDemo02 {
    public static void main(String[] args) throws IOException {
        FileInputStream fis = new FileInputStream("E:\\JavaDate\\test\\fis.txt");
        //int read(byte[] b)从该输入流读取最多 b.length个字节的数据到一个字节数组
        
        //将数据读取到字节数组中
        byte[] bys = new byte[1024];//取1024或其整倍数
        int len;//len输出的是读取的字节长度
        
        while((len = fis.read(bys)) ！= -1){
            System.out.println(new String(bys));
        }
    }
}
```



案例：复制照片

需求：把"E:\\JavaDate\\test\\11.jpg"复制到模块目录下的“11.jpg”

```java
public class FileInputstreamDemo04 {
    public static void main(String[] args) throws IOException {
        FileInputStream fis = new FileInputStream("E:\\JavaDate\\test\\11.jpg");
        FileOutputStream fos = new FileOutputStream("src\\javademo\\passage14\\test04\\11.jpg");

        byte[] bys = new byte[1024];
        int len;
        while((len= fis.read(bys))!=-1){
            fos.write(bys,0,len);
        }

        fis.close();
        fos.close();
    }
}
```

### 14.7字节缓冲流

**字节缓冲流**

- BufferedOutputStream：该类实现缓冲输出流，通过设置这样的输出流，应用程序可以向底层输出流写入字节，不必为写入的每个字节导致底层系统调用
- BufferedInputStream：创建BufferedInputStream将创建一个内部缓冲区数组，当从流中读取或者跳过字节时，内部缓冲区将根据所需要从所包含的输入流中重新填充，一次很多字节

**构造方法**

- 字节缓冲输出流：BufferedOutputStream（OutputStream out）
- 字节缓存输入流：BufferedInputStream（Inputstream in）

**为什么构造方法需要的是字节流，而不是具体的文件或者路径呢？**

- 字节缓冲流**仅仅提供缓冲区**，而真正的读写数据还得依靠基本的字节流对象进行操作x

需求：把“E:\\JavaDate\\test\\11.mp4”复制到模块目录下得的“11.mp4”

```java
public class BufferStreamDemo02 {
    public static void main(String[] args) throws IOException {
        //    记录开始时间
        long startTime = System.currentTimeMillis();
        //    复制视频
//        创建字节流对象
        FileOutputStream fos = new FileOutputStream("src\\javademo\\passage14\\test04\\11.mp4");
        FileInputStream fis = new FileInputStream("E:\\JavaDate\\test\\11.mp4");
//        创建字节缓冲流对象
        BufferedOutputStream bfos = new BufferedOutputStream(fos);
        BufferedInputStream bfis = new BufferedInputStream(fis);

        //        1.基本字节流一次读写一个字节
//        method1(fos,fis);//程序运行时间为：5668
        //      2.基本字节流一次读写一个数组数据
//        method02(fos,fis);//程序运行时间为：11
        //       3.字节缓存流一次读写一个字节
//        method03(bfos,bfis);//程序运行时间为：50
        //      4.字节缓冲流一次读写一个数组数据
        method04(bfos,bfis);//程序运行时间为：9

        //    记录结束时间
        long endTime = System.currentTimeMillis();
        System.out.println("程序运行时间为："+(endTime-startTime));

//      释放
        fis.close();
        fos.close();
    }
//        1.基本字节流一次读写一个字节
    public static void method1(FileOutputStream fos,FileInputStream fis) throws IOException {
        int by;
        while ((by = fis.read())!= -1){
            fos.write(by);
        }
    }
//      2.基本字节流一次读写一个数组数据
    public static void method02(FileOutputStream fos,FileInputStream fis) throws IOException{
        byte[] bys = new byte[1024];
        int len;
        while ((len = fis.read(bys))!= -1){
            fos.write(bys,0,len);
        }
    }
//    3.字节缓存流一次读写一个字节
    public static void method03(BufferedOutputStream bfos,BufferedInputStream bfis) throws IOException{
        int by;
        while ((by = bfis.read())!= -1){
            bfos.write(by);
        }
    }
//      4.字节缓冲流一次读写一个数组数据
    public static void method04(BufferedOutputStream bfos,BufferedInputStream bfis) throws IOException{
        byte[] bys = new byte[1024];
        int len;
        while ((len = bfis.read(bys))!= -1){
            bfos.write(bys,0,len);
        }
    }
}

```



### 14.8字符流

**为什么会出现字符流？**

由于字节流操作中文不是特别方便，所以Java就提供了字符流

- **字符流 = 字节流 + 编码表**
- 一个汉字存储
  *           如果是GBK编码占用2个字节
  *           如果是UTF-8编码占用3个字节

字节流复制中文文本时，文件也含有中文但是却没有出错，**原因是最终底层操作时会自动进行字节拼接成中文**，但是如何识别中文的呢？

- 汉字在存储的时候，无论选择哪一种编码存储，第一个字节都是负数

```java
public class FileInputStreamDemo {
    public static void main(String[] args) throws IOException {
//        FileInputStream fis = new FileInputStream("src\\javademo\\passage14\\test05\\fis.txt");
//         每个字节输出有中文乱码
        /*int by;
        while ((by = fis.read())!=-1){
            System.out.print((char) by);
        }
        fis.close();*/
//        String s = "abc";//[97, 98, 99]
        String s = "中国";
//        byte[] bys = s.getBytes();//[-28, -72, -83, -27, -101, -67]默认UTF-8编码
//        可以强制转换为GBK编码输出：[-42, -48, -71, -6]
        byte[] bys = s.getBytes("GBK");
        System.out.println(Arrays.toString(bys));

    }
}
```

### 14.9编码表

**基础知识：**

- 计算机中存储的信息都是用**二进制数**表示的；我们在屏幕上看到的英文，汉字等字符是二进制数转换之后得到结构

- 按照某种规则，将字符存储到计算机中，称为**编码**。反之，将存储在计算机中的二进制数按照按某种规则解析出来，称为**解码**。这里强调一下，按照A编码存储，必须按照A编码解析，这样才能显示正确的文本符号，否则导致乱码现象

  字符编码：就是一套自然语言得到字符与二进制数之间的对应规则（A，65）

**字符集**

- 是一个系统支持得到所有字符的集合，包括各国家文字，标点符号，图像符号，数字等

- 计算机要准确的存储和识别各种字符集符号，就需要进行字符编码，一套字符集必然至少有一套字符编码

  常见的字符集有ASCII（美国信息交换标准代码）字符集，GBXXX字符集，Unicode字符集等

**ASCII字符集：**

- ASCII（美国信息交换标准代码）是基于拉丁字母的一套的电脑编码系统，用于显示现代英语，主要包括控制字符（回车键，空格换行符等）和可显示字符（英文大小写，阿拉伯数字和西文符号）
- 基本ASCII字符集，使用7位表示一个字符，一共128字符。ASCII的拓展字符集使用8位表示一个字符，共256字符，方便支持欧洲常用字符，是一个系统支持的所有字符的集合，包括各种国家文字，标点符号，图形符号，数字等

**GBXXX字符集**：

- GB2312：简体中文码表。一个小于127的字符意义与原来相同，但两个大于127的字符连在一起时，就表示一个汉字，这样大约可以组合包含7000多个简体汉字，此外数学符号，罗马希腊字符，日文的假名等都编进去了，连在ASCII里面本来就有的数字，标点，字母都统统重新编了两个字节长的编码，这就是常说的“全角”字符，而原来在127号以下的那些就叫做“半角”字符了
- **GBK**：最常用的中文码表。是在GB2312标基础上的扩展规范，使用了双字节编码方案，共收录了21003个汉字，完全兼容GB2312标准，同时支持繁体汉字以及日韩汉字等
- GB18030：最新的中文码表。收录汉字70244个，采用多字节编码，每个字可以由1个，2个，或者4个字节组成。支持中国国内少数民族的文字，同时支持繁体汉字以及日韩汉字等

**Unicode字符集：**

- 为表达任意语言的任意字符而设计，是业界的一种标准，也称为统一码表，标准万国码。他最多使用4个字节的数组来表达每一个字母，符号或者文字。有三种编码方案，UTF-8，UTF-16和UTF-32，最为常用的是UTF-8编码

- **UTF-8编码**：可以用来表示Unicode标准中任意字符，它是电子邮件，网页及其他存储或者传送文字的应用中优先采用的编码。互联网工程工作小组（IETF）要求所有互联网协议都必须支持UTF-8编码，它使用一到四个字节为每个字符编码

  **编码规则：**

  ​	128个US-ASCII字符，只需要一个字节编码

  ​	拉丁文等字符，需要两个字节编码

  ​	大部分常用字（含中文），使用三个字节编码

  ​	其他极少使用的Unicode辅助字符，使用四个字节编码

**小结：采用何种规则编码，就要采用对应规则进行解码，否则出现乱码**

### 14.10字符串中的编码解码问题

编码：

- **byte[] getBytes()**：使用平台的默认字符集将该String编码为一系列字节，将结果存储到新的字节数组中
- **byte[] getBytes(String charsetName)**：使用指定的字符集将该String编码为一系列字节，将结果存储到新的字节数组中

解码：

- **String(byte[] bytes)**：通过平台的默认字符集解码指定的字节数组来构造新的String
- **String(byte[] bytes，String charsetName)**：通过指定的字符集解码指定的字节数组来构造新的String

### 14.11字符流中的编码和解码问题

字符流抽象基类

- Reader:字符输入流的抽象类
- Writer:字符输出流的抽象类

字符流中和编码解码问题相关的两个类：

- InputStreamReader
- OutputStreamWriter

#### 14.11.1字符流写数据的五种方法

|                 方法名                  |                      说明                      |
| :-------------------------------------: | :--------------------------------------------: |
|            void write(int c)            |                  写入一个字符                  |
|         void write(char[] cbuf)         |                写入一个字符数组                |
| void write(char[] cbuf,int off,int len) | 写入一个字符数组的一部分，off起始位置，len长度 |
|          void write(String s)           |                 写入一个字符串                 |
| void write(String str,int off,int len)  |  写入一个字符串的一部分，off起始位置，len长度  |

**注意：写入的数据并不会直接写入到文件中，先会再缓冲区存储，需要刷新**

- flush():刷新流
- close():关闭流，先刷新

#### 14.11.2字符流读取数据的两种方法

|       方法名        |           说明           |
| :-----------------: | :----------------------: |
|     int read()      |   一次读取一个字符数据   |
| int read(char cbuf) | 一次读取一个字符数组数据 |

案例：字符流复制Java文件

需求：把模块目录下的”src\\javademo\\passage14\\test05\\InputStreamReaderDemo.java“文件复制到文件”E:\\JavaDate\\test\\copy.txt“中

```java
//需求：把模块目录下的”src\\javademo\\passage14\\test05\\InputStreamReaderDemo.java“文件复制到文件”E:\\JavaDate\\test\\copy.txt“中
public class ConversionStreamCopyFileDemo {
    public static void main(String[] args) throws IOException {
//        创建字符流对象
        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("E:\\JavaDate\\test\\copy.txt"));
        InputStreamReader isr = new InputStreamReader(new FileInputStream("src\\javademo\\passage14\\test05\\InputStreamReaderDemo.java"));
//        读取文件内容
        int ch;
        while ((ch = isr.read()) != -1) {
            System.out.print((char) ch);
            osw.write(ch);
            osw.flush();
        }
        osw.close();
        isr.close();
    }
}

```

#### 14.11.3InputStreamReader，OutputStreamWriter的便捷子类

- FileReader:用于读取字符文件的便捷类
  - FileReader（String fileName）
- FileWriter:用于写入字符文件的便捷类
  - FileWriter（String fileName）

数据源和目的地的分析

​	数据源：文件路径---读数据---Reader---InputStreamReader---FileReader

​	目的地：文件路径---写入数据---Writer---OutputStreamWriter---FileWriter

### 14.12字符缓冲流

**字符缓冲流：**

- **BufferedWriter**：将文本写入字符输出流，缓冲字符，以提供单个字符，数组和字符串的高效写入，可以指定缓冲区大小，或者接受默认大小，默认值足够大，可用于大多数用途
  - BufferedWriter(Writer out)
- **BufferedReader**：将字符输入流读取文本，缓冲字符，以提供字符，数组和行的高效读取，可以指定缓冲区大小，或者可以使用默认值大小，默认值足够大，可用于大多数用途
  - BufferedReader(Reader in)

需求：对前面案例copy文件进行改进

```java
//对前面案例进行改进，copy文件
public class BufferedStreamCopyDemo {
    public static void main(String[] args) throws IOException {
//        创建字符缓冲流对象
        BufferedReader br = new BufferedReader(new FileReader("src\\javademo\\passage14\\test05\\BufferedStreamCopyDemo.java"));
        BufferedWriter bw = new BufferedWriter(new FileWriter("E:\\JavaDate\\test\\copy.txt"));

//        读取数据，写入数据
        int len;
        char[] cbuf = new char[1024];
        while ((len = br.read(cbuf))!=-1){
            bw.write(cbuf,0,len);
        }
//        释放资源
        br.close();
        bw.close();
    }
}
```

#### 字符缓冲流的特有功能

BufferedWriter

- void newLine()：写一行行分隔符，行分隔符字符串由系统定义

BufferedReader

- void String readLine()：读一行文字。结果包含行的内容的字符串，不包括任何终止字符，如果流的结尾已经到达，则返回null

需求：使用字符缓冲流特有功能对前面案例copy文件进行改进

```java
//使用字符缓冲流特有方法改进copy代码
public class BufferedStreamCopyDemo02 {
    public static void main(String[] args) throws IOException {
        //        创建字符缓冲流对象
        BufferedReader br = new BufferedReader(new FileReader("src\\javademo\\passage14\\test05\\BufferedStreamCopyDemo02.java"));
        BufferedWriter bw = new BufferedWriter(new FileWriter("E:\\JavaDate\\test\\copy.txt"));

//        读取数据，写入数据
        String line;
        while ((line = br.readLine()) != null) {
            bw.write(line);
            bw.newLine();
            bw.flush();
        }
//        释放资源
        br.close();
        bw.close();
    }
}
```

### 14.13 IO流小结

![](C:\Users\Asinil\Desktop\学习\Java\14.13.png)

![](C:\Users\Asinil\Desktop\学习\Java\14.13_2.png)

#### 案例：集合与文件

需求：把ArrayList集合中的字符串数据写到文本文件中，要求：每一个字符串元素作为文件中的一行数据

```java
public class ArrayListToFileDemo {
    public static void main(String[] args) throws IOException {
//        创建集合对戏
        ArrayList<String> arrayList = new ArrayList<String>();
//        向集合中添加元素
        arrayList.add("hello");
        arrayList.add("world");
        arrayList.add("hello");
        arrayList.add("java");
        arrayList.add("hi");
//        创建字符缓冲输出流
        BufferedWriter bw = new BufferedWriter(new FileWriter("src/javademo/passage14/test05/test/copy.txt"));
//        循环遍历集合
        for(String s : arrayList){
            bw.write(s);
            bw.newLine();
            bw.flush();
        }
//      释放资源
        bw.close();
    }
}
```

需求：把File文件中数据存入到ArrayList集合中，要求：文件中的一行数据是一个集合元素

```java
//需求：把File文件中数据存入到ArrayList集合中，要求：文件中的一行数据是一个集合元素
public class FileToArrayListDemo {
    public static void main(String[] args) throws IOException {
//        创建集合对戏
        ArrayList<String> arrayList = new ArrayList<String>();
//        创建字符缓冲输入流
        BufferedReader br = new BufferedReader(new FileReader("src/javademo/passage14/test05/test/copy.txt"));
//        读取数据
        String line;
        while((line = br.readLine())!=null){
            arrayList.add(line);
        }
//        释放资源
        br.close();
//        输出集合
        for(String s : arrayList){
            System.out.println(s);
        }
    }
}
```

#### 案例：点名器

需求：我有一个文件里面存储了班级学生的姓名，每个姓名占一行，要求通过程序实现随机点名

思路：

1. 新建一个文件存储学生姓名，每行一个姓名
2. 创建HashMap集合将序号与学生姓名对应起来
3. Random随机生成序号进行点名

```java
public class DMStudentDemo {
    public static void main(String[] args) throws IOException {
//        创建字符缓冲输入流
        BufferedReader br = new BufferedReader(new FileReader("src/javademo/passage14/test05/test/students.txt"));
//        创建hashmap集合对象
        HashMap<Integer,String> map = new HashMap<Integer,String>();
//        将姓名与序号建立联系
        String line;
        int index = 0;
        while ((line = br.readLine())!=null){
            map.put(index,line);
            index++;
        }
//        释放资源
        br.close();
//        Random随机生成序号进行点名
        Random r= new Random();
        int num = r.nextInt(index);//在序号范围内进行点名
        String name = map.get(num);
        System.out.println(name);
    }
}
```

也可以使用ArrayList进行实现，利用索引进行随即数查询

#### 案例：从集合到文件（进阶版）

需求：把ArrayList集合中的学生数据写入到文本文件中。要求：每一个学生对象的数据作为文件中的一行数据

​	格式：学号，学生姓名，年龄，居住地		举例：20230901，林青霞，30，湖北

```java
//需求：把ArrayList集合中的学生数据写入到文本文件中。要求：每一个学生对象的数据作为文件中的一行数据
//	格式：学号，学生姓名，年龄，居住地		举例：20230901，林青霞，30，湖北
public class ArrayListToFileDemo02 {
    public static void main(String[] args) throws IOException {
//        创建ArrayList集合对象
        ArrayList<Student> arrayList = new ArrayList<Student>();
//        创建学生对象
        Student s1 = new Student(20230901,"林青霞",34,"湖北");
        Student s2 = new Student(20230902,"风清扬",56,"河南");
        Student s3 = new Student(20230903,"林正英",45,"广州");
        Student s4 = new Student(20230904,"张三丰",67,"湖北");
        Student s5 = new Student(20230905,"岳不群",30,"湖南");
//        将学生对象存入集合中
        arrayList.add(s1);
        arrayList.add(s2);
        arrayList.add(s3);
        arrayList.add(s4);
        arrayList.add(s5);
//        创建字符缓冲流
        BufferedWriter bw = new BufferedWriter(new FileWriter("src/javademo/passage14/test05/test/copy.txt"));
        for(Student s:arrayList){
            StringBuilder sb = new StringBuilder();
            sb.append(s.getId()).append(",").append(s.getName()).append(",").append(s.getAge()).append(",").append(s.getAdress());
            String stu = sb.toString();
            bw.write(stu);
            bw.newLine();
            bw.flush();
        }
//        释放资源
        bw.close();
    }
}
```

#### 案例：从文件到集合（改进版）

需求：把File文件中数据存入到ArrayList集合中，要求：文件中的一行数据是一个学生对象的成员变量的值

```java
//需求：把File文件中数据存入到ArrayList集合中，要求：文件中的一行数据是一个学生对象的成员变量的值
public class FileToArrayListDemo02 {
    public static void main(String[] args) throws IOException {
//        创建字符缓冲流
        BufferedReader br = new BufferedReader(new FileReader("src/javademo/passage14/test05/test/copy.txt"));
//        创建集合对象
        ArrayList<Student> arrayList = new ArrayList<Student>();
//        循环读取文件每行数据
        String line;
        while ((line = br.readLine()) != null) {
//            将数据通过，分割开来
            String[] stu = line.split(",");
            long id = Long.parseLong(stu[0]);
            int age = Integer.parseInt(stu[2]);
            Student s = new Student(id,stu[1],age,stu[3]);
            arrayList.add(s);
        }
//        释放资源
        br.close();

//        输出集合,并重写stu的tostring方法
        for(Student s :arrayList){
            System.out.println(s);
        }
    }
}
```

#### 案例：集合到文件（改进版plus）

需求：把ArrayList集合中的学生数据写入到文本文件中。要求：每一个学生对象的数据作为文件中的一行数据，并且要按照语数外成绩排序

```java
//需求：把集合中的学生数据写入到文本文件中。要求：每一个学生对象的数据作为文件中的一行数据，并且要按照语数外成绩总分排序
public class ArrayListToFileDemo03 {
    public static void main(String[] args) throws IOException {
//        创建集合对象
        TreeSet<Students> set = new TreeSet<Students>(new Comparator<Students>() {
//           自定义比较规则:
//            比较总成绩，然后依次比较语文数学英语成绩，然后比较名字
            @Override
            public int compare(Students s1, Students s2) {
                int num1 = s1.getSum() - s2.getSum();
                int num2 = num1 == 0?s1.getChinese()-s2.getChinese():num1;
                int num3 = num2 == 0?s1.getMath()-s2.getMath():num2;
                int num4 = num3 == 0?s1.getName().compareTo(s2.getName()):num3;
                return num4;
            }
        });
//        创建学生对象
        Students s1 = new Students("林青霞",91,94,86);
        Students s2 = new Students("胡歌",87,97,90);
        Students s3 = new Students("迪丽热巴",94,88,92);
        Students s4 = new Students("杨洋",90,90,90);
        Students s5 = new Students("江晨",90,90,90);
//        将学生对象添加到集合中
        set.add(s1);
        set.add(s2);
        set.add(s3);
        set.add(s4);
        set.add(s5);
//        创建字符缓冲流，循环遍历集合写入文件
        BufferedWriter bw = new BufferedWriter(new FileWriter("src/javademo/passage14/test05/test/copy.txt"));
        for(Students s:set){
            StringBuilder sb = new StringBuilder();
            sb.append(s.getName()).append(",").append(s.getChinese()).append(",").append(s.getMath()).append(",").append(s.getEnglish()).append(",").append(s.getSum());
            String str = sb.toString();
            bw.write(str);
            bw.newLine();
            bw.flush();
        }
//        释放资源
        bw.close();
    }
}
```

#### 案例：复制单级文件夹

需求：把“E:\\test”这个文件夹复制到模块目录下

​	思路：

- 创建数据源目录File对象，路径为“E:\\test”
- 获取数据源目录File对象的名称test
- 创建目的地目录File对象，路径名是模块名+test
- 判断目的地目录对应的File是否存在，如果不存在，就创建
- 获取数据源目录下的所有文件File数组
- 遍历File数组，得到每一个File对象，该File对象其实就是数据源文件
- 获取数据源文件File对象的名称
- 创建目的地文件File对象，路径名是目的目录+文件名组成
- 复制文件，使用字节流进行

```java
public class CopyFileDemo {
    public static void main(String[] args) throws IOException {
//        创建目的的文件的路径对象
        File file = new File("E:\\test");
//        获取数据源目录File对象的名称
        String fileName = file.getName();
//        创建目的地目录File对象，路径名是模块名+test
        File file1 =new File("src",fileName);

//        判断目的地目录对应的File是否存在，如果不存在，就创建
        if(!file1.exists()){
            file1.mkdir();
        }
//        获取目的地目录下的文件路径对象数组
        File[] files = file.listFiles();

//        遍历File数组，得到每一个File对象，该File对象其实就是数据源文件
        for(File f :files){
//            获取数据源文件File对象的名称
            String name = f.getName();
//            创建目的地文件File对象，路径名是目的目录+文件名组成
            File mfile = new File("src\\test",name);
//        复制文件，使用字节流进行
//        创建字节流对象
            FileInputStream is = new FileInputStream(f);
            BufferedInputStream bis = new BufferedInputStream(is);
            FileOutputStream os = new FileOutputStream(mfile);
            BufferedOutputStream bos = new BufferedOutputStream(os);
            int len;
            byte[] bys = new byte[1024];
            while ((len = bis.read(bys))!=-1){
                bos.write(bys,0,len);
                bos.flush();
            }
            is.close();
            os.close();
        }
    }
}
```

#### 案例：复制多级文件夹

需求：把“E:\\test”这个文件夹及下的目录与文件复制到模块目录下

思路：

1. 创建数据源File对象，路径为“E:\\test”
2. 创建目的地File对象，路径是“src”
3. 写方法实现文件夹的复制，参数为数据源File对象和目的地File对象
4. 判断数据源File对象是否为目录：
   - 是目录
     - 在目的地下创建和数据源File名称一样的目录
     - 获取数据源File下所有文件或者目录的File数组
     - 遍历该File数组得到每一个File对象
     - 把该File作为数据源对象进行递归调用
   - 不是目录则是文件
     - 直接复制，使用字节流

```java
public class CopyFileDemo02 {
    public static void main(String[] args) throws IOException {
//        创建目的地目录路径对象
//        1. 创建数据源File对象，路径为“E:\\test”
//        2. 创建目的地File对象，路径是“src”
        File srcFile = new File("E:\\test");
        File destFile = new File("src");
//        3. 写方法实现文件夹的复制，参数为数据源File对象和目的地File对象
        copyFile(srcFile,destFile);
    }
//    遍历文件递归方法
    public static void copyFile(File srcFile,File devFile) throws IOException {
        if(srcFile.isDirectory()){
            /* 是目录
     - 在目的地下创建和数据源File名称一样的目录
     - 获取数据源File下所有文件或者目录的File数组
     - 遍历该File数组得到每一个File对象
     - 把该File作为数据源对象进行递归调用*/
            String fileName = srcFile.getName();
            File devFile1 = new File(devFile,fileName);
            if(!devFile1.exists()){
                devFile1.mkdir();
            }
            File[] srcfiles = srcFile.listFiles();
            for(File f:srcfiles){
                copyFile(f,devFile1);
            }

        }else{
//            在目的地创建相同路径文件
            String fileName = srcFile.getName();
            File devFile2 = new File(devFile,fileName);
//            直接复制，使用字节流
            BufferedInputStream bis = new BufferedInputStream(new FileInputStream(srcFile));
            BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream(devFile2));
            byte[] bys = new byte[1024];
            int len;
            while ((len = bis.read(bys))!=-1){
                bos.write(bys,0,len);
                bos.flush();
            }
            bis.close();
            bos.close();
        }
    }
}
```

#### 复制文件的异常处理

try…catch…finally的做法

```java
try{
	可能出现异常的代码
}catch(异常类名 变量名){
	异常处理代码
}finally{
	执行所有清除操作
}
```

JDK7改进的异常处理方案

```java
try(定义流对象){
	可能出现异常的代码
}catch(异常类名 变量名){
	异常处理代码
}
//自动释放资源
```

JDK9改进的异常处理方案

```java
定义输出流对象
定义输入流对象
try(输入流对象:输出流对象){
	可能出现异常的代码
}catch(异常类名 变量名){
	异常处理代码
}
//自动释放资源
```



### 14.14 特殊操作流

#### 14.14.1标准输入输出流

System类中有两个静态的成员变量：

- **public static final InputStream in**:标准输入流，通常该流对应于键盘输入或由主机环境或用户指定的另一个输入源
- **public static final OutputStream out**:标准输出流，通常该流对应于显示输出或由主机环境或用户指定的另一个输出目标

我们可以自己实现键盘录入数据：

- BufferedReader br = new BufferedReader(new InputStreamReader (System.in));

写的太麻烦了，java就提供了一个类实现键盘录入

- Scanner sc = new Scanner(System.in);

输出语句的本质：是一个标准输出流

- printStream ps = System.out;
- PrintStream类的特有方法，System.out都能使用

#### 14.14.2打印流

打印流分类

- 字节打印流：PrintStream
- 字符打印流：PrintWrite

打印流特点

- 只负责输出数据，不负责读取数据
- 有自己特有方法

**字节打印流**

- PrintStream(String fileName)：使用指定文件名创建新的打印流
- 字节打印流如果使用继承父类的方法写数据，查看时会转码，使用自己的特有方法写数据，查看的数据原样输出

**字符打印流的构造方法**

- PrintWriter(String fileName)：使用指定文件名创建新的打印流，而不需要自动执行刷新
- PrintWriter(Writer out,boolean autoFlush)：创建一个新的PrintWrite，其中out为字符输出流对象，**autoflush为boolean类型，如果为真则println，printf或者format方法将刷新输出缓冲区**

**案例：复制java文件（打印流改进版）**

需求：将模块目录下的PrintStreamDemo.java文件复制到模块目录下的copy.txt文件

```java
//需求：将模块目录下的PrintStreamDemo.java文件复制到模块目录下的copy.txt文件
public class CopyFileDemo {
    public static void main(String[] args) throws IOException {
//        创建输入流对象
        BufferedReader br = new BufferedReader(new FileReader("src/javademo/passage14/test06/PrintStreamDemo.java"));
        //            创建字节打印流对象
/*        PrintStream ps = new PrintStream("src/javademo/passage14/test06/copy.txt");
        String line;
        while ((line = br.readLine())!= null){
            byte[] bytes = line.getBytes();
            ps.write(bytes);
            ps.println();
            ps.flush();//需要进行手动更新缓冲区
        }
        ps.close();*/

//        创建字符打印流对象
        PrintWriter pw = new PrintWriter(new FileWriter("src/javademo/passage14/test06/copy.txt"),true);
        String line;
        while ((line = br.readLine())!= null){
            pw.println(line);
        }
        pw.close();

        br.close();
    }
}

```

#### 14.14.3对象序列化流

**对象序列化**：就是将对象保存到磁盘中，或者在网络传输对象

这种机制就是使用一个字节序列表示对象，该字节序列包括：对象类型，对象的数据和对象中存储的属性等信息

字节序列写到文件之后，相当于在文件中持久保存了一个对象信息

反之，该字节序列还可从文件中读取回来，重构对象，对它进行反序列化



要使用序列化和反序列化就要使用对象序列化流和对象反序列化流：

- 对象序列化：ObjectOutputStream
- 反序列化：ObjectInputStream



**对象序列化流：ObjectOutputStream**

- 将Java对象的原始数据类型和图形写入OutputStream，可以使用ObjectOutputStream读取（重构）对象，可以通过使用流的文件来实现对象的持久存储。如果使用的是网络套接字流，则可以在另一个主机上或者另一个进程中重构对象

构造方法

- ObjectOutputStream（OutputStream out）：创建一个写入指定的OutputStream的ObjectOutputStream

序列化对象的方法

- void writeObject（Object obj）：将指定的对象写入ObjectOutputStream

**注意：**

- NotSerializableException报错：抛出一个实例需要一个Serializable接口。 序列化运行时或实例的类可能会抛出此异常
- Serializable接口：类的序列化由实现java.io.Serializable接口的类启用， **不实现此接口的类将不会使任何状态序列化或反序列化**
- Serializable接口是一个**标识接口**，实现该接口，不需要重写任何方法

```java
public class ObjectOutputStreamDemo {
    public static void main(String[] args) throws IOException {
//        ObjectOutputStream（OutputStream out）：创建一个写入指定的OutputStream的ObjectOutputStream
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("src/javademo/passage14/test07/oos.txt"));
//        创建学生对象
        Student s1 = new Student("王思聪",31);

//        void writeObject（Object obj）：将指定的对象写入ObjectOutputStream*/
        oos.writeObject(s1);
/*NotSerializableException报错：
    抛出一个实例需要一个Serializable接口。 序列化运行时或实例的类可能会抛出此异常
  Serializable：类的序列化由实现java.io.Serializable接口的类启用。 不实现此接口的类将不会使任何状态序列化或反序列化
  Serializable接口是一个标识接口，不需要重写任何方法
*/
        oos.close();
    }
}
```

**对象序列化流：ObjectInputStream**

- ObjectInputStream反序列化先前使用ObjectOutputStream编写的原始数据和对象

构造方法

- ObjectInputStream（InputStream in）：创建从指定的InputStream读取的ObjectInputStream

反序列化对象的方法：

- Object readObject（）：从ObjectInputStream读取一个对象

```java
public class ObjectInputStreamDemo {
    public static void main(String[] args) throws IOException, ClassNotFoundException {
//        ObjectInputStream（InputStream in）：创建从指定的InputStream读取的ObjectInputStream
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream("src/javademo/passage14/test07/oos.txt"));
//        Object readObject（）：从ObjectInputStream读取一个对象
        Object obj = ois.readObject();
        Student s = (Student)obj;
        System.out.println(s);
        ois.close();

        /*报错分析：
        在第一次读取的时候没有报错,直接输出Person对象的时候,打印的是地址值,看得不是很方便,所以我在Person重写了toString方法此时报错了。
        InvalidClassException: com.ginger.demo01.Person;
        local class incompatible: stream classdesc serialVersionUID = 311183030272692197, local class serialVersionUID = 6499259360078010285

        为什么第一次读取不出现异常,在Person重写toString方法的时候在读取,就出现上述异常?
            原因:Person类实现了序列化接口Serializable,那么它本身也因该有一个标记值。
            假设该标记值为1000。
                Person.class -- 序列化id=1000	(把java文件编译成class文件)
                writer数据 -- oos.txt  -- 序列化id该是=1000
                read数据 -- oos.txt -- 反序列化id也是=1000
                所以我第一次读取的时候没有抛出异常

		因为输出的是地址值,重写Person的toString方法，也正是因为修改了Person方法。
		Person.class -- 此时序列化id=2000	(把java文件重新编译成class文件)
		writer数据 -- oos.txt -- 因为还是以前的文件,序列化id就是=1000 (此时的writer方法我已经注释了,没有重新写到文件)
		read数据 -- oos.txt -- 所以读取的也还是以前的文件,序列化就是=1000

        出现该异常要怎么解决?
	修改Person过后,重新写文件,重新读文件。(这样有一个问题,就是以前读的数据被覆盖了?)
	在实际开发中,可能还需要使用以前写过的数据,不能重新写入。怎么办呢?
		通过异常信息可以看出来,报错原因是因为id值不匹配,每次修改java文件内容的时候,class文件的id值就会发生改变。而读取文件的时候，会和class
		文件中的id进行匹配。所以就会出问题。
		如果我有办法,让这个id值在java文件中是一个固定的值,这样,在修改java文件的时候,这个id值就不会发生改变了。
		怎么获取到这个ID值呢?
		eclipse:实现序列化接口的时候会出现一个黄色警告线,点击提示中的两个其中一个即可。
		在IDEA里面需要安装一个插件，这个在网上找就可以了。安装好后使用快捷键Alt+insert就可以了,自动生成。
		private static final long serialVersionUID = 6499259360078010285L;

要知道的是：
		序列化id：private static final long serialVersionUID = 6499259360078010285L;
		产生这个值以后，我们对类进行任何改动，它读取以前的数据是没有问题的。(读取还是以前的信息,不是改变过后的。)
注意：
		我一个类中可能有很多的成员变量，有些我不想进行序列化。请问该怎么办呢?
		使用transient关键字声明不需要序列化的成员变量
*/
    }
}
```

##### InvalidClassException的报错分析：

- 在第一次读取的时候没有报错,直接输出Student对象的时候,打印的是地址值,看得不是很方便,所以我在Student重写了toString方法此时报错了

  InvalidClassException：local class incompatible: stream classdesc serialVersionUID = 311183030272692197, local class serialVersionUID = 6499259360078010285

 **为什么第一次读取不出现异常,在Student重写toString方法的时候在读取,就出现上述异常?**

原因:Student类实现了序列化接口Serializable,那么它本身也因该有一个标记值。

假设该标记值为1000。

- 第一次输出：

  Student.class -- 序列化id=1000 (把java文件编译成class文件)

  write数据 -- oos.txt  -- 序列化id该是=1000

  read数据 -- oos.txt -- 反序列化返回的id也是=1000

  所以我第一次读取的时候没有抛出异常

- 第二次输出：

  因为输出的是地址值,重写Student的toString方法，也正是因为修改了Student方法。

  Student.class -- 此时序列化id=2000   (把java文件重新编译成class文件)

  write数据 -- oos.txt -- 因为还是以前的文件,序列化id就是=1000

  read数据 -- oos.txt -- 所以读取的也还是以前的文件,序列化id就是=1000 ，但是返回的id却是2000报错

 **出现该异常要怎么解决?**

- 修改Person过后,重新写文件,重新读文件。(这样有一个问题,就是以前读的数据被覆盖了?)

**在实际开发中,可能还需要使用以前写过的数据，不能重新写入，怎么办呢?**

通过异常信息可以看出来,报错原因是因为id值不匹配,每次修改java文件内容的时候,class文件的id值就会发生改变。而读取文件的时候，会和class文件中的id进行匹配，所以就会出问题。

如果我有办法,让**这个id值在java文件中是一个固定的值,这样,在修改java文件的时候,这个id值就不会发生改变了。**

**怎么获取到这个ID值呢?**

- eclipse:实现序列化接口的时候会出现一个黄色警告线,点击提示中的两个其中一个即可。

- 在IDEA里面需要安装一个插件，这个在网上找就可以了。安装好后使用快捷键Alt+insert就可以了,自动生成。

要知道的是：

​      序列化id：private static final long serialVersionUID = 6499259360078010285L;
​      产生这个值以后，我们对类进行任何改动，它读取以前的数据是没有问题的。(读取还是以前的信息,不是改变过后的。)

 **一个类中可能有很多的成员变量，有些我不想进行序列化。请问该怎么办呢?**

- 使用transient关键字声明不需要序列化的成员变量

**总结：**

- 用序列化流序列化一个对象后修改对象的类文件，会导致读取时抛出**InvalidClassException异常**

- 如何解决？**给对象所属类中添加一个成员变量serialVersionUID**

  ```java
  private static final long serialVersionUID = 42L；
  ```

- 如果一个对象的某个成员变量不想被序列化？**使用transient关键字修饰该变量**



### 14.15Properties

#### 14.15.1Properties概述

- 是一个Map体系的集合类
- Properties可以**保存到流中或从流中加载**



练习：Properties作为Map集合的使用

```java
public class PropertiesDemo {
    public static void main(String[] args) {
//        创建集合对象
//        Properties<String,String> prop = new Properties<String,String>();//错误的
        Properties prop = new Properties();
//        存储元素
        prop.put("hello001","张三丰");
        prop.put("hello002","曾小贤");
        prop.put("hello003","胡一菲");
        prop.put("hello004","张伟");
//        遍历集合
        Set<Object> key = prop.keySet();
        for(Object obj:key){
            Object value = prop.get(obj);
            System.out.println(obj+","+value);
        }
    }
}
```



#### 14.15.2Properties作为集合的特有方法

|                    方法名                    |                             说明                             |
| :------------------------------------------: | :----------------------------------------------------------: |
| Object setProperty(String key, String value) |  设置集合的键和值，都是string类型，底层调用hashtable方法put  |
|        String getProperty(String key)        |               使用此属性列表中指定的键搜索属性               |
|       Set<String> stringPropertyName()       | 从该属性列表中返回一个不可修改的键集，其中键及对应的值都是字符串 |

#### 14.15.3Properties和IO流结合的方法

|                    方法名                     |                             说明                             |
| :-------------------------------------------: | :----------------------------------------------------------: |
|           void load(InputStream in)           |            从输入字节流读取属性列表（键和元素对）            |
|         **void load(Reader reader)**          |            从输入字符流读取属性列表（键和元素对）            |
| void store(OutputStream out,String comments)  | 将此属性列表（键和元素对）写入此Properties表中，以合适于使用load(InputStream )方法格式写入输出字节流 |
| **void store(Writer writer,String comments)** | 将此属性列表（键和元素对）写入此Properties表中，以合适于使用load(Reader)方法格式写入输出字符流 |

**案例：游戏次数**

需求：请写程序实现猜数字小游戏，只能试玩三次，如果还想玩，提示：游戏试玩已结束，想继续玩请充值（www.cast.cn）

思路：

1. 写一个游戏类，里面一个猜数字小游戏
2. 写一个测试类
   1. 从文件中读取数据到Properties集合，用load方法实现
      - 文件已存在，game.txt
      - 里面有一个数值count=0
   2. 通过Properties集合获取玩到游戏的次数
   3. 判断是否到三次了
      - 如果到了，给出提示：游戏试玩已结束，想玩请充值
      - 如果不到三次：继续游戏，次数加一，使用Properties的store方法实现

```java
//游戏类
public class GameDemo {
    private GameDemo(){}

    public static void start(){
        Random r = new Random();
        int num = r.nextInt(100);
        while(true){
            Scanner sc = new Scanner(System.in);
            System.out.println("输入你猜的数：");
            int i = sc.nextInt();
            if(i<num){
                System.out.println("你的数字猜小了");
            }else if(num<i){
                System.out.println("你的数字猜大了");
            }else {
                System.out.println("恭喜你，猜对了");
                break;
            }
        }
    }
}
//测试类
public class GameTestDemo {
    public static void main(String[] args) throws IOException {
        FileReader fr = new FileReader("src/javademo/passage14/test08/test/game.txt");
        Properties prop = new Properties();
        prop.load(fr);
        fr.close();

        String count = prop.getProperty("count");
        int num = Integer.parseInt(count);

        if(num >= 3){
            System.out.println("游戏试玩已结束，想玩请充值");
        }else {
//            玩游戏
            GameDemo.start();
            num++;
            String s = String.valueOf(num);
            prop.setProperty("count",s);
            FileWriter fw = new FileWriter("src/javademo/passage14/test08/test/game.txt");
            prop.store(fw,null);
            fw.close();
        }
    }
}
```

## 15 进程和线程

### 15.1实现多线程

**进程**：是在正在运行的程序

- 进程是系统进行资源分配和调用的独立单位
- 每一个进程都有它自己的内存空间和系统资源

**线程**：是进程中的单个顺序控制流，是一条执行路径

- **单线程**：一个进程如果只有一条执行路径，称为单线程程序
- **多线程**：一个进程如果有多条执行路径，则成为多线程程序



#### 15.1.1 继承Thead类实现多线程

**方法一：继承Tread类**

- 定义一个类MyTread继承Tread类
- 在MyTread类中重写run()方法
- 创建MyTread类的对象
- 启动线程

两个小问题：

1. 为什么要重写run方法？

   因为run方法是用来封装被线程执行的代码

2. run方法和start方法的区别？

   run()：封装线程执行的代码，直接调用，相当于普通方法的调用

   start()：启动线程，然后再JVM调用此线程的run()方法



#### 15.1.2 设置和获取线程名称

**Thread类中设置和获取线程名称的方法**

方法一：使用setName()设置线程名称

- void setName(String name)：将此线程的名称更改为等于参数name
- String getName()：返回此线程的名称

方法二：使用带参构造方法设置线程名称

- 在MyThread类中定义无参和带参构造方法MyThread(String name)，创建对象时直接设置名称

如何获取main()方法所在线程的名称呢？

- static Thread currentThread():返回当前正在执行的线程对象的引用

```java
public class MyThreadDemo {
    public static void main(String[] args) {
//        MyThread my1 = new MyThread();
//        MyThread my2 = new MyThread();

//        my1.run();
//        my2.run();
        //void start() 开始执行线程，java虚拟机调用此线程的run方法
//        my1.start();
//        my2.start();
        
//        my1.setName("中国");
//        my2.setName("日本");

//        使用带参构造方法对线程命名
//        MyThread my1 = new MyThread("火车");
//        MyThread my2 = new MyThread("飞机");
//
//        my1.start();
//        my2.start();

        //        static Thread currentTread():返回当前正在执行的线程对象的引用
        System.out.println(Thread.currentThread().getName());//main
    }
}
```



#### 15.1.3 线程调度

**线程有两种调度模型**：

- 分时调度模型：所有线程轮流使用CPU的使用权，平均分配每个线程占用CPU的时间片
- 抢占式调度模型：优先让让优先级高的线程使用CPU，如果线程的优先级相同，那么会随机选择一个，优先级高的线程获取的CPU时间片相对多一些

**Java使用的是抢占式调度模型**



假如计算机只有一个CPU，那么CPU在某时刻只能执行一条指令，线程只有得到CPU的时间片，也就是使用权，才可以执行命令，所以说多线程程序的执行是有**随机性**，因为谁抢到CPU的使用权说不一定的



**Thread类中设置和获取线程优先级的方法：**

- public final int getPriority()：返回此线程的优先级
- public final void  setPriority(int newPriority)：更改此线程的优先级

**线程默认优先级是5，最小优先级是1，最大优先级是10**

**线程优先级高仅仅代表线程获取CPU时间片的机率高**，并不是一定的，但要在次数较多或者多次运行的时候才能看出效果



#### 15.1.4线程控制

|             方法名             |                             说明                             |
| :----------------------------: | :----------------------------------------------------------: |
| static void sleep(long millis) |       使当前正在执行的线程停留（或者暂停）指定的毫秒数       |
|          void jion()           |                       等待这个线程死亡                       |
|  void setDaemon(booleean on)   | 将此线程标记为守护线程，当运行的线程都是守护线程时，JVM将退出 |



#### 15.1.5 线程生命周期

![](C:\Users\Asinil\Desktop\学习\Java\15.1.5.png)

#### 15.1.6 实现Runnable接口实现多线程

**方法二：实现Runnable接口**

- 定义一个类MyRunnable实现Runnable接口
- 在MyRunnable类中重写run()方法
- 创建MyRunnable类的对象
- 创建Thread类对象，把MyRunnable对象作为构造方法的参数
- 启动线程

**总结：实现多线程有两种方法：**

1. 继承Thread类
2. 实现Runnable接口

**相比于继承Thread类，实现Runnable接口的好处**

- 避免了Java单继承的局限性（实现了接口，还可以去继承一个父类）
- 适合多个相同程序的代码去**处理同一个资源的情况**，把线程和程序的代码，数据有效分离开，较好的体现了面向对象的设计思想



### 15.2线程同步

需求：某电影院目前正在上映国产大片，共有100张票，而他有三个窗口买票，请设计一个程序模拟该电影院卖票

思路：

- 定义一个类SellTicket实现Runnable接口，里面定义一个成员变量：private int tickets = 10;
- 在SellTicket类中重写run方法实现卖票
  - 判断票数大于零，就卖票，并告知是哪个窗口卖的
  - 卖了票之后，总票数减一
  - while循环让买票动作一直进行

- 定义一个测试类SellTicketDemo，里面有mian方法
  - 创建SellTicket对象
  - 创建三个Thread对象，并给出相应的窗口名称
  - 启动线程

```java
public class SellTicket implements Runnable{
    private int tickets = 100;
    @Override
    public void run() {
        while(true) {
            if (tickets > 0) {
                System.out.println(Thread.currentThread().getName() + "售卖了序号为" + tickets + "的票");
                tickets--;
            }
        }
    }
}
public class SellTicketDemo {
    public static void main(String[] args) {
        SellTicket st = new SellTicket();

        Thread t1 = new Thread(st,"窗口1");
        Thread t2 = new Thread(st,"窗口2");
        Thread t3 = new Thread(st,"窗口3");

        t1.start();
        t2.start();
        t3.start();
    }
}
```

上面程序是有缺陷的，接下来我们对其进行改进：

- 先给它加上一个售票延迟功能：每次出票需要100毫秒延迟

```java
public class SellTicket implements Runnable{
    private int tickets = 100;
    @Override
    public void run() {
        while(true) {
            if (tickets > 0) {
                //卖同一张票多次：线程1抢到了CPU的执行权，输出100
                
                	/*出现负数票：线程1抢到了CPU的执行权，tickets=1*/
                	/*出现负数票：但此时执行到此，线程2抢到了CPU的执行权，tickets=1*/
                System.out.println(Thread.currentThread().getName() + "售卖了序号为" + tickets + "的票");
                //卖同一张票多次：但此时执行到此，线程2抢到了CPU的执行权，输出100
                //卖同一张票多次：同时也可能线程3抢到了CPU的执行权，输出100
                	/*出现负数票：线程1抢到了CPU的执行权，输出1*/
                tickets--;
                	/*出现负数票：线程1继续执行执行权，tickets=0*/
                try {
                    Thread.sleep(100);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                	/*出现负数票：但此时执行到此，线程2抢到了CPU的执行权，tickets=-1*/
                //卖同一张票多次：这里tickets就变成了97，相同票被卖了三次
            }
        }
    }
}
```

为什么会出现数据安全问题呢？

- 是否是多线程环境
- 是否共享数据
- 是否有多条语句操作共享数据

如何解决？

- **基本思想：让程序没有安全问题的环境**



#### 15.2.1同步代码块

锁多条语句操作共享数据，可以使用同步代码块实现

- 格式：

  ```java
  synchronized(任意对象){
  	多条语句操作共享数据代码
  }
  ```

- synchronized（任意对象）：就相当于给代码加了锁，任意对象就可以看成是一把锁



**同步的好处和弊端**

- 好处：解决了多线程数据安全问题
- 弊端：当线程很多时，每个线程都要去判断同步上的锁，很耗费资源，无形中降低程序运行效率

下面我们对上面案例代码进行改进：

```java
public class SellTicket implements Runnable{
    private int tickets = 100;
    private Object obj = new Object();//必须使用同一把锁，否则锁不住

    @Override
    public void run() {
        while(true) {
            synchronized (obj) {
                if (tickets > 0) {
                    System.out.println(Thread.currentThread().getName() + "售卖了序号为" + tickets + "的票");
                    tickets--;
                    try {
                        Thread.sleep(100);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
            }
        }
    }
}
```

根据我们封装的思想，我们能不能把同步代码块的程序封装成一个方法呢？



#### 15.2.2同步方法

同步方法：就是把synchronized关键字加到方法上

格式：

- 修饰符 synchronized 返回值类型 方法名（方法参数）{}

对上述代码进行改进：

```java
public class SellTicket implements Runnable {
    private int tickets = 100;
    private Object obj = new Object();//必须使用同一把锁，否则锁不住
    private int count = 0;
    @Override
    public void run() {
        while (true) {
            if (count % 2 == 0) {
//                synchronized (obj) {
                synchronized (this) {
                    if (tickets > 0) {
                        System.out.println(Thread.currentThread().getName() + "售卖了序号为" + tickets + "的票");
                        tickets--;
                        try {
                            Thread.sleep(100);
                        } catch (InterruptedException e) {
                            e.printStackTrace();
                        }
                    }
                }
            } else {
                sellTickets();
            }
            count++;
        }
    }
    private synchronized void sellTickets() {//同步方法的锁是this
        if (tickets > 0) {
            System.out.println(Thread.currentThread().getName() + "售卖了序号为" + tickets + "的票");
            tickets--;
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

同步代码块的锁对象是什么？

- **this**



**同步静态方法：就是把synchronized关键字加到静态方法上**

- 修饰符 static synchronized 返回值类型 方法名（方法参数）{}

但是同步静态方法的锁对象是什么呢？还是this吗？

- 静态是与类相关的，**同步静态方法的锁就是该类的字节码文件对象，可以用类名.class表示**



#### 15.2.3线程安全的类

|      **类**      |                           **说明**                           |
| :--------------: | :----------------------------------------------------------: |
| **StringBuffer** | 线程安全，可变的字符序列。从JDK5开始，被StringBuilder替代，通常使用StingBuilder类，因为它支持相同操作，速度更快但不同步 |
|    **Vector**    | 从Java2平台v1.2开始，该类改进了List接口，使其成为JavaCollectionsFramework的成员。与新的集合实现不同，Vector被同步。如果不需要线程安全的实现，建议使用ArrayList替代Vector |
|  **Hashtable**   | 该类实现了一个hash表，它将键映射到值，任何非null对象都可以用作键或者值。从Java平台V1.2开始，该类进行了改进，实现了Map接口，使其成为JavaCollectionsFramework的成员，与新的集合实现不同，hashtable被同步了，如果不需要线程安全的实现，建议使用HashMap替代Hashtable |

**但在实际的编程中Vector和Hashtable类都不经常使用**

- 原因：有替代他们的方法

  - static <T> Collection<T> synchronizedCollection (Collection<T> c) 返回由指定集合支持的同步（线程安全）集合。

  - static <T> List<T> synchronizedList (List<T> list) 返回由指定列表支持的同步（线程安全）列表。

  - static <T> Set<T> synchronizedSet (Set<T> s) 返回由指定集合支持的同步（线程安全）集。

  - static <K,V> Map<K,V> synchronizedMap (Map<K,V> m) 返回由指定地图支持的同步（线程安全）映射。



#### 15.2.4Lock锁

虽然我们可以理解同步代码块和同步方法的锁对象问题，但是我们并没有直接看到在哪里加上了锁，在哪里释放了锁，**为了更清晰的表达如何加锁和释放锁，JDK5之后提供了一个新的锁对象Lock**



Lock实现提供比使用synchronized方法和语句可以获得的更广泛的锁定操作。

**Lock提供了获得锁和释放锁的两个方法**

- void lock()	获得锁
- void unlock() 释放锁

Lock是接口不能实例化，这里采用Lock的实现类ReentrantLock来实例化

- ReentrantLock的构造方法:

  ReentrantLock()：创建一个ReentrantLock的实例

对上面买票代码进行Lock改进：

```java
public class ReentrantLocks implements Runnable {
    private int tickets = 100;
    private Lock lock = new ReentrantLock();
    @Override
    public void run() {
        while (true) {
            try {//防止代码块中报错，导致无法释放锁，所以需要使用try...finaly
                lock.lock();
                if (tickets > 0) {
                    System.out.println(Thread.currentThread().getName() + "售卖了序号为" + tickets + "的票");
                    tickets--;
                    try {
                        Thread.sleep(100);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
            }finally {
                lock.unlock();
            }
        }
    }
}
```

**finally**：在异常处理时提供finally块来执行所有清除操作，比如说：IO流在释放资源，Lock在释放锁

**特点：被finally控制的语句一定会执行，除非JVM退出**



### 15.3 生产者和消费者

#### 15.3.1生产者和消费者概述

生产者消费者模式是一个十分经典的多线程协作模式，弄懂生产者消费者问题能够让我们对多线程编程的理解更加深刻

所谓的生产者消费者问题，实际上只包含了**两类线程**：

- 一类是生产者线程用于生产数据
- 一类是消费者线程用于消费数据

为了解耦生产者消费者关系，通常会采用一个共享的数据区域，就像一个仓库

- 生产者生产数据之后直接放置在共享区域中，并不需要关心消费者的行为
- 消费者只需要从共享区域中获取数据，并不需要去关心生产者行为



为了**体现生产和消费过程中的等待和唤醒**，Java就提供了几个方法供我们使用，这几个方法在Object类中

|      方法名      |                             说明                             |
| :--------------: | :----------------------------------------------------------: |
|   void wait()    | 导致当前线程等待，直到另一个线程调用该对象的notify方法或notifyAll方法 |
|  void notify()   |               唤醒正在等待对象监视器的单个线程               |
| void notifyAll() |               唤醒正在等待对象监视器的所有线程               |



#### 15.3.2生产者和消费者案例

生产者和消费者案例中包含的类：

- 奶箱类（Box）：定义一个成员变量，表示第x瓶奶，提供存储牛奶和获取牛奶的操作
- 生产者类（Producer）：实现Runnable接口，重写run方法，调用存储牛奶的操作
- 消费者类（Customer）：实现Runnable接口，重写run方法，调用获取牛奶的操作
- 测试类（BoxDemo）：包含main方法
  - 创建奶箱对象，创建共享数据区域
  - 创建生产者对象，把奶箱对象当作构造方法参数传递，因为在这个类中需要调用存储牛奶的操作
  - 创建消费者对象，把奶箱对象当作构造方法参数传递，因为在这个类中需要调用获取牛奶的操作
  - 创建两个线程对象，分别把生产者和消费者对象当作参数传递
  - 启动线程

```java
public class Box {
    private  int Count = 0;//牛奶数量
    private boolean state = false;//奶箱状态

//    存放牛奶操作
    public synchronized void storeMilk(){
//        如果奶箱中有奶则停止生产
        if(state){
            try {
                wait();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
//        如果没有牛奶则生产牛奶
        Count++;
        System.out.println("存放第"+Count+"瓶牛奶");
//        生产完毕修改状态
        state = true;
//        唤醒其他等待的线程
        notifyAll();
    }
//    获取牛奶操作
    public synchronized void getMlk(){
//        没有牛奶则等待
        if(!state) {
            try {
                wait();
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
//        如果有牛奶获取牛奶
        System.out.println("获取第" + Count + "瓶牛奶");
        state = false;
//        唤醒其他等待的线程
        notifyAll();
    }
}
//IllegalMonitorStateException：抛出以表示线程以尝试在对象的监视器上等待或通知其他线程等待对象的监视器，而不拥有指定的监视器
//简单来说：报错原因是因为wait()和notify()等方法只能在同步中使用
```

```java
public class Producer implements Runnable{
    private Box box;
    public Producer() {
    }
    public Producer(Box box) {
        this.box = box;
    }
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            box.storeMilk();
        }
    }
}
```

```java
public class Customer implements Runnable{
    private Box box;

    public Customer() {
    }

    public Customer(Box box) {
        this.box = box;
    }

    @Override
    public void run() {
        while (true) {
            box.getMlk();
        }
    }
}
```

```java
public class BoxDemo {
    public static void main(String[] args) {
        Box box = new Box();
        Producer p = new Producer(box);
        Customer c = new Customer(box);

        Thread t1 = new Thread(p);
        Thread t2 = new Thread(c);

        t1.start();
        t2.start();
    }
}
```



## 16网络编程

### 16.1网络编程入门

#### 16.1.1网络编程概述

计算机网络

- 是指将地理位置不同的具有独立功能的多台计算机以及其外部设备，通过通信线路连接起来，在网络操作系统，网络管理软件以及网络通讯协议的管理和协调下，实现资源共享和信息传递的计算机系统

网络编程

- 在网络通信协议下，实现网络互联的不同计算机上运行的程序间可以进行数据交换

#### 16.1.2网络编程三要素

**IP地址**

- 要想让网络中的计算机能够相互通讯，必须为每台计算机指定一个标识号，通过这个标识号来指定要接收数据的计算机和识别发送的计算机，而IP地址就是这个标识号，也就是设备的标识



**端口**

- 网络的通信，本质上是两个应用程序的通信。每台计算机都有很多的应用程序，那么在网络通信时，如何区分这些应用程序呢？如果说IP地址可以唯一识别网络中的设备，那么端口号就可以唯一识别设备中的应用程序了，也是应用程序的标识

**协议**

- 通过计算机网络可以使很多台计算机实现连接，位于同一个网络中的计算机在进行连接和通信时需要遵守一定的规则，就像开车必须遵守交通规则一样。在计算网络中，这些连接和通信的规则被称为网络通信协议，它对数据的传输格式，传输速率，传输步骤等做了统一的规定，通信双方必须同时遵守才能完成数据交换，常见的协议有UDP协议和TCP协议



#### 16.1.3 IP地址

**IP地址：是网络中设备的唯一标识**

**IP地址分为两大类**

- **IPv4**：是给每一个连接在网络上的主机分配一个32bit的地址。按照TCP/IP规定，IP地址用二进制来表示，每一个IP地址长32bit，也就是4个字节。

  例如：一个采用二进制的IP地址是“11000000 10101000 00000001 01000010”，这么长的地址处理起来太过于费劲。为了方便使用，IP地址常被写为十进制的形式，中间使用符号“.”分隔不同的字节。于是上面的IP地址可表示为“192.168.1.66”，IP地址的这种表示方法称为“**点分十进制表示法**”。

- **IPv6**：由于互联网的蓬勃发展，IP地址的需求量越来越大，但是网络地址资源有限，使得IP的分配愈发紧张。为了扩大地址空间，通过IPv6重新定义地址空间，采用128位地址长度，每16个字节一组，分成8组十六进制数，这样就解决了网络地址资源数量不够的问题

**常用命令：**

- ipconfig：查看本机IP地址
- ping IP地址：检查网络是否连接

**特殊IP地址：**

- **127.0.0.1**：回送地址，可以代表本机地址，一般用来测试用



#### 16.1.4 InetAddress 的使用

为了方便我们对IP地址的获取和操作，Java提供了InetAddress类供我们使用

InetAddress：此类表示Internet协议（IP）地址

|                  方法名                   |                             说明                             |
| :---------------------------------------: | :----------------------------------------------------------: |
| static InetAddress getByName(String host) | 确定主机名称的IP地址。主机名称可以是机器名称，也可以是IP地址 |
|           String getHostName()            |                    获取此IP地址的主机名称                    |
|          String getHostAddress()          |                 返回文本显示中的IP地址字符串                 |



#### 16.1.5 端口和协议

**端口**：设备上应用程序的唯一标识

**端口号**：用两个字节表示的整数，它的取值范围为0~65535。其中，0~1023之间的端口号用于一些知名的网络服务和应用。普通的应用程序需要使用1024以上的端口号。如果端口号被另外的服务器或应用所占用，会导致当前程序启动失败



**协议**：计算机网络中，连接和通信规则被称为网络通信协议

**UDP协议**

- 用户数据报协议（User Datagram Protocol）

- UDP是无连接通信协议，即在数据传输时，数据的发送端和接收端不建立逻辑连接。简单来说，当一台计算机向另一台计算机发送数据时，**发送端不会确认接收端是否存在，就会发出数据，同样接受端在收到数据时，也不会向发送端反馈是否收到数据**

  由于使用UDP协议**消耗资源小，通信效率高**，所以通常都会用于音频，视频和普通数据的传输

- 例如视频会议通常采用UDP协议，因为这种情况即使偶尔丢失一两个数据包，也不会对接收结果产生太大影响。但是在UDP协议传输数据时，由于**UDP的面向无连接性，不能保证数据的完整性，因此在传输重要数据时不建议使用UDP协议**

**TCP协议**

- 传输控制协议（Transmission Control Protocol）
- TCP协议是面向连接的通信协议，即传输数据之前，在发送端和接收端建立逻辑连接，然后传输数据，它提供了两台计算机之间可靠无差错的数据传输。在TCP连接中必须要明确客户端和服务器端，由客户端向服务端发送连接请求，每次连接的创建都要经过“三次握手”
- **三次握手：TCP协议中，发送数据的准备阶段，客户端和服务器之间的三次交互，以保证连接的可靠**
  - 第一次握手：客户端向服务器端发送连接请求，等待服务器确认
  - 第二次握手：服务器端向客户端回送一个响应，通知客户端收到了连接请求
  - 第三次握手：客户端再次向服务器端发送确认消息，确认连接

![](C:\Users\Asinil\Desktop\学习\Java\16.1.5.png)

- 完成三次握手，建立连接之后，客户端和服务器就可以开始进行数据传输了。由于这种面向连接的特性，TCP协议可以保证传输数据的安全，所以应用十分广泛。例如下载文件，上传文件，浏览网页等



### 16.2UDP通信程序

UDP是一种不可靠的的网络协议，它在通信的两端各建立一个Socket对象，但是这两个Socket只是发送，接收数据对象

因此，对于基于UDP协议的通信双方而言，没有所谓的客户端和服务器的概念

**Java提供了DatagramSocket类作为基于UDP协议的Socket**

#### 16.2.1UDP发送数据

发送数据的步骤：

1. 创建发送端的Socket对象（DatagramSocket）

   **DatagramSocket()：无参方法构造对象**

2. 创建数据，并把数据打包

   **使用DatagramPacket类，创建数据包，使用构造方法DatagramPacket(byte[] buf, int length, InetAddress address, int port)**

3. 调用DatagramSocket对象的方法发送数据

   **调用send(DatagramPacket p)方法发送数据包**

4. 关闭发送端

   **调用close()方法关闭发送端**

```java
public class UDPSendDemo {
    public static void main(String[] args) throws IOException {
        //1. 创建发送端的Socket对象（DatagramSocket）
//        DatagramSocket() 构造数据报套接字并将其绑定到本地主机上的任何可用端口
        DatagramSocket ds = new DatagramSocket();

        //2. 创建数据，并把数据打包
//        DatagramPacket (byte[] buf, int length, InetAddress address, int port) 构造一个数据包，发送长度为 length的数据包到指定主机上的指定端口号。
        byte[] bytes = "hellp,udp发送".getBytes();
//        int length = bytes.length;
//        InetAddress ip = InetAddress.getByName("192.168.80.1");
//        int port = 10086;
//        DatagramPacket dp = new DatagramPacket(bytes,length,ip,port);
        DatagramPacket dp = new DatagramPacket(bytes,bytes.length,InetAddress.getByName("192.168.80.1"),10086);

        //3. 调用DatagramSocket对象的方法发送数据
//        void send (DatagramPacket p) 从此套接字发送数据报包。
        ds.send(dp);

        //4. 关闭发送端
        ds.close();
    }
}
```

#### 16.2.2UDP接收数据

接收数据步骤：

1. 创建接收端Socket对象（DatagramSocket）

   **DatagramSocket (int port) 构造数据报套接字并将其绑定到本地主机上的指定端口**

2. 创建一个数据包用于接收数据

   **DatagramPacket (byte[] buf, int length) 构造一个 DatagramPacket用于接收长度为 length数据包**

3. 调用DatagramSocket对象的方法接受数据

   **调用receive(DatagramPacket p)方法**

4. 解析数据包，并把数据在控制台输出

   **调用DatagramPacket中的getData方法得到byte[]，调用getLength方法的到数据长度**

   **构造String(byte[],0,length)方法得到字符串数据** 

5. 关闭接收端

```java
public class UDPReceiveDemo {
    public static void main(String[] args) throws IOException {
        //1. 创建接收端Socket对象（DatagramSocket）
//        DatagramSocket (int port) 构造数据报套接字并将其绑定到本地主机上的指定端口。
        DatagramSocket ds = new DatagramSocket(10086);
        //2. 创建一个数据包用于接收数据
//        DatagramPacket (byte[] buf, int length) 构造一个 DatagramPacket用于接收长度为 length数据包。
        byte[] bytes = new byte[1024];
        DatagramPacket dp = new DatagramPacket(bytes,bytes.length);

        //3. 调用DatagramSocket对象的方法接受数据
        ds.receive(dp);

        //4. 解析数据包，并把数据在控制台输出
//        byte[] getData() 返回数据缓冲区。
//        byte[] data = dp.getData();
//        int length = dp.getLength();
//        String strData = new String(data,0,length);
//        System.out.println(strData);
        System.out.println("数据是："+new String(dp.getData(),0, dp.getLength()));

        //5. 关闭接收端
        ds.close();
    }
}
```

需求：

- UDP发送数据：数据来自键盘录入，直到输入的数据是886，发送数据结束
- UDP接受数据：因为接收端不知道发送端什么时候停止发送数据，故采用死循环接收

```java
//UDP发送数据：数据来自键盘录入，直到输入的数据是886，发送数据结束
public class UDPSendDemo {
    public static void main(String[] args) throws IOException {
//        创建发送端对象
        DatagramSocket ds = new DatagramSocket();
//        创建数据包
//        从键盘获取数据
        /*Scanner sc = new Scanner(System.in);
        while (true) {
            System.out.println("发送：");
            String s = sc.nextLine();
            byte[] bytes = s.getBytes();
            DatagramPacket dp = new DatagramPacket(bytes, bytes.length, InetAddress.getByName("192.168.80.1"), 10086);
//        发送数据包
            ds.send(dp);
            if(s.equals("886")){
                break;
            }
        }*/

//        自己封装键盘录入,使用标准输入流
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String line ;
        while((line = br.readLine()) != null){
            if (line.equals("886")){
                break;
            }
            DatagramPacket dp = new DatagramPacket(line.getBytes(), line.getBytes().length, InetAddress.getByName("192.168.80.1"), 10086);
//        发送数据包
            ds.send(dp);
        }
//        关闭发送端对象
        ds.close();
    }
}
```

```java
//- UDP接受数据：因为接收端不知道发送端什么时候停止发送数据，故采用死循环接收
public class UDPReceiveDemo {
    public static void main(String[] args) throws IOException {
//        创建接收端对象
        DatagramSocket ds = new DatagramSocket(10086);
        while(true) {
//        创建数据包接收对象
            byte[] bytes = new byte[1024];
            DatagramPacket dp = new DatagramPacket(bytes, bytes.length);
//        接受数据
            ds.receive(dp);
//        将其输出到控制台
            String s = new String(dp.getData(), 0, dp.getLength());
            System.out.println("接收的数据是：" + s);
        }
//        关闭接收端
//        ds.close();
    }
}
```



### 16.3 TCP通信程序

TCP通信协议是一种可靠的网络协议，它在通信的两端各建立一个Socket对象，从而在通信的两端形成网络虚拟链路，一旦建立了虚拟的网络链路，两端的程序就可以通过虚拟链路进行通信

**Java对基于TCP协议的网络提供了良好的封装，使用Socket对象来代表两端的通信端口，并通过Socket产生的IO流进行网络通信**

**Java为客户端提高了Socket类，为服务器端提供了ServerSocket类**

#### 16.3.1 TCP发送数据

客户端发送数据的步骤：

1. 创建客户端的Socket对象（Socket）

   下面两种构造方法都行：

   **Socket(String host,int port)**

   **Socket(InetAddress address,int port)**

2. 获取输出流写数据

   **OutputStream getOutputStream()**

3. 释放IO流资源

   **void close()**

```java
public class TCPClientDemo {
    public static void main(String[] args) throws IOException {
        //1. 创建客户端的Socket对象（Socket）
//         Socket (InetAddress address, int port) 创建流套接字并将其连接到指定IP地址的指定端口号
//        Socket s = new Socket(InetAddress.getByName("192.168.80.1"),10086);
//        Socket (String host, int port) 创建流套接字并将其连接到指定主机上的指定端口号
        Socket s = new Socket("192.168.80.1",10086);
        //2. 获取输出流写数据
//       OutputStream getOutputStream() 返回此套接字的输出流
        OutputStream os = s.getOutputStream();
        os.write("hello,tcp".getBytes());
//      3. 释放IO流资源
        s.close();
    }
}
```



#### 16.3.2 TCP接收数据

服务器接受数据步骤：

1. 创建服务器端的Socket对象（ServerSocket）

   **ServerSocket (int port) 创建绑定到指定端口的服务器套接字**

2. 监听客户端连接，返回一个Socket对象

   **Socket accept() 侦听要连接到此套接字并接受**

3. 获取输入流，读取数据，并把数据显示在控制台

   **InputStream getInputStream()获取输入流**

4. 释放资源

   **void close()**

```java
public class TCPServerDemo {
    public static void main(String[] args) throws IOException {
//        1. 创建服务器端的Socket对象（ServerSocket）
//        ServerSocket (int port) 创建绑定到指定端口的服务器套接字
        ServerSocket ss = new ServerSocket(10086);

//        Socket accept() 侦听要连接到此套接字并接受它
//        服务器端监听数据得到的是Socket对象
        Socket s = ss.accept();
//        2. 获取输入流，读取数据，并把数据显示在控制台
        InputStream is = s.getInputStream();
        byte[] bytes = new byte[1024];
        int len = is.read(bytes);
        String data = new String(bytes,0,len);
        System.out.println(data);
//      3. 释放资源
        s.close();
        ss.close();
    }
}
```

**TCP通信练习**

练习1：

- 客户端：发送数据，接收服务器反馈
- 服务器：接受数据，给出反馈

```java
public class TCPClientDemo1 {
    public static void main(String[] args) throws IOException {
//        创建客户端Socket对象
        Socket s = new Socket("192.168.80.1", 10086);
//        获取输出流
        OutputStream os = s.getOutputStream();
//        封装键盘输入
        System.out.println("要发送的数据：");
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String line = br.readLine();
        os.write(line.getBytes());
//        接收服务器反馈
        InputStream is = s.getInputStream();
        byte[] bys = new byte[1024];
        int len = is.read(bys);
        String data = new String(bys,0,len);
        System.out.println("服务器反馈："+data);
//      释放资源
        s.close();
    }
}
```

```java
public class TCPServerDemo1 {
    public static void main(String[] args) throws IOException {
//        创建服务器ServerSocket对象
        ServerSocket ss = new ServerSocket(10086);
//        监听客户端，得到Socket对象
        Socket s = ss.accept();
//        获得输入流
        InputStream is = s.getInputStream();
        byte[] bys = new byte[1024];
        int len = is.read(bys);
        String data = new String(bys,0,len);
        System.out.println("获取的数据："+data);
//        获取输出流
        OutputStream os = s.getOutputStream();
        os.write("服务器已接受数据".getBytes());
//        释放资源
        ss.close();

    }
}
```

练习2：改进上面程序，让客户端一直发送数据，直到输入886结束，服务器一直接受数据

```java
public class TCPClientDemo2 {
    public static void main(String[] args) throws IOException {
        Socket s = new Socket(InetAddress.getByName("192.168.80.1"), 10086);
//      自己封装键盘录入
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String line;
////      获取输出流
//        OutputStream os = s.getOutputStream();
////      获取输入流
//        InputStream is = s.getInputStream();
//        byte[] bys = new byte[1024];
//
//        while ((line = br.readLine()) != null) {
//            if (line.equals("886")) {
//                break;
//            }
//            os.write(line.getBytes());
////          获取反馈
//            int len = is.read(bys);
//            String data = new String(bys, 0, len);
//            System.out.println("服务器：" + data);
//        }

//      获取输出流
//        将字节输出流包装成字符输出
        BufferedWriter bwrite = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
//        再将字节输入流包装
        BufferedReader bread = new BufferedReader(new InputStreamReader(s.getInputStream()));
        while ((line = br.readLine()) != null) {
            if (line.equals("886")) {
                break;
            }
            bwrite.write(line);
            bwrite.newLine();
            bwrite.flush();
            //接收服务器反馈
            String data = bread.readLine();
            System.out.println("服务器：" + data);
        }
        s.close();
    }
}
```

```java
public class TCPServerDemo2 {
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(10086);
//        监听客户端对象
        Socket s = ss.accept();
////        获取输入流
//        InputStream is = s.getInputStream();
//        byte[] bys = new byte[1024];
//        int len;
////        获取输出流
//        OutputStream os = s.getOutputStream();
//        while((len = is.read(bys))!=-1){
//            String data = new String(bys, 0, len);
//            System.out.println("客户端：" + data);
//
//            os.write("服务器已接收数据".getBytes());
//        }

//        将字节输入流包装为字符输入
//        InputStream is = s.getInputStream();
//        InputStreamReader isr = new InputStreamReader(is);
//        BufferedReader br = new BufferedReader(isr);
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
//        再包装字符输出
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
        String line;
        while ((line = br.readLine())!= null){
            System.out.println(line);

            bw.write("服务器已接收数据");
            bw.newLine();
            bw.flush();
        }

        ss.close();
    }
}
```

练习3：继续改写上面程序

- 客户端：数据来自键盘输入，直到输入886，结束
- 服务器：将接收的数据写入server.txt文本中

```java
//服务器：将接收的数据写入tcp.txt文本中
public class TCPServerDemo3 {
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(10086);
//        监听客户端连接
        Socket s = ss.accept();

//        创建字符输流对象
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
//        创建文件字符输出流对象
        BufferedWriter bwrite = new BufferedWriter(new FileWriter("src/javademo/passage16/test05/server.txt"));
        String line;
        while ((line = br.readLine())!=null){
            bw.write("服务器已接收数据");
            bw.newLine();
            bw.flush();

            bwrite.write(line);
            bwrite.newLine();
            bwrite.flush();
        }
        ss.close();
        bwrite.close();
    }
}
```

练习4：继续改写上面程序

- 客户端：数据来自client.txt文件
- 服务器：将接收的数据写入server.txt文本中

```java
//客户端：数据来自client.txt文件
public class TCPClientDemo4 {
    public static void main(String[] args) throws IOException {
        Socket s = new Socket("192.168.80.1", 10086);
//        获取输入字节输出流，并包装为字符流
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
//        创建文件输入流对象
        BufferedReader bread = new BufferedReader(new FileReader("src/javademo/passage16/test05/client.txt"));

        String line;
        while ((line = bread.readLine()) != null) {
//            传输数据
            bw.write(line);
            bw.newLine();
            bw.flush();
        }
//        解决服务器接受数据一直等待
//        public void shutdownOutput()输出结束
        s.shutdownOutput();

//            接收反馈
        String data = br.readLine();
        System.out.println("服务器：" + data);

        s.close();
        bread.close();
    }
}

```

```java
public class TCPServerDemo4 {
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(10086);
        Socket s = ss.accept();

//        获取字节流对象，并包装为字符流
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
        BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
//        创建文件字符流对象
        BufferedWriter bwrite = new BufferedWriter(new FileWriter("src/javademo/passage16/test05/server.txt"));

        String line;
        while ((line = br.readLine())!= null){
//            写入文件
            bwrite.write(line);
            bwrite.newLine();
            bwrite.flush();
        }
        //        readLine阻塞住了，上面循环未能正常结束
//            发送反馈
        bw.write("已接收数据");
        bw.newLine();
        bw.flush();

        ss.close();
        bwrite.close();
    }
}
```

**出现问题：服务器接收数据一直等待**

问题原因：读取数据的方式是阻塞式的

解决办法：自定义结束标记；**使用shutdownOutput()方法（推荐）**



练习5：继续改进上面的代码

- 客户端：数据来自文本文件，接收服务器反馈
- 服务端：接收的数据都写入文本文件中，给出反馈，代码用线程封装，为每一个客户端开启一个线程

```java
//服务器类
public class TCPServerDemo5 {
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(10086);
        while (true){
//            监听客户端连接
            Socket s = ss.accept();
//            创建线程
            new Thread(new ServerThread(s)).start();

        }
    }
}
//线程类
public class ServerThread implements Runnable {
    private Socket s;
    public ServerThread(Socket s) {
        this.s = s;
    }

    @Override
    public void run(){
        try {
//        获取字符流对象，并将其打包为字符流对象
            BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
            BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));

//            创建文件字符输入流对象
//            BufferedWriter bwrite = new BufferedWriter(new FileWriter("src/javademo/passage16/test05/server.txt"));
//            解决多个文件名称冲突问题
            int Count = 0;
            File file = new File("src/javademo/passage16/test05/sserver"+Count+".txt");
            while (file.exists()){
                Count++;
                file = new File("src/javademo/passage16/test05/sserver"+Count+".txt");
            }
            BufferedWriter bwrite = new BufferedWriter(new FileWriter(file));

            String line;
            while((line = br.readLine())!=null){
                bwrite.write(line);
                bwrite.newLine();
                bwrite.flush();
            }

//            发出反馈
            bw.write("已接收文件");
            bw.newLine();
            bw.flush();

            s.close();
            bwrite.close();

        } catch (IOException e) {
            e.printStackTrace();
        }

    }
}
```





## 17 Lambda表达式

### 17.1函数式编程思想概述

![](C:\Users\Asinil\Desktop\学习\Java\17.1.1.png)

在数学中，函数就是有输入量，输出量的一套计算方案，也就是“拿数据做操作”

面向对象思想强调“必须通过对象的形式来做事情“

函数式思想则是尽量忽略面向对象的复杂语法，强调做什么，而不是以什么形式去做

而我们要学的Lambda表达式就是函数式思想的体现



**体验一下Lambda表达式**

需求：启动一个线程，在控制台输出”线程启动了“

```java
public class LambdaDemo {
    public static void main(String[] args) {
//        面向对象编程
//        MyThread m = new MyThread();
//        Thread t = new Thread(m);
//        t.start();

//        匿名内部类的方式改进
//        new Thread(new Runnable() {
//            @Override
//            public void run() {
//                System.out.println("线程启动了");
//            }
//        }).start();

//        函数式编程
//        Lambda表达式改进上述代码
        new Thread(()->{
            System.out.println("线程启动了");
        }).start();
    }
}
```



### 17.2 Lambda表达式的标准格式

匿名内部类中重写run()方法的代码分析：

```java
	new Thread(new Runnable() {
         @Override
            public void run() {
                System.out.println("线程启动了");
            }
   }).start();
```

- 方法形参为空，不需要调用参数
- 返回类型void，不需要返回值
- 方法体则是我们需要做的事情



Lambda表达式的代码分析：

```java
	new Thread(()->{
        System.out.println("线程启动了");
    }).start();
```

- （）：内部没有内容，可以看作方法形式参数为空
- ->：用箭头指向后要做的事情
- {}：包含一段代码，我们称之为代码块，可以看作方法体的内容

组成Lambda表达式的三要素：**形参，箭头，代码块**



**Lambda表达式格式：**

- 格式：(形式参数)->{代码块}

- 形参：如果有多个参数，参数之间用逗号隔开；如果没有参数，留空即可
- ->：由英文中画线和大小符号组成，固定写法，代表指向动作
- 代码块：方法体内容，具体要做的事情



**Lambda表达式的使用前提：**

- 有一个接口
- 接口中有且只有一个抽象方法



##### 练习Lambda表达式

练习1：

- 定义一个接口（Eatable），里面定义一个抽象方法void eat()
- 定义一个测试类（EatDemo），测试类中提供两个方法
  - 一个方法：useEatable（Eatable e）
  - 一个方法是主方法，在主方法中调用useEatable方法

```java
public interface Eatable {
    void eat();
}
public class EatDemo {
    public static void main(String[] args) {
        useEatable(()->{
            System.out.println("调用了Eatable接口");
        });
    }
    public static void useEatable(Eatable e){
        e.eat();
    }
}
```

练习2：

- 定义一个接口（Flyable），里面定义一个抽象方法void fly(String s)
- 定义一个测试类（FlyableDemo），测试类中提供两个方法
  - 一个方法：useFlyable（Flyable f）
  - 一个方法是主方法，在主方法中调用useFlyable方法

```java
public interface Flyable {
    void fly(String s);
}
public class FlyableDemo {
    public static void main(String[] args) {
        useFlyable((String s)->{
            System.out.println(s);
        });
    }
    public static void useFlyable(Flyable f){
        String s = "老鹰能飞的很快";
        f.fly();
    }
}
```

练习3：

- 定义一个接口（Addable），里面定义一个抽象方法int add(int x,int y)
- 定义一个测试类（AddableDemo），测试类中提供两个方法
  - 一个方法：useAddable（Addable a）
  - 一个方法是主方法，在主方法中调用useAddable方法

```java
public interface Addable {
    int add(int x ,int y);
}
public class AddableDemo {
    public static void main(String[] args) {
        useAdd((int x, int y) -> {
            return x + y;
        });
    }
    public static void useAdd(Addable a) {
        int sum = a.add(10, 10);
        System.out.println("sum:" + sum);
    }
}
```



##### Lambda表达式的省略模式

```java
public interface Addable {
    int add(int x ,int y);
}
public interface Flyable {
    void fly(String s);
}
public class AddableDemo {
    public static void main(String[] args) {
        /*
        useAdd((int x, int y) -> {
            return x + y;
        });
        useFlyable((String s)->{
            System.out.println(s);
        });
        */
        	//表达式中参数的类型可以省略不写，但如果有多个参数，要么都不写要么都写
        /*
        useAdd((x, y) -> {
            return x + y;
        });
        useFlyable((s)->{
            System.out.println(s);
        });
        */
        	//表达式的如果只有一个形式参数，括号可以不写
        /*
        useFlyable(s->{
            System.out.println(s);
        });
        */
        	//表达式的代码块中如果只有一条语句，可以省略大括号和分号，如果有return，则省略return
        useAdd((x, y) -> x + y);
        useFlyable(s -> System.out.println(s));
    }
    public static void useAdd(Addable a) {
        int sum = a.add(10, 10);
        System.out.println("sum:" + sum);
    }
     public static void useFlyable(Flyable f){
        String s = "老鹰能飞的很快";
        f.fly();
    }
}
```

**省略规则：**

- 表达式中参数的类型可以省略，但如果有多个参数，要么都不写要么都写
- 表达式的如果只有一个形式参数，括号可以不写
- 表达式的代码块中如果只有一条语句，可以省略大括号和分号，如果有return，return也可以省略

##### Lambda表达式使用的注意事项：

- 使用Lambda表达式必须要有接口，且接口中有且只有一个抽象方法
- 必须要有上下文环境，才可以推导出lambda对应的接口
  - 根据**局部变量的赋值**得知Lambda对应的接口：Runnable r = ()->System.out.println("Lambda表达式");
  - 根据**调用方法的参数**得知Lambda对应的接口：new Thread(()->System.out.println("Lambda表达式")).start();

### 17.3 Lambda表达式和匿名内部类的区别

**所需类型不同**

- 匿名内部类：可以是接口，也可以是抽象类，还可以是具体类
- Lambda表达式：只能是接口

**使用限制不同**

- 如果接口中只有一个抽象方法，可以使用Lambda表达式，也可使用匿名内部类
- 如果接口中有多于一个抽象方法，只能使用匿名内部类

**实现原理不同**

- 匿名内部类：**编译以后，产生一个单独的.class字节码文件**
- Lambda表达式：编译之后，没有一个独立的.class字节码文件，对应的字节码文件在运行的时候动态生成

### 17.4 接口组成更新

#### 17.4.1接口组成更新概述

**接口的组成**

- 常量
  - public static final 

- 抽象方法
  - public abstract

- 默认方法（Java8）
- 静态方法（Java8）
- 私有方法（Java9）



#### 17.4.2接口中默认方法

**接口中默认方法的格式：**

- 格式：public **default** 返回值类型 方法名(参数列表){}

**接口中默认方法的注意事项：**

- 默认方法不是抽象方法，所以不强制被重写，但是可以被重写，重写的时候去掉default关键字
- public可以被省略，default不可以被省略



#### 17.4.3接口中的静态方法

**接口中静态方法的定义格式：**

- 格式：public static 返回值类型 方法名(参数列表){}

**接口中静态方法的注意事项：**

- 静态方法只能通过接口名调用，不能通过实现类或者对象调用
- public可以省略，static不能省略



#### 17.4.4接口中的私有方法

**私有方法形成环境**

​		当两个默认方法或者静态方法中包含一段相同的代码实现时，程序必然考虑将这段代码抽取为一个共性方法，这个共性方法不需要让别人使用，因此用私有标识符隐藏起来

**接口中定义私有方法的定义格式：**

- 格式1：private 返回值类型 方法名(参数列表){}
- 格式2：private static 返回值类型 方法名(参数列表){}

**接口中私有方法的注意事项：**

- 默认方法可以调用私有静态方法和非静态方法
- 静态方法只能调用私有静态方法



### 17.5方法引用

在使用Lambda表达式时，我们实际传递进去的代码就是一种解决方案：拿参数做操作

那么考虑一种情况：如果我们在Lambda中所指定的操作方案，已经有地方存在相同的的方案，那么是否还有必要再重写逻辑呢？

答案当然是没有必要，那么我们又是如何使用已经存在的方案呢？

这就是我们要学习的方法引用，我们就是**通过方法引用来使用已经存在的方案**

**为什么要使用方法引用?**

如果lambad体中的内容有方法已经实现了，我们可以使用方法引用，可以理解为方法引用是lambad[表达式](https://so.csdn.net/so/search?q=表达式&spm=1001.2101.3001.7020)的另外一种表现形式

#### 17.5.1体验方法引用

```java
public interface Printable {
    void printString(String s);
}
public class PrintableDemo {
    public static void main(String[] args) {
//        lambda表达式
//        usePrint(s -> System.out.println(s));

//        实际上的解决方案
//        System.out.println("爱生活，爱Java");

//        方法引用改进
        //原理是将s直接传递给了System.out对象下的println方法
        usePrint(System.out::println);
    }

    public static void usePrint(Printable p) {
        p.printString("爱生活，爱Java");
    }
}
```



#### 17.5.2方法引用符

**方法引用符**

- :: 该符号为方法引用运算符，而它所在的表达式被称为方法引用表达式

**回顾在前面体验的方法引用中的代码**

- Lambda表达式：usePrint(s->System.out.println(s));

  分析：拿到参数s后通过Lambda表达式传递给System.out.println()方法去处理

- 方法引用：usePrint(System.out**::**println);

  分析：直接使用System.out中的println方法来取代Lambda，usePrint方法得到s后传递给System.out对象的Println方法中，代码更加简洁

**推导和省略**

- 如果使用Lambda，那么根据“可推导可省略”的原则，无需指定参数类型，也无需指定重载形式，它们都将自动被推导
- 如果使用方法引用，也是同样可以进行上下文推导
- 方法引用是Lambda的孪生兄弟



#### 17.5.3Lambda表达式支持的方法引用

**常见的引用方式**

- 引用类方法
- 引用对象的实例方法
- 引用类的实例方法
- 引用构造器



##### 引用类方法

引用类方法，其实就是引用类的静态方法

- 格式：**类名::静态方法**

引用练习：

- 定义一个接口（Converter），里面定义一个抽象方法int convert(String s)

- 定义一个测试类（ConverterDemo），在测试类中提供两个方法

  一个方法是useConverter(Converter c)

  一个是main方法，在主方法体中调用useConverter方法

```java
public interface Converter {
    int convert(String s);
}
public class ConverterDemo {
    public static void main(String[] args) {
//        Lambda方法
//        useConverter(s -> Integer.parseInt(s));

//        方法引用
        useConverter(Integer::parseInt);
//      Lambda表达式被类方法替代时，它的形式参数全部传递给静态方法作为参数

    }
    public static void useConverter(Converter c){
        int i = c.convert("12345");
        System.out.println(i);
    }
}
```



##### 引用对象的实例方法

引用对象的实例方法，其实就引用类中的成员方法

- 格式：**对象::成员方法**

- 范例：**"hello"::toUpperCase**

  String类中的方法：**public String toUpperCase()将此String所有字符转换为大写**

引用练习：

- 定义一个类（PrintString），里面定义一个方法

  public void printUpper(String s)：把字符串参数变成大写的数据，然后在控制台输出

- 定义一个接口（Printer），里面定义一个抽象方法

  void printUpperCase(Stirng s)

- 定义一个测试类（PrinterDemo），在测试类中提供两个方法

  一个方法是usePrinter(Printerc)

  一个是main方法，在主方法体中调用usePrinter方法

```java 
public interface Printer {
    void printUpperCase(String s);
}
public class PrintString {
    public void printUpper(String s){
        System.out.println(s.toUpperCase());
    }
}
public class PrinterDemo {
    public static void main(String[] args) {
//        Lambda表达式
        usePrinter(s -> System.out.println(s.toUpperCase()));

//        引用方法
//        PrintString ps = new PrintString();
//        usePrinter(ps::printUpper);
        usePrinter(new PrintString()::printUpper);
//        Lambda表达式被对象的实例方法替代的时候，它的形式参数全部传递给该方法作为参数
    }

    public static void usePrinter(Printer p){
        p.printUpperCase("abcdefg");
    }
}
```



##### 引用类的实例方法

引用类的实例方法，就是引用类的成员方法

- 格式：**类名::成员方法**

- 范例：**String::substring**

  String类中的方法：**public String substring (int beginIndex,int endIndex)**

  从beginIndex开始到endIndex结束，截取字符串，返回一个字串，字串的长度为endIndex-beginIndex

引用练习：

- 定义一个接口（MyString），里面定义一个抽象方法String mySubString(String s,int x,int y)

- 定义一个测试类（MyStringDemo），在测试类中提供两个方法

  一个方法是useMyString(MyString m)

  一个是main方法，在主方法体中调用useMyString方法

```java
public interface MyString {
    String mySubString(String s,int x,int y);
}
public class MyStringDemo {
    public static void main(String[] args) {
//        Lambda方法
//        useMyString((s,x,y) -> s.substring(x,y));

//        引用类的实例方法
        useMyString(String::substring);
//      Lambda表达式被类方法替代时，它有三个参数
//		它的第一个参数作为这个方法的调用者，后面的参数全部传递给该方法作为参数

    }
    public static void useMyString(MyString m){
        String s = m.mySubString("helloworld",2,4)
        System.out.println(s);
    }
}
```



##### 引用构造器

引用构造器，即引用类的构造方法

- 格式：类名::new
- 范例：Student::new

引用练习：

- 定义一个类（Student），里面有两个成员变量（name，age）

  并提供无参构造和带参构造方法，以及成员对应的get/set方法

- 定义一个接口（StudentBuilder），里面定义一个抽象方法

  Student build(String name,int age)

- 定义一个测试类（StudentDemo），在测试类中提供两个方法

  一个方法是useStudentBuilder(StudentBuilder s)

  一个是main方法，在主方法体中调用useStudentBuilder方法

```java
public interface StudentBuilder {
    Student build(String name,int age);
}
public class Student {
    private String name;
    private int    age;
    public Student() {
    }
    public Student(String name, int age) {
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
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
public class StudentDemo {
    public static void main(String[] args) {
//        Lambda表达式
//        useStudentBuilder(((name, age) -> new Student(name,age)));
//        引用构造器
        useStudentBuilder(Student::new);
//        Lambda表达式被构造器替代的时候，它的形式参数全部传递给构造器作为参数
    }
    public static void useStudentBuilder(StudentBuilder sb){
        Student s = sb.build("张三", 19);
        System.out.println(s);
    }
}
```



## 18 函数式接口

### 18.1函数式接口概述

**函数式接口**：有且只有一个抽象方法的接口

Java中函数式编程体现的就是Lambda表达式，函数式接口可以适用于Lambda表达式使用的接口

只有确保接口中有且仅有一个抽象方法，Java中的Lambda才能顺利的进行推导



**如何检测一个接口是否是函数式接口呢？**

- **@FunctionalInterface**
- 该注解放在接口上方，标识该接口为函数式接口，如果接口不符合函数式接口条件则报错
- 我们自己定义函数式接口时，@FunctionalInterface是可选的，就算不写这个注解，只要满足函数式接口的定义条件，也照样是函数式接口，**但是建议加上**该注解



### 18.2函数式接口作为方法的参数

需求：定义一个类（RunnableDemo），在类中提供两个方法

- 一个方法是startThread（Runnable r），方法参数Runnable是一个函数式接口
- 一个方法是main函数，里面调用startThread方法

```java
/*需求：定义一个类（RunnableDemo），在类中提供两个方法

- 一个方法是startThread（Runnable r），方法参数Runnable是一个函数式接口
- 一个方法是main函数，里面调用startThread方法*/
public class RunnableDemo {
    public static void main(String[] args) {
//      匿名内部类的方法啊调用startRunnable方法
        /*startRunnable(new Runnable() {
            @Override
            public void run() {
                System.out.println(Thread.currentThread().getName()+"线程启动了");
            }
        });*/

//        Lambda表达式来进行改进
        startRunnable(()-> System.out.println(Thread.currentThread().getName()+"线程启动了"));
    }

    public static void startRunnable(Runnable r){
//        Thread t = new Thread(r);
//        t.start();
        new Thread(r).start();
    }
}
```

### 18.3函数式接口作为方法的返回值

需求：定义一个类（ComparatorDemo），在类中提供两个方法

- 一个方法是Comparator<String>getComparator()，方法返回值Comparator是一个函数式接口
- 一个方法是main函数，里面调用getComparator方法

```java
public class ComparatorDemo {
    public static void main(String[] args) {
//        构造使用场景
//        定义集合，存储字符串元素
        ArrayList<String> arrayList = new ArrayList<String>();
        arrayList.add("aaaaa");
        arrayList.add("ddd");
        arrayList.add("cccc");
        arrayList.add("eee");
        System.out.println("排序前："+arrayList);
//        自然排序
//        Collections.sort(arrayList);
//        按长度排序
        Collections.sort(arrayList,getComparator());
        System.out.println("排序后："+arrayList);
    }

    public static Comparator<String> getComparator(){
//      匿名内部类的方式实现
       /* Comparator<String> comp = new Comparator<String>() {
            @Override
            public int compare(String s1, String s2) {
                return s1.length()-s2.length();
            }
        };
        return comp;*/
        /*return new Comparator<String>() {
            @Override
            public int compare(String s1, String s2) {
                return s1.length()-s2.length();
            }
        };*/

//        Lambda表达式改进
        return (s1,s2) -> s1.length()-s2.length();
    }
}
```

如果一个方法的返回值是函数式接口，我们可以使用Lambda表达式作为结果返回

- ```java
  public static Comparator<String> getComparator(){
  	return (s1,s2) -> s1.length()-s2.length();
  }
  ```

### 18.4常用的函数式接口

Java8在java.util.function包下预定义了大量的函数式接口供我们使用

我们重点学习下面的4个接口

- Supplier接口
- Consumer接口
- Predicate接口
- Function接口



#### 18.4.1Supplier接口

Supplier<T>:包含一个无参方法

- T get()：获得结果
- 该方法不许要参数，它会按照某种逻辑（由Lambda表达式实现）返回一个参数
- Supplier<T>接口也被称为**生产型接口**，如果我们指定了接口的泛型是什么类型，那么接口中的get方法就会生产什么类型的数据供我们使用



练习

- 定义一个类SupplierTest，在类中提供两个方法
  - 一个方法是：int getMax(Supplier<Integer> sup)用于返回一个int数组中的最大值
  - 一个方法是main方法，在主函数中调用getMax方法

```java
/*练习

- 定义一个类SupplierTest，在类中提供两个方法
  - 一个方法是：int getMax(Supplier<Integer> sup)用于返回一个int数组中的最大值
  - 一个方法是main方法，在主函数中调用getMax方法*/
public class SupplierDemo02 {
    public static void main(String[] args) {
        int[] arr = {11,15,12,16,18,15};
//        匿名内部类的方法实现
        /*int i = getMax(new Supplier<Integer>() {
            @Override
            public Integer get() {
                int max = arr[0];
                for (int j = 1;j<arr.length;j++){
                    if(arr[j]>max){
                        max = arr[j];
                    }
                }
                return max;
            }
        });*/
//        Lambda表达式实现
        int i = getMax(()->{
            int max = arr[0];
            for (int j = 1;j<arr.length;j++){
                if(arr[j]>max){
                    max = arr[j];
                }
            }
            return max;
        });

        System.out.println(i);
    }
//    一个方法是：int getMax(Supplier<Integer> sup)用于返回一个int数组中的最大值
    private static int getMax(Supplier<Integer> sup){
        return sup.get();
    }
}
```



#### 18.4.2Consumer接口

Consumer<T>：包含两个方法

- void accept(T t)：对给定的参数执行此操作
- default Consumer<T> andThen(Consumer after)：返回一个组合的Consumer，依次执行此操作，然后执行after操作
- Consumer<T>接口也被称为消费型接口，他消费的数据类型由泛型决定



练习：

- String[] strArray = {"张三,30","李四,27","王五,31"};
- 字符串数组中有多条信息，请按照格式：”姓名：XX，年龄：XX“的格式打印出来
- 要求：
  - 把打印姓名的动作作为第一个Consumer接口的Lambda实例
  - 把打印年龄的动作作为第二个Consumer接口的Lambda实例
  - 将两个Consumer接口按照顺序组合到一起使用

```java
public class ConsumerDemo02 {
    public static void main(String[] args) {
        String[] strArray = {"张三,30", "李四,27", "王五,31"};
        /*operatorStringArray(strArray,(String s)->{
            String name = s.split(",")[0];
            System.out.print("姓名："+name+",");
        },(String s)->{
            int age = Integer.parseInt(s.split(",")[1]);
            System.out.println("年龄："+age);
        });*/

//        简化
        operatorStringArray(strArray,
                s -> System.out.print("姓名：" + s.split(",")[0] + ","),
                s -> System.out.println("年龄：" + Integer.parseInt(s.split(",")[1]))
        );

    }

    private static void operatorStringArray(String[] strArray, Consumer<String> con1, Consumer<String> con2) {
        for (String s : strArray) {
            con1.andThen(con2).accept(s);
        }
    }
}
```



#### 18.4.3Predicate接口

Predicate<T>：常用的四个方法

- boolean test(T t)：对给定的参数进行判断（判断逻辑由Lambda表达式实现），返回一个boolean值
- default Predicate<T> negate()：返回一个逻辑的否定，对应逻辑非
- default Predicate<T> and(Predicate other)：返回一个组合判断，对应短路与
- default Predicate<T> or(Predicate other)：返回一个组合判断，对应短路或
- Predeicate<T>接口通常用于判断参数是否满足指定的条件

练习：

- String[] strArray = {"张三丰,30","李世民,27","王维,31","秦琼,29"};
- 字符串数组中有多条信息，请通过Predicate接口的拼装将符合要求的字符筛选到集合ArrayList中，并遍历ArrayList集合
- 同时满足如下要求：姓名长度大于2，年龄大于30

```java
public class PredicateDemo03 {
    public static void main(String[] args) {
        String[] strArray = {"王维,31", "李世民,27", "张三丰,41", "秦琼,29"};
        /*ArrayList<String> arrayList = checkArray(strArray, (String s) -> {
            String name = s.split(",")[0];
            return name.length() > 2;
        }, (String s) -> {
            int age = Integer.parseInt(s.split(",")[1]);
            return age > 30;
        });*/

//        简化
        ArrayList<String> arrayList = checkArray(strArray, s -> s.split(",")[0].length() > 2, s -> Integer.parseInt(s.split(",")[1]) > 30);

        for (String s : arrayList) {
            System.out.println(s);
        }
    }

    private static ArrayList<String> checkArray(String[] strArray, Predicate<String> p1, Predicate<String> p2) {
        ArrayList<String> array = new ArrayList<String>();
        for (String s : strArray) {
            if (p1.and(p2).test(s)) {
                array.add(s);
            }
        }
        return array;
    }
}
```



#### 18.4.4Function接口

 Function<T,R>:常用的两个方法

- R apply(T t)：将此函数应用于给定的参数
- default <V>Function andThen(Function after)：返回一个组合函数，首先将该函数应用于输入 ，然后将after函数应用于结果
- Function<T,R>接口常用于对参数进行处理，转换（处理逻辑使用Lambda表达式实现），然后后返回一个新的值

练习

- String  s = "张三,30";
- 按照下面要求进行操作：
  - 将字符串截取获得年龄部分
  - 将上一步获取的字符串转换为int类型的数据
  - 将上一步得到的int类型数据加上70，在控制台输出

- 请通过Function接口实现

```java
public class FunctionDemo02 {
    public static void main(String[] args) {
        String str = "张三,30";
//        operatorString(str,s -> str.split(",")[1],s -> Integer.parseInt(s),i -> i+70);
        operatorString(str, s -> str.split(",")[1], Integer::parseInt, i -> i + 70);
    }

    private static void operatorString(String s, Function<String, String> f1, Function<String, Integer> f2, Function<Integer, Integer> f3) {
        int i = f1.andThen(f2).andThen(f3).apply(s);
        System.out.println(i);
    }
}
```



### 18.5 Steam流

**体验Stream流**

需求：按照下面要求完成集合的创建和遍历

- 创建一个集合，存储多个字符串元素
- 把集合中所有以”张“开头的元素存储到一个集合中
- 把”张“开头的集合中长度为3的元素存储到一个新的集合中
- 遍历上一步得到的集合

```java
public class StreamDemo {
    public static void main(String[] args) {
//        创建一个集合，存储多个字符串元素
        ArrayList<String> arrayList = new ArrayList<String>();
        arrayList.add("张三丰");
        arrayList.add("柳岩");
        arrayList.add("张无忌");
        arrayList.add("王维");
        arrayList.add("张三");
        arrayList.add("张曼玉");
//        把集合中所有以”张“开头的元素存储到一个集合中
        ArrayList<String> zhangList = new ArrayList<String>();

        for(String s:arrayList){
            if(s.startsWith("张")){
                zhangList.add(s);
            }
        }
//        System.out.println(zhangList);
//    - 把”张“开头的集合中长度为3的元素存储到一个新的集合中
        ArrayList<String> threeList = new ArrayList<String>();
        for(String s:zhangList){
            if(s.length() == 3){
                threeList.add(s);
            }
        }

        for(String s:threeList){
            System.out.println(s);
        }
        System.out.println("--------------------");

//       使用Stream流来改进上述代码
//        arrayList.stream().filter(s -> s.startsWith("张")).filter(s -> s.length() == 3).forEach(s -> System.out.println(s));
//        方法引用进行改进
        arrayList.stream().filter(s -> s.startsWith("张")).filter(s -> s.length() == 3).forEach(System.out::println);
    }
}
```

使用Stream流的方式完成过滤操作

- arrayList.stream().filter(s -> s.startsWith("张")).filter(s -> s.length() == 3).forEach(System.out::println);
- 直接阅读代码的字面意思即可完美展示无关逻辑方式的语义：生成流，过滤姓张，过滤长度为三，逐一打印
- Stream流把真正的函数式编程风格引入到Java中



#### 18.5.1 Stream流的生成方式

**Stream流的使用**

- **生成流**

  通过数据源（集合，数组等）生成流

  list.stream()

- **中间操作**

  一个流后面可以跟随零个或者多个中间操作，其目的主要是打开流，做出某种程度的数据过滤/映射。然后返回一个新的流，交给下一个操作使用

  filter()

- **终结操作**

  一个流只能有一个终结操作，当这个操作执行后，流就被使用“光”了，无法再被操作

  forEach()

**Stream流的常见生成方式**

- Collection体系的集合可以使用默认的方法stream()生成流

  default Stream<E> stream()

- Map体系的集合间接的生成流
- 数组可以通过Stream接口的静态方法of(T...values)生成流



#### 18.5.2 Stream流的常见中间操作方法

- Stream<T> filter(Predicate predicate):用于对流中的数据进行**过滤**

  Predicate接口中的方法		boolean test(T t)对给定的参数进行判断，返回一个布尔值



- Stream<T> limit(long maxSize):返回此流中的元素组成的流，**截取**前指定个参数个数的数据

- Stream<T> skip(long n):**跳过**指定参数个数的数据，返回此流中的元素组成的流



- static <T> Stream<T> concat(Steam a,Stream b):合并a和b两个流为一个流

- Stream<T> distinct():返回由该流的不同元素（根据Object.equals(Object)）组成的流(去重)



- Stream<T> sorted():返回此流的元素组成的流，根据自然顺序排序

- Stream<T> sorted(Comperator comperator):返回此流的元素组成的流，根据提供的Comperator进行排序



- <R>Stream<R>map(Function mapper):返回由给定函数应用于此流的元素的结果组成的流

  Function接口中的方法         R apply(T t)

- IntStream mapToInt(ToIntFunction mapper):返回一个IntStream其中包含将给定函数应用与此流的元素结果

  IntStream：表示原始int流

  ToIntFunction接口中的方法       int applyAsInt(T value)



#### 18.5.3 Stream流的常见终结操作方法

- void forEach(Consumer action):对此流的每个元素执行操作

  Consumer接口中的方法		void accept(T t)：对给定的参数执行此操作

- long count():返回此流中的元素数





**Stream流练习**

现在有两个ArrayList集合，分别存储6名男演员名称和6名女演员名称，要求完成如下操作

- 男演员只要名字为3个字的前三人

- 女演员只要姓林的，且不要第一个

- 把过滤后的男演员和女演员姓名合并到一起

- 把上一步操作后元素作为构造方法的参数创建演员对象，遍历数据

  演员类Actor已经提供，里面有一个成员变量，一个带参构造方法，以及成员变量对应的get/set方法

```java
public class Demo {
    public static void main(String[] args) {
        List<String> actorList = new ArrayList<String>();
        List<String> actressList  = new ArrayList<String>();
//        男演员集合
        actorList.add("张三丰");
        actorList.add("令狐冲");
        actorList.add("林平之");
        actorList.add("段誉");
        actorList.add("杨过");
        actorList.add("任我行");
        actorList.add("萧峰");
//        女演员集合
        actressList.add("薛宝钗");
        actressList.add("林青霞");
        actressList.add("林黛玉");
        actressList.add("王熙凤");
        actressList.add("甄晴");
        actressList.add("贾元春");
/*
//        男演员只要名字为3个字的前三人
        Stream<String> actorStream = actorList.stream().filter(s -> s.length() == 3).limit(3);
//        女演员只要姓林的，且不要第一个
        Stream<String> actressStream = actressList.stream().filter(s -> s.startsWith("林")).skip(1);

//        把过滤后的男演员和女演员姓名合并到一起
        Stream<String> actStream = Stream.concat(actorStream, actressStream);
//      把上一步操作后元素作为构造方法的参数创建演员对象，遍历数据
//        actStream.map(s -> new Actor(s)).forEach(s -> System.out.println("姓名："+s.getName()));
        actStream.map(Actor::new).forEach(s -> System.out.println("姓名："+s.getName()));
        */

//        简化合并
        Stream.concat(actorList.stream().filter(s -> s.length() == 3).limit(3),
                actressList.stream().filter(s -> s.startsWith("林")).skip(1)).map(Actor::new).forEach(s -> System.out.println("姓名："+s.getName()));
    }
}
```



#### 18.5.4 Stream流的收集操作

对数据使用Stream流的方式操作完毕后，我想把流中的数据收集到集合中，该怎么办呢？

**Stream流的收集方法**

- R collect(Collector collector)
- 但是这个收集方法的参数是一个Collector接口



**工具类Collectors提供了具体的收集方法**

- public static <T> Collector toList()把元素收集到List集合中
- public static <T> Collector toSet()把元素收集到Set集合中
- public static Collector toMap(Function keyMapper,Function valueMapper)把元素收集到List集合中

```java
public class StreamDemo09 {
    public static void main(String[] args) {
/*//        创建List集合对象
        List<String> list = new ArrayList<>();
        list.add("林黛玉");
        list.add("薛宝钗");
        list.add("王熙凤");
        list.add("秦可卿");
        list.add("甄晴");
        list.add("贾元春");

//        需求1：得到名字长度为三个字的流
        Stream<String> nameStream = list.stream().filter(s -> s.length() == 3);

//        需求2：把使用Stream流操作完毕的数据收集到list集合中并遍历
        List<String> name = nameStream.collect(Collectors.toList());
        for(String s :name){
            System.out.println(s);
        }*/
/*
//        创建Set集合对象
        Set<Integer> set = new HashSet<>();
        set.add(20);
        set.add(23);
        set.add(30);
        set.add(18);
        set.add(16);

//        需求3：得到年龄大于20的流
        Stream<Integer> ageStream = set.stream().filter(s -> s > 20);
//        需求4：把使用Stream流操作完毕的数据收集到Set集合中并遍历
        Set<Integer> ages = ageStream.collect(Collectors.toSet());
        for(int i :ages){
            System.out.println(i);
        }
        */

//        定义一个字符串数组，每一个字符串数据由姓名和年龄组成
        String[] strArrays = {"林黛玉,16", "秦可卿,21", "薛宝钗,17", "贾宝玉,17", "王熙凤,26"};

//        需求5：得到字符串中年龄数组大于20的流
        Stream<String> strStream = Stream.of(strArrays);
        Stream<String> ageStream = strStream.filter(s -> Integer.parseInt(s.split(",")[1]) > 20);

//        需求6：把使用Stream流操作完毕的数据收集到Map集合中并遍历，字符串中姓名作为键，年龄作为值
        /*
        IllegalStateException: stream has already been operated upon or closed报错：
        Stream流只能被操作或消费一次，再次消费就会报错
        */
        Map<String, Integer> strMap = ageStream.collect(Collectors.toMap(s -> s.split(",")[0], ss -> Integer.parseInt(ss.split(",")[1])));
        Set<String> keySet = strMap.keySet();
        for (String s : keySet) {
            Integer value = strMap.get(s);
            System.out.println("姓名：" + s + ",年龄：" + value);
        }

    }
}
```



## 19 反射

### 19.1类加载器

#### 19.1.1类加载

当程序要使用某个类时，如果该类还未被加载到内存中，则系统会通过**类的加载，类的连接，类的初始化**这三个步骤来对类进行初始化。如果不出现意外情况，JVM将会连续完成这三个步骤，所有有时也把这三个步骤统称为类加载或者类初始化



**类的加载**

- 就是指将.class文件读入内存，并为之创建一个java.lang.Class对象
- 任何类被使用时，系统都会为之建立一个java.lang.Class对象

**类的连接**

- 验证阶段：用于检验被加载的类是否有正确的内部结构，并和其他类协调一致
- 准备阶段：负责为类的类变量分配内存，并设置默认初始化值
- 解析阶段：将类的二进制数据中的符号引用替换为直接引用

**类的初始化**

- 在该阶段，主要就是对类变量进行初始化



**类的初始化步骤**

- 假如类还未被加载和连接，则程序先加载并连接该类
- 假如该类的直接父类还未被初始化，则先初始化其直接父类
- 假如类中有初始化语句，则系统依次执行这些初始化语句

**注意**：在执行第二个步骤，系统对直接父类的初始化步骤也遵循初始化步骤1-3



**类的初始化时机**

- 创建类的实例
- 调用类的类方法
- 访问类或者接口的类变量，或者为该类变量赋值
- 使用反射的方式来强制创建某个类或接口对应的java.lang.Class对象
- 初始化某个类的子类
- 直接使用java.exe命令来运行某个主类



#### 19.1.2类加载器

**类加载器的作用**

- 负责将.class文件加载到内存中，并为之生成对应的java.lang.Classs对象
- 虽然我们不用过分了解类加载机制，但是了解这个机制我们能更好的理解程序的运行

**JVM的类加载机制**

- **全盘负责**：就是当一个类加载器负责加载某个Class时，该Class所依赖的和引用的其他也将由该类加载器负责载入，除非显示使用另一个类加载器来载入
- **父类委托**：就是当一个类加载器负责加载某个Class时，先让其父类加载器试图加载该Class，只有在父类加载器无法加载该类时才尝试从自己的类路径中加载该类
- **缓存机制：**保证所有加载过的Class都会被缓存，当程序需要使用某个Class对象时，类加载器先从缓冲区中搜索该类Class，只有当缓冲区中不存在该Class对象时，系统才会读取该类对应的二进制文件，并将其转换成Class对象，存储到缓存区



**ClassLoader**：是负责加载类的对象

**Java运行时具有以下内置类加载器**

- **Bootstrap class loader**： 它是虚拟机的**内置类加载器**，通常表示为null，并且没有父null
- **Platform class  loader**：**平台类加载器**可以看到所有平台类，平台类包括由平台类加载器或其祖先定义的Java SE平台API，其实现类和JDK特定的运行时类
- **System  class loader**：它也被称为**应用程序类加载器**，与平台类加载器不同，系统类加载器通常用于定义应用程序类路径，模块路径和JDK特定工具上的类
- **类加载器的继承关系：System的父加载器为Platform，而Platform的父加载器为Bootstrap**



**ClassLoader中的两个方法**

- static ClassLoader getSystemClassLoader()：返回用于委派的系统类加载器
- ClassLoader getParent()：返回父类加载器进行委派



### 19.2反射

#### 19.2.1反射概述

**Java反射机制**：是指在**运行时去获取一个类的变量和方法信息**，然后**通过获取到的信息来创建对象**，调用方法的一种机制。由于这种动态性，可以极大的增强程序的灵活性，**程序不用在编译期就完成确定，在运行期仍然可以扩展**



#### 19.2.2 获取Class类的对象

我们想要通过反射去使用一个类，**首先我们就要获取到该类的字节码文件对象**，也就是类型为Class类型的对象

**这里我们提供三种方式获取Class类型对象**

- 使用类的**Class属性**来获取该类对应的Class对象。举例：Student.class将会返回Student类对应的Class对象

- 调用对象的**getClass()**方法，返回该对象所属类对应的Class对象

  该方法是Object类中的方法，所有Java对象都可以调用该方法

- 使用Class类中的静态方法**forName(String className)**，该方法需要传入字符串参数，**该字符串参数的值是某个类的全路径，也就是完整包名的路径**

**第一种方式最方便，在普通编程环境下，最适合使用**

**第三种方式最灵活，我们可以将字符串写入到一个配置文件中，更加方便的调用**



#### 19.2.3反射获取构造方法并使用

**Constructor**提供了一个类的单个构造函数的信息和访问权限



**Class类中用于获取构造方法Constructor的方法**

- Constructor<?>[] getConstructors()：返回所有**公共**构造方法对象的**数组**
- Constructor<?>[] getDeclaredConstructor()：返回所有构造方法的对象**数组**
- Constructor<T> getConstructor(Class<?>...parameterTypes)：返回单个**公共**构造方法对象
- Constructor<T> getDeclaredConstructor(Class<?>...parameterTypes)：返回单个构造方法对象

parameterTypes构造方法的类型Class对象

例如：Constructor<T> getConstructor(String.class,int.class,String.class)

**Constructor类中用于创建对象的方法**

- T newInstance(Object...initargs)：根据指定的构造方法创建对象



练习1：通过反射实现如下操作

- Student s = new Student("林黛玉",18,"江西");
- System.out.println(s);

```java
public class ReflectionDemo03 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {
//        获取Student类的Class对象
        Class<?> c = Class.forName("Reflection.Student");
//        通过Class对象获取Student类的构造方法对象
//        public Student(String name, int age, String address)
        Constructor<?> con = c.getDeclaredConstructor(String.class, int.class, String.class);
//        基本数据类型也可以通过.class得到对应的Class类型

//        通过Constructor调用newInstance()方法创建对象
        Object obj = con.newInstance("林黛玉", 18, "江西");
        System.out.println(obj);
    }
}
```

**基本数据类型也可以通过.class得到对应的Class类型**



练习2：通过反射实现如下操作

- Student s = new Student("林黛玉");
- System.out.println(s);

```java
public class ReflectionDemo04 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {
//        获取类的Class对象
        Class<?> c = Class.forName("Reflection.Student");
//        通过Constructor获取构造方法对象
//        private Student(String name)
        Constructor<?> con = c.getDeclaredConstructor(String.class);

//        通过构造方法对象构造对象
//        Object obj = con.newInstance("林黛玉");
//        报错：无法通过对象调用私有方法

/*        解决方法：暴力反射
*              public void setAccessible(boolean flag)将此反射对象的accessible标志设置为指示的布尔值，值为true表示反射对象应该在使用Java语言访问控制时抑制检查。
* */
        con.setAccessible(true);
        Object obj = con.newInstance("林黛玉");
        System.out.println(obj);
    }
}
```

- public void setAccessible(boolean flag)
- 将此反射对象的accessible标志设置为指示的布尔值，值为true表示反射对象应该在使用Java语言访问控制时抑制检查



#### 19.2.4反射获取成员变量并使用

**Class类中用于获取成员变量的方法**

- Field[] getFields()：返回所有**公共**成员变量对象的**数组**
- Field[] getDeclaredFields()：返回所有成员变量对象的**数组**
- Field getField(String name)：返回单个**公共**成员变量对象
- Field getDeclaredField(String name)：返回单个成员变量对象



**Field类中用于给成员变量赋值的方法**

- void set(Object obj,Object value)：给**obj对象的成员变量赋值为value**



练习：通过反射实现如下操作

- Student s = new Student();
- s.name = "林黛玉";
- s.age = 16;
- s.address = "杭州";
- System.out.println(s);

```java
public class ReflectionDemo06 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, NoSuchFieldException, InvocationTargetException, InstantiationException, IllegalAccessException {
//        获取Class对象
        Class<?> c = Class.forName("Reflection.Test01.Student");
//        获取构造方法对象
        Constructor<?> con = c.getConstructor();//无参构造方法
//        获取成员变量对象
        Field name = c.getDeclaredField("name");
        Field age = c.getDeclaredField("age");
        Field address = c.getDeclaredField("address");
//        通过构造方法对象创建类对象
        Object obj = con.newInstance();
//        给对象的成员变量赋值
//        name.set(obj,"林黛玉");报错：私有成员变量无法通过调用方法进行赋值
//        age.set(obj,16);报错：默认成员变量无法通过调用方法进行赋值
       /* 解决方法：暴力反射
       * void setAccessible(boolean flag) 将此反射对象的accessible标志设置为指示的布尔值， 值为true表示反射对象应该在使用Java语言访问控制时抑制检查
        * */

        name.setAccessible(true);
        name.set(obj,"林黛玉");
        age.setAccessible(true);
        age.set(obj,16);
        address.set(obj,"杭州");

        System.out.println(obj);
    }
}
```



#### 19.2.5反射获取成员方法并使用

**Class类用于获取成员方法的方法**

- Method[] getMethods()：返回所有公共成员方法对象的数组，**包括继承父类的方法以及实现接口方法等**
- 
  Method[] getDeclaredMethods()： 返回所有成员方法对象的数组，但**不包括继承方法**。

- Method getMethod(String name, Class<?>... parameterTypes)：返回单个公共成员方法对象
- Method getDeclaredMethod(String name, Class<?>... parameterTypes) ：返回单个成员方法对象



**Method类中用于调用成员方法的方法**

Method在类或接口上提供有关单一方法的信息和访问权限

Object invoke(Object obj, Object... args) 在具有指定参数的指定对象上调用此 方法对象表示的基础方法

Object:返回类型       obj:调用方法对象      args:方法需要的参数



练习：通过发射实现如下操作

- Student s = new Student();
- s.method1();
- s.method2("林黛玉");
- String ss = s.method3("林黛玉",16);
- System.out.println(ss);
- s.function();

```java
public class ReflectionDemo08 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {
//        获取Class对象
        Class<?> c = Class.forName("Reflection.Test01.Student");
//        获取无参构造方法并创建对象
        Constructor<?> con = c.getConstructor();
        Object obj = con.newInstance();
//        获取成员方法对象
        Method method01 = c.getDeclaredMethod("method01");
        Method method02 = c.getDeclaredMethod("method02", String.class);
        Method method03 = c.getDeclaredMethod("method03", String.class, int.class);

        method01.invoke(obj);
        method02.invoke(obj,"林黛玉");
        Object ss = method03.invoke(obj, "林黛玉", 16);
        System.out.println(ss);

        Method function = c.getDeclaredMethod("function");
        function.setAccessible(true);
        function.invoke(obj);
    }
}
```



#### 19.2.6反射练习

练习1：有一个ArrayList<Integer>集合，我现在要在这个及合作添加一个字符串数据，如何实现？

```java
public class ReflectionDemo01 {
    public static void main(String[] args) throws NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        ArrayList<Integer> arrayList = new ArrayList<>();
        arrayList.add(100);
        arrayList.add(120);
//        获取Class对象
        Class<? extends ArrayList> c = arrayList.getClass();
//        获取集合对象的成员方法
        Method add = c.getDeclaredMethod("add", Object.class);
//        调用方法添加数据进集合中
        add.setAccessible(true);
        add.invoke(arrayList,"hello");

        System.out.println(arrayList);
    }
}
```

练习2：通过配置文件运行类中的方法

```java
public class ReflectionDemo02 {
    public static void main(String[] args) throws IOException, ClassNotFoundException, NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {
        /*
            class.txt中配置
            className = xxx
            classMethod = xxx
        */
//      加载数据
        Properties prop = new Properties();
        FileReader fr = new FileReader("19Reflection/src/Reflection/Test05/class.txt");
        prop.load(fr);
        fr.close();
        String className = prop.getProperty("className");
        String classMethod = prop.getProperty("classMethod");

//        获取Class类型对象
        Class<?> c = Class.forName(className);
//        获取无参构造方法，创建对象
        Constructor<?> con = c.getConstructor();
        Object obj = con.newInstance();

//        获取成员方法对象
        Method m = c.getDeclaredMethod(classMethod);
        m.setAccessible(true);
        m.invoke(obj);
    }
}
```



## 20 模块化

### 20.1模块化概述

Java语言随着这些年的发展已经成为了一门影响深远的编程语言，无数平台，系统都采用Java语言编写。但是随着发展，Java也越来越庞大，逐渐发展成为一门”臃肿“的语言。而且，无论是运行一个大型的软件系统，还是运行一个小程序，即使程序只需要使用Java的部分核心功能，JVM也要加载整个JRE环境

为了给Java”瘦身“，让Java实现轻量化，Java9正式推出了模块化系统。Java被拆分为N多个模块，并允许Java程序可以根据需要选择加载程序必须的Java模块，这样就可以让Java以轻量化的方式来运行

其实，Java7的时候已经提出了模块化的概念，但由于其过于复杂，Java7，Java8都一直未能真正推出，直到Java9才真正成熟起来。对于Java而言，模块化系统是一次真正的自我革新，这种革新使得”古老而庞大“的Java语言重新焕发出年轻的活力

![](C:\Users\Asinil\Desktop\学习\Java\20.1.png)



### 20.2模块的基本使用

**模块的基本使用步骤**

- 创建模块（按照以前的讲解方式创建模块，创建包，创建类，定义方法）

  为了体现模块的使用，我们创建2个模块，一个是myOne，一个是myTwo

- 在模块的src目录下新建一个名为**module-info.java**的描述性文件，该文件专门定义模块名，访问权限，模块依赖等信息

  描述性文件中使用**模块导出**和**模块依赖**来进行配置使用

- 模块中所有未导出的包都是模块私有的，他们是不能在模块之外被访问的

  在myOne这个模块下的描述性文件中配置模块导出

  **模块导出格式：export 包名;**

- 一个模块要访问其他模块，必须明确指定依赖哪些模块，未明确指定依赖的模块不能访问

  在myTwo这个模块下的描述性文件中配置模块依赖

  **模块依赖格式：requires 模块名;**

**注意：写模块名报错，需要按下Alt+Enter提示，然后选择模块依赖**

- 在myTwo模块下的类中就可以使用依赖模块下的内容



### 20.3模块服务的使用

**服务**：从Java6开始，Java提供了一种服务机制，允许服务提供者和服务使用者之间完成解耦

简单的说，就是**服务使用者只面向接口编程，但不清楚服务提供者的实现类**

Java9的模块化系统则进一步简化了Java的服务机制。Java9允许将服务接口定义在一个模块中，并使用**uses**语句来声明该服务接口，然后针对该服务接口提供不同的服务实现类，这些服务实现类可以分布在不同的模块中，服务实现模块则使用**provides**语句为服务接口指定实现类

服务使用者只需要面向程序编程即可



**模块服务的使用步骤**

- 在myOne模块下创建一个包com.test_03，在该包下提供一个接口，接口中定义一个抽象方法

  public Interface MyService{

  ​	void service

  }

- 在com.test_03包下创建一个包impl，在该包下提供接口的两个实现类SchoolOfComputer和SchoolOfAI

- 在myOne这个模块下的描述性文件中添加如下配置

  模块导出：exports com.test_03;

  服务提供：**provides** MyService with SchoolOfComputer;		指定MyService的服务实现类是SchoolOfComputer

- 在myTwo这个模块下的描述性文件在添加如下配置

  声明服务接口：**uses** MyService;

- 在myTwo下的类中使用MyService接口提供的服务

  **ServiceLoader**：一种加载服务实现类



## 21 进制

### 21.1进制基础知识

**进制概述**：指进位制，是一种计数方式，也被称为进位计数法或位值计数法

十进制：0，1，2，3，4，5，6，7，8，9

**R进制**：由0~（R-1）个数组成，并且每一位上的数据逢R进1



我们的计算机是由逻辑电路组成，逻辑电路通常只有两个状态：开关的接通与断开

这两种状态正好可以使用“1”和“0”进行表示，也就是我们要学习的组成二进制的数字符号

二进制：1和0



虽然计算机喜欢二进制，但是使用二进制表示的数据太长了

为了解决这个问题，八进制和十六进制就来了

八进制：0，1，2，3，4，5，6，7

十六进制：0，1，2，3，4，5，6，7，8，9，**A，B，C，D，E，F（大小写均可）**



举例：使用二进制，八进制，十六进制分别表示同一个数

二进制：10000000000

八进制：2000

十六进制：400

**结论：进制越大，表现形式越短**



**常见进制的数据组成：**

**二进制**：1和0。在Java中以**0b**开头

**八进制**：0，1，2，3，4，5，6，7。在Java中以**0**开头

**十进制**：0，1，2，3，4，5，6，7，8，9。整数**默认**是十进制

**十六进制**：0，1，2，3，4，5，6，7，8，9，**A，B，C，D，E，F（大小写均可）**。在Java中以**0x**开头



练习：在控制台输出下面数据，看结果是多少

0b10000000000

02000

0x400

```java
public class Demo01 {
    public static void main(String[] args) {
        System.out.println(0b10000000000);//1024
        System.out.println(02000);//1024
        System.out.println(0x400);//1024
    }
}
```



### 21.2进制转换

**R进制到十进制的转换**

**规则：按权展开法（系数*基数的权次幂相加）**

- 系数：每一位上的数
- 基数：R进制，R就是基数
- 权：从数值的右侧，以0开始编号，对应位上的编号就是该位上的权
- 举例：0b101010 = 1x2^1+1x2^3+1x2^5



**十进制到R进制的转换**

**规则：重复相除法（除基取余，直到商为0，余数反转）**

- 例：把42转换为二进制

| 十进制数 | 基数 |  商   | 余数  |
| :------: | :--: | :---: | :---: |
|    42    |  2   |  21   | **0** |
|    21    |  2   |  10   | **1** |
|    10    |  2   |   5   | **0** |
|    5     |  2   |   2   | **1** |
|    2     |  2   |   1   | **0** |
|    1     |  2   | **0** | **1** |

所以42转换为二进制数为0b101010



**如何实现二进制和十进制的快速转换呢？**

采用8421码可以实现



8421码：是BCD代码中最常用的一种

BCD：（Binary-Coded Decimal）二进制码十进制数，在这种编码方式中，每一位二进制代码的1都是代表一个固定的数值，把每一个的1代表的十进制数加起来得到的结果就是它所代表的十进制数码

![](C:\Users\Asinil\Desktop\学习\Java\21.2.png)

**二进制到八进制如何转换？**

**思路1**：把二进制转换为十进制，然后再把该十进制数转换为八进制

**思路2**：**三位组合法（0b111为7）**

把二进制的数据，从右开始，每三位一组合，最左边不够的时候，补0

然后，分别计算对应的十进制数值

最后，从左往右，把每一个十进制的数据组合起来，就是一个八进制数据



例如：二进制数0b1101011

拆分为001，101，011   计算为1，5，3

八进制数为0153

**从八进制到二进制则用三位组合法反过来即可**



**二进制到十六进制转换**

按照刚才的思路提供一个方法：**四位组合法（0b1111为15）**

把二进制的数据，从右开始，每四位一组合，最左边不够的时候，补0

然后，分别计算对应的十进制数值

最后，从左往右，把每一个十进制的数据组合起来，就是一个十六位进制数据

例如：二进制数0b1101011

拆分为0110，1011   计算为7，11（B）

十六进制数为0x7B

**从十六进制到二进制则用四位组合法反过来即可**



### 21.3Java内置的进制转换

**java.lang.Integer 类中的静态方法：**

public static String toBinaryString(int i)  ：在基数2中返回整数参数的字符串表示形式为无符号整数

public static String toOctalString(int i)：在基数8中返回整数参数的字符串表示形式为无符号整数

public static String toHexString(int i) ：返回整数参数的字符串表示形式，作为16位中的无符号整数



public static String toString(int i,  int radix)：返回由第二个参数指定的基数中的第一个参数的字符串表示形式

```java
public class Demo02 {
    public static void main(String[] args) {
//         public static String toBinaryString(int i)  ：在基数2中返回整数参数的字符串表示形式为无符号整数
        System.out.println(Integer.toBinaryString(42));
//        public static String toOctalString(int i)：在基数8中返回整数参数的字符串表示形式为无符号整数
        System.out.println(Integer.toOctalString(42));
//        public static String toHexString(int i) ：返回整数参数的字符串表示形式，作为16位中的无符号整数
        System.out.println(Integer.toHexString(42));
        System.out.println("----------------------");

//         public static String toString(int i,  int radix)：返回由第二个参数指定的基数中的第一个参数的字符串表示形式
        System.out.println(Integer.toString(0b101010,10));
        System.out.println(Integer.toString(052,10));
        System.out.println(Integer.toString(0x2a,10));
        System.out.println("----------------");
//			将其他进制转八进制
        System.out.println(Integer.toString(0x2a,8));
        System.out.println(Integer.toString(0b101010,8));

    }
}
```



### 21.4有符号数据表示法

十进制的数据：

- +表示正数，-表示负数

计算机中的数据：

- 1表示负数，0表示正数

而对于计算机识别的数据来说，0和1本省也表示数据值，那么我们怎么判断它是数值还是符号位呢？

**规定：符号位位于数值第一位**

例如：二进制数0b101010，用一个字节来存储

![](C:\Users\Asinil\Desktop\学习\Java\21.4.png)

这就是我们有符号数据表示法的一种表示形式，叫做**源码表示法**



#### 原码表示法

是最简单的机器数表示法。用最高位表示符号位，1表示负号，0表示正号，其余位表示数值大小

![](C:\Users\Asinil\Desktop\学习\Java\21.4.2.PNG)

**原码表示法只能适用于两个正数相加，不适用一正一负或两个负数相加**



#### 反码表示法

- 正数的反码和原码相同
- 负数的反码就是它们原码**除符号位**外，按位去反（1取0，0取1）

![](C:\Users\Asinil\Desktop\学习\Java\21.4.3.PNG)

**反码表示法能适用于两个正数加和一正一负相加（相加后的值按照反码对照），但不适用于两个负数相加**



#### 补码表示法

- 正数的补码和原码相同
- 负数的补码等于反码+1

![](C:\Users\Asinil\Desktop\学习\Java\21.4.4.PNG)

**补码能够完美的完成正负数的相加操作，计算机的底层运算逻辑也是通过补码实现的**，计算过程中，**符号进位舍弃**



练习：

- 已知某个数X的源码为0b10110100，试求出X的补码和反码
- 已知某个数X的补码0b11101110，试求其原码

原码为0b10110100，反码为0b11001011，补码为0b11001100

补码为0b11101110，反码为0b11101101，源码为0b10010010



### 21.5整数强制转换之数据溢出

下面代码是否有问题呢？如果有问题，如何解决？解决后结果为多少？

byte b = 130;

- 有问题，可以利用强制转换解决：byte b = (byte) 130;

![](C:\Users\Asinil\Desktop\学习\Java\21.5.PNG)

最后得到原码为11111110，对应的十进制数为-126



### 21.6浮点数存储

**二进制浮点数转换为十进制浮点数**

**规则：按权展开法（系数*基数的权次幂相加）**

- 系数：每一位上的数
- 基数，R进制，基数为R
- 权：
  - 整数部分：从小数点左侧，以0开始编号，对应位上的编号就是该位上的权
  - 小数部分：从小数点右侧，以-1开始编号，对应位上的编号就是该位上的权

- 例如：把二进制数101.101转换为十进制数
- 101.101 = 1x2^2+0x2^1+1x2^0+1x2^-1+0x2^-2+1x2^-2 = 4+2+0+0.5+0+0.125=6.625



**十进制浮点数转换为二进制浮点数**

**规则：整数部分重复相除法，小数部分重复相乘法**

- 整数部分 重复相除法：基数取余，直到商为0，余数反转
- 小数部分 重复相乘法：基数取整，直到小数为0或者达到指定精确度位，整数顺序排列

- 举例：把十进制浮点数6.625转换为二进制浮点数
  - 整数部分：110
  - 小数部分：101

![](C:\Users\Asinil\Desktop\学习\Java\21.6.PNG)

**浮点数存储**

根据国际标准IEEE754，任意一个二进制浮点数都可以表示为：**V = （-1）^s`*`M`*` 2^E**

- s标识符号位，当s = 0，V为正数，当s = 1，V为负数
- M表示有效数字
- E表示指数位
- 举例：十进制数的浮点数6.625，写成二进制是110.101，相当于1.10101*2^2
- 按照上面格式，可以得出s=0，M=1.10101，E=2

**IEEE 754对浮点数存储的规定：**

对于32位的浮点数，也就是**float**类型的，**最高的1位是符号位s**，**接着的8位是指数E**，**接下来的23位为有效数字M**

对于64位的浮点数，也就是**double**类型，**最高的1位是符号位**，**接着11位是指数E**，**接下来的52位为有效数字M**



**IEEE 754对有效数字M和指数E，还有一些特别的规定：**

- 规范化表示的时候，M要写成1.xxxx的形式，其中xxxx表示小数部分

- IEEE 754规定，在计算机内部保存M时，**默认这个数的第一位总是1，因此可能被舍去，只保留后面的xxxx部分**

- 指数E，为一个无符号整数。这意味着E如果为8位，它的取值范围为0~255；如果E为11位，它的取值范围为0~2047
- 但是我们知道，科学计数法里E是可能出现负数的，所以IEEE 754规定，**E的真实值必须再减去一个中间数，对于8位的E，这个中间数是127；对于11位的E，这个中间数为1023；**

举例：浮点数6.625F的存储

二进制浮点数：110.101

规范化表示：1.10101*2^2   M补上18个0：1.10101000000000000000000`*`2^2

- 符号s：0
- 有效数M：1.10101000000000000000000
- 指数E：2+127=129=10000001



### 21.7浮点数运算之结果有误

请问下面程序结果是什么？

System.out.println(2.0f-1.5f);

System.out.println(2.0f-1.3f);

System.out.println(2.0f-1.4f);

我们认为的结果：0.5，0.7，0.6

实际运行结果：0.5，0.70000005，0.6



那么，我们来用二进制分析一下程序：

System.out.println(2.0f-1.5f);

- 十进制：2.0f		二进制：10.0		规范化：1.0000000000000000000000*2^1
- 存储在计算机内的二进制码为：0 10000000 10000000000000000000000	

- 十进制：1.5f        二进制：1.1           规范化：1.1000000000000000000000*2^0
- 存储在计算机内的二进制码为：0 01111111 1100000000000000000000

计算：

1.0000000000000000000000*2^1 减去

0.1100000000000000000000*2^1

结果为：0.0100000000000000000*2^1

规范化结果为：1.0000000000000000000000*2^-1



System.out.println(2.0f-1.3f);

- 十进制：2.0f		二进制：10.0		规范化：1.0000000000000000000000*2^1
- 存储在计算机内的二进制码为：0 10000000 10000000000000000000000	

- 十进制：1.3f        二进制：1.01001100110011001100110           规范化：1.01001100110011001100110*2^0
- 存储在计算机内的二进制码为：0 01111111 01001100110011001100110

计算：

1.0000000000000000000000*2^1 减去

0.101001100110011001100110*2^1		**原因：存储位数有限无法包含整个循环的二进制码，导致精度丢失**

结果为：0.010110011001100110011001*2^1

结果规范化：1.011001100110011001100100*2^-1

- 十进制：0.7f		二进制：0.1011001100110011001100110

规范化：1.011001100110011001100110011*2^-1



System.out.println(2.0f-1.4f);

- 十进制：2.0f		二进制：10.0		规范化：1.0000000000000000000000*2^1
- 十进制：1.4f        二进制：1.011001100110011001100110          规范化：1.01100110011001100110011*2^0

计算：

1.0000000000000000000000*2^1 减去

0.101100110011001100110011*2^1	

结果：0.010011001100110011001101*2^1

规范化：1.00110011001100110011010*2^-1

- 十进制：0.6f		二进制：0.10011001100110011001100		规范化：1.00110011001100110011010*2^-1（如果最后舍弃的数字为1则需要进位+1）

**浮点数运算，在存储和运算过程都可能会有精度丢失，故而出现的结果和我们以为的结果就会有出入**

**在实际开发过程中，不太建议直接使用float或者double做运算**



那么，我们到底该如何避免这种进度丢失问题呢？

**使用java.math.BigDecimal中的方法即可解决精度丢失问题**

- 构造方法：BigDecimal(String val)
- 成员方法：

  - public BigDecimal subtract(BigDecimal subtrahend)：减法操作
  - public BigDecimal add(BigDecimal augend)：加法操作
  - public BigDecimal divide(BigDecimal divisor)  ：除法操作
  - BigDecimal multiply(BigDecimal multiplicand)：乘法操作



### 21.8位运算符

位运算符就是直接对整数在内存中的**二进制位**进行操作

**分类：**

- 逻辑位运算符：位与（&），位或（|），位异或（^），位取反（~）
- 移位运算符：左移（<<），右移（>>），无符号右移（>>>）



**逻辑位运算符**

| 符号 |  作用  | 范例 |     运算规则     |
| :--: | :----: | :--: | :--------------: |
|  &   |  位与  | 3&4  | 同1为1，其余为0  |
|  \|  |  位或  | 3\|4 |  有1为1，同0为0  |
|  ^   | 位异或 | 3^4  | 相同为0，不同为1 |
|  ~   | 位取反 |  ~3  |    0变1，1变0    |

**注意事项：**

- 作位运算，首先得把数据转换为二进制
- 负数需要计算出**补码**参与运算

```java
public class OperatorDemo01 {
    public static void main(String[] args) {
//        &     位与   同1为1，其余为0
        System.out.println(3&4);
        /*
        * 二进制：3=11      4=100
        * 计算机存储为：3=0 00000000 00000000 00000000 0000011
        *             4=0 00000000 00000000 00000000 0000100
        *           3&4=0 00000000 00000000 00000000 0000000 = 0
        * */

//        |    位或   有1为1，同0为0
        System.out.println(3|4);
        /*
        * 二进制：3=11      4=100
         * 计算机存储为：3=0 00000000 00000000 00000000 0000011
         *             4=0 00000000 00000000 00000000 0000100
         *           3&4=0 00000000 00000000 00000000 0000111 = 7
        * */

//        ^    位异或  相同为0，不同为1
        System.out.println(3^4);
        /*
        * 二进制：3=11      4=100
         * 计算机存储为：3=0 00000000 00000000 00000000 0000011
         *             4=0 00000000 00000000 00000000 0000100
         *           3^4=0 00000000 00000000 00000000 0000111 = 7
        * */

        System.out.println(~3);
        /*
        * 二进制：3=11
        * 计算机存储为：3=0 00000000 00000000 00000000 0000011
        *            ~3=1 11111111 11111111 11111111 1111100
        *            因为为负数，通过补码需要计算出原码
        *            补码-1，然后取反：反码：1 11111111 11111111 1111011
        *                           原码：1 00000000 00000000 0000100 = -4
        * */
    }
}
```





**移位运算符**

| 符号 |    作用    |  范例  |               运算规则                |
| :--: | :--------: | :----: | :-----------------------------------: |
|  <<  |    左移    |  3<<2  |           高位丢弃，低位补0           |
|  >>  |    右移    | 24>>2  |         正数左补0，负数左补1          |
| >>>  | 无符号右移 | 24>>>2 | 无论该数是正数还是负数，右移之后左补0 |

```java
public class OperatorDemo02 {
    public static void main(String[] args) {
//        <<      左移               高位丢弃，低位补0
        System.out.println(3<<2);//3*2^2=12
        /*
        * 二进制：3=11
        * 计算机存储为：3=0 00000000 00000000 00000000 0000011
        * 左移2位：
        *       000000000 00000000 00000000 0000011
        *   (00)0000000 00000000 00000000 000001100
        * 移动后结果：0000000 00000000 00000000 000001100 = 12
        * */

//        >>      右移             正数左补0，负数左补1
        System.out.println(24>>2);//24*2^-2=6
        /*
         * 二进制：24=11000
         * 计算机存储为：24=0 00000000 00000000 00000000 0011000
         * 右移2位：
         *       000000000 00000000 00000000 0011000
         *       00000000000 00000000 00000000 00110(00)
         * 移动后结果：00000000000 00000000 00000000 00110 = 12
         * */

        System.out.println(-24>>2);//-24*2^-2=-6
        /*
         * 二进制：24=11000
         * 原码：1 00000000 00000000 00000000 0011000
         * 反码：1 11111111 11111111 11111111 1100111
         * 补码：1 11111111 11111111 11111111 1101000
         * 计算机存储为：-24=1 11111111 11111111 11111111 1101000
         * 右移2位：
         *       111111111 11111111 11111111 1101000
         *       11111111111 11111111 11111111 11010(00)
         * 移动后结果：11111111111 11111111 11111111 11010
         *   结果反码：11111111111 11111111 11111111 11001
         *   结果原码：10000000000 00000000 00000000 00110 = -6
         * */

//       >>>   无符号右移        无论该数是正数还是负数，右移之后左补0
        System.out.println(24>>>2);//24*2^-2=6
        /*
         * 二进制：24=11000
         * 计算机存储为：24=0 00000000 00000000 00000000 0011000
         * 右移2位：
         *       000000000 00000000 00000000 0011000
         *       00000000000 00000000 00000000 00110(00)
         * 移动后结果：00000000000 00000000 00000000 00110 = 12
         * */
        System.out.println(-24>>>2);//(2*32-24)*2^-2
        /*
         * 二进制：24=11000
         * 原码：1 00000000 00000000 00000000 0011000
         * 反码：1 11111111 11111111 11111111 1100111
         * 补码：1 11111111 11111111 11111111 1101000
         * 计算机存储为：-24=1 11111111 11111111 11111111 1101000
         * 右移2位：
         *       111111111 11111111 11111111 1101000
         *       00111111111 11111111 11111111 11010(00)
         * 移动后结果：00111111111 11111111 11111111 11010 = 1073741818
        * */
    }
}
```

**总结：**

- 作移位运算，首先得把数据转换为二进制，然后进行移位运算

- 移位运算可以相当于：

  - (int) A << X：A*2^X

  - (int)A >> X：A*2^-X

  - (int)A>>>X：
    - 如果A为负数：(2^32-A)*2^X
    - 如果A为正数：A*2^-X



**练习**

**乘法运算**

- 请用最有效率的方式写出计算2乘以8的结果

```java
//      请用最有效率的方式写出计算2乘以8的结果
//        System.out.println(2*8);
        System.out.println(2<<3);//2*2^3
```

**判断奇偶**

- 判断一个数据是奇数还是偶数

```java
//        判断一个数据是奇数还是偶数
        int a = 10;
//        a = 9;
       /* if(a%2 == 0){
            System.out.println("是偶数");
        }*/

        /*
        * 00000000 00000000 00000000 00001010
        * &00000000 00000000 00000000 00000001
        * ------------------------------------
        * 000000000 000000000 00000000 00000000
        * 根据数据a的末尾是0还是1来判断是奇数还是偶数，如何获取到a的末尾数据？我们可以直接与1做位与运算
        * */
        if ((a&1) == 0){
            System.out.println("是偶数");
```

**两个变量的交换**

*   需求1：交换变量a和b的值
*   需求2：交换变量a和b的值，不能使用第三方变量

```java
public class Test02 {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;
        System.out.println("交换前a：" + a + " b：" + b);
//        需求1：交换变量a和b的值
      /*  int temp = a;
        a = b;
        b = temp;*/

//        需求2：交换变量a和b的值，不能使用第三方变量
        /*数据a针对数据b做位异或
         * 如果a=b：a^b = 0
         * 如果b=0：a^b = a
         *
         * 如果a=3
         * 3的二进制： 00000000 00000000 00000000 00000011
         *   3^3
         *   00000000 00000000 00000000 00000011
         *  ^00000000 00000000 00000000 00000011
         * -------------------------------------------
         *   00000000 00000000 00000000 00000000
         *
         *   3^0
         *   00000000 00000000 00000000 00000011
         *  ^00000000 00000000 00000000 00000000
         * -------------------------------------------
         *   00000000 00000000 00000000 00000011
         * */

        a = a ^ b;//a = a ^ b;
        b = a ^ b;//b = a ^ b = a ^ b ^ b = a
        a = a ^ b;//a = a ^ b = a ^ b ^ a = b
        System.out.println("交换后a：" + a + " b：" + b);
    }
}
```

**找重复数**

现有0到99，共计100个整数，各不相同，将这100个整数放入数组中，然后在这个数组中添加一个0~99的任意一个整数（唯一重复数字），把这101个数打乱

需求：将这个重复数找出来

```java
public class Test03 {
    public static void main(String[] args) {
        int[] array = new int[101];
        for (int i = 0; i < 100; i++) {
            array[i] = i;
        }
//        在索引为100的位置提供重复数字
//        array[100] = 66;
//        把这里数据也可以改为随机数实现
        Random r = new Random();
        array[100] = r.nextInt(100);

//        打乱之前遍历一下
        System.out.println("打乱之前：");
        printArray(array);

//      将数组打乱
        for (int i = 0; i < 1000; i++) {
            int n = r.nextInt(101);
            int m = r.nextInt(101);
            int temp = array[n];
            array[n] = array[m];
            array[m] = temp;
        }
        System.out.println("打乱之后：");
        printArray(array);

        //找到重复数
//        方法1：初学者思维
        /*Arrays.sort(array);
        int num = array[0];
        for (int i = 1; i < array.length; i++) {
            if(num == array[i]){
                System.out.println("重复数为："+array[i]);
                break;
            }
            num = array[i];
        }*/
//        方法2：巧妙的算法
//        首先将数组的所有元素加起来，减去0~99的总和得到的结果即是重复数
      /*  int sum = 0;
        for (int i = 0; i < array.length; i++) {
            sum += array[i];
        }
        for (int i = 0; i < 100; i++) {
            sum -= i;
        }
        System.out.println("重复数：" + sum);
    */

//        方式3：异或运算符
        /*数据a针对数据b做位异或
          b ^ b = 0
          a ^ 0 = a
        */
        for (int i = 1; i < array.length; i++) {
            array[0] ^= array[i];
//            得到0~99（除了重复数之外）的数连续异或结果
        }
        for (int i = 0; i < 100; i++) {
            array[0] ^= i;
//            使得0~99（除了重复数之外）的数变为0，重复数^0=重复数
        }
        System.out.println("重复数：" + array[0]);

    }
    private static void printArray(int[] array) {
        for (int i = 0; i < array.length; i++) {
            if (i % 10 == 0 && i != 0) {
                System.out.println();
            }
            System.out.print(array[i] + "\t");
            if (i == array.length - 1) {
                System.out.println();
            }
        }
    }
}

```



### 21.9 BigDecimal

**BigDecimal用于小数的精确计算**

构造方法：

- BigDecimal（String val）

四则运算：

- public BigDecimal subtract(BigDecimal subtrahend)：减法操作
- public BigDecimal add(BigDecimal augend)：加法操作
- public BigDecimal divide(BigDecimal divisor)  ：除法操作
- public BigDecimal multiply(BigDecimal multiplicand)：乘法操作



**BigDecimal除法运算**：

- public BigDecimal divide(另一个BigDecimal对象，精确几位，舍入模式)
- RoundingMode.UP：进一法
- RoundingMode.FOOLR：去尾法
- RoundingMode.HALE_UP：四舍五入

```java
public class BigDecimalDemo02 {
    public static void main(String[] args) {
        BigDecimal bd1 = new BigDecimal("10.0");
        BigDecimal bd2 = new BigDecimal("3.0");

//        System.out.println(bd1.divide(bd2));//除法
//        除法报错：未指定精确到多少小数位
        /*
            public BigDecimal divide(另一个BigDecimal对象，精确几位，舍入模式)
                参数1：表示参与运算的BigDecimal对象
                参数2：表示小数点后精确到多少位
                参数3：舍入模式
         */

        System.out.println(bd1.divide(bd2,2, RoundingMode.HALF_UP));//3.33
        System.out.println(bd1.divide(bd2,2, RoundingMode.DOWN));//3.33
        System.out.println(bd1.divide(bd2,2, RoundingMode.UP));//3.34
    }
}
```





## 22 Java8日期API

**Java8 日期API的优点**

- Date如果不格式化，输出的日期可读性很差，而Java8的时间类直接输出可读性好
- Date存在线程安全问题，而Java8的时间类都是线程安全的

**Java8新增的日期类**

![](C:\Users\Asinil\Desktop\学习\Java\22.1.PNG)

### LocalDateTime

通过查询API文档，LocalDateTime没有构造方法，常用下面两个方法获取时间对象：

- public static LocalDateTime now()：从默认时区中的系统时钟获取当前的日期时间

- public static LocalDateTime of(int year ,int month ,int dayOfMonth ,int hour ,int minute ,int second)

  从年月日小时分钟和秒获得LocalDateTime的实例，将纳秒设置为0



**LocalDateTime的格式化和解析**

**格式化：**

- String format(DateTimeFormatter formatter):使用指定的格式化程序格式化此日期时间

**解析：**

- static LocalDateTime parse(CharSequence text,DateTimeFormatter formatter)：使用特定格式化程序从文本字符串中获取LocalDateTime的实例
- DateTimeFormatter ：没有看到构造方法，用下面的静态方法获取日期格式化对象
  - public static DateTimeFormatter ofPattern(String pattern)：使用指定的模式创建格式化程序

```java
public class LocalDateTimeDemo02 {
    public static void main(String[] args) {
//        String format(DateTimeFormatter formatter):使用指定的格式化程序格式化此日期时间
  /*      LocalDateTime now = LocalDateTime.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        String time = now.format(formatter);
        System.out.println(time);//2023-10-22 22:16:25*/

//        使用链式编程简化
        String format = LocalDateTime.now().format(DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
        System.out.println(format);

//        static LocalDateTime parse(CharSequence text,DateTimeFormatter formatter)：使用特定格式化程序从文本字符串中获取LocalDateTime的实例
        /*String time = "2024-01-25 12:15:25";
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        LocalDateTime dateTime = LocalDateTime.parse(time, formatter);
        System.out.println(dateTime);//2024-01-25T12:15:25*/

        LocalDateTime parse = LocalDateTime.parse("2024-01-25 12:15:25", DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
        System.out.println(parse);

    }
}
```





## 23 设计模式

- **设计模式（Design pattern）**是一套被**反复使用，多数人知晓的，经过分类编目的，代码设计经验总结**。使用设计模式是为了可重用代码，让代码更容易被他人理解，保证代码可靠性
- 设计模式和具体的语言无关，学习设计模式就是要建立面向对象思想，尽可能的面向接口编程，低耦合，高内聚，使设计的程序可复用



### 单例设计模式

- **单例设计模式就是要确保类在内存中只有一个对象，该实例必须自动创建，并且对外提供**
- 在系统内存中只存在一个对象，因此可以节约系统资源，**对于一些需要频繁创建和销毁的对象，单例设计模式无疑可以提高系统的性能**

**如何保证类在内存中只有一个对象？**

- 把构造方法私有化
- 在成员位置自己创建一个对象
- 通过一个公共的方法提供访问



 **单例设计模式：**
*       饿汉式：类一加载就创建对象
*       懒汉式：用的时候，才创建对象

在实际开发中，我们会使用饿汉式，因为这种方式不会出现线程安全问题

产生线程安全的三个条件：

*   1.是否是多线程环境
*   2.是否有共享数据
*   3.是否有多条语句操作共享数据



**JDK中单例设计模式的体现**

```java
//每个Java应用程序都有一个Runtime类的Runtime ，允许应用程序与运行应用程序的环境进行接口。 当前运行时可以从getRuntime获取
public class RuntimeDemo {
    public static void main(String[] args) throws IOException {
        Runtime r = Runtime.getRuntime();
       /* Runtime r2 = Runtime.getRuntime();
        System.out.println(r == r2);*/

        /*
            public class Runtime {
                private Runtime() {}

                private static final Runtime currentRuntime = new Runtime();

                public static Runtime getRuntime() {
                    return currentRuntime;
                }
            }
         */
//        r.exec("calc");//可以输入一些命令
//        r.exec("notepad");//记事本
//        r.exec("shutdown -s -t 10000");//定时关机
//        r.exec("shutdown -a");//取消定时关机

    }
}
```



## 24 枚举

### 枚举概述

- 枚举是将变量的值一一列举出来，变量的值只限于列举出来的值的范围。举例：一周七天，一年有12个月等



回想单例设计模式：单例类只有一个实例

那么，多例类就是一个类有多个实例，但不是无限个实例，而是有限个实例，这才能是枚举类

- 自定义枚举类

  public class 类名{

  ​		实例1；

  ​		实列2；

  ​		实例3；

  ​		……

  }



我们自定义一个枚举类比较麻烦，所以Java给我们提供了枚举类供我们使用

- 格式：只有枚举项的枚举类

  public enum 枚举类名{

  ​		枚举项1，枚举项2，枚举项3……;

  }

 

### 枚举类的注意事项

- 定义枚举类要用关键字enum
- 所有枚举类都是Enum的子类
- 枚举类的第一行必须是枚举项，最后一个枚举项后面的分号是可以省略的，但是如果枚举类有其他的代码，这个分号就不能省略。这里建议一直都不要省略
- 枚举类可以有构造器，但必须是private的，它默认的也是private的。枚举类的用法比较特殊：枚举（“ ”）
- 枚举类可以有抽象方法，但是枚举类必须重写该方法
- 枚举在switch语句中的使用



## 25 注解

### 25.1注解概述

我们在重写方法时，经常会看到@Override，@Override就是一个注解

- **@Override**：用来修饰方法，表示该方法是重写父类的方法，如果不是，就会报错



**注解（Annotation）**：也叫元数据，一种代码级别的说明，它是JDK1.5及以后版本引进的一个特性

它可以声明在包，类，字段，方法，局部变量，方法参数等的前面，用来对这些元素进行说明



**注解和注释：**

- 注解：用来说明程序，**给计算机看的**
- 注释：用来对程序进行说明的文字，**给程序员看的**



在系统的学习注解语法之前，我们先看看Java中常见的几个注解：

- @Override
- @Deprecated
- @SuppressWarnings
- @FunctionalInterface



### 25.2常用注解

**@Override**

- 用于指定方法是**重写父类的方法**，只能修饰方法，不能修饰其他程序元素
- 单独来看，可能丝毫看不出程序中@Override有何作用，因为它的作用是告诉编译器检查这个方法，保证父类要包含一个被该方法重写的方法

**@Deprecated**

- 用于表示某个**程序元素（类，方法等）已过时**，当其他程序使用已过时的类，方法时，编译器将会给出警告

- Java9为@Deprecated增加了两个属性：

  **since**：该String类型的属性指定该API从哪个版本被标记为过时

  **forRemoval**：该boolean类型的属性指定该API在将来是否会被删除

**@SuppressWarnings**

- 指示被该注解修饰的程序元素（以及该程序元素中所有的子元素）**取消显示指定的编译器警告**
- 使用注解来关闭编译器警告时，一定要在括号里使用name = value的形式为该注解的成员变量设置值
- @SuppressWarnings（value = “all”）

**@FunctionalInterface**

- Java8新增的，只能用来修饰接口，**表示该接口是一个函数式接口**
- 函数式接口：接口中有且仅有一个抽象方法
- Lambda表达式的使用前提：接口中有且仅有一个抽象方法



### 25.3元注解

- 对注解进行注解的注解，也就是写在注解上面的注解



常用的两个元注解：

- @Retention
- @Target



**@Retention**

- 只能用于修饰注解定义，用于指定被修饰注解可以保留多长时间
- 只包含了一个RetentionPolicy类型的value成员变量，所以使用的@Retention时必须为该value成员变量指定值

**@Retention中可使用的值定义在RetentionPolicy中，常用值如下：**

- RetentionPolicy.CLASS：编译器把注解记录在class文件在，当运行Java程序时，JVM不可获取注解信息，这是默认值
- **RetentionPolicy.RUNTIME**：编译器把注解记录在class文件在，当运行Java程序时，JVM也可以获取注解信息，**开发中使用**
- RetentionPolicy.SOURCE：注解只保留在源代码中，编译器直接丢弃这种注解



**@Target**

- 只能用于修饰注解定义，用于指定被修饰的注解能用于修饰哪些程序单元，包含一个名为value的成员变量

**@Target中可以的值定义在ElementType中，常用值如下：**

- @Target(ElementType.TYPE)：可以用于接口，类，枚举，注解
- @Target(ElementType.FIELD)：可以用于属性字段，枚举常量
- @Target(ElementType.METHOD)：可以用于方法
- @Target(ElementType.PARAMETER)：可以用于方法参数
- @Target(ElementType.CONSTRUCTOP)：可以用于构造方法
- @Target(ElementType.LOCAL_VARIABLE)：可以用于局部变量



### 25.4自定义注解

定义格式：

- 元注解

  public @interface 注解名称{

  ​	属性列表;

  }

注解的本质：

- public interface MyAnnotation extends Annotation{}
- 是一个接口，该接口默认继承Annotation接口
- 既然是接口，那么内部定义的内容，就是接口中可以定义的内容



注解的属性

- 属性：接口中的抽象方法

- 格式：返回值类型 属性名称()[default默认值]



注解属性类型可以有以下列出的类型：

- 基本数据类型
- String
- 枚举类型
- 注解类型
- Class类型
- 以上类型的一维数组类型

![](C:\Users\Asinil\Desktop\学习\Java\25.4.PNG)



#### 注解的使用和解析

使用注解：

- 如果注解有多个属性，可以在注解括号中用“，”号分隔开分别给对应的属性赋值
- 如果定义属性时，使用default关键字给属性默认初始值，则使用注解时，可以不进行属性的赋值
- 如果只有一个属性需要赋值，并且属性的名称为value，则value可以省略，直接定义即可
- 数组赋值时，值需要用{}包裹。如果数组中只有一个值，则{}可以省略



解析注解：

- 获取字节码文件对象，获取谁的呢？谁使用了注解就获取谁的

  Class<MyAnnotationDemo> c = MyAnnotationDemo.class

- 获取字节码对象上的注解信息

  MyAnnotation annotation = c.getAnnotation(MyAnnotation.class);

- 解析注解

  String name = annotation.name();

  int age = annotation.age();



**案例：框架通用技术**

需求：通过注解，运行指定类中的指定方法

```java
@MyAnnotation(className = "com.test_05.Student", classMathod = "show")
public class Test {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {
//        获取注解类的字节码对象
        Class<Test> testClass = Test.class;
//        通过类的字节码文件获取注解信息
        MyAnnotation annotation = testClass.getAnnotation(MyAnnotation.class);
//        通过注解获取里面的方法
        String name = annotation.className();
        String method = annotation.classMathod();

//        获取类的字节码文件对象
        Class<?> c = Class.forName(name);
//        通过类获取构造方法,并构造无参对象
        Constructor<?> con = c.getConstructor();
        Object obj = con.newInstance();

//        通过类的字节码文件对象获取成员方法
        Method show = c.getDeclaredMethod(method);
        show.invoke(obj);
    }
}
```

**框架运行的两种方式：**

- 配置文件
- 注解（大部分）



## 26 XML

### 26.1XML概述

- XML的全称为（EXtensible Markup Language），是一种可扩展的标记语言
- 可标记语言：通过标签来描述数据的一门语言（标签有时我们也将其称之为元素）
- 可扩展：标签的名字是可以自己定义的

| 语法规则                                                     | 示例代码                                          |
| ------------------------------------------------------------ | ------------------------------------------------- |
| 是有一对尖括号和一组合法标识符组成                           | <student>                                         |
| 在xml标签**往往是成对出现**的，有开始也有结束                | <student></student>                               |
| 在xml中有一些**特殊的标签**也可以**不成对出现**，但是**必须要存在结束标记** | <student/>                                        |
| 在xml中标签可以定义属性，但是属性必须通过**引号引起来**      | <student id = "stu001"></student>                 |
| 标签可以进行**正确嵌套**                                     | <student id = "stu001"><name>fqy</name></student> |

**XML的作用**

- 用于进行**存储数据**和**传输数据**（把数据按照xml文件的格式存储起来，并且可以把xml文件作为数据的载体在多个系统之间进行传输）
- 作为软件的**配置文件**（可以把软件在运行时所需要的一些信息按照xml文件格式配置到文件中）



### 26.2XML的语法规则

| 语法规则                                    | 示例代码                                   |
| ------------------------------------------- | ------------------------------------------ |
| xml文件的后缀名普遍是xml                    | user.xml,student.xml                       |
| xml要有文档声明，文档声明必须是第一行第一列 | <?xml version = "1.0" encoding = "utf-8"?> |
| xml必须要存在一个根标签，并且有且仅有一个   | <student></student>                        |
| xml文件中可以定义注释信息                   | <!-- 这里是注释信息-->                     |
| xml文件中可以存在以下特殊字符               | `&`It;`&`gt;                               |
| xml文件中可以存在CDATA区                    | <![CDATA[ a<b]]>                           |

**文档声明属性说明：**

- version：必须的，声明当前xml文件版本。一般我们使用的都是1.0
- encoding：不是必须的，字符集，是使用浏览器打开的时候采用的默认的字符集编码
- standalone：不是必须的，描述xml文档是否需要依赖其他的文件

**如何验证XML是否正确**

有两种方式：

- 通过idea开发工具进行校验，如果xml编写的有问题，idea开发工具会有错误提示信息
- 使用浏览器打开，如果可以正常显示xml文件的内容，那么就说明我们所编写的xml文件没有问题，如果我们编写的xml文件是存在问题的，那么在使用浏览器打开时就会出现错误



### 26.3XML解析思想

- 所谓的解析就是从XML中获取到数据
- 常见的解析思想：*DOM（Document Object Model）* **文档对象模型，就是把文档的各个组成部分看做成对应的对象**

![](C:\Users\Asinil\Desktop\学习\Java\26.2.PNG)

**结构说明：**

- Document对象代表的是整个xml文档
- 蓝色部分都是xml文档中的**标签（元素）**，使用Element对象表示

- 绿色部分都是xml标签的**文本内容**，使用Text对象表示
- 粉红色部分都是xml标签的**属性**，使用Attribute表示
- Element，Text，Attribute这几个对象存在一个公共的父类就是Node

针对这种解析思想，不同的公司提供了不同的API的实现

**常见的XML解析技术：**

- JAXP：SUN公司提供的一套XML的解析API
- JDOM：开源组织提供了一套XML的解析的API-jdom
- **DOM4J**：开源组织提供了一套XML的解析的API-dom4j
- Pull：主要应用在Android手机解析XML



**案例：XML的解析**

需求：使用DOM4J解析students.xml文件，将解析到的数据封装到学生对象中，并将学生对象存储到ArrayList集合中，最后遍历集合

实现步骤：

1. 创建学生类（id，name，age，address）
2. 导入jar包（dom4j-1.6.1.jar）
3. 创建解析器（可以参考dom4j文档中的index.html文件中的Quick start条目进行创建）
4. 通过解析器读取xml文档数据，得到Document对象
5. 获取根节点元素对象
6. 从根节点下查找其他的节点元素，读取数据

```java
public class XMLParseDemo {
    public static void main(String[] args) throws FileNotFoundException, DocumentException {
//        创建学生集合对象
        ArrayList<Student> arrayList = new ArrayList<>();

//        创建解析器
        SAXReader saxReader = new SAXReader();
//        通过解析器读取xml文档数据，得到Document对象
        Document document = saxReader.read(new FileInputStream("26XMLProject/src/students.xml"));
//        获取根节点元素对象
        Element root = document.getRootElement();
//        从根节点下查找其他的节点元素，读取数据
        List<Element> elements = root.elements("student");

//        遍历集合得到每一个学生元素
        for(Element student:elements){
//            获取属性

            Attribute attribute = student.attribute("id");
//            获取id的属性值
            String id = attribute.getValue();
            
//          获取name元素
            Element nameElement = student.element("name");
            String name = nameElement.getText();

//          获取age元素
            Element ageElement = student.element("age");
            String age = ageElement.getText();

//            获取address元素
            Element addressElement = student.element("address");
            String address = addressElement.getText();

            arrayList.add(new Student(id,name,age,address));
        }
        
        arrayList.forEach(student -> System.out.println(student));
    }
}
```



#### 实现对XML文档的增删改查

```java
public class Demo3 {

	@Test
	public void method1() throws Exception {
		// 创建解析器
		SAXReader reader = new SAXReader();//这个是用来读取文件内容的
		Document doc = reader.read(new File("students.xml")); //指定要读取的文件
		//System.out.println(doc.asXML()); //打印出文件
	}
	
	//实现对XML文件的复制
	@Test
	public void method2() throws Exception {
		// 得到Document
		SAXReader reader = new SAXReader();
		Document doc = reader.read(new File("students.xml"));
		
		// 保存Document，指定将写入的目的文件（复制功能）
		XMLWriter writer = new XMLWriter(new FileOutputStream("students_copy.xml"));
		writer.write(doc); //开始写入
	}
	
	//遍历Document
	@Test
	public void method3() throws Exception {
		// 要遍历文档，首先要得到Document对象
		SAXReader reader = new SAXReader();
		Document doc = reader.read(new File("students.xml"));

		//获取根元素
		Element root = doc.getRootElement();
		//获取根元素中所有student元素
		List<Element> stuEleList = root.elements("student");
		// 循环遍历所有学生元素
		for(Element stuEle : stuEleList) {
			//获取学生元素的number
			String number = stuEle.attributeValue("number");
			//获取学生元素名为name的子元素的文本内容
			String name = stuEle.elementText("name");
			//获取学生元素名为age的子元素的文本内容
			String age = stuEle.elementText("age");
			//获取学生元素名为sex的子元素的文本内容
			String sex = stuEle.elementText("sex");		
			System.out.println(number + ", " + name + ", " + age + ", " + sex);
		}
	}
	
	//添加元素
	@Test
	public void method4() throws Exception {
		// 得到Document
		SAXReader reader = new SAXReader();
		Document doc = reader.read(new File("src/students.xml"));

		//获取root元素
		Element root = doc.getRootElement();
		Element stuEle = root.addElement("student"); //添加了student元素
		// 给stuEle添加属性，名为number，值为1003
		stuEle.addAttribute("number", "1003"); 
		// 分别为stuEle添加名为name、age、sex的子元素，并为子元素设置文本内容
		stuEle.addElement("name").setText("wangWu");
		stuEle.addElement("age").setText("18");
		stuEle.addElement("sex").setText("male");
		
		// 设置保存的格式化器  1. \t，使用什么来完成缩进 2. true, 是否要添加换行
		OutputFormat format = new OutputFormat("\t", true);
		format.setTrimText(true); //去掉空白
		// 在创建Writer时，指定格式化器
		XMLWriter writer = new XMLWriter(new FileOutputStream("src/students_copy.xml"), format);
		writer.write(doc);
        //释放资源
        writer.close();
	}
	
	//修改元素
	@Test
	public void method5() throws Exception {

		// 得到Document
		SAXReader reader = new SAXReader();
		Document doc = reader.read(new File("src/students_copy.xml"));

		//使用XPath找到符合条件的元素
		// 查询student元素，条件是number属性的值为1003
		Element stuEle = (Element) doc.selectSingleNode("//student[@number='ITCAST_1003']");
		//修改stuEle的age子元素内容为81
		stuEle.element("age").setText("81");
		//修改stuEle的sex子元素的内容为female
		stuEle.element("sex").setText("female");

	}
	
	//删除元素
	@Test
	public void method6() throws Exception {

		// 得到Document
		SAXReader reader = new SAXReader();
		Document doc = reader.read(new File("src/students_copy.xml"));
		
		// 查找student元素，条件是name子元素的文本内容为wangWu
		Element stuEle = (Element) doc.selectSingleNode("//student[name='wangWu']");
		
		// 2. 获取父元素，使用父元素删除指定子元素
		stuEle.getParent().remove(stuEle);
	}
}
```



### 26.4XML文档约束

- xml文件最常见的作用就是作为软件的配置文件，那么解析xml文件的代码一般都是提前编好的，而我们程序员只需要编写xml文件就可以了，但是大家试想一下，如果在编写这个xml文件时没有按照解析的要求去编写，而是随意去定义标签，那么再使用解析代码的时候势必就会出现问题



如何限定程序员在xml文件中去定义哪些标签呢？

- 我们需要去了解一下xml文件的约束技术
- 简单来说：xml文档的约束技术，就是用来限定xml文件中可以使用的标签以及属性



**xml文件常见的约束技术有两种：**

- dtd
- schema

 

#### 26.4.1dtd约束

入门案例：为了快速的了解dtd，我们首先来写一个dtd的约束文件

需求：对比下面的xml文件写出一个dtd约束文件

```xml
<?xml version = "1.0" encoding = "UTF-8"?>
<students>
    <student id = "stu001">
        <name>林黛玉</name>
        <age>16</age>
        <address>江南</address>
    </student>
</students>
```



**dtd文件书写步骤：**

- 创建一个文件，这个文件的后缀名为.dtd

- 看xml文件中使用了哪些元素，使用了哪些元素就通过<!ELEMENT>去定义那些元素

- 元素标签定义属性<!ATTLIST>    定义属性格式：<!ATTLIST 元素名 属性名 ID #REQUIRED> 其中ID #REQUIRED是必须填的

- 判断元素是简单元素还是复杂元素

  - 简单元素：没有子元素；		简单元素定义：<!ELEMENT 元素名称(#PCDATA)>  PCDATA表示元素类型为字符串

  - 复杂元素：有子元素的元素； 复杂元素定义：<!ELEMENT 元素名称(子元素)>

```xml-dtd
<!ELEMENT students (student)>
<!ELEMENT student (name,age,address)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT age (#PCDATA)>
<!ELEMENT address (#PCDATA)>
<!ATTLIST student id ID #REQUIRED>
```



##### dtd的引入方式

方式一：内部引入（不推荐）

格式：<!DOCTYOE 根元素名称 [dtd文件内容]>

```xml-dtd
<?xml version = "1.0" encoding = "UTF-8"?>

<!-- dtd的内部引入 -->
<!DOCTYPE students [
        <!ELEMENT students (student)>
		<!ELEMENT student (name,age,address)>
		<!ELEMENT name (#PCDATA)>
		<!ELEMENT age (#PCDATA)>
		<!ELEMENT address (#PCDATA)>
		<!ATTLIST student id ID #REQUIRED>
    ]>

<students>
    <student id = "stu001">
        <name>林黛玉</name>
        <age>16</age>
        <address>江南</address>
    </student>
</students>
```

**方式二：引入本地dtd（推荐）**

格式：<!DOCTYPE 根元素名称 SYSTEM'DTD文件路径'>

```xml-dtd
<?xml version = "1.0" encoding = "UTF-8"?>
<!-- dtd的本地引入 -->
<!DOCTYPE students SYSTEM'src/studentdtd.dtd'>

<students>
    <student id = "stu001">
        <name>林黛玉</name>
        <age>16</age>
        <address>江南</address>
    </student>
</students>
```

方式三：引入网络dtd

格式：<!DOCTYPE 根元素名称 PUBLIC "DTD的文件名称" "DTD文档的URL">

```xml-dtd
<?xml version = "1.0" encoding = "UTF-8"?>
<!-- dtd的网络引入 -->
<!DOCTYPE students PUBLIC "studentdtd.dtd" "http://hibernate.sourceforge.net/studentdtd.dtd">

<students>
    <student id = "stu001">
        <name>林黛玉</name>
        <age>16</age>
        <address>江南</address>
    </student>
</students>
```



##### dtd语法

**定义元素**

定义一个元素的格式：

**简单元素：没有子元素**		

简单元素定义：<!ELEMENT 元素名称 CONTENT> 

- ELEMENT是关键字，是不能修改的

- CONTENT是元素类型，必须要大写且有三种写法：
  - EMPTY表示该元素不能包含子元素和文本，但可以有属性	
  - ANY表示该元素可以包含**任何在该DTD中定义的元素内容**
  - PCDATA表示该元素内部内容为字符串，但是不能包含任何子元素



**复杂元素：有子元素的元素；** 

复杂元素定义：<!ELEMENT 元素名称 (子元素)>

单个子元素直接写子元素名称，多个子元素可以用“，”或者“|”隔开

`,`隔开表示元素的顺序，`|`隔开表示子元素至少出现任意一个

子元素后面接`?`表示出现零次或者一次；`+`表示出现一次或多次；`*`表示出现零次或多次；如果不写就表示只出现一次



**定义属性**

定义一个元素属性的格式：

<!ATTLIST 元素名称 

​	属性名称 类型 属性特点

​	属性名称 类型 属性特点……>

**属性的类型有下面五种：**

- CDATA：表示属性的值可以是任何字符（包括中文和数字）

  ```xml-dtd
  <!ATTLIST 木偶
      姓名 CDATA #REQUIRED
  >
  ```

  ```xml
  <木偶 姓名="匹诺曹"/>
  <木偶 姓名="PiNuocao"/>
  <木偶 姓名="123"/>
  ```

- ID：表明该属性的取值必须是唯一的，但是**属性的值不能以数字开头**

  ```xml-dtd
  <!ELEMENT 公司职员 ANY>
  <!ATTLIST 公司职员
      编号 ID #REQUIRED
      姓名 CDATA #REQUIRED
  >
  ```

  ```xml
  <公司职员 编号="Z001" 姓名="张三"/>
  <公司职员 编号="Z002" 姓名="李思"/>
  ```

- IDREF/IDREFS：IDREF属性指向文档中其他地方声明的ID类型的值；IDREFS同IDREF，但是可以具有**空格**分开的多个引用

  ```xml-dtd
  <!ELEMENT 家庭(人+)>
  <!ELEMENT 人 EMPTY>
  <!ATTLIST 人
      relID ID #REQUIRED
      paraentID IDREFS #IMPLIED
      name CDATA #REQUIRED
  >
  ```

  ```xml
  <家庭>
      <人 relID="P_1" name="爸爸"/>
      <人 relID="P_2" name="妈妈"/>
      <人 relID="P_3" parentID="P_1 P_2" name="儿子"/>
  </家庭>
  ```

- Enumerated：事先定义好一些值，属性的值必须在所列出的值的范围内

  ```xml-dtd
  <!ATTLIST person
      婚姻状态 (single|married|divorced|widowed) #IMPLIED
  >
  <!ATTLIST person
      性别 (男|女) #REQUIRED
  >
  ```

- ENTITY：实体

  实体定义：

  - 实体用于为一段内容创建一个别名，以后在XML文档中就可以使用这些别名引用这段内容了
  - 在DTD定义中，一条!ELEMENT语句用于定义一个实体
  - 实体可分为两种类型：**引用实体和参数实体**。引用实体是被XML文档应用的，而参数实体是被DTD文件本身应用的

- 引用实体：引用实体是被XML文档应用的，定义内容最好放在DTD文件的最后

  - 格式：<!ELEMENT 实体名称 "实体内容">

  - 引用方式：&实体名称;

    ```xml-dtd
    <!ENTITY copyright "I am a programmer">
    ....
    &copyright;
    ```

- 参数实体：参数实体是被DTD文件本身应用的

  - 格式：<!ELEMENT % 实体名称 "实体内容">

  - 引用方式：% 实体名称

    ```xml-dtd
    <!ENTITY % TAG_NAME "姓名|EMAIL|电话|地址">
    
    <!ELEMENT 个人信息 (%TAG_NAME;|生日)>
    <!ELEMENT 客户信息 (%TAG_NAME;|公司名)>
    ```

**属性特点有如下四种：**

- #REQUIRED：表示这个属性是必须给的，不给就报错
- #IMPLIED：表示这个属性可以给也可不给
- #FIXED value：表示这个属性必须给一个固定的value值
- Default value：表示这个属性如果没有值，就分配一个默认的value值



#### 26.4.2 schema约束

**schema与dtd约束的比较**

- dtd的数据类型少不能很好的对xml文档进行约束，而schema功能更加强大，提供了丰富的数据类型
- **一般我们在写框架时，schema更加常用**

**Schema的优点：**

- XML Schema可针对未来的需求进行扩展

- XML Schema更完善，功能更加强大

- XML Schema基于XML编写（schema本质上就是一个xml文件）

- XML Schema支持数据类型（提供更加丰富的数据类型）

- XML Schema支持命名空间

  同一个xml文件可以被不同的schema约束，通过名称空间约束

  通过名称空间来区分多个schema约束

后面学习框架时学习……



## 27 JUnit

### 27.1单元测试

**单元测试概述**

- 在程序中，一个单元可以是一个完整的模块，但它通常是一个单独的方法或者程序
- 在面向对象的编程中，一个单元通常是一整个界面，例如类，但是可能是单个方法

**JUnit是一个Java编程语言的单元测试框架**

- 通过先为最小的可测试单元编写测试，然后编写这些单元之间的复合行为，就可以为复杂的应用程序建立全面的测试



**自己编写main方法存在的问题：**

- 无法得到测试的结果报告，需要程序员自己去观察测试是否成功
- 如果一个测试方法失败了，其他方法测试会受到影响
- 无法一键完成全部模块的全部方法的测试

**单元测试的优点：**

- 可以生成全部方法的测试报告，如果执行的结果为**绿色**，**那么测试结果通过**，如果执行的结果为**红色**的，**表明测试不通过**

- 单元测试中，某个方法测试失败了，不影响其他测试方法的测试
- 可以一键执行全部测试方法



**单元测试的编码约定：**

- 类要放在test包下
- 在test包下创建和原包名相同的包
- 类名用XxxTest结尾
- 方法用testMethod命名

**单元测试步骤：**

1. 和src同级建立test目录，并修改该目录为Test Source Root

2. 在test目录下建包com.wtu

3. 在com.wtu包下新建类MyMathTest

4. 在类中编写第一个测试方法：testAdd()

   方法修饰符：public void testAdd(){}

5. 如何让该方法称为Junit中的测试方法呢？

   - 导入junit-4.12.jar和hamcrest-1.3.jar包
   - 然后在方法上添加@Test注解

6. 运行测试方法

7. 使用断言改进测试方法的运行



**断言：其实就是判断**

Junit测试框架在Assert类就是实现断言工具，主要作用如下：

- 单元测试用于判断某个特定条件下某个方法的行为
- 执行单元测试就是为了证明某段代码的执行结果和期望一致



查看两个对象是否相等，类似于字符串比较使用的equals()方法

- public static void assertEquals(Object expected,Object actual)
- public static void assertNotEquals(Object unexpected,Object actual)

```java
public class MyMathTest {
    /*@Test
    public void testAdd(){
        MyMath myMath = new MyMath();
        int result = myMath.add(10, 20);
        System.out.println(result);
    }*/

    /*查看两个对象是否相等，类似于字符串比较使用的equals()方法

- public static void assertEquals(Object expected,Object actual)
- public static void assertNotEquals(Object unexpected,Object actual)*/
    @Test
    public void testAdd(){
        MyMath myMath = new MyMath();
        int result = myMath.add(10, 20);
//        public static void assertEquals(Object expected,Object actual)
        Assert.assertEquals(30,result);
//        Assert.assertEquals(25,result);
    }
    @Test
    public void testSub(){
        MyMath myMath = new MyMath();
        int result = myMath.sub(20, 10);
        Assert.assertEquals(10,result);
    }
}
```



### 27.2Junit常用注解

|    方法名    |                             说明                             |
| :----------: | :----------------------------------------------------------: |
|    @Test     |     说明依附在JUnit的public void方法可以作为一个测试案例     |
|   @Before    | 修饰实例方法，方法针对每一个测试用例，但是是在**执行测试用例之前** |
|    @After    | 修饰实例方法，方法针对每一个测试用例，但是是在**执行测试用例之后** |
| @BeforeClass | 修饰静态方法，方法首先执行，并且只执行一次，用于**初始化资源** |
| @AfterClass  | 修饰静态方法，方法最后执行，并且只执行一次，用于**释放资源** |

```java
public class MyMathTest {
    /*
    @Test      说明依附在JUnit的public void方法可以作为一个测试案例
   @Before     修饰实例方法，方法针对每一个测试用例，但是是在**执行测试用例之前**
    @After     修饰实例方法，方法针对每一个测试用例，但是是在**执行测试用例之后**
 @BeforeClass  修饰静态方法，方法首先执行，并且只执行一次，用于**初始化资源**
 @AfterClass   修饰静态方法，方法最后执行，并且只执行一次，用于**释放资源**
 */

    @BeforeClass
    public  static void beforeClass(){
        System.out.println("beforeClass");
    }

    @Before
    public  void before(){
        System.out.println("before");
    }

    @Test
    public void testAdd(){
        MyMath myMath = new MyMath();
        int result = myMath.add(10, 20);
//        public static void assertEquals(Object expected,Object actual)
        Assert.assertEquals(30,result);
//        Assert.assertEquals(25,result);
        System.out.println("加法操作完成");
    }
    @Test
    public void testSub(){
        MyMath myMath = new MyMath();
        int result = myMath.sub(20, 10);
        Assert.assertEquals(10,result);
        System.out.println("减法操作完成");
    }

    @After
    public void after(){
        System.out.println("after");
    }

    @AfterClass
    public  static void afterClass(){
        System.out.println("afterClass");
    }
}
/*
beforeClass
before
加法操作完成
after
before
减法操作完成
after
afterClass
*/
```



## 28 AWT编程

Java使用AWT和Swing相关的类可以完成图形化界面编程，其中AWT的全程是抽象窗口工具集（Abstract Window Toolkit）。

它是sun公司早期提供的GUI库，这个GUI库提供了一些基本功能，但是这个GUI库的功能比较有限，所以后来sun公司又提供了Swing库。通过使用AWT和Swing提供的图形化界面组件库，java的图形化界面变成非常简单，程序只需要依次创建所需的图形组件，并以合适的方式将这些组件组织在一起，就可以开发出非常美观的用户界面。

### 28.1AWT简介

当JDK1.0发布时，Sun公司提供了一套基本的GUI类库，这个GUI类库希望可以在所有平台下都能运行，这套基本类库被称为“抽象窗口工具集（Abstract Window Toolkit）”，它为Java程序提供了基本的图形组件。AWT是窗口框架，它从不同平台的窗口系统中抽出共同的组件，当程序运行时，将这些组件的创建和动作委托给程序所在的运行平台。**简而言之，当使用AWT编写图形界面应用时，程序仅指定了界面组件的位置和行为，并未提供真正的实现，JVM调用操作系统的本地图形界面来创建和平台一致的对等体。**

使用AWT创建的图形界面应用和所在的运行平台有相同的界面风格，比如在Windows操作系统上，他就表现出Windows风格；在UNIX操作系统上，他就表现出UNIX风格。sun希望采用这种方式实现“Write Once,Run Anywhere”的目标。



### 28.2 AWT的继承体系

![](C:\Users\Asinil\Desktop\学习\Java\28.2.PNG)

所有和AWT编程相关的类都放在java.awt包以及它的子包中，AWT编程中有两个基类：Component和MeanComponent

- **Component（组件）**：代表一个能以图形化方式显现出来，并可与用户交互的对象，例如Button代表一个按钮，TextField代表一个文本框等
- **MeanComponent（菜单组件）**：则代表图形界面的菜单组件，包括MenuBar（菜单条），MenuItem（菜单项）等子类

其中，**Container是一种特殊的Component，它代表一种容器，可以盛装普通的Components**

**AWT还有一个非常重要的接口叫LayoutManager（布局管理器），如果一个容器中有多个组件，那么容器就需要使用LayoutManager来管理这些组件的布局方式**

![](C:\Users\Asinil\Desktop\学习\Java\28.2.2.PNG)



### 28.3Container容器

#### 28.3.1Container继承体系

![](C:\Users\Asinil\Desktop\学习\Java\28.3.PNG)

- Window是**可以独立存在的顶级窗口**，默认使用**BorderLayout**管理其内部组件布局
- Panel可以容纳其他组件，但**不能独立存在**，它必须内嵌其他容器中使用，默认使用**FlowLayout**管理其内部组件布局
- ScrollPane是一个带滚动条的容器，它也**不能独立存在**，默认使用**BorderLayout**管理其内部组件布局



#### 28.3.2常见API

Component作为基类，提供了如下常用的方法来设置组件的大小，位置，可见性等

|                     方法名                      |             功能             |
| :---------------------------------------------: | :--------------------------: |
|            setLocation(int x,int y)             |        设置组件的位置        |
|          setSize(int width,int height)          |        设置组件的大小        |
| **setBounds(int x,int y,int width,int height)** | **同时设置组件的大小和位置** |
|              setVisible(Boolean b)              |       设置组件的可见性       |

Container作为容器根类，提供了如下方法来访问容器中的组件

|                方法名                 |                             功能                             |
| :-----------------------------------: | :----------------------------------------------------------: |
|     Component add(Component comp)     | 向容器中添加其他组件（**该组件既可以是普通组件，也可以是容器**），并返回添加后的组件 |
| Component getComponentAt(int x,int y) |                       返回指定点的组件                       |
|        int getComponentCount()        |                    返回该容器内组件的数量                    |
|      Component[] getComponents()      |                    返回该容器内的所有组件                    |



#### 28.3.3 常见容器

##### 1.Window

![](C:\Users\Asinil\Desktop\学习\Java\28.3.3.PNG)

**创建Window窗口的步骤：**

- 创建一个窗口对象（使用Frame类，Frame是Window的子类）
- 指定窗口创建的位置，大小
- 设置窗口可视化

```java
public class WindowDemo {
    public static void main(String[] args) {
//        创建一个窗口对象
        Frame frame = new Frame("这里测试Window窗口");
//        指定窗口创建的位置，大小
//     	  frame.setLocation(100,100);
//        frame.setSize(500,300);
        frame.setBounds(100,100,500,300);//这里设置位置，大小的单位是像素
//        设置窗口对象可见
        frame.setVisible(true);
    }
}
```



##### 2.Panel

![](C:\Users\Asinil\Desktop\学习\Java\28.3.4.PNG)

**创建Panel内嵌容器步骤：**

- 先创建一个窗口对象（依旧使用Frame类）
- 创建一个Panel对象
- 往Panel容器中添加组件（文本和按钮）
- 将Panel添加到Window中
- 设置Window的位置和大小
- 设置Window可见

```java
public class PanelDemo {
    public static void main(String[] args) {
//        创建一个窗口对象，因为Panel以及其他容器对象都不能独立存在，都必须依附于Window存在
        Frame frame = new Frame("测试Panel容器窗口");
//        创建一个Panel对象
        Panel panel = new Panel();
//        在Panel容器中添加组件
//        创建一个文本框和按钮
        panel.add(new TextField("这里是一个测试文本"));
        panel.add(new Button("这里是一个测试按钮"));
//        将Panel放在在Window中
        frame.add(panel);
//        设置Window的位置和大小
        frame.setBounds(100,100,500,300);
//        设置Window可见
        frame.setVisible(true);
    }
}
```

**注意：idea程序的默认编码是UTF-8，但是操作系统创建窗口和按钮的默认编码是gbk，会出现乱码情况**

**解决方法：在运行-编辑配置中找到VM options配置，添加-Dfile.encoding=gbk**



##### 3.ScrollPane

![](C:\Users\Asinil\Desktop\学习\Java\28.3.5.PNG)

**创建ScrollPane容器步骤：**

- 先创建一个窗口对象（依旧使用Frame类）
- 创建一个ScrollPane对象
- 往ScrollPane容器中添加组件（文本和按钮）
- 将ScrollPane添加到Window中
- 设置Window的位置和大小
- 设置Window可见

```java
public class ScrollPaneDemo {
    public static void main(String[] args) {
//        创建一个窗口对象
        Frame frame = new Frame();

//        创建一个ScrollPane对象
        ScrollPane scrollPane = new ScrollPane(ScrollPane.SCROLLBARS_ALWAYS);//ScrollPane.SCROLLBARS_ALWAYS表示始终显示滚动条
//        往ScrollPane中添加内容
        scrollPane.add(new TextField("这是测试文本"));
        scrollPane.add(new Button("这是测试按钮"));
//        将ScrollPane添加到frame中
        frame.add(scrollPane);
//        对窗口设置位置和大小，以及可视化
        frame.setBounds(100,100,500,300);
        frame.setVisible(true);
    }
}
```

**为啥定义两个组件，只显示了一个按钮组件呢？**

这是因为ScrollPane使用了BorderLayout布局管理器的缘故



### 28.4LayoutManager布局管理器

#### 28.4.1LayoutManager概述

之前我们发现了一个问题，在ScrollPane容器中定义的组件，只显示了一个而另一个未显示，接下来我们就学习LayoutManager布局管理器的作用

**当我们在容器中定义一个组件，可以为组件手动设置位置和大小，就会造成程序的不通用性**；

例如：定义个Label组件显示”你好，世界“，我们需要让Label组件的宽和高刚好能显示出文本，这种大小为**最佳大小**。由于操作系统存在差异，在Windows上我们要达到这种效果需要把Label的高和宽分别设置为20px，100px；而Linux上需要设置为24px和120px才可以达到同样的效果

为了解决这个问题，**Java提供了LayoutManger布局管理器，可以根据运行平台自动调整组件大小，程序员不用再手动设置组件的大小和位置了，只需要为容器选择合适的布局管理器即可**



**布局管理器的继承体系**

![](C:\Users\Asinil\Desktop\学习\Java\28.4.1.PNG)



- GridLayout：网格布局
- FlowLayout：流式布局
- CardLayout：卡片布局
- GridBagLayout：网格包布局
- BorderLayout：边框布局



#### 28.4.2 FlowLayout

在FlowLayout布局管理器中，组件像水流一样像某方向流动（排列），遇到障碍（边界）就折回，重头开始排列。在默认情况下，FlowLayout布局管理器从左向右排列所有组件，遇到边界就会折回下一行重新开始

|                构造方法                 |                           方法功能                           |
| :-------------------------------------: | :----------------------------------------------------------: |
|              FlowLayout()               | 使用默认的对齐方式及默认的垂直间距，水平间距创建FlowLayout布局管理器 |
|          FlowLayout(int align)          | 使用**指定的对齐方式**及默认的垂直间距，水平间距创建FlowLayout布局管理器 |
| FlowLayout(int align,int hgap,int vgap) | 使用**指定的的对齐方式及指定的垂直间距，水平间距**创建FlowLayout布局管理器 |

**FlowLayout中组件的排列方向（从左向右，从右向左，从中间向两边等）**

该参数使用的是FlowLayout类的静态常量：**FlowLayout.LEFT，FlowLayout.CENTER，FlowLayout.RIGHT**，默认是左对齐

**FlowLayout中组件中间距通过参数设置，单位是像素，默认是5个像素**



**案例：FlowLayout演示**

需求：使用FlowLayout布局管理器，在窗口中创建100个按钮

![](C:\Users\Asinil\Desktop\学习\Java\28.4.2.PNG)

```java
public class FlowLayoutDemo {
    public static void main(String[] args) {
//        创建一个窗口对象
        Frame frame = new Frame("测试FlowLayout窗口");

//        通过setLayout方法设置容器的布局管理器
        frame.setLayout(new FlowLayout(FlowLayout.LEFT,20,20));
//        添加多个按钮到frame中
        for (int i = 0; i < 100; i++) {
            frame.add(new Button("按钮"+i));
        }
//        自定义大小已经不适合多个组件的窗口了
//        设置窗口的最佳大小，pack()方法
        frame.pack();

//        设置窗口可见
        frame.setVisible(true);
    }
}
```



#### 28.4.3 BorderLayout

**BorderLayout将容器分为EAST，SOUTH，WEST，NORTH，CENTER五个区域，普通组件可以被放置在这5个区域的任意一个中**。

![](C:\Users\Asinil\Desktop\学习\Java\28.4.3.PNG)

当改变使用BorderLayout的容器大小时，NORTH，SOUTH，CENTER的区域水平调整，而EAST，WEST和CENTER区域垂直调整

**使用BorderLayout的注意事项：**

- 当向使用的BorderLayout布局管理器的容器中添加组件时，需要指定添加到哪个区域，若果没有指定添加到哪个区域，**默认添加到CENTER区域**
- 如果向同一个区域添加多个组件时，**后放入的组件会覆盖先放入的组件**

**BorderLayout的构造方法：**

|             方法名              |                           说明                           |
| :-----------------------------: | :------------------------------------------------------: |
|         BorderLayout()          | 使用默认的水平间距，垂直间距，创建BorderLayout布局管理器 |
| BorderLayout(int hgap,int vgap) | 使用指定的水平间距，垂直间距，创建BorderLayout布局管理器 |

**案例1：BorderLayout演示**

需求：使用BorderLayout布局管理器，在容器的每一个区域中创建一个按钮

![](C:\Users\Asinil\Desktop\学习\Java\28.4.4.PNG)

```java
public class BorderLayoutDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("测试BorderLayout布局管理器窗口");

//        指定窗口的创建位置
        frame.setLocation(300,300);
//        将窗口的布局管理器切换为BorderLayout
        frame.setLayout(new BorderLayout(20,10));
//        在不同区域创建按钮
        frame.add(new Button("北侧按钮"),BorderLayout.NORTH);
        frame.add(new Button("南侧按钮"),BorderLayout.SOUTH);
        frame.add(new Button("东侧按钮"),BorderLayout.EAST);
        frame.add(new Button("西侧按钮"),BorderLayout.WEST);
        frame.add(new Button("中间按钮"),BorderLayout.CENTER);

        frame.pack();
        frame.setVisible(true);
    }
}
```

**如果不往某个区域中放入组件，那么该区域不会空出来，而是被中间区域覆盖**



**案例2：BorderLayout演示Plus**

需求：放入多个组件在同一个区域会被覆盖，那么如何在中间区域同时放一个按钮和一个文本框两个组件？

![](C:\Users\Asinil\Desktop\学习\Java\28.4.5.PNG)

```java
public class BorderLayoutDemo02 {
    public static void main(String[] args) {
        Frame frame = new Frame("测试BorderLayout布局管理器窗口2");

//        指定窗口的创建位置
        frame.setLocation(300,300);
//        将窗口的布局管理器切换为BorderLayout
        frame.setLayout(new BorderLayout(20,10));
//        在不同区域创建按钮
        frame.add(new Button("北侧按钮"),BorderLayout.NORTH);
        frame.add(new Button("南侧按钮"),BorderLayout.SOUTH);

        /*需求：放入多个组件在同一个区域会被覆盖，那么如何在中间区域同时放一个按钮和一个文本框两个组件？*/
//        frame.add(new Button("中间按钮"),BorderLayout.CENTER);
//        我们可以使用一个内嵌容器Panel，将多个按钮添加到当中，然后添加到窗口里
        Panel p = new Panel();
        p.add(new Button("中间按钮"));
        p.add(new TextField("BorderLayout测试文本"));

        frame.add(p);

        frame.pack();
        frame.setVisible(true);
    }
}
```



#### 28.4.4 GridLayout

GirdLayout布局管理器将容器分割成横纵分隔的网格，每一个网格所占区域大小相同。当向GirdLayout布局管理器添加组件时，默认从左向右，从上到下依次添加到每一个网格中。

于FlowLayout不同的是，放置在GirdLayout布局管理器中的各组件大小由组件所处区域决定（每个组件将自动占满整个区域）

**GirdLayout的构造方法**

|                    构造方法                     |                             说明                             |
| :---------------------------------------------: | :----------------------------------------------------------: |
|          GirdLayout(int rows,int cols)          | 采用指定的行数，列数，以及默认的横向间距和纵向间距将容器分割成多个网络 |
| GirdLayout(int rows,int cols,int hgap,int vgap) | 采用指定的行数，列数，以及指定的横向间距和纵向间距将容器分割成多个网络 |



**案例：计算器**

需求：使用Frame+Panel，配合BorderLayout+GirdLayout布局管理器完成一个计算器效果

![](C:\Users\Asinil\Desktop\学习\Java\28.4.6.PNG)

```java
public class GirdLayoutDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("计算器");
        frame.setLocation(500,500);
//        创建一个Panel对象，里面只存放一个TextField对象
        Panel p1 = new Panel();
        p1.add(new TextField(30));//这里的30表示可容纳数字

//        把这个Panel添加到窗口的北边区域
        frame.add(p1,BorderLayout.NORTH);//窗口的默认布局管理器为BorderLayout

//        创建一个Panel对象，并将其布局管理器设置为GirdLayout
        Panel p2 = new Panel();
        p2.setLayout(new GridLayout(5,4,10,10));
//        往这个Panel容器中添加组件
        p2.add(new Button("1"));
        p2.add(new Button("2"));
        p2.add(new Button("3"));
        p2.add(new Button("+"));
        p2.add(new Button("4"));
        p2.add(new Button("5"));
        p2.add(new Button("6"));
        p2.add(new Button("-"));
        p2.add(new Button("7"));
        p2.add(new Button("8"));
        p2.add(new Button("9"));
        p2.add(new Button("*"));
        p2.add(new Button("C"));
        p2.add(new Button("0"));
        p2.add(new Button("="));
        p2.add(new Button("/"));
//        将Panel添加到中间区域
        frame.add(p2);

        frame.pack();
        frame.setVisible(true);
    }
}
```



#### 28.4.5 GirdBagLayout

GirdBagLayout布局管理器的功能最强大，但也最复杂，**与GridLayout布局管理器不同的是，在GirdBagLayout布局管理器中，一个组件可以跨一个或者多个网格，并且可以设置各网格的大小互不相同，从而增加布局的灵活性。当窗口发生变化时，GirdBagLayout布局管理器也可以准确的控制窗口各部分的拉伸，**

由于在GirdBagLayout布局中，每个组件可以占用多个网格，此时我们往容器中添加组件时，就需要具体的控制每一个组件占用多少个网格，Java提供的**GirdBagConstraints类，与特定的组件绑定，可以完成具体大小和跨越性的设置**。



**但在Swing中有更强大的布局管理器完成相同的功能效果，对于GirdBagLayout我们只需要简单的做个了解**



#### 28.4.6 CardLayout

**CardLayout布局管理器以时间而非空间来管理它里面的组件，他将加入容器的所有组件看成一叠卡片（每个卡片其实都是一个组件），每次只有最上面的那个Component才可见**。就好像一副扑克，它们叠在一起，每次只有最上面的卡片才会被看见

|               方法名               |                             说明                             |
| :--------------------------------: | :----------------------------------------------------------: |
|            CardLayout()            |                创建默认的CardLayout布局管理器                |
|   CardLayout(int hgap,int vgap)    | 通过指定卡片与容器左右边界的间距（hgap），上下间距（vgap）来创建CardLayout布局管理器 |
|      first(Container target)       |                 显示target容器中的第一张卡片                 |
|       last(Container target)       |                显示target容器中的最后一张卡片                |
|     previous(Container target)     |                 显示target容器中的前一张卡片                 |
|       next(Container target)       |                 显示target容器中的后一张卡片                 |
| show(Container target,String name) |               显示target容器中的指定名称的卡片               |



**案例：CardLayout演示**

需求：使用Frame+Panel，以及CardLayout布局管理器，完成以下图片的效果，点击底部按钮切换卡片

![](C:\Users\Asinil\Desktop\学习\Java\28.4.7.PNG)

```java
public class CardLayoutDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("测试CardLayout布局管理器窗口");

//        创建一个panel，用于存放卡片，并设置容器布局管理器为CardLayout
        Panel p1 = new Panel();
        CardLayout cardLayout = new CardLayout(10, 10);//后面会使用到，需要写出来
        p1.setLayout(cardLayout);
//        往容器中添加组件并命名
        String[] strName = {"第一张","第二张","第三张","第四张","第五张"};
        for (int i = 0; i < strName.length; i++) {
            p1.add(strName[i],new Button(strName[i]));
        }
//        将容器存放在窗口中间区域
        frame.add(p1);

//        创建第二个panel容器，并创建组件
        Panel p2 = new Panel();
        Button b1 = new Button("第一张");
        Button b2 = new Button("最后一张");
        Button b3 = new Button("上一张");
        Button b4 = new Button("下一张");
        Button b5 = new Button("第三张");
        
//        实现下面按钮功能
//        创建事件监听器
        ActionListener listener= new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
//                监听器监听你当前按下的按钮是哪个按钮
                String actionCommand = e.getActionCommand();//这个返回的是按钮上的字符串
                switch (actionCommand){
                    case "第一张":
                        cardLayout.first(p1);
                        break;
                    case "最后一张":
                        cardLayout.last(p1);
                        break;
                    case "上一张":
                        cardLayout.previous(p1);
                        break;
                    case "下一张":
                        cardLayout.next(p1);
                        break;
                    case "第三张":
                        cardLayout.show(p1,"第三张");
                        break;
                }

            }
        };
//        将这些按钮和事件监听器绑定到一块
        b1.addActionListener(listener);
        b2.addActionListener(listener);
        b3.addActionListener(listener);
        b4.addActionListener(listener);
        b5.addActionListener(listener);

//      将这些组件添加到容器中
        p2.add(b1);
        p2.add(b2);
        p2.add(b3);
        p2.add(b4);
        p2.add(b5);

//        将容器添加到窗口的下区域
        frame.add(p2,BorderLayout.SOUTH);

        frame.pack();
        frame.setVisible(true);
    }
}
```



#### 28.4.7 BoxLayout

为了简化开发，**Swing引入了一个新的布局管理器：BoxLayout**。BoxLayout可以在垂直和水平两个方向上摆放GUI组件，BoxLayout提供了如下简单的构造器：

- BoxLayout(Container target,int axis)：指定创建基于target容器的BoxLayout布局管理器，该布局管理器里的组件按axis方向排列。其中axis有BoxLayout.X_AXIS（横向）和BoxLayout.Y_AXIS（纵向）两个方向

**案例：演示BoxLayout布局管理器**

需求：使用Frame和BoxLayout完成下图效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.4.8.PNG)

```java
public class BoxLayoutDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("测试BoxLayout布局管理器");

//        基于frame容器，创建BoxLayout对象，并且该对象存放组件是垂直存放
        BoxLayout boxLayout = new BoxLayout(frame, BoxLayout.Y_AXIS);

//        将BoxLayout对象赋值给窗口对象
        frame.setLayout(boxLayout);

//        将两个按钮添加到窗口中
        frame.add(new Button("按钮1"));
        frame.add(new Button("按钮2"));

        frame.pack();
        frame.setVisible(true);
    }
}
```



在java.swing包中，提供了一个新的容器Box，该容器的默认布局管理器为BoxLayout，大多数情况下，使用Box容器去容纳多个GUI组件，然后把Box容器去作为一个组件，添加到其他容器中，从而形成整体的窗口布局

|             方法名              |             说明              |
| :-----------------------------: | :---------------------------: |
| static Box creatHorizontalBox() | 创建一个水平排列组件的Box容器 |
|  static Box creatVerticalBox()  | 创建一个垂直排列组件的Box容器 |

案例2：Box使用

需求：使用Frame和Box完成下图效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.4.9.png)

```java
public class BoxLayoutDemo02 {
    public static void main(String[] args) {
        Frame frame= new Frame("测试Box容器窗口");

//        创建两个box容器，一个水平排列，一个垂直排列
        Box b1 = Box.createHorizontalBox();
        Box b2 = Box.createVerticalBox();

//        分别向两个容器中添加两个按钮
        b1.add(new Button("水平按钮1"));
        b1.add(new Button("水平按钮2"));
        b2.add(new Button("垂直按钮1"));
        b2.add(new Button("垂直按钮2"));
//        再创建一个box容器，垂直排列，将前面两个box容器添加进去
        Box b = Box.createVerticalBox();
        b.add(b1);
        b.add(b2);
//        将最后一个box容器，添加到frame窗口对象中
        frame.add(b);
        frame.pack();
        frame.setVisible(true);
    }
}
```

通过前面的案例，我们发现被它管理的容器的组件之间是没有间隔的，不是特别美观，但之前学习的几种布局，组件之间都会有一些间隔，那么使用BoxLayout布局管理器如何给组件设置间隔呢？

其实很简单，我们只需要在原有的组件需要间隔的地方，添加间隔即可，而每一个间隔都可以看作一个组件，只不过该组件内有内容，仅仅起到一种分隔作用

Box类中，提供了5个方便的静态方法来生成这些间隔组件：

|                       方法名                        |                             说明                             |
| :-------------------------------------------------: | :----------------------------------------------------------: |
|       static Component createHorizontalGlue()       |       创建一条水平Glue（可在两个方向上同时拉伸的间距）       |
|        static Component createVerticalGlue()        |       创建一条垂直Glue（可在两个方向上同时拉伸的间距）       |
|  static Component createHorizontalStrut(int width)  | 创建一条指定宽度（宽度固定了，不能拉伸）的水平Strut（可在垂直方向上拉伸的间距） |
| static Component createVerticaltalStrut(int height) | 创建一条指定高度（高度固定了，不能拉伸）的垂直Strut（可在水平方向上拉伸的间距） |

**案例3：Box间距**

需求：在案例二的基础上，给每个按钮之间创建间距

![](C:\Users\Asinil\Desktop\学习\Java\28.4.10.PNG)

```java
public class BoxLayoutDemo03 {
    public static void main(String[] args) {
        Frame frame = new Frame("测试Box类创建间距的窗口");

//        创建水平排列的Box容器，和垂直排列的Box容器
        Box hbox = Box.createHorizontalBox();
        Box vbox = Box.createVerticalBox();
//        向前面两个容器中添加按钮，并添加每个按钮之间的间隔
        hbox.add(new Button("水平按钮1"));
        hbox.add(Box.createHorizontalGlue());//该分隔在两个方向上都可以拉伸
        hbox.add(new Button("水平按钮2"));
        hbox.add(Box.createHorizontalStrut(30));
        hbox.add(new Button("水平按钮3"));

        vbox.add(new Button("垂直按钮1"));
        vbox.add(Box.createVerticalStrut(20));
        vbox.add(new Button("垂直按钮2"));

//        创建一个新的容器，将之前两个box容器垂直排列
        Box box = Box.createVerticalBox();
        box.add(hbox);
        box.add(Box.createVerticalStrut(10));
        box.add(vbox);

//        把Box容器添加到frame中
//        frame.add(hbox,BorderLayout.NORTH);
//        frame.add(vbox);
        frame.add(box);

        frame.pack();
        frame.setVisible(true);
    }
}
```



### 28.5AWT中常用的组件

#### 28.5.1常用组件

|    组件名     |                             功能                             |
| :-----------: | :----------------------------------------------------------: |
|    Button     |                             按钮                             |
|    Canvas     |                        用于绘图的画布                        |
|   Checkbox    |             复选框组件（也可当作单选框组件使用）             |
| CheckboxGroup | 用于将多个Checkbox组件组合成一组，一组Checkbox组件将只有一个可以被选中，即全部变成单选框组件 |
|    Choice     |                          下拉选择框                          |
|     Frame     |               窗口，GUI程序里通过该类创建窗口                |
|     Label     |                  标签类，用于放置提示性文本                  |
|     List      |                 列表框组件，可以添加多项条目                 |
|     Panel     |         不能单独存在基本容器类，必须放置到其他容器中         |
|   Scrollbar   | 滑动条组件，如果用户需要输入位于某个范围的值，就可以使用滑动条组件，比如调色板中的RGB的三个值所用的滑动条。当创建一个滑动条时，必须指定它的方向，初始值，滑块大小，最大值和最小值 |
|  ScrollPane   |                带水平以及垂直滚动条的容器组件                |
|   TextArea    |                          多行文本域                          |
|   TextField   |                          单行文本框                          |



需求：实现下图效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.5.1.PNG)

```java
public class BasicComponentDemo {
//    将组件都定义到类中
    Frame frame = new Frame("测试基本组件窗口");

    TextArea ta  = new TextArea(5,20);//5行20列

    Choice colorChoice = new Choice();

    CheckboxGroup cbg = new CheckboxGroup();
    Checkbox male = new Checkbox("男",cbg,true);//属于cbg这组，默认选中true
    Checkbox female = new Checkbox("女",cbg,false);

    Checkbox isMarried = new Checkbox("是否已婚？");

    TextField tf = new TextField(50);
    Button ok  = new Button("确认");

    List colorList = new List(6,true);//true表示支持多选，默认为单选

    public void init(){
//        组装界面
//        组装底部区域
    /*    Panel p1 = new Panel();
        p1.add(tf);
        p1.add(ok);
        frame.add(p1,BorderLayout.SOUTH);*/
        
//        为什么不使用Panel而使用Box来作为容器组装：Panel使用的是FlowLayout流式布局管理器，当将窗口放大时，不能很好的将组件覆盖到整片区域
        Box box1 = Box.createHorizontalBox();
        box1.add(tf);
        box1.add(Box.createHorizontalStrut(5));
        box1.add(ok);
        frame.add(box1,BorderLayout.SOUTH);

//        组装左边区域
//          组装选择部分
        colorChoice.add("红色");
        colorChoice.add("绿色");
        colorChoice.add("蓝色");
        Box box2 = Box.createHorizontalBox();
        box2.add(colorChoice);
        box2.add(male);
        box2.add(female);
        box2.add(isMarried);

//          组装文本域
        Box topLeft = Box.createVerticalBox();
        topLeft.add(ta);
        topLeft.add(box2);
//        组装顶部左边和顶部右边
        colorList.add("红色");
        colorList.add("绿色");
        colorList.add("蓝色");
        colorList.add("黄色");
        colorList.add("紫色");
        Box top = Box.createHorizontalBox();
        top.add(topLeft);
        top.add(colorList);
        frame.add(top);

        frame.pack();
        frame.setVisible(true);
    }

    public static void main(String[] args) {
        new BasicComponentDemo().init();
    }
}
```



#### 28.5.2对话框Dialog

**Dialog**是Window类的另一个子类（Frame也是），**是一个容器类，属于特殊组件**。

对话框是**可以独立存在的顶级窗口**，因此**用法与普通窗口的用法几乎完全一致**，但是使用对话框需要注意以下几点：

- 对话框通常依赖于其他窗口，就是通常有一个父窗口
- 对话框有非模式（non-modal）和模式（modal）两种，当某个模式对话框被打开后，该模式对话框总是位于它的父窗口之上，在模式对话框被关闭之前，父窗口无法获得焦点

|                     方法名                     |                             说明                             |
| :--------------------------------------------: | :----------------------------------------------------------: |
| Dialog(Frame owner,String title,Boolean modal) | 创建一个对话框对象<br/>owner：当前对话框的父窗口<br/>title：当前对话框的标题<br/>modal：当前对话框是否是模式对话框，true/false |

**案例：演示Dialog**

需求：通过frame,button,dialog来实现下图所示的效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.5.2.PNG)

```java
public class DialogDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("测试Dialog对话框窗口");
//        创建两个对话框Dialog对象，一个模式的，一个非模式的
        Dialog d1 = new Dialog(frame,"模式对话框",true);
        Dialog d2 = new Dialog(frame,"非模式对话框",false);
//        通过setBounds方法设置对话框大小
        d1.setBounds(20,30,300,200);
        d2.setBounds(20,30,300,200);
//        创建两个按钮
        Button b1 = new Button("模式对话框");
        Button b2 = new Button("非模式对话框");
//        给这两个按钮添加点击后的行为
        ActionListener listener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String actionCommand = e.getActionCommand();
                switch (actionCommand){
                    case "模式对话框":
                        d1.setVisible(true);
                        break;
                    case "非模式对话框":
                        d2.setVisible(true);
                        break;
                }
            }
        };
        b1.addActionListener(listener);
        b2.addActionListener(listener);
//        把按钮添加到frame中
        frame.add(b1,BorderLayout.NORTH);
        frame.add(b2,BorderLayout.SOUTH);


//        设置最佳大小，并设置可见
        frame.pack();
        frame.setVisible(true);
    }
}
```



在Dialog对话框中，可以根据需求，自定义内容

**案例：Dialog内容**

需求：点击按钮，弹出一个模式对话框，其内容如下：

![](C:\Users\Asinil\Desktop\学习\Java\28.5.3.PNG)

```java
public class DialogDemo02 {
    public static void main(String[] args) {
        Frame frame = new Frame("测试模式对话框的窗口");
//        创建一个模式对话框
        Dialog dialog = new Dialog(frame,true);
        dialog.setBounds(100,100,500,300);
//        在模式对话框中添加一个文本框和一个按钮（垂直排列），点击后模式对话框消失
        Box box = Box.createVerticalBox();
        box.add(new TextField(20));

        Button b1 = new Button("确认");
        b1.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                dialog.setVisible(false);
            }
        });
        box.add(b1);

        dialog.add(box);

//        在frame中添加一个模式对话框按钮,并为其添加响应事件
        Button b2 = new Button("模式对话框");
        b2.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                dialog.setVisible(true);
            }
        });

        frame.add(b2);

        frame.pack();
        frame.setVisible(true);
    }
}
```



#### 28.5.3 FileDialog

Dialog还有一个子类：**FileDialog，它代表一个文件对话框，用于打开或者保存文件**

**注意**：FileDialog无法指定模态或者非模态，这是因为FileDialog依赖运行平台的实现，如果运行平台的文件对话框是模态的，那么FileDialog也是模态的，否则就是非模态的

|                     方法名                     |                             说明                             |
| :--------------------------------------------: | :----------------------------------------------------------: |
| FileDialog(Frame parent,String title,int mode) | 创建一个文件对话框<br/>parent：指定父类窗口<br/>title：对话框标题<br/>mode：文件对话框类型，如果指定为FileDialog.LOAD，用于打开文件；如果指定为FileDialog.SAVE用于保存文件 |
|             String getDirectory()              |               获取被打开或者保存的文件绝对路径               |
|                String getFile()                |                  获取被打开或者保存的文件名                  |

**案例：演示FileDialog**

需求：使用frame,button和FileDialog完成下图的效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.5.4.PNG)

```java
public class FileDialogDemo {
    public static void main(String[] args) {
//        创建窗口对象
        Frame frame = new Frame("演示FileDialog的窗口");
//        创建两个按钮到窗口上（垂直排列）
        Button b1 = new Button("打开文件");
        Button b2 = new Button("保存文件");

//        创建文件对话框，并将事件绑定到按钮上
        FileDialog fd1 = new FileDialog(frame,"选择要打开的文件",FileDialog.LOAD);
        FileDialog fd2 = new FileDialog(frame,"保存要保存的文件",FileDialog.SAVE);

        b1.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                fd1.setVisible(true);//代码会阻塞在这
//                获取打开文件的路径
                String directory = fd1.getDirectory();
                String file = fd1.getFile();
                System.out.println("打开的文件路径为："+directory);
                System.out.println("打开的文件名为："+file);
            }
        });

        b2.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                fd2.setVisible(true);
//                获取打开文件的路径
                String directory = fd2.getDirectory();
                String file = fd2.getFile();
                System.out.println("保存的文件路径为："+directory);
                System.out.println("保存的文件名为："+file);
            }
        });

//        将按钮添加到frame上
        Box vbox = Box.createVerticalBox();
        vbox.add(b1);
        vbox.add(b2);
        frame.add(vbox);
//        设置窗口
        frame.pack();
        frame.setVisible(true);
    }
}
```



### 28.6事件处理

前面介绍了如何放置各种组件，从而得到了丰富多彩1图形界面，但这些界面还不能响应用户的任何操作。比如单机前面窗口右上角的`X`按钮，但是窗口依然不会关闭。因为在AWT编程中，所有用户的操作都必须经过一套事件处理机制来完成，而Frame和组件本省并没有事件处理能力

#### 28.6.1GUI事件处理机制

什么是事件处理机制呢？

**定义**：当某个**组件（事件源）**上发生**某些操作（事件**）的时候，会自动的触发一段**代码的执行（事件监听器）**

- **事件源（Event Source）**：操作发生的场所，**通常指某个组件**，例如按钮，窗口等
- **事件（Event）**：在**事件源上发生的操作可以称为事件**，GUI会把事件都封装到一个Event对象中，如果需要知道该事件的详细信息，就可以通过Event对象来获取
- **事件监听器（Event Listener）**：当在某个事件源上发生了某个事件，**事件监听器就可以对这个事件进行处理**
- **注册监听**：把某个事件监听器（A）通过某个事件（B）绑定到某个事件源（C）上，当在事件源C上发生了事件B后，那么事件监听器A的代码就会自动执行

![](C:\Users\Asinil\Desktop\学习\Java\28.6.1.PNG)

**使用步骤：**

- 创建事件源组件对象
- 自定义类，实现XxxListener接口，重写方法
- 创建事件监听器对象（自定义对象）
- 事件源组件对象的addXxxListener方法完成注册监听



案例：完成下图效果，点击确定按钮，在单行文本域内显示Hello World！

![](C:\Users\Asinil\Desktop\学习\Java\28.6.2.PNG)

```java
public class EventDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("案例：完成下图效果，点击确定按钮，在单行文本域内显示Hello World！");
//        创建事件源组件对象
        TextField textField = new TextField();
        Button button = new Button("确定");

//        自定义类，实现XxxListener接口，重写方法
//        创建事件监听器对象（自定义对象）
//        事件源组件对象的addXxxListener方法完成注册监听
      /*  ActionListener listener = new ActionListener(){
            @Override
            public void actionPerformed(ActionEvent e) {
                textField.setText("Hello World!");
            }
        };
        button.addActionListener(listener);
        */
//      简化：这里实现actionListener接口,使用匿名内部类方法
        /*
        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                textField.setText("Hello World!");
            }
        });
        */

        //        Lambda表达式继续简化
        button.addActionListener((e -> textField.setText("Hello World!")));
        
        Box box = Box.createVerticalBox();
        box.add(textField);
        box.add(button);

        frame.add(box);
        frame.pack();
        frame.setVisible(true);
    }
}
```

**注意**：如果事件监听器只监听一个事件源，使用匿名内部类方便（或者Lambda表达式）；如果多个事件源都要用到这个事件监听器，建议使用内部类方式



#### 28.6.2 GUI中常见的事件和事件监听器

事件监听器必须实现事件监听器的接口，AWT提供了大量的事件监听器接口用于实现不同类型的事件监听器，用于监听器不同的事件

AWT中提供了丰富的事件类，用于封装不同组件上所发生的特定操作，AWT的事件类都是AWTEvent类的子类，AWTEvent是AWTObject的子类



##### 1.事件

AWT吧事件分为两大类：

- **低级事件：这类事件是基于某个特定动作的事件。**比如：进入，点击，拖放等动作的鼠标事件，再比如得到焦点等失去焦点事件

  |      事件      |                           触发时机                           |
  | :------------: | :----------------------------------------------------------: |
  | ComponentEvent | 组件事件，当组件尺寸，位置发生移动，显示/隐藏状态发生改变时触发该事件 |
  | ContainerEvent |     容器事件，当容器里发生添加组件，删除组件时触发该事件     |
  |  WindowEvent   | 窗口事件，当窗口状态发生改变（打开，关闭，最大化，最小化）时触发该事件 |
  |   FocusEvent   |       焦点事件，当组件得到焦点或者失去焦点时触发该事件       |
  |    KeyEvent    |         键盘事件，当按键按下，松开，单击时触发该事件         |
  |   MouseEvent   | 鼠标事件，当进行单击，按下，松开，移动鼠标等动作时触发该事件 |
  |   PaintEvent   | 组件绘制事件，该事件是一个特殊事件类型，当GUI组件调用update/paint方法来呈现自身时触发该事件，该事件并非专用于事件处理模型 |

  

- **高级事件：这类事件并不会基于某一个特定的动作，而是根据功能含义定义的事件**

  |      事件       |                           触发时机                           |
  | :-------------: | :----------------------------------------------------------: |
  |   ActionEvent   | 动作事件，当按钮，菜单项被单击，在TextField中按enter键时触发 |
  | AdjustmentEvent |      调节事件，在滑动条上移动滑块以调节数值时触发该事件      |
  |    ItemEvent    |      选项事件，当用户选中某一项或取消某一项时触发该事件      |
  |    TextEvent    |     文本事件，当文本框，文本域的文本发生改变时触发该事件     |

  

##### 2.事件监听器

不同事件需要使用不同的事件监听器，不同的事件监听器需要实现不同的监听器接口，当指定事件发生后，事件监听器就会调用所包含的事件处理器（实例方法）来处理事件

|    事件类别     |             说明             |    监听器接口名     |
| :-------------: | :--------------------------: | :-----------------: |
|   ActionEvent   |           激活组件           |   ActionListener    |
|    ItemEvent    |         选择某些项目         |    ItemListener     |
|   MouseEvent    |           鼠标移动           | MouseMotionListener |
|   MouseEvent    |          鼠标点击等          |    MouseListener    |
|    KeyEvent     |           键盘输入           |     KeyListener     |
|   FocusEvent    |     组件收到或者失去焦点     |    FocusListener    |
| AdjustmentEvent |       移动滚动条等组件       | AdjustmentListener  |
| ComponentEvent  | 对象移动，缩放，显示，隐藏等 |  ComponentListener  |
|   WindowEvent   |      窗口收到窗口级事件      |   WindowListener    |
| ContainerEvent  |      容器内添加删除组件      |  ContainerListener  |
|    TextEvent    |   文本字段或文本区发生改变   |    TextListener     |



##### 3.案例

案例一

需求：通过ContainerListener监听Frame容器添加组件，通过TextListener监听TextField组件内容变化，通过ItemListener监听choice条目中状态变化

![](C:\Users\Asinil\Desktop\学习\Java\28.6.3.PNG)

```java
public class ListenerDemo {
    public static void main(String[] args) {
        Frame frame = new Frame("测试事件监听器窗口");
        TextField tf = new TextField(30);
        Choice c = new Choice();
        c.add("柳岩");
        c.add("舒淇");
        c.add("闫妮");

//        通过ContainerListener监听Frame容器添加组件
        frame.addContainerListener(new ContainerListener() {
            @Override
            public void componentAdded(ContainerEvent e) {
                Component child = e.getChild();
                System.out.println("添加了一个组件:" + child);
            }

            @Override
            public void componentRemoved(ContainerEvent e) {
                Component child = e.getChild();
                System.out.println("移除了一个组件" + child);
            }
        });
//          通过TextListener监听TextField组件内容变化，
        tf.addTextListener(new TextListener() {
            @Override
            public void textValueChanged(TextEvent e) {
                String text = tf.getText();
                System.out.println("当前文本框的内容为：" + text);
            }
        });
//          通过ItemListener监听choice条目中状态变化
        c.addItemListener(new ItemListener() {
            @Override
            public void itemStateChanged(ItemEvent e) {
                Object item = e.getItem();
                System.out.println("切换选项为：" + item);
            }
        });


        frame.add(c, BorderLayout.WEST);
        frame.add(tf);

        frame.pack();
        frame.setVisible(true);
    }
}
```



案例二

需求：给frame设置windowListener，监听用户点击X的动作，如果用户点击X，则关闭当前对话框

```java
public class ListenerDemo02 {
    public static void main(String[] args) {
        Frame frame = new Frame("测试窗口关闭的功能");
        frame.setBounds(500,500,500,300);
//        适配器设计模式：适配器类将接口的类全部重写空方法，我们调用适配器类就可以想重写哪个方法就重写哪个方法
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
//                停止当前程序
                System.exit(0);
            }
        });

        frame.setVisible(true);
    }
}
```



### 28.7菜单组件

前面讲解了如果构建GUI界面，其实就是把一些GUI组件，按照一定的布局放入容器中展示就可以了。

在实际开发过程中，除了主界面，还有一类比较重要的内容就是菜单相关组件，可通过菜单相关组件很方便的使用特定的功能，在AWT中菜单相关组件的使用和之前学习的组件是一模一样的，只需要把菜单条，菜单，菜单项组合到一起，按照一定的布局，放入容器中即可



**下表给出常见的菜单相关组件：**

|   菜单组件名称   |                             功能                             |
| :--------------: | :----------------------------------------------------------: |
|     MenuBar      |                      菜单条，菜单的容器                      |
|       Menu       | 菜单组件，菜单项的容器，他也是MenuItem的子类，所以可作为菜单项使用 |
|    PopupMenu     |                上下文菜单组件（右键菜单组件）                |
|     MenuItem     |                          菜单项组件                          |
| CheckboxMenuItem |                       复选框菜单项组件                       |

**下图是常见菜单相关组件继承体系图：**

![](C:\Users\Asinil\Desktop\学习\Java\28.7.1.PNG)



**菜单相关组件使用**

1. 准备菜单项组件，这些组件可以是MenuItem及其子类对象
2. 准备菜单组件menu或者PopupMenu（右键弹出菜单），把第一步中准备好的菜单项组件添加进来
3. 准备菜单条组件MenuBar，把第二步中准备好的菜单组件Menu添加进来
4. 把第三步准备好的菜单条组件添加到窗口对象中显示



**小技巧：**

1. 如果要在某个菜单的菜单项之间添加分割线，那么只需要调用Menu的add(new MenuItem("."))即可

2. 如果要给某个菜单项关联快捷键功能，那么只需要在创建菜单对象时设置即可

   例如给菜单项关联crtl+shift+Q的快捷键，只需要：new MenuItem("菜单项名称",new MenuShortcut(KeyEvent.VK Q,true));



案例1

需求：使用awt中常用的菜单组件，完成下图效果

![](C:\Users\Asinil\Desktop\学习\Java\28.7.2.PNG)

```java
public class BasicMenuDemo {
    private Frame frame = new Frame("菜单测试窗口");

    //        创建菜单项
    MenuItem mi1 = new MenuItem("自动换行");
    MenuItem mi2 = new MenuItem("复制");
    MenuItem mi3 = new MenuItem("粘贴");
    MenuItem mi4 = new MenuItem("注释",new MenuShortcut(KeyEvent.VK_Q,true));//关联快捷键，ctrl+shift+Q
    MenuItem mi5 = new MenuItem("取消注释");

    Menu m1 = new Menu("文件");
    Menu m2 = new Menu("编辑");
    Menu m3 = new Menu("格式");

    //创建菜单条
    MenuBar mb = new MenuBar();
//    创建文本框
    TextArea ta = new TextArea(6,40);

    public void init(){
//        将前面的菜单项组装起来
        mi4.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                ta.append("注释：");
            }
        });
//        组装格式菜单项
        m3.add(mi4);
        m3.add(mi5);
//        组装编辑菜单
        m2.add(mi1);
        m2.add(mi2);
        m2.add(mi3);
        m2.add(m3);
//        组装菜单条
        mb.add(m1);
        mb.add(m2);
//       将菜单条放入frame中
        frame.setMenuBar(mb);
        frame.add(ta);

        frame.pack();
        frame.setVisible(true);
    }

    public static void main(String[] args) {
        new BasicMenuDemo().init();
    }
}
```



案例2

需求：通过PopupMenu实现下图效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.7.3.PNG)

实现思路：

1. 创建PupopMenu菜单组件
2. 创建多个MenuItem菜单项，并添加到PopupMenu中
3. 将PopupMenutian加到目标组件中
4. 为需要右击出现PopupMenu菜单的组件，注册鼠标监听事件，当监听到用户释放鼠标右键时，弹出菜单

```java
public class BasicPopupMenuDemo {
    Frame frame = new Frame("PopupMemu菜单测试窗口");
//    创建PopupMenu菜单组件
    PopupMenu pop = new PopupMenu();
//    创建菜单项
    MenuItem mi1 = new MenuItem("注释");
    MenuItem mi2 = new MenuItem("取消注释");
    MenuItem mi3 = new MenuItem("复制");
    MenuItem mi4 = new MenuItem("保存");

//    创建窗口内其他组件
    TextArea ta = new TextArea("我爱中华",6,40);
    Panel p = new Panel();

    public void init(){
//        写一个事件监听器
        ActionListener listener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String actionCommand = e.getActionCommand();
                ta.append(actionCommand+"\n");
            }
        };

        mi1.addActionListener(listener);
        mi2.addActionListener(listener);
        mi3.addActionListener(listener);
        mi4.addActionListener(listener);
//     将菜单项添加到PopupMenu菜单中
        pop.add(mi1);
        pop.add(mi2);
        pop.add(mi3);
        pop.add(mi4);

//        将PopupMenu组件添加到需要右键菜单的容器中
        p.add(pop);
//        设置popupmenu菜单大小
        p.setPreferredSize(new Dimension(400,200));//和setBounds的效果一样

//        给PopupMenu注册鼠标事件，当鼠标右键松开弹出菜单
        p.addMouseListener(new MouseAdapter() {
            @Override
            public void mouseReleased(MouseEvent e) {
                boolean flag = e.isPopupTrigger();
                if(flag){
//                    显示popupmenu
                    pop.show(p,e.getX(),e.getY());
                }
            }
        });

//        放置文本域和Panel
        Box vbox = Box.createVerticalBox();
        vbox.add(ta);
        vbox.add(p);
        frame.add(vbox);

        frame.pack();
        frame.setVisible(true);
    }

    public static void main(String[] args) {
        new BasicPopupMenuDemo().init();
    }
}
```



### 28.8绘图

很多程序如各种游戏都需要在窗口绘制各种图形，除此之外，即使在开发JavaEE项目时，有时候也必须“动态”的向客户端生成各种图形，图表，比如图形验证码，统计图等，这些都需要利用AWT的绘图功能



#### 28.8.1组件绘图原理

之前我们学习了很多组件，例如Button，Frame，Checkbox等，不同的组件，展示出来的图形都不一样，其实这些组件展示出来的图形其本质就是用AWT的绘图完成的

**在AWT中真正提供绘图功能的是Graphics对象**，那么Component组件和Graphics对象存在什么关系呢，才能让Component绘制自身图形呢？

**在Component类中，提供了下列三个方法来完成组件图形的绘制与刷新：**

- paint(Graphics g)：绘制组件的外观
- update(Graphics g)：内部调用paint方法，刷新组件外观
- repaint()：调用update方法，刷新组件外观

![](C:\Users\Asinil\Desktop\学习\Java\28.8.1.PNG)

一般情况下，update和paint方法是由AWT系统负责调用，如果程序要希望系统重新绘制组件，可以调用repaint方法完成



#### 28.8.2 Graphics对象调用

程序中的绘图也一样的流程，需要画布，画笔，颜料等等。AWT中提供了Canvas类充当画布，提供了Graphics类来充当画笔，通过调用Graphics对象的setColor()方法可以给画笔设置颜色

**画图的步骤：**

- 自定义类，继承Canvas类，重写二paint(Graphics g)方法完成画图
- 在paint方法内部，真正开始画图之前调用Graphics对象的seetColor().setFont()等方法设置画笔颜色，字体等属性
- 调用Graphics画笔的drawXxx()方法开始画图



其实画图的核心就是在于使用Graphics画笔在Canvas画布上画什么颜色，什么样的形式的图形，所以核心在画笔上，下表列出了Graphics类中的常用的一些方法

|       方法名       |          说明          |
| :----------------: | :--------------------: |
| setColor(Color c)  |        设置颜色        |
| setFont(Font font) |        设置字体        |
|     drawLine()     |        绘制直线        |
|     drawRect()     |        绘制矩形        |
|  drawRoundRect()   |      绘制圆角矩形      |
|     drawOval()     |       绘制椭圆形       |
|   drawPolygon()    |       绘制多边形       |
|     drawArc()      |        绘制圆弧        |
|   drawPolyline()   |        绘制折线        |
|     fillRect()     |      填充矩形区域      |
|  fillRoundRect()   |    填充圆角矩形区域    |
|     fillOval()     |     填充椭圆形区域     |
|   fillPolygon()    |    填充多边形球区域    |
|     fillArc()      | 填充圆弧对应的扇形区域 |
|    drawImage()     |        绘制位图        |

**案例**

需求：使用AWT绘图API，完成下图效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.8.2.PNG)

```java
public class SimpleDrawDemo {
    private final String OVAL_SHAPE = "oval";
    private final String RECT_SHAPE = "rect";

    private Frame frame = new Frame("测试绘图窗口");

    //  创建组件
    Button paintRect = new Button("绘制矩形");
    Button paintOval = new Button("绘制椭圆");

//    选择绘制的形状
    private String shape = "";

// - 自定义类，继承Canvas类，重写二paint(Graphics g)方法完成画图
    private class MyCanvas extends Canvas {
        @Override
        public void paint(Graphics g) {
            if (shape.equals(RECT_SHAPE)) {
    //            绘制矩形
    //             - 在paint方法内部，真正开始画图之前调用Graphics对象的seetColor().setFont()等方法设置画笔颜色，字体等属性
                g.setColor(Color.BLACK);
                g.drawRect(100, 100, 200, 100);

            } else if (shape.equals(OVAL_SHAPE)) {
    //            绘制椭圆形
                g.setColor(Color.RED);
                g.drawOval(200, 100, 200, 100);
            }
        }
    }
    //    创建画布对象
    MyCanvas mc = new MyCanvas();

    public void init(){
//        按钮创建事件监听器
        ActionListener listener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String actionCommand = e.getActionCommand();
                if (actionCommand.equals("绘制矩形")){
                    shape = RECT_SHAPE;
                    mc.repaint();
                }else if(actionCommand.equals("绘制椭圆")){
                    shape = OVAL_SHAPE;
                    mc.repaint();
                }
            }
        };
        paintRect.addActionListener(listener);
        paintOval.addActionListener(listener);

        Panel p = new Panel();
        p.add(paintRect);
        p.add(paintOval);
//      画布大小需要设置
        mc.setPreferredSize(new Dimension(300,150));
        frame.add(mc);
        frame.add(p,BorderLayout.SOUTH);

        frame.pack();
        frame.setVisible(true);
    }


    public static void main(String[] args) {
        new SimpleDrawDemo().init();
    }
}
```



Java也可用于开发一些动画，就是间隔一定时间（通常是0秒）重新绘制新的图像，两次绘制的图像差异较小，肉眼看起来就形成了所谓的动画

为了实现间隔一定的时间就重新调用组件的repaint方法，可以借助于Swing提供的Timer类，Timer类是一个定时器，它有如下一个构造器:

- Timer(int delay,ActionListener listener)：每间隔delay毫秒，系统自动触发ActionListener监听器里面的时间处理器方法，在方法内部我们就可以调用组件的repaint方法，完成组件重绘



案例2

需求：使用AWT图画技术以及Timer计时器，完成下图弹球小游戏

![](C:\Users\Asinil\Desktop\学习\Java\28.8.3.PNG)

![](C:\Users\Asinil\Desktop\学习\Java\28.8.4.PNG)

```java
public class PinBallDemo {
    private Frame frame = new Frame("弹球小游戏");

    //  球桌属性
    //球桌大小
    private final int tableHeight = 400;
    private final int tableWidth = 300;

    //  小球的属性
    //小球的大小
    private final int ballSize = 16;
    //小球的坐标
    private int startPoint_X = 100;
    private int startPoint_Y = 100;
    //小球速度
    private int startSpeed_X = 30;
    private int startSpeed_Y = 20;

    //  球拍的属性
    //球拍大小
    private final int racketHeight = 20;
    private final int racketWidth = 60;
    //球拍位置
    private int racket_X = 120;
    private final int racket_Y = 350;//Y坐标锁死
    //球拍水平移动速度
    private int racketSpeed = 40;

    //    游戏进行标记，标识游戏状态
    private Boolean gameFlag = true;

    //    声明一个定时器
    private Timer time;
    private int times = 500;

    //  自定义类，充当画布，重写paint方法
    private class MyCanvas extends Canvas {
        @Override
        public void paint(Graphics g) {
            //判断游戏状态
            if (gameFlag) {
                //  游戏进行中
                //绘制小球
                g.setColor(Color.RED);
                g.fillOval(startPoint_X, startPoint_Y, ballSize, ballSize);
                //绘制球拍
                g.setColor(Color.PINK);
                g.fillRect(racket_X, racket_Y, racketWidth, racketHeight);
            } else {
                //  游戏结束
                g.setColor(Color.BLACK);
                g.setFont(new Font("Over", Font.BOLD, 30));
                g.drawString("游戏结束", 50, 200);
            }
        }
    }

    //创建画布
    MyCanvas mc = new MyCanvas();

    public void init() {
        //球拍事件监听
        KeyListener listener = new KeyAdapter() {
            @Override
            public void keyPressed(KeyEvent e) {
                //获取当前按下的键
                int keyCode = e.getKeyCode();
                if (keyCode == KeyEvent.VK_LEFT) {
                    //向左移动
                    if (racket_X > 0) {
                        racket_X -= racketSpeed;
                    }
                }
                if (keyCode == KeyEvent.VK_RIGHT) {
                    //向右移动
                    if (racket_X < tableWidth - racketWidth) {
                        racket_X += racketSpeed;
                    }
                }
            }
        };
        //同时给frame和mc注册监听器
        frame.addKeyListener(listener);
        mc.addKeyListener(listener);

        //设置定时器，500毫秒/次
        time = new Timer(times, new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                //小球运动
                //小球和墙壁之间的碰撞
                if (startPoint_X <= 0 || startPoint_X + ballSize > tableWidth) {
                    startSpeed_X = -startSpeed_X;
                }
                if (startPoint_Y <= 0) {
                    startSpeed_Y = -startSpeed_Y;
                }
                //小球和球拍之间的碰撞
                if (startPoint_Y + ballSize > racket_Y) {
                    if(startPoint_X > racket_X && startPoint_X < racket_X + racketWidth){
                        startSpeed_Y = -startSpeed_Y;
                    }else{
                        //游戏结束
                        gameFlag = false;
                        //停止定时器
                        time.stop();
                        mc.repaint();
                    }
                }
                startPoint_X += startSpeed_X;
                startPoint_Y += startSpeed_Y;
                //重绘小球和球拍
                mc.repaint();
            }
        });
        time.start();

        //设置桌面大小
        mc.setPreferredSize(new Dimension(tableWidth,tableHeight));
        frame.add(mc);

        frame.pack();
        frame.setVisible(true);
    }

    public static void main(String[] args) {
        new PinBallDemo().init();
    }
}
```



#### 28.8.3位图处理

如果仅仅绘制一些简单的几何程序，程序的图形效果依然比较单调。A**WT也允许在组件上绘制位图，Graphics提供了drawImage（Image image）方法用于绘制位图，该方法需要一个Image参数--代表位图，通过该方法就可以绘制指定的位图**



**位图使用步骤：**

1. 创建Image的子类对象BufferedImage（int width,int height ,int ImageType）,创建时需要指定位图的宽高以及类型属性，此时相当于在内存中生成了一张图片
2. 调用BufferedImage对象的getGraphics()方法获取画笔，此时就可以往内存中的这张照片上绘图了，绘图的方法和之前的一样
3. 调用组件paint方法中提供的Graphics对象的drawImge方法，一次性的内存中的图片BufferedImag绘制到特定的组件上

**使用位图绘制组件的好处：**

- 使用位图绘制组件，相当于实现了图的缓冲区，此时绘图时没有直接把图形绘制到组件上，而是先绘制到内存中的BufferedImage上，等全部绘制完毕，在一次性的图像显示到组件上，这样用户的体验会好一些



**案例：演示位图**

需求：通过BufferedImage实现了一个简单的手绘程序：通过鼠标可以在窗口画画

![](C:\Users\Asinil\Desktop\学习\Java\28.8.5.PNG)

```java
public class BufferedImageDemo {
    private Frame frame = new Frame("BufferedImage位图演示窗口");
//    画图区参数
    private final int Canvas_Width = 500;
    private final int Canvas_Height = 500;

//    创建右键菜单组件
    private PopupMenu popupMenu = new PopupMenu();
    private MenuItem red = new MenuItem("红色");
    private MenuItem green = new MenuItem("绿色");
    private MenuItem blue = new MenuItem("蓝色");

//    记录当前画笔颜色
    private Color panColor = Color.RED;

//    创建一个BufferedImage位图对象,BufferedImage(宽，高，位图类别)
    private BufferedImage image = new BufferedImage(Canvas_Width,Canvas_Height,BufferedImage.TYPE_INT_RGB);//这里的类别为三原色

    //    通过位图来获取关联的Graphics对象
    Graphics g = image.getGraphics();

//    创建画布类
    private class MyCanvas extends Canvas{
        @Override
        public void paint(Graphics g) {
            g.drawImage(image,0,0,null);//drawImage(所画位图，位置x，位置y，观察者)
        }
    }
//  创建画布
    MyCanvas myCanvas = new MyCanvas();

//    定义变量记录鼠标上一次所处的坐标
    private int preX = -1;
    private int preY = -1;


    public void init(){
//        创建事件监听器
        //菜单事件监听器
        ActionListener listener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String actionCommand = e.getActionCommand();
                switch (actionCommand){
                    case "红色":
                        panColor = Color.RED;
                        break;
                    case "绿色":
                        panColor = Color.GREEN;
                        break;
                    case "蓝色":
                        panColor = Color.BLUE;
                        break;
                }
            }
        };
        //注册监听器
        red.addActionListener(listener);
        green.addActionListener(listener);
        blue.addActionListener(listener);

        popupMenu.add(red);
        popupMenu.add(green);
        popupMenu.add(blue);

        //右键弹出菜单的鼠标监听器
        myCanvas.add(popupMenu);
        MouseAdapter mouseAdapter = new MouseAdapter() {
            @Override
            public void mouseReleased(MouseEvent e) {
                boolean popupTrigger = e.isPopupTrigger();
                if (popupTrigger){
                    popupMenu.show(myCanvas,e.getX(),e.getY());
                }

                //这里监听鼠标弹起动作，表示一组画图完成，修正鼠标坐标
                preX = -1;
                preY = -1;
            }
        };
        //注册监听器
        myCanvas.addMouseListener(mouseAdapter);

        //设置位图背景为白色
        g.setColor(Color.white);
        g.fillRect(0,0,Canvas_Width,Canvas_Height);
        //监听鼠标的移动，完成线条的控制
        MouseMotionAdapter mouseMotionAdapter = new MouseMotionAdapter() {
            //当鼠标左键按下，并拖动时会被调用
            @Override
            public void mouseDragged(MouseEvent e) {
                //画线条   需要两组坐标(x1,y1) (x2,y2)
                if(preX>0&&preY>0) {
                    g.setColor(panColor);
                    g.drawLine(preX, preY, e.getX(), e.getY());
                }
                //修正坐标
                preX = e.getX();
                preY = e.getY();

                //重绘组件
                myCanvas.repaint();
            }
        };
        myCanvas.addMouseMotionListener(mouseMotionAdapter);

        myCanvas.setPreferredSize(new Dimension(Canvas_Width,Canvas_Height));
        frame.add(myCanvas);

        frame.pack();
        frame.setVisible(true);
    }

    public static void main(String[] args) {
        new BufferedImageDemo().init();
    }
}
```



#### 28.8.4ImageIO的使用

在实际生活中，很多软件都支持打开本地磁盘已经存在的图片，然后进行编辑，编辑完毕后，再重新保存到本地磁盘。如果使用AWT要完成这样的功能，那么需要使用到ImageIO这个类，可以操作本地磁盘的图片文件

| 方法名                                                       | 说明                   |
| ------------------------------------------------------------ | ---------------------- |
| static BufferedImage readFile(File input)                    | 读取本地磁盘图片文件   |
| static BufferedImage read(InputStream input)                 | 读取本地磁盘图片文件   |
| static Boolean write(RenderedImage im,String formatName,File output) | 往本地磁盘输出图片文件 |



案例：编辑图片查看程序，支持另存操作

![](C:\Users\Asinil\Desktop\学习\Java\28.8.6.PNG)

```java
public class ImageIODemo {
    private Frame frame = new Frame("测试ImageIO窗口");


    //    菜单组件
    private MenuBar menuBar = new MenuBar();
    private Menu fileMenu = new Menu("文件");
    private MenuItem openFile = new MenuItem("打开");
    private MenuItem saveOther = new MenuItem("另存为");

    //    创建位图对象,记录本地读取到内存中的图片
    BufferedImage image;

    //      创建画布类
    private class MyCanvas extends Canvas {
        @Override
        public void paint(Graphics g) {
            g.drawImage(image, 0, 0, null);
        }
    }

    //      创建画布
    MyCanvas myCanvas = new MyCanvas();

    //组装窗口
    public void init() {
//        实现菜单功能
        openFile.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
//                打开一个文件对话框
                FileDialog fileDialog = new FileDialog(frame, "打开文件", FileDialog.LOAD);
                fileDialog.setVisible(true);
//                用户选择的文件名以及路径
                String name = fileDialog.getFile();
                String directory = fileDialog.getDirectory();

//                将选择的图片读取到内存中
                try {
                    image = ImageIO.read(new File(directory, name));
                    myCanvas.repaint();
                } catch (IOException ex) {
                    ex.printStackTrace();
                }
            }
        });
        saveOther.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                FileDialog fileDialog = new FileDialog(frame, "保存图片", FileDialog.SAVE);
                fileDialog.setVisible(true);
//                获取图片的文件名和路径
                String name = fileDialog.getFile();
                String directory = fileDialog.getDirectory();
                try {
                    ImageIO.write(image, "JPEG", new File(directory, name));
                } catch (IOException ex) {
                    ex.printStackTrace();
                }

            }
        });
        fileMenu.add(openFile);
        fileMenu.add(saveOther);
        menuBar.add(fileMenu);
        frame.setMenuBar(menuBar);

        frame.add(myCanvas);

//        设置窗口功能
        frame.setBounds(200, 200, 800, 600);
//        窗口关闭动作
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
        frame.setVisible(true);
    }

    public static void main(String[] args) {
        new ImageIODemo().init();
    }
}
```



#### 28.8.5 五子棋案例

五子棋小游戏，完成下图效果：

![](C:\Users\Asinil\Desktop\学习\Java\28.8.7.PNG)

```java
public class GoBangGame {
    //private Frame frame = new Frame("五子棋游戏"); 最老版本的Frame没有缓冲区会导致每一次刷新都会一闪一闪的
    private JFrame frame = new JFrame("五子棋游戏");
    //按钮组件
    private Button White = new Button("白棋");
    private Button Black = new Button("黑棋");
    private Button Return = new Button("悔棋");

    //创建位图对象（棋盘，棋子，光标）
    private BufferedImage imageBoard;
    private BufferedImage imageWhite;
    private BufferedImage imageBlack;
    private BufferedImage imageMark;

    //声明棋盘的宽和高
    private final int BOARD_WIDTH = 535;
    private final int BOARD_HEIGHT = 536;
    //声明棋盘横向和纵向分别能下多少个棋子，都是15个
    private final int BOARD_SIZE = 15;

    //声明每个棋子占用的空间大小
    private final int RATE = BOARD_WIDTH / BOARD_SIZE;
    //声明棋子对于x方向和y方向的偏移量
    private final int X_OFFSET = 5;
    private final int Y_OFFSET = 6;
    //声明一个二维数组记录棋子位置，如果索引[i][j]处的值为：0-没有棋子，1-白棋，2-黑棋
    private int[][] board = new int[BOARD_SIZE][BOARD_SIZE];

    //声明红框的位置信息，就是二维数组的索引
    private int MARK_X = -1;
    private int MARK_Y = -1;

    //当前棋子颜色标记
    private int chessType = 0;//初始为没有棋子

    //创建画布类
    // private class MyCanvas extends Canvas { 老版本画布，没有缓冲区，每一次重绘都是直接绘图上去的
    private class MyCanvas extends JPanel {
        @Override
        public void paint(Graphics g) {
            //绘图
            //绘制棋盘
            g.drawImage(imageBoard, 0, 0, null);

            //绘制选择框，因为棋盘有边框，所以需要加上偏移量
            if (MARK_X > 0 && MARK_Y > 0) {//说明鼠标移动到棋盘上
                g.drawImage(imageMark, MARK_X * RATE + X_OFFSET, MARK_Y * RATE + Y_OFFSET, null);
            }

            //绘制棋子
            for (int i = 0; i < BOARD_SIZE; i++) {
                for (int j = 0; j < BOARD_SIZE; j++) {
                    //绘制棋子
                    if (board[i][j] == 1) {
                        g.drawImage(imageWhite, i * RATE + X_OFFSET, j * RATE + Y_OFFSET, null);
                    }
                    if (board[i][j] == 2) {
                        g.drawImage(imageBlack, i * RATE + X_OFFSET, j * RATE + Y_OFFSET, null);
                    }
                }
            }
        }
    }

    //创建画布
    MyCanvas myCanvas = new MyCanvas();

    //刷新按钮颜色方法
    public void reflushBtn(Color whiteBtnColor, Color blackBtnColor, Color returnBtnColor) {
        White.setBackground(whiteBtnColor);
        Black.setBackground(blackBtnColor);
        Return.setBackground(returnBtnColor);
    }

    //组装窗口棋盘，编写逻辑
    public void init() throws IOException {
        //设置按钮的事件响应
        White.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                //修改当前使用的棋子类型
                chessType = 1;
                //修改按钮颜色
                reflushBtn(Color.GREEN, Color.LIGHT_GRAY, Color.LIGHT_GRAY);
            }
        });
        Black.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                chessType = 2;
                reflushBtn(Color.LIGHT_GRAY, Color.GREEN, Color.LIGHT_GRAY);
            }
        });
        Return.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                chessType = 0;//代表没有棋子
                reflushBtn(Color.LIGHT_GRAY, Color.LIGHT_GRAY, Color.GREEN);
            }
        });
        //将按钮添加到窗口中
        Panel p = new Panel();
        p.add(White);
        p.add(Black);
        p.add(Return);
        frame.add(p, BorderLayout.SOUTH);

        //将位图传进内存中
        imageBoard = ImageIO.read(new File("28AWT/image/board.jpg"));
        imageWhite = ImageIO.read(new File("28AWT/image/white.gif"));
        imageBlack = ImageIO.read(new File("28AWT/image/black.gif"));
        imageMark = ImageIO.read(new File("28AWT/image/selected.gif"));

        //监听鼠标位置事件，和鼠标点击事件
        MouseMotionAdapter mouseMotionAdapter = new MouseMotionAdapter() {
            //当鼠标移动时会调用这个方法
            @Override
            public void mouseMoved(MouseEvent e) {
                MARK_X = (e.getX() - X_OFFSET) / RATE;
                MARK_Y = (e.getY() - Y_OFFSET) / RATE;
                myCanvas.repaint();
            }
        };
        MouseAdapter mouseAdapter = new MouseAdapter() {
            @Override
            public void mouseClicked(MouseEvent e) {
                int clickX = (e.getX() - X_OFFSET) / RATE;
                int clickY = (e.getY() - Y_OFFSET) / RATE;
                board[clickX][clickY] = chessType;
                myCanvas.repaint();
            }

            @Override
            public void mouseExited(MouseEvent e) {
                MARK_X = -1;
                MARK_Y = -1;
                myCanvas.repaint();
            }
        };
        myCanvas.addMouseMotionListener(mouseMotionAdapter);
        myCanvas.addMouseListener(mouseAdapter);

        //将画布添加到窗口中，并覆盖位图
        myCanvas.setPreferredSize(new Dimension(BOARD_WIDTH, BOARD_HEIGHT));
        frame.add(myCanvas);

        //设置frame最佳大小，设置可见
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
        frame.pack();
        frame.setVisible(true);
    }

    public static void main(String[] args) throws IOException {
        new GoBangGame().init();
    }
}
```



## 29Swing编程

### 29.1 Swing概述

**Swing是由100%纯Java实现的**，不再依赖于本地平台的GUI，因此，可以在所有平台上都保持相同的界面外观。独立于本地平台的Swing组件被称为**轻量级组件**，而依赖于本地平台的AWT组件被称为**重量级组件**。

**使用Swing的优势：**

- Swing组件不再依赖本地平台的GUI，无需采用各种平台的GUI交集，因此Swing提供了大量的图形界面组件，远远超出了AWT所提供的图形界面组件集
- Swing组件不在依赖于平台GUI，因此不会产生平台相关的bug
- Swing组件在各个平台都可以运行时可保证具有相同的图形界面外观



**Swing的特征：**

1. Swing组件采用了**MVC（model-view-controller），即模型-视图-控制器设计模式：**

   - 模型（model）：用于维护组件的各种状态

   - 视图（view）：是组件的可视化表现

   - 控制器（controller）：用于控制对于各种事件，组件做出响应

     **当模型发生改变时，它会通知所有依赖它的视图，试图会根据模型的数据来更新自己。Swing使用UI代理来包装视图和控制器，还有一个模型对象来维护该组件的状态。**例如：按钮JButton有一个维护其状态信息的模型ButtonMode对象。Swing组件的模型是自动设置的，因此一般都使用JButton，为无需关系ButtonMode对象

2. Swing在不同平台上的表现一致，并且有能力提供本地平台不支持的显示外观。由于Swing采用MVC模式来维护各组件，所以当外观改变时，对组件的状态信息（由模型维护）没有任何影响。因此，**Swing可以采用插拔式外观感觉来控制组件外观，使得Swing图形界面在同一个平台上运行时能拥有不同的外观，用户可以选择自己喜欢的外观。**



### 29.2 Swing基本组件的用法

![](C:\Users\Asinil\Desktop\学习\Java\29.2.1.png)

大部分Swing组件都是JComponent抽象类的直接或者间接子类（并不是全部的Swing组件），JComponent类定义了所有子类组件的通用方法，jComponent类是AWT里java.awt.Container类的子类，这也是AWT和Swing的联系之一。绝大部分Swing组件类继承了Container，所以Swing组件都可以作为容器使用（JFrame继承了Frame类）

**Swing组件和AWT组件的对应关系**

大部分情况下，只需要再AWT组件名称前面加上一个J就可以得到Swing对应的组件名称，但有几个例外：

1. JComboBox：对应AWT组件里的Choice组件，但比Choice组件功能更加丰富
2. JFileChooser：对应组件里的FileDialog组件
3. JScrollBar：对应于AWT里的Scrollbar组件，大小写差异
4. JCheckBox：对应AWT里的Checkbox组件，大小写差异
5. JCheckBoxMenuItem：对应AWT里的CheckboxMeunItem组件，大小写差异



**Swing组件按照功能来分类：**

1. 顶层容器：JFrame，JApplet，JDialog和JWindow
2. 中间容器：JPanel，JScollPane，JSplitPane，JToolBar等
3. 特殊容器：在用户界面上具有特殊作用的容器，如：JIntemalFrame，JRootPane，JLayeredPane和JDestopPane等
4. 基本组件：实现人机交互的组件，如JButton，JComboBox，JList，JMenu，JSlider等
5. 不可编辑信息的显示组件：向用户显示不能被编辑的格式化信息组件，如JLabel，JProgressBar和JToolTip等
6. 可编辑信息的显示组件：向用户显示能被编辑的格式化信息组件，如JTable，JTextArea和JField等
7. 特殊对话框组件：可以直接生产特殊对话框的组件，如JColorChooser和JFileChooser等



### 29.3 AWT组件的Swing实现

Swing为除了Canvas之外的所有AWT组件提供了相应的实现，Swing组件相比AWT组件功能更加强大，相对于AWT组件，**Swing组件具有如下4个额外功能：**

1. **可以为Swing组件设置提示信息**，使用setToolTipText()方法，为组件设置用户有帮助的提示信息
2. **很多Swing组件如按钮，标签，菜单项等，除了使用文字之外，还可以使用图标修饰自己**。为了允许在Swing组件中使用图标，Swing为Icon接口提供了一个实现类：ImageIcon，该实现类代表一个图像图标
3. **支持插拔式的外观风格**。每一个JComponent对象都有一个相应的ComponentUI对象，为他完成所有的绘画，事件处理，决定尺寸等大小工作。ComponentUI依赖当前使用的PLAF，使用UIManager.setLookAndFeel()方法可以改变图形界面的外观风格
4. **支持设置边框。**Swing组件可以设置一个或者多个边框。Swing组件中提供了各式各样的边框供用户使用，也能建立组合边框或者自己设计的边框。一种空白白边框可以用来增大组件，同时协同布局管理器对容器中的组件进行合理的布局



每个Swing组件都有一个对应的UI类。每一个Swing组件的UI代理的类名总是将组件名J去掉加上UI后缀。UI代理通常是一个抽象基类，不同的PLAF会有不同的UI代理实现类。Swing类库中包含了几套UI代理，分别放在不同的包下，每一套UI代理几乎包含了所有Swing组件的ComponentUI实现，每套这样的实现都被称为一种PLAF实现

以JButton为例，其UI代理的继承层次下图：

![](C:\Users\Asinil\Desktop\学习\Java\29.2.2.png)

如果需要改变程序的外观风格，则可以使用如下代码：

```java
//容器
JFrame jf = new JFrame();
try{
    //设置外观风格
    UIManager.setLookAndFeel("com.sun.java.swing.plaf.windows.windowsLookAndFeel");
    //刷新jf容器及其内部组件的外观
    SwingUtilties.updateComponentTreeUI(jf);
}catch(Exception e){
    e.printStackTrace();
}
```



案例：使用Swing组件替代AWT组件完成下图效果

![](C:\Users\Asinil\Desktop\学习\Java\29.2.3.png)

![](C:\Users\Asinil\Desktop\学习\Java\29.2.4.png)

```java
public class SwingComponentDemo {
    private JFrame jf = new JFrame("测试Swing组件窗口");

//    菜单组件
    JMenuBar jb = new JMenuBar();
    JMenu file = new JMenu("文件");
    JMenu edit = new JMenu("编辑");
    //编辑菜单的菜单项
    JMenuItem wrap = new JMenuItem("自动换行");
    JMenuItem copy = new JMenuItem("复制",new ImageIcon("29Swing/image/Component/copy.png"));//给图标添加图片
    JMenuItem paste = new JMenuItem("粘贴",new ImageIcon("29Swing/image/Component/paste.png"));//给图标添加图片
    JMenu farmate = new JMenu("格式");
    //格式菜单的菜单项
    JMenuItem isAnnotation = new JMenuItem("注释");
    JMenuItem notAnnotation = new JMenuItem("取消注释");

//    列表组件
    String[] color = {"红色","绿色","蓝色"};
    JList<String> colorLsits = new JList<String>(color);

//    声明文本域
    JTextArea jta = new JTextArea(6,20);

//    选择相关组件
    //下拉选择框
    JComboBox<String> colorChoice = new JComboBox<String>();
    //单选框选择组件
    ButtonGroup sex = new ButtonGroup();
    JRadioButton male = new JRadioButton("男",true);
    JRadioButton female = new JRadioButton("女",false);
    //复选框选择组件
    JCheckBox isMarried = new JCheckBox("是否已婚？",true);

//    输入框和按钮组件
    JButton ok = new JButton("确定");
    JTextField jtf = new JTextField(40);

//    声明右键菜单组件
    JPopupMenu jpm = new JPopupMenu();

    ButtonGroup popBG = new ButtonGroup();
    JRadioButtonMenuItem metal = new JRadioButtonMenuItem("Metal风格");
    JRadioButtonMenuItem nimbus = new JRadioButtonMenuItem("Nimbus风格");
    JRadioButtonMenuItem windows = new JRadioButtonMenuItem("Windows风格",true);
    JRadioButtonMenuItem windowsBaisc = new JRadioButtonMenuItem("Windows经典风格");
    JRadioButtonMenuItem motif = new JRadioButtonMenuItem("Motif风格");

    public void init(){
//        组装界面
//        组转菜单
        farmate.add(isAnnotation);
        farmate.add(notAnnotation);
        edit.add(wrap);
        edit.addSeparator();//添加横杠
        edit.add(copy);
        edit.add(paste);
        edit.add(farmate);
        jb.add(file);
        jb.add(edit);
        jf.setJMenuBar(jb);

//        组装右键菜单
        ActionListener actionListenerPop = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String actionCommand = e.getActionCommand();
                try {
                    changeFlavor(actionCommand);
                } catch (Exception ex) {
                    ex.printStackTrace();
                }
            }
        };
        metal.addActionListener(actionListenerPop);
        nimbus.addActionListener(actionListenerPop);
        windows.addActionListener(actionListenerPop);
        windowsBaisc.addActionListener(actionListenerPop);
        motif.addActionListener(actionListenerPop);

        popBG.add(metal);
        popBG.add(nimbus);
        popBG.add(windows);
        popBG.add(windowsBaisc);
        popBG.add(motif);
        jpm.add(metal);
        jpm.add(nimbus);
        jpm.add(windows);
        jpm.add(windowsBaisc);
        jpm.add(motif);

        jta.setComponentPopupMenu(jpm);//不需要再设置事件监听

//        组装底部
        JPanel jp = new JPanel();
        jp.add(jtf);
        jp.add(ok);
        jf.add(jp, BorderLayout.SOUTH);
//        组装选择区域
        JPanel jp2 = new JPanel();
        colorChoice.addItem("红色");
        colorChoice.addItem("绿色");
        colorChoice.addItem("蓝色");
        jp2.add(colorChoice);

        sex.add(male);
        sex.add(female);
        jp2.add(male);
        jp2.add(female);
        jp2.add(isMarried);

//        组装文本域以及颜色列表
        Box b1 = Box.createVerticalBox();
        b1.add(jta);
        b1.add(jp2);
        Box b2 = Box.createHorizontalBox();
        b2.add(b1);
        b2.add(colorLsits);
        jf.add(b2);

        jf.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);//点击x关闭窗口
        jf.pack();
        jf.setVisible(true);
    }

//    定义一个方法，用于改变界面风格
    private void changeFlavor(String command) throws Exception{
        switch (command){
            case "Metal风格":
                UIManager.setLookAndFeel("javax.swing.plaf.metal.MetalLookAndFeel");
                break;
            case "Nimbus风格":
                UIManager.setLookAndFeel("javax.swing.plaf.nimbus.NimbusLookAndFeel");
                break;
            case "Windows风格":
                UIManager.setLookAndFeel("com.sun.java.swing.plaf.windows.WindowsLookAndFeel");
                break;
            case "Windows经典风格":
                UIManager.setLookAndFeel("com.sun.java.swing.plaf.windows.WindowsClassicLookAndFeel");
                break;
            case "Motif风格":
                UIManager.setLookAndFeel("com.sun.java.swing.plaf.motif.MotifLookAndFeel");
                break;
        }

        SwingUtilities.updateComponentTreeUI(jf.getContentPane());
        SwingUtilities.updateComponentTreeUI(jb);
        SwingUtilities.updateComponentTreeUI(jpm);
    }

    public static void main(String[] args) {
        new SwingComponentDemo().init();
    }
}
```



### 29.4 为组件设置边框

为了让界面的层次感更强，Swing中提供了Border对象来代表一个边框，下图是Border的继承体系图：

![](C:\Users\Asinil\Desktop\学习\Java\29.4.1.png)

**特殊的Border：**

- **TitleBorder**：它的作用并不是直接为其他组件添加边框，而是为其他边框设置标题，创建该类的对象，需要传入一个其他的Border对象
- **CompoundBorder**：用来组合其他两个边框，创建该类的对象时，需要传入其他两个Border对象，一个作为内边框，一个作为外边框

**给组件设置边框步骤：**

1. 使用BorderFactory或者XxxBorder创建Border的实例对象
2. 调用Swing组件的setBorder(Border b)方法作为组件设置边框



**案例：使用Border实现下图效果**

![]()

```java

```

