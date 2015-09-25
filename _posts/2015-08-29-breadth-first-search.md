---
layout: post
author: chenDoInG
title: "Breadth First Search"
description: ""
category: Algorithms
tags: [Algorithms]
---
# 广度优先搜索算法（Breadth-First-Search）

 又译作宽度优先搜索，或横向优先搜索，简称BFS，是一种图形搜索算法。

## 原理：从初始访问结点出发，访问该结点的所有邻接结点，然后依次以初始结点的邻接结点为初始访问结点，继续计算邻接结点，直到所有结点都被访问。

![alt='bfs'](/public/img/bfs.png)

Tips：先计算结点1，发现结点1，有两个邻接结点2、3,然后计算结点2，找到2的邻接结点4、5，计算3的邻接结点6、7。我们发现最新找出的邻接结点总是先计算，而java的队列实现原理就是FIFO（先进先出），因此我们可以使用一个队列来保存统计的邻接结点。1先进队列，取出队列的头元素1计算出23，23进入队列，1已经计算结束出队列，继续取队列的头元素2，计算出45，45入队列……

#### 具体算法表现：

	1. 访问初始结点v，标记v为已访问
	2. v进入队列
	3. 当队列不为空时，继续执行，否则算法结束
	4. 出队列，取得队列头元素u
	5. 查找u的第一个邻接结点w
	6. 如果w不存在，则跳转到步骤3；否则循环执行以下两个步骤：
		a. 如果w未被访问，则标记w为已访问,w进入队列
		b. 查找u的下一个邻接结点w，转到步骤6
		
####具体用法：

	例一：统计网站的所有静态链接，从主页开始，计算主页里面的静态链接，打开第一个静态……
	例二：统计从某地方到某地方的最短路径，从地点a开始，计算a通向的所有地点b、c的距离……