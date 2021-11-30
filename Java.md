

# 第一章

public class Test {

 public static void main(String[ ] args   )    {     / /表示定义一个公开的静态方法，args可修改； 

​    System.out.println( );

​    }

}

  

public表示公开的;

class表示类;

static表示静态的;

void表示空;

main表示方法名是main;

(String[ ] args)是一个main方法形式参数列表;



public calss 和 class 的区别：

+ 一个java源文件中可以定义多个class
+ 一个java源文件中**不一定**有public 的 class
+ 一个class会定义生成xxx.class字节码文件
+ 一个java源文件当中定义公开的类的话，public的class只能有1个，并且该类名称必须和java源文件名称一致
+ 每一个class中都可以编写main方法，都可以设定程序的入口，想执行B.class中的main方法：-java B
+ 当在命令窗口中执行java Hello，那么要求Hello.class当中必须有主方法。没有主方法会出现运行阶段的错误

总结第一章：

1. 能够自己搭建java的开发环境
2. 能够独立编写Helloworld程序，编译并运行
3. 掌握变量path的原理及如何配置
4. 掌握环境变量classpath的原理以及如何配置
5. Java中的注释
6. public class 和 class 的区别

| 修饰符    | 同一个类中 | 同一个包中子类无关类 | 不同包的子类 | 不同包的无关类 |
| --------- | ---------- | -------------------- | ------------ | -------------- |
| private   | √          |                      |              |                |
| 默认      | √          | √                    |              |                |
| protected | √          | √                    | √            |                |
| public    | √          | √                    | √            | √              |



------

# 第二章

标识符

1. 在java源程序中程序员有权利自己命名的单词都是标识符
2. 标识符在编译器中以特殊颜色显示
3. 标识符可以标识*类名 *方法名 *变量名 *接口名 *常量名.......
4. 标识符的命名规则：*一个合法的标识符只能由数字、字母、下划线、美元符号组成，不能有其它符号！***不能以数字开头！**严格区分大小写！关键字不能做标识符！
5. **规范！最好见名知意！遵守驼峰命名方式！**
6. **类名，接口名首字母大写，后面每个单词首字母大写**
7. **变量名、方法名：首字母小写，后面每个单词首字母大写**
8. **常量名：全部大写！**

基本数据类型

1. 整数型：byte ,short,int,long
2. 浮点型 :  float ,double 
3. 布尔型 : boolean
4. 字符型 : char

| 基本数据类型 | 占用空间大小 |
| ------------ | ------------ |
| byte         | 1            |
| short        | 2            |
| int          | 4            |
| long         | 8            |
| float        | 4            |
| double       | 8            |
| boolean      | 1            |
| char         | 2            |

char c = ' a ';

char c = "a"; 编译错误，字符不用“ ”括起来；

char c = 'ab'; 编译错误，ab是字符串，不能用' '括起来；

System.out println() 与System.out.print()的区别在于System.out.println有换行功能！

\n 是回车换行；\t 是制表符，打印出空格；

   \ ' 表示一个普通无含义的普通的单引号字符

\ \  前面的斜杠把后面的反斜杠转义为一个普通的反斜杠字符

在java中2个反斜杠字符表示一个普通的 \ 字符

char k = ' \ ' 编译错误 ； char k = ' \ \ '  编译出 \ ;

char a = ' \ ' '   输出 '  ; 反斜杠+单引号等于单引号；

& 逻辑并且

| 逻辑或

！非

^ 异或，两边式子不一样则为true

&& 短路与

|| 短路或

当“+”运算符两边的数据只要有一个是字符串，那么就进行字符串连接运算。

# 从键盘输入！！！

public class Test

{

public static void main(String[] args)

{

java.util.scanner s = new java.util.Scanner(System.in);   //创建键盘扫描器对象

String userInputContent = s.next();    //调用Scanner对象的next()方法开始接受用户键盘输入字符串

int sum = s.nextInt();    //以整数型int形式接收

System.out.println("您输入了：" + userInputContent);

}

}

--------------------

1. 导包 import java.util.Scanner;             // 导包的动作必须在定义的类上面；
2. 创建对象 Scanner sc = new Scanner(System.in);    //sc是为变量名称，可以发生变化，其它都不允许发生变化；
3. 接受数据 int i = sc.nextInt();        //接受一个数据，i 为变量名称；

-----------

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Test {
    public static void main(String[] args) {
        Scanner sc =  new Scanner(System.in);
        System.out.println("请输入a~e中的一个字符：");
        char n = sc.next().charAt(0);
        switch(n){
            case 'a' :
                System.out.println("A"); break;
            case 'b' :
                System.out.println("B");break;
            case 'c':
                System.out.println("C");break;
            case'd':
                System.out.println("D");break;
            case'e':
                System.out.println("E");break;
                   default:
                System.out.println("error");
        }
    }
}
```

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Test {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入成绩：");
        int n = sc.nextInt();
        if (n >= 0 && n <= 100) {
            switch (n / 60) {
                case 0:
                    System.out.println("不及格");
                    break;
                case 1:
                    System.out.println("及格");
                    break;
                default:
                    System.out.println("error");
            }
        }
        else {
            System.out.println("请输入0~100的分数：");
        }
    }
}
```

------

for循环细节：

1. 循环初始值可以有多条初始化语句，但要求类型一样，中间用逗号隔开

2. 变量迭代也可以有多条语句，用“ ，”隔开


完全数：

package com.zhoumi.test;
public class Te {
    public static void main(String[] args) {
        //完全数：一个数的因数，出去它本身外相加等于它本身；
        //遍历数字
        for (int i = 0; i < 10000; i++) {
            int sum =0;
            for (int j = 1;j<i;j++){
                    if (i % j == 0) {
                        sum += j;
                    }
                }
                if (sum == i) {
                    System.out.println( i + "是完全数");
                }
            }
        }
     }

----

# 字符串比较（用equals比较）

equals:

String name =" 123 ";

System.out.println(" 123 ".equals(name));     //ture

====字符串.equals(字符串)====

--------------

# 数组



二维数组的动态初始化：

1. 语法：类型 [ ] [ ] = new 类型 [行数 ] [列数 ] ;
2. 

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Test {
    public static void main(String[] args) {
        int temp;
int [] array = new int [10];
Scanner sc = new Scanner(System.in);
for(int i=0;i<array.length;i++) {
    array[i] = sc.nextInt();
}
System.out.println("输出前的数组：");
for (int i =0;i<array.length;i++) {
    System.out.print(array[i]+" ");
}

for(int i = 0;i < 9;i++) {
    for (int j = 0; j < 9; j++) {
        if (array[j] < array[j + 1]) {
            temp = array[j];
            array[j] = array[j + 1];
            array[j + 1] = temp;
        }
    }
}
System.out.println("输出后的数组：");
for (int i=0;i<array.length;i++){
    System.out.print(array[i]+"  ");
}
    }
}
-----------------------------------------------------------------------------------------------------
   //数组的扩容：
package com.zhoumi.test;
import java.sql.Array;
import java.util.Scanner;
import java.util.Arrays;
public class Test {
    public static void main(String[] args) {
        int[] array = {1, 2, 3};
        do{ Scanner sc = new Scanner(System.in);
        System.out.println("===扩容前的数组===");
        for (int i=0;i<array.length;i++){
        System.out.print(array[i]+" ");
        }
        System.out.print('\n');
        int[] newArray = new int[array.length + 1];
        for (int i = 0; i < array.length; i++) {
            newArray[i] = array[i];
        }
        System.out.println("请输入想扩充的数字：");
        newArray[newArray.length - 1] = sc.nextInt();
        array=newArray;
        System.out.println("===扩容后的数组===");
        for (int j = 0; j < array.length; j++) {
            System.out.print(array[j]+" ");
        }
        System.out.println("是否继续添加 y/n");
        char key = sc.next().charAt(0);
        if(key=='n'){
            break;
        }}
while (true);
    }
}

```

### 杨辉三角

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Y {
    public static void main(String[] args){
        /*
        1
        1 1
        1 2 1
        1 3 3 1
        1 4 6 4 1
        1 5 10 10 5 1
         */
        /*
        1. 创建一个二维数组
        2. 第n行有n个元素
        3. 每行的第一个跟最后一个都是1
        4. 第n行m列的数等于第n-1行的第m和第m-1的数的和
        5. 遍历二维数组，创建一维数组的空间
        6. 遍历一维数组，特殊位置赋值，其他位置另外赋值
        7. 遍历二维数组，输出杨辉三角
        */
        int [][] array = new int[10][];
        for(int i=0;i<10;i++){
            array[i]=new int[i+1];
            for(int j=0;j<array[i].length;j++){
                if(j==array[i].length-1||j==0){
                    array[i][j]=1;
                }
                else{
                array[i][j]=array[i-1][j-1]+array[i-1][j];
                    }
            }
        }
        for (int i=0;i<array.length;i++){
            for(int j=0;j<array[i].length;j++){
                System.out.print(array[i][j]+" ");
            }
            System.out.println(); 
        }
    }
}
```

-------

# 函数

1.斐波那契数列：

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Test {
    public static void main(String[] args) {
        for(int n=0;n<=100;n++) {
            System.out.println(f(n));
        }
    }
        public static int f(int n){
            if(n==0 || n==1)
            {
                return 1;
            }
            else {
               return f(n-1)+f(n-2);
            }
    }
}
```

2.猴子吃桃

```java
package com.zhoumi.test;
import java.util.Scanner;
public class C {
    public static void main(String[] args) {
        for (int i = 10; i > 0; i--) {
            System.out.println("猴子第"+i+"天"+"有"+hou(i)+"个桃子");
        }
    }
    public static int hou(int day) {
        if (day == 10) {
            return 1;
        } else {
            return (hou(day+1)+1)*2;
        }
    }
}

