---
title: 十大排序算法（1）
date: 2018-04-24 17:01:29
categories:
- Coding
tags:
 - Algorithm
---

### 排序算法分类
- 非线性时间比较类排序：通过比较来决定元素间的相对次序，由于其时间复杂度不能突破 $$O(NlogN)$$，因此称为非线性时间比较类排序。
- 线性时间非比较类排序：不通过比较来决定元素间的相对次序，它可以突破基于比较排序的时间下界，以线性时间运行，因此称为线性时间非比较类排序。

### 冒泡排序
##### 算法思想
冒泡排序是一种简单的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果它们的顺序错误就把它们交换过来，重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端。

##### 算法描述
1. 比较相邻的元素。如果第一个比第二个大，就交换它们两个；
2. 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对，这样在最后的元素应该会是最大的数；
3. 针对所有的元素重复以上的步骤，除了最后一个；
4. 重复步骤1~3，直到排序完成。

##### 算法实现

```c++
void swap(int& i,int& j){
	int tmp=i;
	i=j;
	j=tmp;
}
void bubble_sort(vector<int>& num){
	int n=num.size();
	int i,j;
	for(i=0;i<n-1;i++){
		for(j=i+1;j<n;j++){
			if(num[i]>num[j])swap(num[i],num[j]); 
		}
	}
} 
```

##### 算法分析
当数据基本有序时，排序效果最好$$O(N)$$。
当数组逆序时，排序效果最差 $$O(N^2)$$ 。
平均时间复杂度 $$O(N^2)$$。

