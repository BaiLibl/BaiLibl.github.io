---
title: Bellman-Ford算法
date: 2018-04-15 21:20:30
categories:
- Coding
tags:
 - Algorithm
---

Dijkstra算法是处理单源最短路径的有效算法，但它局限于边的权值非负的情况，若图中出现权值为负的边，Dijkstra算法就会失效，求出的最短路径就可能是错的。而Bellman-Ford正是补充Dijkstra不足的算法之一，由美国数学家Richard Bellman（提出动态规划）和Lester Ford发明。

### 适用条件
1. 单源最短路径(从源点s到其它所有顶点v);
2. 有向图&无向图(无向图可以看作(u,v),(v,u)同属于边集E的有向图);
3. 边权可正可负(如有负权回路输出错误提示);

### Bellman-Ford算法步骤

给定图G(V,E)（其中V、E分别为图G的顶点集与边集），源点s，数组Dist[i]记录从源点s到顶点i的路径长度：
第一，初始化所有Dist数组。数组中每元素，表示从源点s到达这个点的距离，将源点s的值设为0，其它的点的值设为无穷大（表示不可达）。即是初始化Dist[n]为无穷大（如在c++里可设置为INT_MAX）, Dist[s]为0；
第二，循环处理，循环下标为从1到n－1（n等于图中点的个数）。在循环内部，遍历所有的边，进行松弛计算。对于每一条边e(u, v)，如果Dist[u] + w(u, v) < Dist[v]，则另Dist[v] = Dist[u]+w(u, v)。w(u, v)为边e(u,v)的权值；

检验负环路：为了检测图中是否存在负环路，即权值之和小于0的环路。对于每一条边e(u, v)，如果存在Dist[u] + w(u, v) < Dist[v]的边，则图中存在负环路，即是说改图无法求出单源最短路径。否则数组Distant[n]中记录的就是源点s到各顶点的最短路径长度。
时间复杂度：Bellman-Ford算法寻找单源最短路径的时间复杂度为O(V*E).
### Bellman-Ford算法C++实现
```C++
/*
times是边信息，每个元素包括(u,v,w)
N是结点个数
K是源点
*/
int MostLongPath(vector<vector<int>>& times, int N, int K) {
    vector<int> res(N+1,INT_MAX); //假设每个点不可达
	res[0]=0;//0点不计算
	res[K]=0;
	int i,j;
	for(j=1;j<N;j++){ //最多重复N-1次 
		for(i=0;i<times.size();i++){
			vector<int> t=times[i];
			int u=t[0],v=t[1],w=t[2];
			if(res[u]!=INT_MAX&&res[u]+w<res[v]){
				res[v]=w+res[u];
			}
		} 	
	}	
	int s=0;
	for(i=1;i<=N;i++){
		if(res[i]==INT_MAX)return -1;
		s=max(s,res[i]);//求最长的路径 
	}
	return s;
    }
```