```

3.走迷宫

```java
package com.zhoumi.test;
import java.net.SocketOption;
import java.util.Scanner;
import java.util.Arrays;
public class C {
    public static void main(String[] args) {
        System.out.println("迷宫的情况如下：");
        //障碍物为1，空格为0，走过为2，死角为3；
        int[][] arr = new int[8][7];
        for (int i = 0; i < 7; i++) {
            arr[0][i] = 1;
            arr[7][i] = 1;
        }
        for (int i = 0; i < 8; i++) {
            arr[i][0] = 1;
            arr[i][6] = 1;
        }
        arr[3][1] = 1;
        arr[3][2] = 1;
        //遍历数组，打印数组
        for (int i = 0; i < 8; i++) {
            for (int j = 0; j < 7; j++) {
                System.out.print(arr[i][j] + "  ");
            }
            System.out.println();
        }
        findWay(arr, 1, 1);
        System.out.println("===找路的情况如下===");
        for (int i = 0; i < 8; i++) {
            for (int j = 0; j < 7; j++) {
                System.out.print(arr[i][j] + "  ");
            }
            System.out.println();
        }
    }

    public static boolean findWay(int[][] map, int i, int j) {
        if (map[6][5] == 2) {
            return true;
        } else {
            if (map[i][j] == 0) {
                map[i][j] = 2;
                if (findWay(map, i + 1, j)) {
                    return true;
                } else if (findWay(map, i, j + 1)) {
                    return true;
                } else if (findWay(map, i - 1, j)) {
                    return true;
                } else if (findWay(map, i, j - 1)) {
                    return true;
                } else {
                    map[i][j] = 3;
                    return false;
                }
            } else {
                return false;
            }
        }
    }
}
```

5.汉诺塔问题

```java
package com.zhoumi.test;
public class Han {
    public static void main(String[] args){
        char a='A',b='B',c='C';
han(5,a,b,c);
    }
    public static void han(int number,char a,char b,char c){
        if(number==1){
            System.out.println(a + "->"+ c);
        }
      else {
          //把n-1个盘从A上借助C移动到B上
        han(number-1,a,c,b);
        //把A上剩下的1个石块移动到C上
        System.out.println(a + "->"+ c);
        //把B上的所有个盘借助A移动到C上
        han(number-1,b,a,c);
        }
    }
}
```

6. 八皇后问题

   

---------------

parse 类型转换

String s5 = "123";

int num1 = Integer.parseInt(s5);

double num2 = Double.parseDouble(s5);

float num3 = Float.parseFloat(s5); 

System.out.println(s5.charAt(1));   //取出2，因为1的编号是0



```java
package com.zhoumi.test;
import java.sql.Array;
import java.util.Scanner;
import java.util.Arrays;
public class Test {
    public static void main(String[] args) {
        int [] array = new int [10];
        for(int i=0;i<=10;i++){
            System.out.println(f(i));
        }
        System.out.println("请输入十个数字：");
            for (int i = 0; i < 10; i++){
Scanner sc =new Scanner(System.in);
        array[i] = sc.nextInt();
            }
            System.out.println("输出的数组为：");
            for(int j=0;j<10;j++) {
                System.out.print( array[j]+"   ");
            }
            int max =0;
       for(int k=0;k<10;k++) {
               if(array[k]>max) {
                   max=array[k];
               }
       }
       System.out.println("最大值为 "+max);
            }

    public static int f(int n){
        if(n==0||n==1){
            return  1;
        }
            else{
                return f(n-1)+f(n-2);
            }

    }
}
```

# 类

```java
package com.zhoumi.test;
import java.util.Scanner;
public class Lei {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);

    Cat cat1 = new Cat();
    System.out.println("请输入小猫咪1号的名称");
      cat1.name = sc.next();
      System.out.println("请输入小猫咪1号的年龄");
      cat1.age = sc.nextInt();
      System.out.println("请输入小猫咪1号的颜色");
      cat1.color = sc.next();
      System.out.println("小猫咪1号的信息"+" "+cat1.name+" "+cat1.age+" "+cat1.color);
    }
}
//类
class Cat{
    //属性 properties
    String name;
    int age;
    String color;
}
```

#### 访问修饰符

+ 控制属性的访问范围
+ 4种简单的运算修饰符： public, proctected, 默认, private
+ 属性的定义类型可以为任意类型，包含基本类型或引用类型
+ 属性如果不赋值，有默认值，规则和数组一致



---------------------------------------

# 重载（Overload）

java中允许同一个类中，多个同名方法的存在，但是参数列表不一致！

比如：System.out.println();   out是PrintStream类型；

+ 重载的好处：

1. 减轻了起名的麻烦
2. 减轻了记名的麻烦

注意事项与使用细节

1. 方法名相同
2. 参数列表不同（形参的类型或个数至少有一个不同，参数名无要求）
3. 返回类型无要求

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Cao {
    public static void main(String[] args) {
        Methods m = new Methods();
        System.out.println(m.m(100));
        System.out.println(m.m(10,100));
        System.out.println(m.m("hello world"));
    }
}
class Methods{
    public static int m(int n){
        return n*n;
    }
    public static int m(int m,int n){
        return m*n;
    }
    public static String m (String s){
        return s;
    }
}
```

可变参数：

Java允许将同一类中多个同名功能但参数个数不同的方法，封装成一个方法，可通过可变参数实现

基本语法：

访问修饰符 返回类型 方法名（数据类型... 形参名）{      

}

// int...表示接受的是可变参数，类型是int ，即可以接收多个int，可以把nums当作数组

public int sum(int ... nums){

}

+ 可变参数可以与普通参数一起在参数列表，但是必须保证可变参数在最后
+ 一个形参列表中，只能有一个可变参数
+ 

```java
package com.zhoumi.test;
import java.sql.Array;
import java.util.Arrays;
import java.util.Scanner;
public class Te {
    public static void main(String[] args) {
        HspMethods cj = new HspMethods();
        String name = "小明";
        Scanner sc = new Scanner(System.in);
        System.out.println("您想输入几门成绩？");
        int n = sc.nextInt();
        int arr[]=new int[n];
        for(int i=0;i<arr.length;i++){
            System.out.println("请输入第"+(i+1)+"门学科的成绩");
            arr[i]=sc.nextInt();
        }
        cj.showScore(name,arr);
        }
}
class HspMethods{
    public static void showScore(String name,int...score){
        int sum=0;
        for(int i=0;i<score.length;i++){
            sum += score[i];
        }
        System.out.println(name+score.length+"门学科"+"的总成绩为"+sum);
    }
}
```

```java
package com.zhoumi.test;
import java.sql.Array;
import java.util.Arrays;
import java.util.Scanner;
public class Te {
    public static void main(String[] args) {
        HspMethods cj = new HspMethods();
        cj.showScore("小明",90,80,78,98,100);
        cj.showScore("小花",99,98,100,76,87,90);
        }
}
class HspMethods{
    public static void showScore(String name,int...score){
        int sum=0;
        for(int i=0;i<score.length;i++){
            sum += score[i];
        }
        System.out.println(name+score.length+"门学科"+"的总成绩为"+sum);
    }
}
```

-------------------------------

作用域：

1. 在java编程中，主要的变量就是属性（成员变量）和局部变量。
2. 我们说的局部变量一般是指在成员方法中定义的变量。
3. 属性/全局变量可以加修饰符（public , private , protected.....）
4. 局部变量不可以加修饰符
5. 属性和局部变量可以重名，访问遵循就近原则



----------------------------------





-------------------------------------------------

# 构造器（构造方法）

基本语法：

[修饰符] 方法名(形参列表){

方法体；

}

