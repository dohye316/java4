# java4
面向对象初级
面向对象
 类与对象
看一个养猫猫问题
张老太养了两只猫：一只名字叫小白，今年3岁，白色。还有一只叫小花，今年100岁，花色，请编写一个程序， 当用户输入小猫的名字时，就显示该猫的名字，年龄，颜色。 如果用户输入的小猫名错误，则显示 张老太没有这只毛猫猫。

public static void main(String[] args) {
		/*看一个养猫猫问题
张老太养了两只猫：一只名字叫小白，今年3岁，白色。还有一只叫小花，今年100岁，花色，请编写一个程序， 
当用户输入小猫的名字时，就显示该猫的名字，年龄，颜色。 如果用户输入的小猫名错误
，则显示 张老太没有这只毛猫猫。
*/
//单独变量来解决 =》 不利于数据的管理（你把一只猫的信息拆解）
//第一只猫：
              String cat1Name = "小白";
              int cat1Age = 3;
              String cat1color = "白色";
//第二只猫：
              String cat2Name = "小花"；


              int cat2Age = 100;

              String cat2color = "花色";

              //用数组====>数据类型体现不出来/只能通过【下标】获取信息/造成变量名字和内容
              //对应关系不明确/不能说明猫的行为

             //所以要引出类与对象，java设计者引入类与对象OOP，根本原因就是现有的技术，不能完美的解决新的需求

	           //类与对象的关系示意图
 //猫类：就是数据类型         对应猫对象}
}                    //把所有猫的特性（属性）提取出来=》 
 //猫类（CAt）-自定义数据类型 name,age,color,run cry eat...=>猫对象（具体一只猫）波斯猫，黑猫，白猫{  对象（实例）对象2（实例）。。。。}
 //而int float 等是java提供的基本数据类型
//从猫类到对象，目前的说法:1.创建一个对象，2.实例化一个对象3.把类实例化...以后大家听到这些说法不要迷糊
//上面的猫也可以是鱼，狗，人...java最大特点就是面向对象根据需求创建一个类及它的对象们。


//使用面向对象来解决养猫问题
		//定义一个猫类 Cat => 自定义的数据类型
		

//使用oop面向对象解决
//实例化一只猫【创建一只猫对象】
//老韩解读
//1.new Cat() 创建一只猫
//2.Cat cat1 = new Cat(); 把创建的猫赋给 cat1
  //3.cat1就是一个对象
  Cat cat1 = new Cat();
cat1.name = "小白"; 
cat1.age = 3;
cat1.color = "白色";
//创建了第二只猫，并赋给 cat2
//cat2 也是一个对象
Cat cat2 = new Cat();
cat2.name = "小花";
cat2.age = 100;
cat2.color = "花色";
//怎么访问对象的属性呢
System.out.println("第一只猫的信息" + cat1.name +
					 " " + cat1.age + " " + cat1.color);	
System.out.println("第一只猫的信息" + cat2.name +
					 " " + cat2.age + " " + cat2.color);

}
}

class Cat{
//属性
String name;
int age;
String color;//可以用类来管理 Cat了

			

		}
类和对象的区别和联系
通过上面的案例和讲解我们可以看出：
1）类是抽象的，概念的，代表一类事物，比如人类，猫类...即它是数据类型。
2）对象是具体的，实际的，代表一个具体事物，即是实例
3）类是对象的模板，对象是类的一个个体，对应一个实例


类与对象
基本介绍：
1，从概念或叫法上看：成员变量 = 属性 = field *（即 成员变量是用来表示属性的， 授课中， 统一叫属性）
2.属性是类的一个组成部分，一般是基本数据类型， 也可是引用类型（对象，数组）。