### 选择排序
##### 算法思想
首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕。
##### 算法描述
n个记录的直接选择排序可经过n-1趟直接选择排序得到有序结果。
1. 初始状态：无序区为R[1..n]，有序区为空；
2. 第i趟排序(i=1,2,3…n-1)开始时，当前有序区和无序区分别为R[1..i-1]和R(i..n）。该趟排序从当前无序区中-选出关键字最小的记录R[k]，将它与无序区的第1个记录R交换，使R[1..i]和R[i+1..n)分别变为记录个数增加1个的新有序区和记录个数减少1个的新无序区；
3. n-1趟结束，数组有序化了。

##### 算法实现

```c++
void swap(int& i,int& j){
	int tmp=i;
	i=j;
	j=tmp;
}
void select_sort(vector<int>& num){
	int n=num.size();
	int i,j;
	int mi;//记录最小值的下标 
	for(i=0;i<n-1;i++){
		mi=i;
		for(j=i+1;j<n;j++){
			if(num[j]<num[mi])mi=j;
		}
		if(mi!=i)swap(num[mi],num[i]);
	}
}
```

##### 算法分析
算法表现很稳定，无论数据如何分布，时间复杂度都是 $$O(N^2)$$ 。如使用选择排序，数据规模越小越好。唯一的好处可能就是不占用额外的内存空间。

### 插入排序
##### 算法思想
通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。
##### 算法描述
一般来说，插入排序都采用in-place在数组上实现。具体算法描述如下：
1. 从第一个元素开始，该元素可以认为已经被排序；
2. 取出下一个元素，在已经排序的元素序列中从后向前扫描；
3. 如果该元素（已排序）大于新元素，将该元素移到下一位置；
4. 重复步骤3，直到找到已排序的元素小于或者等于新元素的位置；
5. 将新元素插入到该位置后；
6. 重复步骤2~5。

##### 算法实现
```c++
void Insert_sort(vector<int>& num){
	int n=num.size();
	int i,j;
	for(i=1;i<n;i++){
		int target=num[i];//暂存要求排序的对象 
		j=i;
		while(j>0&&target<num[j-1]){ //j>0
			num[j]=num[j-1];
			j--;
		}
		//找到合适插入的地方 
		num[j]=target;
	}
} 
```
##### 算法分析
插入排序在实现上，通常采用in-place排序（即只需用到O(1)的额外空间的排序），因而在从后向前扫描过程中，需要反复把已排序元素逐步向后挪位，为最新元素提供插入空间。
当数据有序时，算法表现最好。当数据逆序时，表现最差，复杂度为 $$O(N^2)$$。

### 希尔排序
上几个排序算法，排序一万个整数，还是3位数毫秒级别，刚跑了一下希尔，时间变成1位数量级。。。提升很明显。。。

##### 算法思想
1959年Shell发明，第一个突破 $$O(N^2)$$ 的排序算法，是简单插入排序的改进版。它与插入排序的不同之处在于，它会优先比较距离较远的元素，其实就是间隔的插入排序。
##### 算法描述
先将整个待排序的记录序列分割成为若干子序列分别进行直接插入排序：
1. 选择一个增量序列t1，t2，…，tk，其中ti>tj，tk=1；
2. 按增量序列个数k，对序列进行k趟排序；
3. 每趟排序，根据对应的增量ti，将待排序列分割成若干长度为m的子序列，分别对各子表进行直接插入排序。
4. 仅增量因子为1 时，整个序列作为一个表来处理，表长度即为整个序列的长度。

##### 算法实现
```c++
void shell_partition(vector<int>& num,int d){
	int n=num.size();
	int i,j;
	for(i=d;i<n;i++){
		j=i-d;
		int tmp=num[i];
		while(j>=0&&num[j]>tmp){
			num[j+d]=num[j];
			j=j-d;
		}
		if(j!=i-d)num[j+d]=tmp;//找到合适的位置插入 
								//若是就j<0跳出的，就应该查到j+d上 
	}
} 
void shell_sort(vector<int>& num){
	int n=num.size();
	int d=n/2;//间隔大小
	while(d){
		shell_partition(num,d);
		d=d/2;
	} 
}
```
##### 算法分析
希尔排序的核心在于间隔序列的设定。既可以提前设定好间隔序列，也可以动态的定义间隔序列,比如以2倍数序列。

### 归并排序
###### 算法思想
采用分治法（Divide and Conquer）的一个非常典型的应用。将已有序的子序列合并，得到完全有序的序列；即先使每个子序列有序，再使子序列段间有序。若将两个有序表合并成一个有序表，称为2-路归并。 
###### 算法描述
1. 把长度为n的输入序列分成两个长度为n/2的子序列；
2. 对这两个子序列分别采用归并排序；
3. 将两个排序好的子序列合并成一个最终的排序序列。

###### 算法实现
```c++
void Merge(vector<int>& num,int left,int mid,int right){
	vector<int> res;//作为排序结果的临时保存数组
	int n=num.size()-1;
	int i=left;
	int j=mid+1;
	while(i<=mid&&j<=right){
		if(num[i]<num[j]){
			res.push_back(num[i]);
			i++;
		}else{
			res.push_back(num[j]);
			j++;
		}
	} 
	while(i<=mid){
		res.push_back(num[i]);
		i++;
	}
	while(j<=right){
		res.push_back(num[j]);
		j++;
	}
	for(i=0;i<res.size();i++){
		num[i+left]=res[i];
	}
}
void merge_sort(vector<int>& num,int left,int right){
	if(left>=right)return;//递归结束条件
	int mid=left+(right-left)/2;
	merge_sort(num,left,mid);
	merge_sort(num,mid+1,right);
	Merge(num,left,mid,right); 
}

void MergeSort(vector<int>& num){
	merge_sort(num,0,num.size()-1);
}
```
###### 算法分析
归并排序是一种稳定的排序方法。和选择排序一样，归并排序的性能不受输入数据的影响，始终都是 $$O(nlogn)$$ 的时间复杂度。代价是需要额外的内存空间，以存储临时的排序结果。

### 快速排序
##### 算法思想
通过一趟排序将待排记录分隔成独立的两部分，其中一部分记录的关键字均比另一部分的关键字小，则可分别对这两部分记录继续进行排序，以达到整个序列有序。每一趟排序都能找到为基准位置的数找到正确位置。
##### 算法描述
快速排序使用分治法来把一个串（list）分为两个子串（sub-lists）：
1. 从数列中挑出一个元素，称为 “基准”（pivot）；
2. 重新排序数列，所有元素比基准值小的摆放在基准前面，所有元素比基准值大的摆在基准的后面（相同的数可以到任一边）。在这个分区退出之后，该基准就处于数列的中间位置。这个称为分区（partition）操作；
3. 递归地（recursive）把小于基准值元素的子数列和大于基准值元素的子数列排序。

##### 算法实现
```c++
int partition(vector<int>& num,int start,int end){
	//数组start-end，找到基数的正确位置
	int p=num[start];
	while(start<end){
		while(start<end&&num[end]>=p)end--;
		num[start]=num[end];//start位置的元素已经被保存
		while(start<end&&num[start]<=p)start++;
		num[end]=num[start]; 
	} 
	num[start]=p;
	return start;

}
void quickSort(vector<int>& num, int start, int end){
	if(start>=end)return;
	int p=partition(num,start,end);
	quickSort(num,start,p-1);//p之前的 
	quickSort(num,p+1,end);  //p之后的 
}
void quick_sort(vector<int>& num){
	quickSort(num,0,num.size()-1); 
}
```
##### 算法分析
当数据逆序时，效果最差，时间复杂度为$$O(N^2)$$，不过平均时间复杂度为 $$O(nlogn)$$。