1. 构造器的修饰符可以默认
2. 构造器没有返回值
3. 方法名和类名必须一样
4. 参数列表和成员方法一样的规则
5. 构造器的调用由系统完成
6. 构造器初始化对象
7. 是类的一种特殊方法
8. 构造器的name,age是局部变量，不是属性

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Cao {
    public static void main(String[] args) {
        Person p1 = new Person("小花",18);
    }
}
class Person{
    //定义属性
    String name;
    int age;
    //不能写成 public static void main Person();
    public  Person(String pName,int pAge){
        name = pName;
        age = pAge;
    }
}
```



# this

1. java虚拟机 会给每个对象分配this,代表当前对象。
2. 哪个对象调用，this就代表哪个对象的属性
3. this关键字可以用来访问本类的属性，方法，构造器
4. 用于区分当前类的属性和局部变量
5. 

```java
package com.zhoumi.test;
import java.util.Scanner;
import java.util.Arrays;
public class Cao {
    public static void main(String[] args) {
        Person p1 = new Person("小花",18);
        System.out.println("love");
        Person p2 = new Person("芝麻",19);
        p1.fu();
        p2.fu();
    }
}
class Person{
    String name;
    int age;
    public Person(){}
    public  Person(String name,int age){
        //this.name指的是当前对象的属性
       this.name = name;
        this.age = age;
        System.out.println(name+age);
    }
    public void fu(){
        System.out.println(name+"  "+age);
    }
}
```

# API

(应用程序编程接口)

Java API 指的就是jdk中各种功能的java类：学习这些类如何使用

1. 如何使用帮组文档(Random():生成随机数)
2. 

# StringBuilder

```java
package heima;
public class WuWuWu {
    public static void main(String[] args) {
        int[] array = {1, 2, 3};
        StringBuilder s = new StringBuilder();
        for(int i=0;i<array.length;i++){
            if(i==array.length-1){
                s.append(array[i]);
            }
            else {
                s.append(array[i]).append(", ");
            }
        }
        for(int i=0;i<array.length;i++){
            System.out.print(array[i]);
        }
        System.out.println("=======");
        String sc = s.toString();
        System.out.println(sc);
    }
}
```

StringBuilder sb = new StringBuilder();

StringBuilder sb2 = sb.append("hello");  // append : 添加字符串

链式：sb.append().append().append();

1. StringBuilder转换为String：

public String toString()  : 通过toString()就可以实现把StringBuilder转换为String

```java
StringBuilder c = new StringBuilder("1234");
String y = c.toString();
```

1. String转化为StringBuilder：

public StringBuilder(String s)   : 通过构造方法就可以实现把String转换为StringBuilder 

```java
String s = "222221";
StringBuilder we = new StringBuilder(s);
```



----

# ArrayList

public ArrayList()    :   创建一个空的集合对象

public boolean add(E e)   :    将指定的元素追加到此集合的末尾

public void add(int index, E element)   :   在此集合中

的指定位置插入指定的元素

```java
ArrayList<String> array = new ArrayList<>();
array.add("123");
array.add("456");
array.add("I love 周密");
array.add(3,"sb");
System.out.println(array);
```

public boolean remove(Object o)   :   删除指定的元素，返回删除是否成功 (array.remove() )

public E remove(int index)   :   删除指定索引处的元素，返回被删除的元素(array.remove() )

public E set(int index,E element)  :   删除指定索引出的元素，返回被修改的值 (array.set() )

public E get(int index);   ： 返回指定索引处的元素（ array.get() )

publlic int size()     :    返回集合中元素的个数   ( array.size() )

```java
ArrayList<String> array = new ArrayList<>();
array.add("123");
array.add("456");
array.add("I love 周密");
array.add(3,"sb");
System.out.println(array);
System.out.println(array.remove("sb"));
System.out.println(array.remove(2));
System.out.println(array.set(1,"被改啦"));
System.out.println(array.get(1));
System.out.println(array.size());
```

学生信息：

```java
package heima;
import java.util.ArrayList;
import java.util.Scanner;
public class new2 {
    public static void main(String[] args){
        ArrayList<Student>array = new ArrayList<>();
       AddStudent(array);
       AddStudent(array);
       AddStudent(array);
       for(int i=0;i<array.size();i++){
           Student s = array.get(i);
           System.out.println(s.getName()+", "+s.getAge());
       }
    }
    public static void AddStudent(ArrayList<Student>array){
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入学生姓名：");
        String name = sc.nextLine();
        System.out.println("请输入学生年龄：");
        int age = sc.nextInt();
        Student s = new Student();
        s.setAge(age);
        s.setName(name);
        array.add(s);
    }
}
```

# 学生管理系统

```java
package StudentManager;
import com.zhoumi.test.Sys;
import java.util.ArrayList;
import java.util.Scanner;

public class StudentManage {
    public static void main(String[] args) {
        ArrayList<Student>array = new ArrayList<>();
        while (true) {
            System.out.println("-------欢迎来到学生管理系统-------");
            System.out.println("1 添加学生");
            System.out.println("2 删除学生");
            System.out.println("3 修改学生");
            System.out.println("4 查看所有学生");
            System.out.println("5 退出");
            Scanner sc = new Scanner(System.in);
            String line = sc.nextLine();
            switch (line) {
                case "1":
                    //System.out.println("1 添加学生");
                    addStudent(array);
                    break;
                case "2":
                    //System.out.println("2 删除学生");
                    deleteStudent(array);
                    break;
                case "3":
                    //System.out.println("3 修改学生");
                    upDateStudent(array);
                    break;
                case "4":
                    //System.out.println("4 查看所有学生");
                    lookAllStudent(array);
                    break;
                case "5":
                    System.out.println(" 谢谢使用");
                    //break;
                    System.exit(0);
            }
        }
    }
    public static void addStudent(ArrayList<Student>array){
        Scanner sc = new Scanner(System.in);
        Student s = new Student();
        System.out.println("请输入学生学号：");
        String sid = sc.nextLine();
        System.out.println("请输入学生姓名：");
        String  name = sc.nextLine();
        System.out.println("请输入学生年龄：");
        String age = sc.nextLine();
        System.out.println("请输入学生住址：");
        String address = sc.nextLine();
        s.setAge(age);
        s.setName(name);
        s.setAddress(address);
        s.setSid(sid);
        array.add(s);
        System.out.println("添加成功！");
    }
    public static void lookAllStudent(ArrayList<Student>array) {
        if(array.size()==0){
            System.out.println("无信息，请先添加信息再查询！");
            return;
        }
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            System.out.println("学号" + s.getSid() + " 姓名" + s.getName() + " 年龄" + s.getAge() + "岁 住址" + s.getAddress());
        }
    }
    public static void deleteStudent(ArrayList<Student>array){
       System.out.println("请输入您想删除的学生的学号：");
       Scanner sc = new Scanner(System.in);
       String sid = sc.nextLine();
       int index = -1;
       for(int i=0;i<array.size();i++) {
       Student s = array.get(i);
       if(s.getSid().equals(sid)){
           array.remove(i);
           System.out.println("删除成功！");
           index = 1;
           break;
       }
       }
       if(index != 1){
           System.out.println("删除失败");
       }

       /* array.remove(sid);
       if(array.remove(sid)==true) {
           System.out.println("删除成功！");
       }
       else {
           System.out.println("无此学生信息");
       } */
    }
    public static void upDateStudent(ArrayList<Student>array){
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入您想修改的学生的学号：");
        String sid = sc.nextLine();
        System.out.println("请输入学生新姓名：");
        String name = sc.nextLine();
        System.out.println("请输入学生新年龄：");
        String age = sc.nextLine();
        System.out.println("请输入学生新住址：");
        String address = sc.nextLine();
        Student s = new Student();
        s.setSid(sid);
        s.setName(name);
        s.setAge(age);
        s.setAddress(address);
        for(int i=0;i<array.size();i++){
            Student student = array.get(i);
            if(student.getSid().equals(sid)){
                array.set(i,s);
                break;
            }
        }
    }
}

```

升级版学生管理系统（解决学号重复问题）：

```java
package StudentManager;
import com.zhoumi.test.Sys;
import java.util.ArrayList;
import java.util.Scanner;

public class StudentManage {
    public static void main(String[] args) {
        ArrayList<Student>array = new ArrayList<>();
        while (true) {
            System.out.println("-------欢迎来到学生管理系统-------");
            System.out.println("1 添加学生");
            System.out.println("2 删除学生");
            System.out.println("3 修改学生");
            System.out.println("4 查看所有学生");
            System.out.println("5 退出");
            Scanner sc = new Scanner(System.in);
            String line = sc.nextLine();
            switch (line) {
                case "1":
                    //System.out.println("1 添加学生");
                    addStudent(array);
                    break;
                case "2":
                    //System.out.println("2 删除学生");
                    deleteStudent(array);
                    break;
                case "3":
                    //System.out.println("3 修改学生");
                    upDateStudent(array);
                    break;
                case "4":
                    //System.out.println("4 查看所有学生");
                    lookAllStudent(array);
                    break;
                case "5":
                    System.out.println(" 谢谢使用");
                    //break;
                    System.exit(0);
            }
        }
    }
    /*public static void addStudent(ArrayList<Student>array) {
        Scanner sc = new Scanner(System.in);
        Student s = new Student();
        System.out.println("请输入学生学号：");
        String sid = sc.nextLine();
        s.setSid(sid);
        int index = 1;
        for (int i = 0; i < array.size(); i++) {
            Student student = array.get(i);
            if (student.getSid().equals(s.getSid())) {
                System.out.println("该学生学号重复，请重新添加！");
                index = -1;
            }
        }
        if(index==1){
        System.out.println("请输入学生姓名：");
        String name = sc.nextLine();
        System.out.println("请输入学生年龄：");
        String age = sc.nextLine();
        System.out.println("请输入学生住址：");
        String address = sc.nextLine();
        s.setAge(age);
        s.setName(name);
        s.setAddress(address);
        array.add(s);
        System.out.println("添加成功！");
    }
    }*/
    public static void addStudent(ArrayList<Student>array){
        Scanner sc = new Scanner(System.in);
        Student s = new Student();
        String sid;
        while(true) {
            System.out.println("请输入学生学号：");
             sid = sc.nextLine();
            boolean flag = isUsed(array, sid);
            if (flag == false) {
                System.out.println("该学号已经存在，请重新输入！");
            }
            else {
                break;
            }
        }
            System.out.println("请输入学生姓名：");
            String name = sc.nextLine();
            System.out.println("请输入学生年龄：");
            String age = sc.nextLine();
            System.out.println("请输入学生住址：");
            String address = sc.nextLine();
            s.setAge(age);
            s.setName(name);
            s.setAddress(address);
            s.setSid(sid);
            array.add(s);
            System.out.println("添加成功！");
    }
    public static void lookAllStudent(ArrayList<Student>array) {
        if(array.size()==0){
            System.out.println("无信息，请先添加信息再查询！");
            return;
        }
        for (int i = 0; i < array.size(); i++) {
            Student s = array.get(i);
            System.out.println("学号" + s.getSid() + " 姓名" + s.getName() + " 年龄" + s.getAge() + "岁 住址" + s.getAddress());
        }
    }
    public static void deleteStudent(ArrayList<Student>array){
       System.out.println("请输入您想删除的学生的学号：");
       Scanner sc = new Scanner(System.in);
       String sid = sc.nextLine();
       int index = -1;
       for(int i=0;i<array.size();i++) {
       Student s = array.get(i);
       if(s.getSid().equals(sid)){
           array.remove(i);
           System.out.println("删除成功！");
           index = 1;
           break;
       }
       }
       if(index != 1){
           System.out.println("删除失败");
       }

       /* array.remove(sid);
       if(array.remove(sid)==true) {
           System.out.println("删除成功！");
       }
       else {
           System.out.println("无此学生信息");
       } */
    }
    public static void upDateStudent(ArrayList<Student>array){
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入您想修改的学生的学号：");
        String sid = sc.nextLine();
        System.out.println("请输入学生新姓名：");
        String name = sc.nextLine();
        System.out.println("请输入学生新年龄：");
        String age = sc.nextLine();
        System.out.println("请输入学生新住址：");
        String address = sc.nextLine();
        Student s = new Student();
        s.setSid(sid);
        s.setName(name);
        s.setAge(age);
        s.setAddress(address);
        for(int i=0;i<array.size();i++){
            Student student = array.get(i);
            if(student.getSid().equals(sid)){
                array.set(i,s);
                break;
            }
        }
    }
    public static boolean isUsed(ArrayList<Student>array, String s){
        boolean flag = true;
        for(int i=0;i<array.size();i++){
            Student student = array.get(i);
            if(student.getSid().equals(s)){
                flag = false;
            }
        }
        return flag;
    }
}
```

# 11.14 Web组第二次考核：

```java
package LaboratoryManager;
import javax.swing.*;
import java.io.*;
import java.util.*;
import java.util.Comparator;
import static kotlin.reflect.jvm.internal.impl.builtins.StandardNames.FqNames.list;