class Method01{
//main
     public static void main(String[] args) {
     	//方法使用
     	//方法写好后，如果不去调用，不会输出
     	//创建一个对象，然后调用方法即可
     	Person p1 = new Person();
        p1.speak();;//调用方法
     	p1.cal01();//调用cal01方法
     	p1.cal02(5);//调用cal02方法，调用方法即可 n= 5
        p1.cal02(10);
        p1.getSum(10,20);//同时给num1=10，num2=20;
        //把 方法 getSum 返回的值， 赋给 变量 returnRes
        int returnRes = p1.getSum(10,20);
        System.out.println("getSum方法返回的值=" + returnRes);
     		
     	}	
}
class Person{
	   String name;
	   int age;
	   // 1.方法（成员方法）
	   //2.添加speak 成员方法， 输出“我是一个好人”
       //public 表示方法时分开
	   //void ： 表示方法没有返回值
	   //3.speak():speak是方法名，（）形参列表
	   //4.{}方法体，可以写我么要执行的代码
	   //5.System.out.pritnln("我是一个好人")表示我们的方法就是输出一句话
       public void speak(){
       	System.out.println("我是一个好人");

       }
       //添加cal01 成员方法， 可以计算从1+..1000的结果
       public void cal01(){
       	int res = 0;
       	for (int i = 1;i<=1000 ;i++ ) {
       		res += i;
       		
       	}
       	System.out.println("计算结果=" + res);
       }
       //添加cal02，成员方法，该方法可以接收一个数n，计算从1+...+n的结果
       //老韩解读
       //1.(int n)形参列表，表示当前有一个形参 n， 可以接收用户输入
       public void cal02(int n){//用n来控制1到哪个数叠加
       	int res = 0;
       	for (int i = 1;i<=n ;i++ ) {
       		res += i;
       		
       }}
       //添加getSum成员方法，可以计算两个数的和
       //1.pubkic 表示方法时公开的
       //2.int ：表示方法执行后，返回一个int 值
       //3.getSum 方法名
       //4.(int num1, int num2) 形参列表，2个形参，可以接收用户传入的两个数
       public int getSum(int num1, int num2){
              int res = num1 + num2;
              return res;
       }
}








比如我们前面定义猫类的int age 就是属性）

用引用类型String设置属性


class Car{
	 String name;//属性， 成员变量，字段 field
	 double price;
	 String color;
	 String[] master;//属性可以使基本数据类型，也可以是引用类型（对象、数组）
}
注意事项和细节说明
1）属性的定义语法同变量， 实例：访问修饰符 属性类型 属性名；这里老师简单的介绍访问修饰符：控制属性的访问范围
有四种 访问修饰符 Public，proctected，默认， private，后面详细介绍
2）属性的定义类型可以为任意类型，包含基本类型或引用类型。
2）属性如果不赋值， 有默认值，规则和数组一致。		

属性properties
public static void main(String[] args) {
		//创建person对象
		Person p1 = new Person();
        System.out.println("\n当前这个人的信息");
        System.out.println("age=" + p1.age + "name=" +
        	  p1.name + " sal=" + p1.sal + "isPass=" + p1.isPass);
	}
}
class Person{//对象的引用
	//四个属性
	int age = 18;
	String name = "zdx";
	double sal = 5000000;
	boolean isPass = true;}



如何创建对象
1.先声明再创建
Cat cat; //声明对象cat
cat = new Cat（）；//创建
2.直接创建
Cat cat = new Cat();


如何访问属性
基本语法
对象名.属性名；
案例演示赋值和输出
cat.name;
cat.age;
cat.color;

类与对象
类和对象的内存分配机制
java内存的结构分析
1.栈：一般存放基本数据类型（局部变量）
2.堆：存放对象（Cat cat,数组等）
3.方法区：常量池（常量，比如字符串），类加载信息
4.示意图 【Cat（name、age、price）】
java创建对象的流程简答分析
Person p = new Person();
p.name = "jack";
p.age = 10
1.先加载Person类信息（属性和方法信息，只会加载依次）
2.在堆中分配空间，进行默认初始化（看规则）
3.把地址赋给p，p就指向对象
4.进行指定初始化，比如p. name ="jack"p.age = 10


