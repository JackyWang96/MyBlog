---
title: "Java Lesson2 Note"
date: 2023-03-31T02:27:00+11:00
draft: false
---

# Introduction
Today will introduce Java's arrays and their applied algorithms

今天将介绍Java的数组及其应用的算法




# Content
## 3. 数 组
数组(Array)，是多个相同类型数据按一定顺序排列的集合，
并使用一个名字命名，并通过编号的方式对这些数据进行统一管理。

数组里的相关概念
1. Array name
2. Elements
3. Index
4. length

### 3.1 一维数组的使用
用以下的方式熟悉一维数组

    一维数组的声明和初始化

    如何调用数组的指定位置的元素

    如何获取数组的长度

    如何遍历数组

    数组元素的默认初始化值


### 3.2 多维数组的使用
对于二维数组的理解，我们可以看成是一维数组array1 又作为另一个一维数组array2 的元素而存在。
其实，从数组底层的运行机制来看，其实没有多维数组。

        public class ArrayTest2 {
        public static void main(String[] args) {
            //1. 二维数组的声明和初始化
            int[] arr = new int[]{1,2,3};

            // 静态初始化
            int[][] arr1 = new int[][]{{1,2,3},{4,5,6},{7,8,9}};

            // 动态初始化1
            String[][] arr2 = new String[3][2];

            // 动态初始化2
            String[][] arr3 = new String[3][];

            // 错误的情况
            // String[][] arr4 = new String[][];
            // String[][] arr5 = new String[][4];
            // String[][] arr6 = new String[4][3]{{1,2,3},{4,5,6},{7,8,9}};

            // 正确的情况：
            int arr4[][] = new int[][]{{1,2,3},{4,5,12,6},{7,8,9}};
            int[] arr5[] = new int[][]{{1,2,3},{4,5,6},{7,8,9}};

            int[][] arr6 = {{1,2,3},{4,5,6},{7,8,9}};

            //2. 如何调用数组的指定位置的元素
            System.out.println(arr1[0][1]); //2
            System.out.println(arr2[1][1]); //null

            //4. 如何遍历二维数组
            for(int i = 0;i < arr4.length;i++){
            for(int j = 0;j < arr4[i].length;j++){
            System.out.print(arr4[i][ j] + " ");
            }
            System.out.println();
        }
        }


### 3.2 Arrays 工具类的使用
java.util.Arrays 类即为操作数组的工具类，包含了用来操作数组（比如排序和搜索）的各种方法。

    public class ArrayTest4 {
        public static void main(String[] args) {

            //1.boolean equals(int[] a,int[] b) 判断两个数组是否相等。
            int[] arr1 = new int[]{1,2,3,4};
            int[] arr2 = new int[]{1,2,9,3};
            boolean isEquals = Arrays.equals(arr1, arr2);
            System.out.println(isEquals);

            //2.String toString(int[] a) 输出数组信息。
            System.out.println(Arrays.toString(arr1));

            //3.void fill(int[] a,int val) 将指定值填充到数组之中。
            Arrays.fill(arr1, 10);
            System.out.println(Arrays.toString(arr1));

            //4.void sort(int[] a) 对数组进行排序。
            Arrays.sort(arr2);
            System.out.println(Arrays.toString(arr2));

            //5.int binarySearch(int[] a,int key) 对排序后的数组进行二分
            法检索指定的值。
            int[] arr3 = new int[]{43,32,76,92,-65,85,71,-42};
            int index = Arrays.binarySearch(arr3, 210);
            if(index >= 0){
                System.out.println(index);
            }else{
                System.err.println(" 未找到。");
            }
        }
}



### 3.3 数组使用中的常见异常

1. 数组角标越界的异常:ArrayIndexOutOfBoundsException

        for(int i = 0;i <= arr.length;i++){
        // System.out.println(arr[i]);
        // }

2. 空指针异常:NullPointerException

        String[] arr3 = new String[]{"AA","QQ","YY","XX","TT","KK"};
        // arr3[0] = null;
        // System.out.println(arr3[0].toString());


### 3.4 数组中涉及到的常见算法

    选择排序
    直接选择排序、堆排序
    交换排序
    冒泡排序、快速排序
    插入排序
    直接插入排序、折半插入排序、Shell 排序
    归并排序
    桶式排序
    基数排序