public class LaboratoryManager {
    public static void main(String[] args) throws IOException {
        List<Members> array = new ArrayList<Members>();
        while (true) {
            System.out.println("-------欢迎来到实验室成员管理系统-------");
            System.out.println("1 添加成员信息");
            System.out.println("2 删除成员信息");
            System.out.println("3 修改成员信息");
            System.out.println("4 查看所有成员信息");
            System.out.println("5 退出");
            System.out.println("6 根据成员的历次考核的平均成绩进行排序，并展示全体成员信息");
            System.out.println("7 使用txt存储");
            System.out.println("8 使用txt读取");
            System.out.println("9 打开txt文档");
            System.out.println("请输入数字以使用系统:");
            Scanner sc = new Scanner(System.in);
            String line = sc.nextLine();
            switch (line) {
                case ("1"):{
                    //System.out.println("添加成员信息");
                    addLaboratoryMembers(array);
                    break;
                }
                case ("2"):{
                    //System.out.println("删除成员信息");
                    deleteLaboratoryMembers(array);
                    break;
                }
                case ("3"):{
                    //System.out.println("修改成员信息");
                    upDateLaboratoryMembers(array);
                    break;
                }
                case("4"):{
                    //System.out.println("查看所有成员信息");
                    lookAllLaboratoryMembers(array);
                    break;
                }
                case ("5"):{
                    System.out.println("退出成功");
                    System.exit(0);
                }
                case ("6"):{
                    // System.out.println("根据成员的历次考核的平均成绩进行排序，并展示全体成员信息");
//                  Collections.sort(array);
//                    System.out.println("排序后");
//                    for(Members m : array){
//                        System.out.println(m.getSid()+" "+m.getSex()+" "+m.getName()+" "+m.getCollege()+" "+m.getMajor()+" "+m.getScore());
//                    }

                    sortLaboratoryMembers(array);
                    break;
                }
                case ("7"):{
                    txt(array);
                    break;
                }
                case("8"):{
                    // System.out.println(readFileContent("实验室成员管理系统.txt"));
                    // readFileContent("实验室成员管理系统.txt");
                    //System.out.println(readTxtFile("实验室成员管理系统.txt"));
                    readTxt("实验室成员管理系统.txt",array);
                    break;
                }
                case ("9"):{
                    openTxt();
                    break;
                }
            }
        }
    }
    public static void addLaboratoryMembers(List<Members>arr){

        Scanner sc = new Scanner(System.in);
        Members m = new Members();
        String sid;
        while (true){
            System.out.println("请输入成员学号");
            sid = sc.nextLine();
            boolean flag = isUsed(arr,sid);
            if (flag == false){
                System.out.println("该学号已经存在！");
            }
            else {
                break;
            }
        }
        System.out.println("请输入成员姓名");
        String name = sc.nextLine();
        System.out.println("请输入成员性别");
        String sex = sc.nextLine();
        System.out.println("请输入成员年龄");
        String age = sc.nextLine();
        //System.out.println("请输入学生学号");
        //String sid = sc.nextLine();
        System.out.println("请输入成员学院");
        String college = sc.nextLine();
        System.out.println("请输入成员专业");
        String major = sc.nextLine();
        List<Integer>array = new ArrayList<>();
//        System.out.println("请输入分数:");
//        String score1 = sc.nextLine();
        System.out.println("您想输入___次考核成绩？");
        int n = sc.nextInt();
        for (int i=0;i<n;i++){
            System.out.println("请输入第"+(i+1)+"次考核成绩");
            int score = sc.nextInt();
            array.add(score);
        }
        m.setAverage(Members.average(array));
        m.setName(name);
        m.setSex(sex);
        m.setAge(age);
        m.setSid(sid);
        m.setCollege(college);
        m.setMajor(major);
        m.setScore(array);
//        m.setScore1(score1);
        m.setScore(array);
        arr.add(m);
    }
    public static void deleteLaboratoryMembers(List<Members>arr){
        System.out.println("请输入你想删除的成员的学号：");
        Scanner sc = new Scanner(System.in);
        String sid = sc.nextLine();
        int index = -1;
        for(int i=0;i<arr.size();i++) {
            Members m = arr.get(i);
            if (sid.equals(m.getSid())) {
                arr.remove(m);
                System.out.println("删除成功！");
                index = 1;
                break;
            }
        }
        if(index == -1) {
            System.out.println("该成员信息不存在，删除失败");
        }
    }
    public static void lookAllLaboratoryMembers(List<Members>arr){
        for(int i=0;i<arr.size();i++){
            Members m = new Members();
            m = arr.get(i);
            System.out.println(m.getSid()+" "+m.getName()+" "+m.getSex()+" "+m.getAge()+m.getCollege()+" "+m.getMajor()+" "+m.getScore()+" ");
        }
        if(arr.size()==0){
            System.out.println("无学生信息，请添加学生信息！");
        }
    }
    public static void upDateLaboratoryMembers(List<Members>arr) {
        Scanner sc = new Scanner(System.in);
        String sid;
        while (true) {
            System.out.println("请输入你想修改信息的成员的学号");
            sid = sc.nextLine();
            boolean flag = isUsed(arr, sid);
            if (flag == false) {
                System.out.println("成员信息存在，请继续操作");
                break;
            } else {
                System.out.println("该成员信息不存在! ");
            }
        }
        System.out.println("sid 修改学生的学号");
        System.out.println("name 修改学生姓名");
        System.out.println("sex 修改学生性别");
        System.out.println("age 修改学生年龄");
        System.out.println("college 修改学生学院");
        System.out.println("major 修改学生专业");
        System.out.println("score 修改学生分数");
        System.out.println("exit 退出修改");
        String index = sc.nextLine();
        switch(index) {
            case ("sid"): {
                System.out.println("请输入新的学号");
                String newSid = sc.nextLine();
                int temp = 1;
                for (int i = 0; i < arr.size(); i++) {
                    Members m = arr.get(i);
                    if (m.getSid().equals(newSid)) {
                        System.out.println("该学号已经存在，请重新输入！");
                        temp = 0;
                        break;
                    } else {
                        temp = 1;
                    }
                }
                if (temp == 1) {
                    for (int i = 0; i < arr.size(); i++) {
                        Members m = arr.get(i);
                        if (m.getSid().equals(sid)) {
                            m.setSid(newSid);
                        }
                    }
                }
                break;
            }
            case ("name"): {
                System.out.println("请输入新的姓名");
                String newName = sc.nextLine();
                for (int i = 0; i < arr.size(); i++) {
                    Members m = arr.get(i);
                    if (m.getSid().equals(sid)) {
                        m.setName(newName);
                    }
                }
                break;
            }
            case ("sex"): {
                System.out.println("请输入新的性别");
                String newSex = sc.nextLine();
                for (int i = 0; i < arr.size(); i++) {
                    Members m = arr.get(i);
                    if (m.getSid().equals(sid)) {
                        m.setSex(newSex);
                    }
                }
                break;
            }
            case ("age"): {
                System.out.println("请输入新的年龄");
                String newAge = sc.nextLine();
                for (int i = 0; i < arr.size(); i++) {
                    Members m = m = arr.get(i);
                    if (m.getSid().equals(sid)) {
                        m.setAge(newAge);
                    }
                }
                break;
            }
            case ("college"): {
                System.out.println("请输入新的学院");
                String newCollege = sc.nextLine();
                for (int i = 0; i < arr.size(); i++) {
                    Members m = arr.get(i);
                    if (m.getSid().equals(sid)) {
                        m.setCollege(newCollege);
                    }
                }
                break;
            }
            case ("major"): {
                System.out.println("请输入新的专业");
                String newMajor = sc.nextLine();
                for (int i = 0; i < arr.size(); i++) {
                    Members m = arr.get(i);
                    if (m.getSid().equals(sid)) {
                        m.setCollege(newMajor);
                    }
                }
                break;
            }
            case ("score"): {
                System.out.println("请输入修改后的成员历次考核成绩");
                List<Integer> newScore = new ArrayList<>();
                for (int i = 0; i < arr.size(); i++) {
                    Members m = arr.get(i);
                    if (m.getSid().equals(sid)) {
                        for (int j = 0; j < m.getScore().size(); j++) {
                            int newScores = sc.nextInt();
                            newScore.add(newScores);
                        }
                    }
                }
//                System.out.println("请输入新成绩:");
//                String newScore1 = new String();
//                for (int i = 0; i < arr.size(); i++) {
//                    Members m = arr.get(i);
//                    if (m.getSid().equals(sid)) {
//                        m.setSex(newScore1);
//                    }
//                }
                break;
            }
        }
    }
    public static void sortLaboratoryMembers(List<Members>arr){

//        for(int i=0;i<arr.size();i++) {
//            Members m = new Members();
//            m.setAverage(Members.average(m.getScore()));
//        }
        Collections.sort(arr);
        System.out.println("排序后");
        System.out.println(arr.toString());
        if(arr.size()==0){
            System.out.println("暂无成员信息！");
        }
    }
    public static void openTxt(){
        Process p = null;//Process代表一个进程对象
        try {
            p = Runtime.getRuntime().exec("notepad.exe 实验室成员管理系统.txt");
            //参数为操作系统的一个进程的命令，而不是传一个文件
            //启动记事本程序打开java文件
            Thread.sleep(5000);//眠5秒后销毁该进程。
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            p.destroy();//销毁该进程
        }
    }
    public static void txt(List<Members>arr){
        try {
            FileWriter writer = new FileWriter("实验室成员管理系统.txt",true);
            FileReader reader = new FileReader("实验室成员管理系统.txt");
            BufferedWriter bw = new BufferedWriter(writer);
            BufferedReader br = new BufferedReader(reader);
            // bw.write("学号 姓名 性别 年龄 学院 专业    考核成绩   平均成绩\n\n");
            for(int i=0;i<arr.size();i++){
                String s =arr.get(i).toString();
                /*if(s==br.readLine()){
                    continue;
                }*/
                bw.write(s);
                // bw.newLine();  //换行
                //   bw.flush();    //缓冲
            }
            System.out.println("储存成功" );
            bw.close();
        }catch(Exception e){
            System.err.format("IOException: %s%n",e);
        }
        //openTxt();
    }
    private static boolean isUsed(List<Members> arr, String sid) {
        boolean flag = true;
        for(int i=0;i<arr.size();i++){
            Members m = arr.get(i);
            if(sid.equals(m.getSid())){
                flag = false;
            }
        }
        return flag;
    }
    public static void readTxt(String fileName,List<Members>arr) throws IOException {
        /*
        //创建字符缓冲流对象
        BufferedReader br = new BufferedReader(new FileReader(fileName));
        //创建ArrayList集合对象
        ArrayList<String> array = new ArrayList<String>();
        String line;
        while((line = br.readLine()) != null){
            //把读取到的字符串存储到集合中
            array.add(line);
        }
        br.close();
        for(String s : array){
            System.out.println(s);
        }

         */

        BufferedReader br = new BufferedReader(new FileReader(fileName));
        String line = null;
        try {
            while ((line = br.readLine()) != null ) {
                if(line.equals((""))){
                    continue;
                }
                //分割字符串
                String[] strArray = line.split("\\s");
                Members m = new Members();
                m.setSid(strArray[0]);
                m.setName(strArray[1]);
                m.setSex(strArray[2]);
                m.setAge(strArray[3]);
                m.setCollege(strArray[4]);
                m.setMajor(strArray[5]);
                String s = new String();
                List<Integer>array = new ArrayList<>();
                for(int j=0;j<strArray[6].length();j++){
                    if(strArray[6].charAt(j)!='[' && strArray[6].charAt(j)!=']'){
                        s += strArray[6].charAt(j);
                    }
                    if(strArray[6].charAt(j)==']'){
                        break;
                    }
                }
                String[] fg = s.split(",") ;
                for(int k=0;k<fg.length;k++){
                    array.add(Integer.parseInt(fg[k]));
                }
                m.setScore(array);
//                m.setScore1(strArray[6]);
//                int i = Integer.parseInt(strArray[7]);
//                m.setAverage(i);
                arr.add(m);
            }
        }catch (Exception e){
            e.printStackTrace();
        }
        br.close();

    }
}