成员方法
在某些情况下，我们更需要定义成员方法（简称方法）。比如人类：除了有一些属性外（年龄，姓名.）我们人类还有一些行为比如：可以说话，跑步...通过学习，还可以做算术题。这是就要用成员方法才能完成。 现在要求对Person类完善。
1）添加speak成员方法，输出，我是一只好人
2）添加cal01成员方法，可以计算从1+..+1000的结果
3）添加cal02成员方法，该方法可以接收一个数n，计算从1+..+n的结果
4）添加getSum成员方法，可以计算两个数的和
方法的调佣机制原理：

class Test{
	public static void main(String[] args) {
		int [][]map ={{0,0,1},{1,1,1},{1,1,3}};
		//使用方法完成输出
		MyTools myTool = new MyTools();
		myTool.printArr(map);

		//遍历map数组
		//传统的解决方法就是直接遍历
		// for (int i = 0;i < map.length ;i++ ) {
		// 	for(int j = 0;j < map[i].length ;j++ ) {
		//               System.out.print(map[i][j]+"\t");		
		// 	}
		// 	System.out.println(" ");
		// }

		// for (int i = 0;i < map.length ;i++ ) {
		// 	for(int j = 0;j < map[i].length ;j++ ) {
		//               System.out.print(map[i][j]+"\t");		
		// 	}
		// 	System.out.println(" ");
		// }
     myTool.printArr(map);
     myTool.printArr(map);
	}
}
class MyTools {
	public void printArr(int[][]map){
		//对传入的map数组进行遍历
		System.out.println("========");
		for (int i = 0;i < map.length ;i++ ) {
			for(int j = 0;j < map[i].length ;j++ ) {
		              System.out.print(map[i][j]+"\t");		
			}
			System.out.println(" ");
		}
     
	}
}
========
0       0       1
1       1       1
1       1       3
========
0       0       1
1       1       1
1       1       3
========
0       0       1
1       1       1
1       1       3





成员方法
成员方法定义
public（访问修饰符） 返回数据类型 方法名（形参列表）{//
           方法体语句；
           return 返回值；}

1.参数列表：表示成员方法输入 cal（int n），getSum（int num1,int num2）
2.数据类型（返回类型）：表示成员方法输出 void 表示没有返回值，  
什么时候哦用return如：//用了int
 public int getSum(int num1, int num2){
              int res = num1 + num2;
              return res;
       }

3.方法主体：表示为了实现某一功能代码块
4.return 语句不是必须的。如果有返回的数据类型如：
5.老汉提示：结合前面的提示意图，来理解

 









注意事项和使用细节
MethodDetail.java
访问修饰符（不写就是默认有）有四种：{public，protected，默认、private}（作用是控制 方法使用的范围）
可选，

返回类型
1.一个方法最多有一个返回值【思考，如何返回多个结果？】
2.返回类型可以为任意类型，包含基本类型或引用类型（数组，对象）
public class MethodDetail{
	public static void main(String[] args) {
		//1.一个方法最多有一个返回值

		AA a =new AA();
		int[]res = a.getSumAndSub(1,4);
		System.out.println("和=" + res[0]);
		System.out.println("差=" + res[1]);
	}
}
class AA{
	public int[] getSumAndSub(int n1,int n2){
		int[]res = new int[2];
		res[0] = n1 + n2;
		res[1] = n1 - n2;
		return res;
	}
}


3.如果方法要求有返回数据类型，则方法体中最后的执行语句必须为return值；而且要求返回值类型必须和return 的值类型一致或兼容、
public double f1(){
double d1 = 1.1 * 3;
return d1;//(也可以写1.1等数字，只要符合double类型就行)
	   //int d1 =100;
	   //return d1; 也是可以的兼容  但是double不能转换到int
	   //但是public int f1（）{  double d1 = 1.1; return d1; 是不可以的}	
	}
}

