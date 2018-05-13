---
title: 二叉查找算法
date: 2018-05-13 20:30:01
categories:
- Coding
tags:
 - Algorithm
---

二分查找又称折半查找，优点是比较次数少，查找速度快，平均性能好，占用系统内存较少；但要求待查表为有序表，且插入删除困难。因此，折半查找方法适用于不经常变动而查找频繁的有序列表。

#### 非递归二叉查找实现
```c++
int BinarySearch(int *array, int aSize, int key)  
{  
    if ( array == NULL || aSize == 0 )  
        return -1;  
    int low = 0;  
    int high = aSize - 1;  
    int mid = 0;  
  
    while ( low <= high )//小于等于 
    {  
        mid = (low + high )/2;  
          
        if ( array[mid] < key)  
            low = mid + 1;  
        else if ( array[mid] > key )     
            high = mid - 1;  
        else  
            return mid;  
    }  
    return -1;  
} 
```

#### 递归二叉查找实现
```c++
int BinarySearchRecursive(int *array, int low, int high, int key)  
{  
    if ( low > high )  
        return -1;  
    int mid = ( low + high )/2;  
      
    if ( array[mid] == key )  
        return mid;  
    else if ( array[mid] < key )  
        return BinarySearchRecursive(array, mid+1, high, key);  
    else  
        return BinarySearchRecursive(array, low, mid-1, key);  
} 
```
