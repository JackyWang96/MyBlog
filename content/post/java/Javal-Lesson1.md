---
title: "Java Lesson1 Note"
date: 2023-03-30T00:19:17+11:00
draft: false
---

# Introduction
今天开始我将开始Java基础课程的教授。我会记录我每次备课的note并作为帖子发送至我的blog。



# Content
## 1. Java是什么样的语言
简单而言，使用JDK 的开发工具完成的java 程序，交给JRE 去运行

### - **面向对象:**

OOD（Object Oriented Programming）POP（Prodedure Oriented Programming）

面向对象好在哪：POP小公司人少，所有安排事情是-你去干啥，他去干啥

OOD: 大公司人多，分成多个部门，按职能分派任务




- **三大特性：封装、继承、多态:**

1. 封装
用一个method隐藏赋值的过程、把属性变为private。只有外界用method去调用
public, private, default

2. 继承
inheritance； Child and parent class

3. 多态
overload

### - **健壮性:**
吸收了C/C++ 语言的优点，但去掉了其影响程序健壮性的部分（如指针、
内存的申请与释放等），提供了一个相对安全的内存管理和访问机制。

### - **跨平台性:**
跨平台性：通过Java 语言编写的应用程序在不同的系统平台上都可以运行。“Write once , Run Anywhere”
原理：只要在需要运行java 应用程序的操作系统上，先安装一个Java 虚拟机
(JVM Java Virtual Machine) 即可。由JVM 来负责Java 程序在该系统中的运行。


Java 两种核心机制-Java VirtalMachine，Garbage Collection




## 2. 基本语法

### 2.1 Java 中的名称命名规范
Package name: ：多单词组成时所有字母都小写：xxxyyyzzz
Class、interface：所有单词的首字母大写：XxxYyyZzz
变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写：xxxYyyZzz
常量名：所有字母都大写。多单词时每个单词用下划线连接：XXX_YYY_ZZZ

### 2.2 基本数据类型
变量按照数据类型来分：
基本数据类型：

整型：byte \ short \ int \ long

浮点型：float \ double

字符型：char

布尔型：boolean

引用数据类型：

类：class

接口：interface

数组：array

### 2.3 字符串类型：String

String 类型变量的使用：
1. String 属于引用数据类型 。
2. 声明String 类型变量时，使用一对"" 。
3. String 可以和8 种基本数据类型变量做运算，
且运算只能是连接运算；+
4. 运算的结果任然是String 类型。

### 2.4 强制类型转换

自动类型转换的逆过程，将容量大的数据类型转换为容量小的数据类型。使用时要加上强制转换符：()，但可能造成**精度降低或溢出**, 格外要注意。
通常，字符串不能直接转换为基本类型，但通过基本类型对应的包装类则可以实现把字符串转换成基本类型。



如：String a = “43”; 

inti= Integer.parseInt(a);

boolean 类型不可以转换为其它的数据类型。

### 2.5 运算符
%  取余  7%5=2

++  a=2; b=a++;  a=2;b=3

扩展赋值运算符：+=, -=, *=, /=, %=

逻辑运算符

a||b  a&&b


### 2.6 顺序结构

    public class Test{
    int num1 = 12;
    int num2 = num1 + 2;
    }

    // 错误形式：
    public class Test{
    int num2 = num1 + 2;
    int num1 = 12;
    }


### 2.7 判断语句
#### 2.7.1、分支语句：if-else 结构
    if(X>=0){
        return result
    }
    else if(x<0>){
        return 1;
    }
    else{
        return 0;
        }


### 2.8. 循环结构
##### 2.8.1 for 循环

// 遍历100 以内的偶数, 获取所有偶数的和, 输出偶数的个数
    int sum=0;
    int count=0;
    for(int i=1; i<=100; i++){
        if(i%2==0){
            System.out.println(i);
            sum += i;
            count++
        }
    }
    System.out.println("100 以内的偶数的和：" + sum);
    System.out.println(" 个数为：" + count);



##### 2.8.2 while 循环
    class WhileTest{
    public static void main(String[] args){
    // 遍历100 以内的所有偶数
    int i = 1;
    while(i <= 100){
    if(i % 2 == 0){
    System.out.println(i);
    } i++;
    }
    }
    }

#### 2.8.3 do-while 循环
    int i = 0;

    do {
    System.out.println(i);
    i++;
    } while (i < 5);


### 2.9. break、continue 的使用

1. break 语句用于终止某个语句块的执行

        {
        ......
        break;
        ......
        }


2. continue 的使用
continue 语句：continue 只能使用在循环结构中。

continue 语句用于跳过其所在循环语句块的一次执行，继续下一次
循环。

3. return 

return：并非专门用于结束循环的，它的功能是结束一个方法。当一
个方法执行到一个return 语句时，这个方法将被结束。

与break 和continue 不同的是，return 直接结束整个方法，不管这个
return 处于多少层循环之内。





### 课后作业
目标

需求说明

基本金和收支明细的记录

模拟实现一个基于文本界面的《家庭记账软件》。

主要掌握以下知识点：
变量的定义，
基本数据类型的使用，
循环语句，
分支语句，
方法声明、调用和返回值的接收，
简单的屏幕输出格式控制
模拟实现基于文本界面的《家庭记账软件》。
该软件能够记录家庭收入、支出，并能够打印收支明细表。

项目采用分级菜单方式。主菜单如下：

------------- 家庭收支记账软件-------------
1. 收支明细
2. 登记收入
3. 登记支出
4. 退 出
请选择(1-4):