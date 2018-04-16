---
title: Topological sort
date: 2018-04-16 20:50:29
categories:
 - Coding
tags:
 - Algorithm
---
在图论中，拓扑排序（Topological Sorting）是一个有向无环图（DAG, Directed Acyclic Graph）的所有顶点的线性序列。

### 拓扑排序的条件
- 每个顶点出现且只出现一次。
- 若存在一条从顶点 A 到顶点 B 的路径，那么在序列中顶点 A 出现在顶点 B 的前面。
- 针对有向无环图，但是可以检测有环图

### 拓扑排序的应用
拓扑排序通常用来“排序”具有依赖关系的任务。
比如，如果用一个DAG图来表示一个工程，其中每个顶点表示工程中的一个任务，用有向边<A,B>
表示在做任务 B 之前必须先完成任务A。故在这个工程中，任意两个任务要么具有确定的先后关系，要么是没有关系，绝对不存在互相矛盾的关系（即环路）。

### 拓扑排序的流程
1. 从 DAG 图中选择一个 没有前驱（即入度为0）的顶点并输出。
2. 从图中删除该顶点和所有以它为起点的有向边。
3. 重复 1 和 2 直到当前的 DAG图为空或当前图中不存在无前驱的顶点为止。若是图不为空但是不存在无前驱的顶点则说明有向图中必然存在环。

通常，一个有向无环图可以有一个或多个拓扑排序序列。

### 拓扑排序的C++S实现
```c++
/*
输入：
numCourses:结点个数
prerequisites：边的关系
输出：
拓扑排序序列
*/
vector<int> findOrder(int numCourses, vector< pair<int, int> >& prerequisites){
	int i,j;
	if(numCourses==0)return vector<int>();
	vector<int> ind(numCourses,0);
	vector< vector<int> > graph(numCourses,vector<int>());
	for(i=0;i<prerequisites.size();i++){
		graph[prerequisites[i].first].push_back(prerequisites[i].second);
		ind[prerequisites[i].second]++;
	}
	queue<int> qu;
	vector<int> res;
	for(i=0;i<numCourses;i++){
		if(ind[i]==0)qu.push(i);
	}
	while(!qu.empty()){
		int cur=qu.front();
		qu.pop();
		res.push_back(cur);
		for(i=0;i<graph[cur].size();i++){
			ind[graph[cur][i]]--;
			if(ind[graph[cur][i]]==0)qu.push(graph[cur][i]);
		}
	}
	for(i=0;i<numCourses;i++){
		if(ind[i]!=0)return vector<int>();
	}
	//反转数组
    i=0;
	j=res.size()-1;
	while(i<j){
		int tmp=res[i];
		res[i]=res[j];
		res[j]=tmp;
		i++;
		j--;
	}
    return res;
}
```