```

```java
package LaboratoryManager;

import java.util.List;

public class Members implements Comparable<Members> {
    private String name;
    private String sex;
    private String age;
    private String sid;
    private String college;
    private String major;
    private List<Integer> score;
    private String score1;
    private int average ;
    public Members() {
    }

    public Members(String name, String sex, String age, String sid, String college, String major, List<Integer> score) {
        this.name = name;
        this.sex = sex;
        this.age = age;
        this.sid = sid;
        this.college = college;
        this.major = major;
        this.score = score;
    }

    public String getScore1() {
        return score1;
    }

    public void setScore1(String score1) {
        this.score1 = score1;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSex() {
        return sex;
    }

    public void setSex(String sex) {
        this.sex = sex;
    }

    public String getAge() {
        return age;
    }

    public void setAge(String age) {
        this.age = age;
    }

    public String getSid() {
        return sid;
    }

    public void setSid(String sid) {
        this.sid = sid;
    }

    public String getCollege() {
        return college;
    }

    public void setCollege(String college) {
        this.college = college;
    }

    public String getMajor() {
        return major;
    }

    public void setMajor(String major) {
        this.major = major;
    }

    public List<Integer> getScore() {
        return score;
    }

    public void setScore(List<Integer> score) {
        this.score = score;
    }

    public int getAverage() {
        return average;
    }

    public void setAverage(int average) {
        this.average = average;
    }


//    public static String information(){};

    public static int average(List<Integer>score){
        int num=0;
        for(int i=0;i<score.size();i++){
            num += score.get(i);
        }
        int average = num/score.size();
        return average;
    }
    public static int average(String score1){
        return  Integer.parseInt(score1);
    }
    @Override
    public int compareTo(Members m){
        if( m.average - this.average!=0){
            return m.average - this.average;
        }
        else return 1;
//        return 0; //元素重复不添加
//        return 1;  //升序存储
//        return -1;  //降序存储

    }
    @Override
    public String toString(){
        /*return '\n'+sid+" "+name+" "+sex+" "+age+" "+college+" "+major+" "+
                score
                +'\n';*/
        String s1='\n'+sid+" "+name+" "+sex+" "+age+" "+college+" "+major+" ";
        String s2="[";
        for(int s:score){
            s2+=s+",";
        }
        s2+="]"+'\n';
        String ss = new String();
        for(int i=0;i<s2.length();i++){
            if(i==s2.length()-3){
                continue;
            }
            ss+=s2.charAt(i);
        }
        return s1+ss;
    }
    /*public int compare(Members m1,Members m2){
        int i= m1.getAverage()-m2.getAverage();
        if(i==0){
            return 1;
        }
        return i;
    }

     */
   /* public void getAverage(){
        this.average = average;
    }

    */
}
```



# 继承

+ 是面向对象的三大特征之一，可以使得子类具有父类的属性和方法，还可以在子类中重新定义，追加属性和方法。
+ 好处：提高了代码的复用性（多个类的相同成员放到一个类中）
+ 提高代码的维护性（如果方法的代码需要修改，修改一处即可）
+ 什么时候使用继承？
+ 继承体现的关系： is a
+ 

格式：

public class 子类名 extends 父类名 ( )

父类也被称为基类、超类

子类也被称为派生类

super 关键字 访问的是父类的成员变量（this访问的是本类的成员变量）

每一个子类构造方法的第一条语句默认都是：super()

如果父类中没有无参构造方法，该怎么办呢？

1. 通过使用super关键字显示的调用父类的带参构造方法
2. 在父类中自己提供一个无参构造方法
   + 推荐自己给出无参构造方法

+ 继承中成员方法的访问特点：

通过子类对象访问一个方法：

1.  子类成员范围查找
2. 父类成员范围找
3. 如果都没有就报错（不考虑父亲的父亲...）

方法重写：

概述：子类中出现了和父类中一模一样的方法声明

应用：

1. 当子类需要父类的功能，而功能主体子类有自己特有内容时，可重写父类中的方法，这样既沿袭了父类的功能，又定义了子类特有的内容
2.   @overrid : 是一个注解，帮助我们检查重写方法的方法声明的正确性

继承：可以多层继承，不支持同时继承多个！



# 修饰符

| 修饰符    | 同一个类中 | 同一个包中子类无关类 | 不同包的子类 | 不同包的无关类 |
| --------- | ---------- | -------------------- | ------------ | -------------- |
| private   | √          |                      |              |                |
| 默认      | √          | √                    |              |                |
| protected | √          | √                    | √            |                |
| public    | √          | √                    | √            | √              |

final : 表示最终，不可改变（一次赋值，终身不可变）

可以修饰类、方法、局部变量、成员变量

修饰后的对象不可改变！！！也不可作为父类被继承！

 static 静态的 ： 可以修饰成员方法、成员变量

static 修饰的特点：

1. 被类的所有对象共享
2.  可以通过类名、对象名调用（推荐类名调用）

访问特点：

1. 非静态的成员方法可以调用静态与非静态的成员变量与方法
2. 静态的成员方法只能调用静态的成员变量与方法、

# 多态

同一个对象，不同时刻表现出的不同形态

前提与体现：

1. 有继承/实现关系

2. 有方法重写

3. 有父类引用指向子类对象

   父 = new 子 ( ) 

   成员变量：编译看左边，执行看左边

   成员方法：编译看左边，执行看右边

多态的好处和弊端：

好处：提高了程序的扩展性

具体体现：定义方法的时候，使用父型类作为参数，将来使用的时候，使用具体的子类型参与操作

弊端：

不能使用子类的特有功能

多态中的转型：

向上转型：

1. 从子到父
2. 父类引用指向子类对象

向下转型

1. 从父到子
2. 父类引用转为子类对象



抽象类特点：

+ 抽象类和抽象方法必须使用abstra关键字修饰

​             public abstract class 类名 { }

​             public abstract void eat ( ) ;

抽象类中不一定有抽象方法，有抽象方法的类一定是抽象类

+ 抽象类不能实例化

​            抽象类如何实例化？参照多态的方式，通过子类对象实例化，这叫抽象类多态

+ 抽象类的子类

​            要么重写抽象类中所有抽象方法

​            要么是抽象类

+ 抽象类的成员特点											

+ 抽象方法只能在其它类写





# List

1.什么是列表（list）

列表是容器型数据类型; 将[]作为容器标志，里面多个数据用逗号隔开：[元素1, 元素2, 元素3,…]
列表是可变（可变指的是元素的个数可变；元素的值变量；元素的顺序可变）、列表是有序的（每个元素都有一个表示元素在列表中位置的序号）
元素(容器中的每个独立的数据就是元素)：没有要求（任何类型的数据都可以作为列表的元素）
————————————————

查 - 获取元素
2.1 查单个 - 获取列表中某一个元素

语法：
列表[下标] - 获取列表中指定下标对应的元素

说明：
列表 - 任何结果是列表的表达式，例如：具体的一个列表值、保存列表的变量
[] - 固定写法
下标 - 又叫索引。它是元素在列表中的位置信息。
取值方式1：从0开始依次增加，其中0表示第一个元素，1表示第二个元素
取值方式2：从-1开始依次减少，其中-1表示倒数第一个元素，-2表示倒数第二个元素…

2.2 切片（查部分） - 同时获取列表中的多个元素

原理：通过提供下标的范围来获取范围内下标对应的元素
语法：
列表[开始下标:结束下标:步长] - 从开始下标开始，每次下标值增加步长，取到结束下标前为止。

注意：
1）结束下标对应的元素一定取不到， 开始下标对应的元素可以取到
2）如果步长为正，表示从前往后取，这个时候开始下标对应的位置必须在结束下标对应的位置前，否则结果是[]
3）如果步长为负，表示从后往前取，这个时候开始下标对应的位置必须在结束下标对应的位置后，否则结果是[]

2.3 遍历

方法一： 直接获取元素
for循环

变量取到的就是列表中的每个元素

games = ['王者荣耀', '和平精英', '狼人杀', '植物大战僵尸', '开心消消乐', '红色警戒']
for x in games:
    print(x)

方法二：先获取每个元素对应的下标，然后再通过下标获取元素
for 变量 in range(列表长度):
列表[变量]

len(列表) - 获取列表中元素的个数
————————————————

1.增 - 往列表中添加元素
1.1 列表.append(元素) - 在列表的最后添加指定的元素
1.2 列表.insert(下标, 元素) - 在列表的指定下标对应的元素前插入指定元素

2.删 - 删除列表中的元素

2.1 del 列表[下标] - 删除列表中指定下标对应的元素

2.2 列表.remove(元素) - 删除列表中指定的元素

如果元素不存在会报错；如果被删除的元素在列表中有多个，只删最前面的那一个



```java
public class Main {
    public static void main(String[] args) {
        List<String> list = List.of("A", "B", "C");
        System.out.println(list.contains("C")); // true
        System.out.println(list.contains("X")); // false
        System.out.println(list.indexOf("C")); // 2
        System.out.println(list.indexOf("X")); // -1
    }
}
```

在`List`中查找元素时，`List`的实现类通过元素的`equals()`方法比较两个元素是否相等，因此，放入的元素必须正确覆写`equals()`方法，Java标准库提供的`String`、`Integer`等已经覆写了`equals()`方法；

编写`equals()`方法可借助`Objects.equals()`判断。

如果不在`List`中查找元素，就不必覆写`equals()`方法。

# 接口

+ 用关键字interface修饰
+ 类实现接口用implements表示
+ 接口可以多继承（类只能单继承，但可以多层继承）
+ 接口不能实例化
+ 接口的实现类：
  1. 要么重写接口中所有抽象方法
  2. 要么是抽象类
+ 接口中变量默认被final修饰
+ 接口中无具体方法，可以写抽象方法，因为接口主要对行为进行抽象，无具体存在
+ 一个类如果没有父类，默认继承自Object类
+ 成员方法： 只能是抽象方法、默认修饰符：public abstract



# 内部类

访问特点：

+ 内部类可以直接访问外部类的成员，包括私有
+ 外部类要访问内部类的成员，必须创建对象

1、在类的成员位置：成员内部类

+ 格式：外部类名.内部类名 对象名 = 外部类对象.内部类对象 ; 

+ 范例： Outer.Inner oi = new Outer().new Inner();  (在别的类不针对private的类)

+ ```java
  public class Outer {
  
