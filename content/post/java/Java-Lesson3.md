---
title: "Java Lesson3 Note"
date: 2023-04-01T01:03:20+11:00
draft: false
---

# Introduction
Today will introduce Java's OOP, inclue class, attribute, construtor, method

今天将介绍Java的面向对象学习的三条主线

# Content
## 4. 面向对象
1. Java 类及类的成员：
属性，方法，构造器，代码块，内部类。
2. 面向对象的三大特征：
封装性，继承性，多态性。
3. 其他关键字：this、super、static、final、
abstract、interface、package、import 等。


### 4.1 面向过程(POP) 与面向对象(OOP)
- 面向过程：

Procedure Oriented Programming
强调的是功能行为，以函数为最小单位，考虑怎么做。

- 面向对象：

Object Oriented Programming
强调具备了功能的对象，以类/ 对象为最小单位，考虑谁来做。


### 4.2 类和对象

类：对一类事物的描述，是抽象的，概念上的定义。
对象：是实际存在的该类事物的每个个体，
因而也称为实例（instance）。
> 面向对象程序设计的重点是类的设计。
1. 设计类，就是设计类的成员。
2. 属性 == 成员变量 == field == 域、字段
3. 方法 == 成员方法 == 函数 == method
4. 创建类的对象 == 类的实例化 == 实例化类

----------------------------------------------------------------------------
### 4.2.1 类的成员之一：属性

- 成员变量 VS 局部变量
1. **相同点**

① 定义变量的格式：数据类型 变量名 = 变量值；

② 先声明，后使用；

③ 变量都有其对应的作用域。

2. **不同点**

① 在类中声明的位置不同：

属性：直接定义在类的一对{} 内；

局部变量：声明在方法内、方法形参、代码块内、构造器内部的变量。


② 关于权限修饰符的不同：

属性：可以在声明属性是，指明其权限，使用权限修饰符。

常用的权限修饰符：private、public、缺省、protected

局部变量：不可以使用权限修饰符。


④ 在内存加载中的位置：

属性：加载到堆空间中（非static）；

局部变量：加载到栈空间中。

----------------------------------------------------------------------
### 4.2.2 类的成员之二：方法

方法：描述类应该具有的功能
比如：Math 类：sqrt() / random() / ...

Scanner 类：nextXxx() ...

Arrays 类：sort() / binarysearch() ...

tostring() / equals() / ...

1. 举例
        public void eat(){}
        public void sleep(int hour){}
        public String getName(){}
        public String getNation(String netion){}

2. 方法的声明：权限修饰符、返回值类型、方法名（形参列表）{
    
    方法体

}


        public class Person {
            String name;
            int age;
            boolean isMate;

            public void eat(){
                System.out.println("people eat food");
            }

            public void sleep(){
                System.out.println("people can sleep");
            }

            public void talk(String language){
                System.out.println("People can talk the:"+language);
            }

            public void printIfSex(boolean isMate){
                if(isMate==true){
                    System.out.println("My name is:" + name + "\nMy age is:" +age +"\n");
                }
            }
        }
-------------------------------------------------------------------
### 4.2.3 类的成员之三：构造器（构造方法、constructor）
    
- 构造器的作用:
1. 创建对象
2. 初始化对象的属性
二、说明
1. 如果没有显示的定义类的构造器的话，则系统默认
提供一个空参的构造器。
2. 定义构造器的格式:
权限修饰符 类名( 形参列表) { }
3. 一个类中定义的多个构造器，彼此构成重载。
4. 一旦显示的定义了类的构造器之后，系统不再提供
默认的空参构造器。
5. 一个类中，至少会有一个构造器。

        class Person{
        // 属性
        String name;
        int age;
        // 构造器
        public Person(){
        System.out.println("Person()......");
        }
        public Person(String n){
        name = n;
        }
        public Person(String n,int a){
        name = n;
        age = a;
        }
        // 方法
        public void eat(){
        System.out.println(" 人吃饭");
        }
        public void study(){
        System.out.println(" 人学习");
        }
        }

------------------------------------------------------------------
### 4.2.4 关键字：this

1. this 用来修饰、调用：属性、方法、构造器
2. this 修饰属性和方法:

this 理解为：当前对象, 或当前正在创建的对象。

在类的方法中，我们可以使用"this. 属性" 或"this. 方法" 的方式，调用当前对象属性或方法。

### 4.3 对象的创建和使用：内存解析
- 堆（Heap）：此内存区域的唯一目的就是存放对象实例
- 栈（Stack）：是指虚拟机栈。虚拟机栈用于存储局部变量等。局部变量表存放了编译期可知长度的各种基本数据类型（boolean、byte、char、short、int、float、long、double）、对象引用（reference 类型，它不等同于对象本身，是对象在堆内存的首地址）。方法执行完，自动释放
- 方法区（MethodArea）：用于存储已被虚拟机加载的类信息、常量、静态变量、即时编译器编译后的代码等数据。

