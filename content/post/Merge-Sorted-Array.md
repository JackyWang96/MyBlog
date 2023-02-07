---
title: "Merge Sorted Array"
date: 2023-01-17T18:15:48+11:00
draft: flase
---


### Introduction
This article is about how to use double pointers to solve problems such as merge array 

### Problem details
Leetcode 88. [Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/)
![Merge Sorted Array photo](https://raw.githubusercontent.com/JackyWang96/BlogSite/master/photos/Merge%20Sorted%20Array.png)

### Analysis and thought
Because it is a sorted array, add pointers at the end of nums1 and nums2 respectively. The values at the positions of the two pointers are compared each time. 
Copy the larger number to the last bit of nums1. After that, move the pointer. 
In this case, a third pointer is required at length of nums1. 
The role of the third pointer is to select where the larger number is placed

### Solution
```java
public class MergeSortedArray {
   public static void merge(int[]nums1, int m, int[]nums2, int n) {
       //有序数组条件下，设置3个指针，分别放在nums1，nums2和集合数组的末尾
       int i=m-1;
       int j=n-1;
       int point= nums1.length-1;

       //判断nums2是否遍历完成
       while(j>=0){
           //如果nums2中元素小于nums1中的，则把nums1里的元素放到point指向的位置
           //之后移动i和point指针
           if(i>=0 && nums1[i]>nums2[j]){
               nums1[point]=nums1[i];
               i--;
               point--;
           }
           //nums2的元素较大情况直接把nums2中最大元素放置到数组最右端。
           //移动j和point指针
           else{
               nums1[point]=nums2[j];
               point--;
               j--;
           }
       }
   }
```