      private int num = 10;
      private class Inner{
          void show(){
              System.out.println("我不给你用");
          }
      }
      Inner i = new Inner();
      Outer n = new Outer();
      //i.show();
      public void method() {
          Inner m = new Inner();
          m.show();
          i.show();
      }
  }
  public class Demo1 {
      public static void main(String[] args){
          Outer p = new Outer();
          p.method();
      }
  }
  ```

2、局部内部类（方法内的类）

```java
public class Outer {

    private int num = 10;
    //i.show();
    public void method() {
         class Inner{
            void show(){
                System.out.println("我不给你用");
            }
        }
        Inner i = new Inner();
         i.show();
    }
}
public class Demo1 {
    public static void main(String[] args){
        Outer p = new Outer();
        p.method();
    }
}
```



+ 匿名内部类(**是局部内部类的一种形式**)

+ 前提：存在一个类或者接口，这里的类可以是具体类也可以是抽象类

+ 格式：

  new 类名或接口名（）{

  重写方法；

  }

  本质：一个继承了类或者实现该接口的子类匿名对象

  ```java
  /* new Inter(){
   public void show(){
        
   }
  }      */
  public class Outer {
  
      private int num = 10;
      //i.show();
      public void method() {
          new Inter (){
              public void show(){
                  System.out.println("匿名局部类被调用啦");
              }
          }.show();
      }
  }
  public class Demo1 {
      public static void main(String[] args){
          Outer p = new Outer();
          p.method();
      }
  }
  ```

  或：

  ```java
  public class Outer {
  