4.如果方法是void，则方法体中可以没有return语句，或者 只写 return；
public void f2（）{
    system.out,println("jdsfksl");
return;
方法名
遵循驼峰命名法，最好见名知义，表达出该功能的意思即可，比如 得到两个数的和getSum， 开发中按照规范



形参列表
1.一个方法可以有0个参数，也可以有多个参数，中间用逗号隔开， 比如getSUm（int n1,int n2）
2.参数类型可以为任意类型，包含基本类型或引用类型，比如 printArr（int[][]map）
3.调用代参数的方法时，一定对应这参数列表传入相同类型或兼容类型，的参数{getSum}
4.方法定义时的参数成为形式参数，简称形参；方法调用时的传入参数成为实际参数，简称实参，实参和形参的类型要一致或兼容，个数，顺序必须一致。演示：
a.getSumAndSub(100)。。个数不一致。。不能这样因为public int[] getSumAndSub(int n1,int n2){

方法体
里面写完成功能的具体的语句，可以为输入，输出，变量，运算，分支，循环，方法调用，但里面不能再定义方法！即：方法不能嵌套定义演示：

class AA{
	public void f5(){public double f1(){}//不允许


成员方法
注意事项和使用细节
方法调用说明
1.同一个类中的 方法调用：直接调用即可。比如print（参数）；案例：A类sayOk调用print（）
2.跨类中的方法A类调用B类方法：需要通过对象名调用。比如对象名。方法名（参数）；案例演示：
B类 sayHello调用print（）
3.特别说明一下：跨类的方法调用和方法的访问修饰符相关，先暂时这么提一下，后面我们讲到访问修饰符时，还要再细说。



public class MethodDetail02{
	public static void main(String[] args) {
		
           A a = new A();
           // a.sayOk();
           a.a();
	}
}
class A{
String name；
Int age；
	//同一个类中的方法调用：直接调用即可


    public void print(int n){
    	System.out.println("print（）方法被调用 n=" + n);

    }
    public void sayOk(){
    	print(10);
    	System.out.println("继续执行sayOk()");
    	A.sex = new A();
    	sex.print();
    }
    public void a(){
    	B b = new B();//B是类要new一个桥进行链接如b
    	b,hi();
    }
}
class B {
	public void hi(){
		System.out.println("B类中的hi()被执行")
	}
}


类定义的完整
class 类名{
    属性；
}
class 类名{
属性（成员变量）；
成员方法；
}

//编写类AA，有一个方法：判断一个数是奇数odd还是偶数，返回boolean

public class Method{
    public static void main(String[] args) {
                  AA a = new AA();
                 if (a.isodd(1)) {
                  	 System.out,println("奇数");
                  } else{
                  	System.out.println("偶数");
                  }
                 
    	//编写类AA，有一个方法：判断一个数是奇数odd还是偶数，返回boolean
    	//根据行、列、字符打印对应行数和列数的字符，比如：行:4，列:4，
    	//字符#，则打印相应的小姑
    	
    }
}
class AA{
	//思路
	//1.方法的返回类型 boolean
	//2.方法的名字  is odd
	//3.方法的形参  （int num）
	//4.方法体， 判断
	public boolean isodd(int n){
         
         // if (n % 2 == 0&&n != 0) {
         // return true;
         	
         // }else{
         //    return false;
         

          // returnn n % 2 == 0? true;false;
		return n%2 ==0;

	} 
}

//根据行、列、字符打印对应行数和列数的字符，比如：行:4，列:4，
public class MethodEx01{
    public static void main(String[] args) {
                  AA a = new AA();
            a.print(9,4,'9');
    	
    }
}
class AA{
	//思路
	//1.方法的返回类型 boolean
	//2.方法的名字  is odd
	//3.方法的形参  （int num）
	//4.方法体， 判断
	public boolean judge(int n){
   
         

          // returnn n % 2 == 0&&n != 0 ? true;false;
		return n%2 != 0 ;

	} 
        //根据行、列、字符打印 对应行数和列数的字符，
	   //比如：行：4，列：4，字符#，则打印相应的下效果
	   /* 
	       ####
	       ####
	       ####
	       ####
	       */

	    //思路
	       //1.方法的返回类型 void
	       //2.方法的名子print
	       //3.方法的形参（int row，int column，char c） 
	       //4.方法体，循环
	       public void print(int row, int column,char c){
	       	for (int i = 0;i <= row ; i++) {
	       		for (int j = 0;j <= column  ;j++ ) {
	                       System.out.print(c);       			
	       		}
	       		System.out.println(" ");
	       	}
	       }

}

成员方法传参机制
方法的传参机制对我们今后的编程非常重要，一定要搞得清清楚楚明明白白。我们通过案例来学习

class parameter{
	public static void main(String[] args) {
		int a =10;
		int b = 20;
		
		AA obj = new AA();
		obj.sawp(a,b);//
		System.out.println("a=" +a+"b="+b);a=10,b=20
	}
}
class AA{
	public void swap(int a,int b){
		System.out.println("\na\na=" + a + "\tb=" + b);a=10,b=20
	
		int temp = a;
		a = b;
		b = temp;
			System.out.println("\na\na=" + a + "\tb=" + b);a=20,b=10

	}
}基本数据类型，传递的是值（值拷贝），形参的任何改变不影响实参。


成员方法传参机制
应用数据类型的传参机制
B类中编写一个方法test100，可以接收一个数组，在方法中修改该数组，看看原来的数组是否变化？
B类中编写一个方法test200，可以接收一个Person（age，sal）对象，在方法中修改该对象属性，看看原来的对象是否变化？



class MethodParameter{
	public static void main(String[] args) {
           B b = new B();
           int[] arr = {1,2,3};
           b.test100(arr);
        System.out.println("main的 arr数组");

		for (int i =0; i < arr.length ;i++ ) {

				
			System.out.print(arr[i] + "\t");/arr:/200,2,3
			
		}
		System.out.println();
		
           
	}
}
class B{
	//B类型中编写一个方法test100，
	//可以接收一个数组，在方法中修改该数组，看看原来的数组是否变化
	//
	public void test100(int[]arr){
		rar[0] = 200;
		//遍历数组
		System.out.println("test100的arr数组");
		for (int i =0; i < arr.length ;i++ ) {

				
			System.out.print(arr[i] + "\t");//200,2,3
			
		}
		System.out.println();
	}
}

引用类型传递的是地址，可以从形参影响结果 




class MethodParameter{
	public static void main(String[] args) {
		Pererson p = new Person();
        

        p.name = "jack";
        p.age = 10;
		b.test100(p);//传地址
           
	}
}
class Person{
	//B类型中编写一个方法test100，
	//可以接收一个数组，在方法中修改该数组，看看原来的数组是否变化
	//
	
    String name;
    int age;
class B{




	public void test100(person p){
		p = null;//我的指向是空,不会对main里的p值产生影响
		p = new Person();//新对象导致原先p覆盖掉
		p,name ="tom";
		p.age = 99;//也不会对main里的p值产生影响
	}
}

成员方法传参机制
成员方法返回类型是引用类型应用视力
编写类MyTools类，编写一个方法可以打印二维数组的数据
编写一个方法copyPerson，可以赋值一个Person对象，返回赋值的对象。 克隆对象，注意要求得到新对象和原来的对象是两个独立的对象，只是他们的属性相同
class MethodParameter{
	public static void main(String[] args) {
		//编写一个方法copyPerson，可以赋值一个Person对象，返回赋值的对象。 
		// 克隆对象，注意要求得到新对象和原来的对象是两个独立的对象，
		// 只是他们的属性相同

          Person  p  = new Person();
          p.name ="milan";
          p.age = 100;
          Mytools tools = new Mytools();
          Person p2 = tools.copyPerson(p);
//p和p2都是独立的对象，都是Person的对象，但是两个独立的对象，属性相同。
          System.out.println("p的属性 age =" + p.age + " 名字=" + p.name);
          System.out.println("p2的属性 age =" + p2.age + " 名字=" + p2.name);
          //这里老师提示：可以通过对象比较看看是否为同一个对象
          System.out.println( p == p2);


           
	}
}
class Person{

	
    String name;
    int age;}
class Mytools{
	//方法的返回类型 Person
	//方法的名字 copyPerson
	//方法的形参（Person p）
	//方法体，创建一个新对象，并赋值属性，返回即可
	public Person copyPerson(Person p){//Person Mytools等自定义类型是引用类型、

  克隆p2   Person p2 = new Person();会被main覆盖
		p2.name = p.name;//
		p2.age = p.age;
		return p2;
	}

}