      private int num = 10;
      //i.show();
      public void method() {
         Inter l = new Inter (){
              public void show(){
                  System.out.println("匿名局部类被调用啦");
              }
          };
          l.show();
          l.show();
          l.show();
      }
  }
  ```

#  Math

| Math.abs(double a)          | 返回参数绝对值                  |
| --------------------------- | ------------------------------- |
| Math.ceil(double a)         | 返回大于或等于参数的最小double  |
| Math.round(float a)         | 按照四舍五入返回最接近参数的int |
| Math.max(int a,int b)       | 返回两个int 的较大值            |
| Math.min(int a,int b)       | 返回2个int的较小值              |
| Math.pow(double a,double b) | 返回a的b次幂的值                |
| Math.random()               | 返回double的正值[0.0,1.0)       |
|                             |                                 |



# System

System.exit(0);    //终止当前运行的Java虚拟机

System.currentTimeMillis();           // 输出当前时间与1970年相差的毫秒

# Object

所有的类都直接或间接继承该类

.equals方法

.toString方法

# Arrays

public static String toString(int[] a)             返回指定数组内容的字符串表示形式

public static void sort(int[] a)              按照数字顺序排列指定的数组

```java
int arr[] = {1,3,2,7,5,4,9,6,10,8};
        System.out.println("排序前："+Arrays.toString(arr));
        Arrays.sort(arr);
        System.out.println("排序后："+Arrays.toString(arr));
```

w工具类的设计思想：

+ 构造方法用private修饰
+ 成员用public static 修饰

# 基本类型包装类

## 最常用于基本类型和字符串的相互转换

Integer

Integer(int )   或 Integer(String)

Integer.valueOf(int ) 或 Integer(String)

int 和 String 的相互转换

```java
int i = 100;
String o = "" + i ;
```

或：

```java
String s2 = String.valueOf(int i);
```

------------

```java
String s = "100";
Integer i = Integer.valueOf(s);
int x = i.intValue();
//或：
    // int y = Integer.parseInt(s);
```

字符串中数据排序：

```java
String s ="91 27 46 38 50";
String[] strArray = s.split(" ");
```



## 自动装箱和拆箱

![image-20211104193633544](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211104193633544.png)

emmm

![image-20211104193950018](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211104193950018.png)



### Date

Date（）表示从标准基准时间起的时间，精确到毫秒

Date（long date) : 分配一个Date对象，并将其初始化为表示从标准基准时间起到指定的毫秒数

Date类的常用方法：

public long getTime()   :  从1970年1月1号 00:00:00到现在的毫秒值  

public void steTime(long time)  :  设置时间给毫秒值

# 日期类

SimpleDateFormat

是一个具体的类，用于区域设置敏感的方式格式化和解析日期

日期和时间格式由日期和时间模式字符串指定，在日期和时间模式字符串中，从'A'到'Z'以及从'a'到'z'引号的字母呗解释为表示日期或时间字符串的组件的模式字母。

常用的模式字母以及对应关系如下：

+ y     年
+ M     月
+ d      日
+ H    时
+ m    分
+ s      秒

1. 格式化（从Date 到 String ）：public final String format(Date date )：将日期格式化成日期/时间字符串
2. 解析（从String到Date）：public Date parse(String source)：从给定字符串开始解析文本以生成日期

```java
  public static void main(String[] args) throws ParseException {
       // SimpleDateFormat
        //1. 格式化（从Date 到 String ）：public final String format(Date date )：将日期格式化成日期/时间字符串
       // 2. 解析（从String到Date）：public Date parse(String source)：从给定字符串开始解析文本以生成日期
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日HH时mm分ss秒");
        Date d = new Date();
        String s = sdf.format(d);
        System.out.println(s);
        SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy年MM月dd日HH时mm分ss秒");
        String ss = "2021年11月18日21时08分09秒";
        Date dd = sdf2.parse(ss);
        System.out.println(dd);
    }
```

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
public class DateUtils {
    DateUtils(){};
    public static String dateToString(Date date, String format){
        SimpleDateFormat sdf = new SimpleDateFormat(format);
        String s1 = sdf.format(date);
        return s1;
    }
    public static Date stringToDate(String s,String format) throws ParseException {
        SimpleDateFormat sdf = new SimpleDateFormat(format);
        Date date = sdf.parse(s);
        return date;
    }
    -------------------------------------------------------
    import java.util.Date;

public class DateDemo {
    public static void main(String[] args) throws ParseException {
        Date date = new Date();
        String format = "yyyy年MM月dd日HH时mm分ss秒";
        String s = "2021年11月08日19时23分30秒";
        System.out.println(DateUtils.dateToString(date,format));
        Date date2 =DateUtils.stringToDate(s,format);
        System.out.println(date2);
    }
```



# 日期类

### Calendar

.add(设置当前日期)

.set

.get

```java
public class CalendarUtil {
    public static void main(String[] args) {


//        Calendar c = Calendar.getInstance();
//        int year = c.get(Calendar.YEAR);
//        int month = c.get(Calendar.MONTH)+1;
//        int day = c.get(Calendar.DATE);
//        c.set(2020,10,20);
        int year ;
        Scanner sc = new Scanner(System.in);
        year = sc.nextInt();
        Calendar c = Calendar.getInstance();
        c.set(year,2,1);
//        c.add(Calendar.YEAR,-10);
//        c.add(Calendar.MONTH,-2);
//        c.add(Calendar.DATE,-5);
        c.add(Calendar.DATE,-1);
        int day = c.get(Calendar.DATE);
        System.out.println(year+"的二月有"+day+"天");
        //System.out.println(c.set(2020,10,20));
    }
```





## 异常处理

```
try{   
可能出现异常的代码
}catch(异常类名  变量名 ){
异常处理的代码
}
```

Throwable 的成员方法

![image-20211109184111564](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211109184111564.png)

```java
	方法名后+throws 抛出异常
```

![image-20211110190157539](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211110190157539.png)

1. 建立异常类继承Exception
2. 手动 throws 抛出异常对象 

![image-20211110191117719](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211110191117719.png)

throws 用在方法声明后加异常类名

throw 用在方法体内部，跟异常对象名

```java
package heima;
import java.util.ArrayList;
import java.util.Scanner;
public class checkScore {
    public static void main(String[] args) {
        int score;
        Scanner sc = new Scanner(System.in);
        score = sc.nextInt();
        teacher t = new teacher();
        try {
            t.checkScore(score);
        } catch (abnormal a) {
            a.printStackTrace();
        }
    }
}
package heima;

public class teacher {
    public void checkScore(int score) throws abnormal{
        if(score<0 || score >100){
            throw new abnormal("请输入0~100的分数");
        }else{
            System.out.println("分数正常");
        }
    }
}
package heima;

import java.util.ArrayList;

public class abnormal extends Exception{
    public abnormal(){};
    public abnormal(String message){
        super (message);
    };
}

```



# Collectiona

![image-20211111184908151](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211111184908151.png)

.add：添加元素

.remove：从集合中移除指定的元素

.clear：清空集合中元素

.contains：判断是否存在指定的元素

.isEmpty：判断集合是否为空

.size：集合的长度也就是及集合中的个数

# List

有序，可重复

```java
// 迭代器方法遍历
List<String> list = new ArrayList<String>();
Iterator<String> it = list.iterator();
while(it.hasNext()){
String s = it.next();
System.out.println(s);
}
```

 set(int inex,E element)：修改索引处的元素，返回被修改的元素

get(int index)：返回索引处的元素

## 并发修改异常

原因：迭代器中预期集合中修改次数与实际修改次数不同

修改：用for循环写

```java
for(int i=0;i<list.size();i++){
    String s = list.get(i);
    if(s.equals("world")){
        list.add("javaee");
    }
}
```

# ListIterator : 列表迭代器 （需导包）

![image-20211111194636103](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211111194636103.png)

![image-20211111194647926](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211111194647926.png)

常用方法：

E next()：返回迭代中的下一个元素

boolean hasNext()：如果迭代有更多元素，返回true

E previous()：返回列表中的上一个元素

boolean hasPrevious()：如果此列表迭代器在相反方向遍历列表时有更多元素，则返回true

void add(E e)：将指定的元素插入列表

```java
ListIterator<String> lit = list.ListIterator();
while(lit.hasNext()){
     String s = lit.next();
     if(s.equals("world")){
           lit.add("javaee");   //通过构造器添加列表元素，而Iterator是无法调用此方法的
     }                       
}
System.out.println(list);
```

## iterator

```java
Iterator<Student> it = list.iterator();
while(it.hasNext()){
Student s =it.next();
System.out.println(s.getName());
}
```

![image-20211114192150263](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211114192150263.png)

# List：

### 数据结构：

##### 栈：

常见数据结构之链表（增删快、查询慢）：

![image-20211114204235822](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211114204235822.png)

![image-20211115181326216](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211115181326216.png)

结点的存储位置（地址）

结点：本结点地址【（数据、下一个结点的地址）】



# List常用子类（ArrayList、LinkedList)

Linked：**链表**实现了Lust和Deque接口

ArrayList：底层数据结构是数组，查询快，增删快

LinkedList：底层数据结构是链表，查询慢，增删快

练习：分别使用ArrayList和LinkedList完成储存字符串并遍历

```java
 public class Test {
    public static void main(String[] args) {
        ArrayList<String>arr = new ArrayList<>();
        arr.add("I");
        arr.add("love");
        arr.add("java");
        for(String s :arr){
            System.out.println(s);
        }
        for(int i=0;i<arr.size();i++){
            System.out.println(arr.get(i));
        }
        System.out.println(arr);
        Iterator<String> it = arr.iterator();
        while(it.hasNext()){
            System.out.println(it.next());
        }
        System.out.println("------------");
        LinkedList<String>arr1 = new LinkedList<>();
        arr1.add("I");
        arr1.add("love");
        arr1.add("China");
        for(String ss: arr1){
            System.out.println(ss);
        }
        System.out.println(arr1);
        for(int i=0;i<arr1.size();i++){
            System.out.println(arr1.get(i));
        }
        Iterator<String> it1 = arr1.iterator();
        while(it1.hasNext()){
            System.out.println(it1.next());
        }
    }
}
```

LinkedList集合的特有功能：

addFirst(E e) ：在该列表开头插入指定元素

addLast(E e)：将指定的元素追加到此列表的末尾

getFirst() ：返回列表中第一个元素

getLast() ：返回列表中最后一个元素

removeFirst() ： 从此列表中删除并返回第一个元素

removeLast() ： 从此列表中删除并返回最后一个元素



# Set集合的概述和特点

Interface Set <E> extends Collection<E>

+ 不包含重复元素的集合

+ 没有带索引的方法，所以不能用普通for循环遍历

+ 是一个接口，不能直接实现

+ HashSet：对集合的迭代顺序不作任何保证

+ ```java
  Set<String>set = new HashSet<String>();
  set.add("hello");
  set.add("world");
  set.add("java");
  set.add("java");
  for(String s : set){
  System.out.println(s);
  }
  ```

  

### 哈希值：

是JDK根据对象的地址或者字符串或者数字算出来的int类型的数值

Object类中有一个方法可以获取对象的哈希值

​    public int hasCode()  ：返回对象的哈希码值

```java
Student s1 = new Student("zm",18);
System.out.println(s1.hashCode());
System.out.println(s1.hashCode());
//同一对象多次调用hashCode()方法返回对象的哈希码值是相同的
Student s2 = new Student("zm",18);
System.out.println(s2.hashCode());
//默认情况下，不同对象的哈希值是不同的
```

```
public int compare(Student s1,Student s2){
int num = s1.fetAge() - s2.getAge();
int num2 = num==0?s1.getName().compareTo(s2.getName()) : num;
}
```





# Hashset

集合特点：

1. 底层数据结构是哈希表
2. 对集合的迭代顺序不做任何保证，也就是说不保证存储和取出的元素顺序一致
3. 没有带索引的方法，所以不能使用普通for循环遍历
4. 由于是Set集合，所以不能包含重复元素的集合

```java
HashSet <String> hs = new HashSet<String>();
hs.add("world");
hs.add("world");
hs.add("java");
for(String s : hs){
System.out.println(s);
}
```

# _TreeSet

import java.util.AbstractSet;

特点：元素有序，通过构造方法，可使用自然排序或比较器排序

没有带索引的方法，不能用普通for遍历，可以用迭代器与增强for遍历

Set集合不包含重复元素

```java
TreeSet(){}  //构造一个新的，空的树组，根据元素自然顺序进行排序
TreeSet(Collection< ? extends R> c){} // 构造一个包含指定集合中的元素的新树集，根据其元素的自然排序进行排序。
TreeSet(Comparator<? super E> comparator){} //构造一个新的，空的树集，根据指定的比较器进行排序
TreeSet(SorttedSet<E> a){} //构造一个包含相同元素的新树，并使用与指定排序集相同的顺序。
```

```java
public static void main(String[] args){
TreeSet<Integer> ts = new TreeSet<Integer>();
//添加元素
ts.add(10);
ts.add(9);
ts.add(40);
ts.add(30);
ts.add(50);
ts.add(10);
ts.add(20);
for(Integer i : ts){
System.out.println(i);
}
}
```





# Comparable（比较器排序接口）

```java
compareTo(E e){
return 0; //元素重复不添加
return 1;  //升序存储（存储在前一个元素后面）
return -1;  //降序存储（存储在前一个元素前面）
}

public static void main(String[] args){
    //创建集合对象
    TreeSet<Student> ts = new TreeSet<Student>();
    //创建学生对象
    Student s1 = new Student("xishi",29);
     Student s2 = new Student("wangzhaojun",30);
     Student s3 = new Student("diaochan",28);
     Student s4 = new Student("yangyuhuan",32);
     Student s5 = new Student("zhoumi",18);
    ts.add(s1);
    ts.add(s2);
    ts.add(s3);
    ts.add(s4);
    ts.add(s5);
    for(Student s : ts){
        System.out.println(s.getName+" "+s.getAge);
    }
}
```

# 不重复的随机数

```java
public static void main(String[] args) {
        Set<Integer> r = new HashSet<>();
        Random random = new Random();
        while(r.size()<10){
            int number = random.nextInt(20);
            r.add(number);
        }
        for(Integer i: r ){
            System.out.println(i);
        }
    }
```



# IO流

OutputStream继承自Object是表示字节输出流的所有类的超类

InputStream：表示字节输入流的所有类的超类

子类名特点：子类名都是以其父类名作为子类名的后缀

FileOutputStream：将数据写入File

构造方法：

FileOutputStream(File file)：创建文件输出流以写入由指定的File对象表示的文件

FIleOutputStream(FileDescriptor fdobj)：创建文件输出流以写入指定的文件描述符，表示与文件系统中实际文件的现有连接

FileOutputStream(File file,boolean append)：创建文件输出流以写入指定的FIle对象表示的文件

FileOutputStream(String name)：创建文件输出流以指定的名称写入文件

FileOutputStream(String name,boolean append)：创建文件输出流以指定的名称写入文件



![image-20211122111437990](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211122111437990.png)

```java
public static void main(String[] args)throws IOException{
//创建字节输出流对象
// FileOutputStream(String name):创建文件输出流以指定的名称写入文件
FileOutputStream fos = new FileOutputStream("文件名");
/* 
做了三件事情：
  1. 调用系统功能创建了文件
  2. 创建了字节输出流对象
  3. 让字节输出流对象指向创建好的文件
 */
 //void write (int b) : 将指定的字节写入此文件输出流
 fos.write(97); //写入 a 
 fos.write(57); // 写入 9
 fos.write(55); //写入 7
 // 最后都要释放资源
 // void close() : 关闭此文件输出流并释放与此流相关联的任何系统资源。
 fos.close();
}
```

使用字节输出流写数据的步骤：

1. 创建字节输出流对象（调用系统功能创建文件，创建字节输出流对象，让字节输出流对象指向文件）
2. 调用字节输出流对象的写数据方法
3. 释放资源（关闭此文件输出流并释放与此流相关联的任何系统资源）

## 字节流写数据的3种方式：

void write(int b) : 将指定字节写入此文件输出流，一次写一个字节数据

void write(byte[] b) : 将b.length字节从指定的字节数组写入此文件输出流，一次写一个字节数组数据

void write(byte[] b, int off,int len) : 将len字节从指定的字节数组开始，从偏移量off开始写入此文件输出流，一次写一个字节数组的部分数据

```java
public static void main(String[] args){
FileOutputStream fos = new FileOutputStream("实验室成员管理系统");
//FileOutputStream fos = new FileOutputStream(new FIle("实验室成员管理系统"));
}
fos.write(97);
fos.write(98);
byte[] bys = {97,98,99,100};
fos.write(bys);
//byte[] getBytes():返回字符串对对应的字节数组
"abcde".getBytes();
fos.write(bys); 

//追加写入：
//FileOutputStream fos = new FileOutputStream("实验室成员管理系统",true);
//第二个参数为true，则字节写入文件的末尾，而不是开头

```

字节流写数据加异常处理：

```java
public static void main(String[] args){
try{
FileOutputStream fos = new FileOutputStream("实验室成员管理系统",true);
fos.write("hello".getBytes());
fos.close();
}catch(IOException e){
e.printStackTrace();
}
}
```

finally: 在异常处理时提供finally块来执行所有清除操作，比如IO流中的释放资源特点：呗finally控制的语句一定会执行，出发java虚拟机退出。

![image-20211122205952553](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211122205952553.png)

```java
public static void main(String[] args){
FileOutputStream fos = null;
try{
fos = new FileOutputStream("实验室成员管理系统");
fos.write("hello".getBytes());
}catch(IOException e){
e.printStackTrace();
}finally{
    if(fos != null){
        try{
            fos.close();
        }catch(IOException e){
            e.printStackTrace();
        }
    }
}
}
```

# 字节流读数据

FileInputStream:从文件系统中的文件获取输入字节

![](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211123162650673.png)

  FileInputStream : 从文件系统中的文件获取输入字节

+  FileInputStream(String name): 通过打开与实际文件的连接来创建一个FileInputStream,该文件由文件系统的路径名name命名

使用字节输入流对象的读数据方法

1. 创建字节输入流对象
2. 调节字节输入流对象的读数据方法
3. 释放资源

```java
public static void main(String[] args){
FileInputStream fis = new FileInputStream("实验室成员管理系统");
//调用字节输入流对象的读数据方法
//int read();从该输入流读取一个字节的数据
/*
//第一次读取数据
int by = fis.read();
System.out.println(by);
System.out.println((char)by);
//第二次读取数据
by = fis.read();
System.out.println((char)by);
*/
//循环读取：
int by = fis.read();
while(by != -1){
System.out.print((char)by);
    by = fis.read();
}
//释放资源
fis.close();
}
```

```java
//优化上面的程序
int by;
while((by = fis.read()!=-1)){
System.out.print((char)by);
}
```

# 将文本文件中的数据读取到集合

1. 创建字符缓冲输入流对象
2. 创建ArrayList集合对象
3. 调用字符缓冲输入流对象的方法读数据
4.  把读取到的字符串数据存储到集合中
5. 释放资源

```java
 public static void main(String[] args){
     //创建字符缓冲流对象
     BufferedReader br = new BufferedReader(new FileReader("实验室成员管理系统"));
     //创建ArrayList集合对象
      ArrayList<String> array = new ArrayList<String>();              
     while((line = br.readLine())! = null){
         //把读取到的字符串存储到集合中
         array.add(line);
     }
     br.close();
     for(String s : array){
         System.out.println(s);
     }
 }
```

# 泛型

定义格式：

+ <类型>：指定一种类型的格式，这里的类型可以看成是形参
+ <类型1,类型2...>：指定多种类型的格式，多种类型之间用逗号隔开。这里的类型可以看成是形参·1
+ 将来具体调用时候给定的类型可以看成是形参，并且形参的类型只能是引用数据类型

```java
public static void main(String[] args){
 Collection<> c = new ArrayList<String>();
 c.add("hello");
 c.add("world");
 c.add(100);
 Iterator it = c.iterator();
 while(it.hasNext()){
 //Object obj = it.next();
 //System.out.println(obj);
 //String s = (String)it.next();
 String s = it.next();
 System.out.println(s);
 }
}
```

好处：

1. 把运行时期的问题提前到了编译期间
2. 避免了强制类型转换 

## 泛型类

+ 格式：修饰符 class 类名<类型>{ }

+ 范例：public class Generic<T>{ }

  此处 T 可以随便写为任意标识，常见的如T、E、K、V等形式的参数常用于表示泛型

方法定义格式：

+ 格式：修饰符<类型>返回值类型 方法名（类型，变量名）{ }
+ 范例：public <T> void show(T t){ }

泛型接口：

+ 格式：修饰符 interface 接口名<类型>{ }
+ 范例：public interface Generic <T> { }

类型通配符：

为了表示各种泛型List的父类，可以使用类型通配符

+ 类型通配符：<?>
+ List<?>：表示元素类型未知的List，它的元素可以匹配任何的类型
+ 这种带通配符的List仅表示它是各种泛型List的父类，只希望它代表某一类泛型List的父类，并不能把元素添加到其中

如果我们不希望List<?>是任何泛型List的父类，只希望它代表某一类泛型List的父类，可以使用类型通配符的上限

类型通配符的上限：<?extends类型>

List<?extends Number>：它表示的类型是Number或者其子类型

下限：<?super类型>

List<? super Number>：它表示的类型是Number或其父类

![image-20211129143055303](C:\Users\zhou0212\AppData\Roaming\Typora\typora-user-images\image-20211129143055303.png)
