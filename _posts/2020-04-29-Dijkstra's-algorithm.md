---
layout:     post
title:      Find Dijkstra's algorithm
subtitle:   Dijkstra's algorithm
date:       2020-04-29
author:     oscar
header-img: img/bg_Dijkstra.jpg
catalog: true
tags:
    - Dijkstra's algorithm
    - algorithm 
    - shortest path
    - study notes
---



> [Dijkstra's algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) is an algorithm which is used to find the shortest path.

# Dijkstra's algorithm method
## Step: 0 -- The prerequisite
 

 1. We need to have a map of nodes.
 2. We need to have a start node.
 3. The distance between each adjacent nodes should be known.

## Step: 1 -- Start

 - Set the start node to be the current node, which is the first visited
   node.
   
 - Introduce several concepts:
> The current node is a already-visited node, and will be the predecessor node for the next node. 
>
> The stored distance of each node is the shortest distance from the start node. We will use this later.
> 
> The start node is an exception: 
> The shortest distance is 0, but the stored distance is always infinite (∞). 

## Step: 2 -- Check neighbours
Go through all the **non-visited**  **neighbour nodes** of the current node, and calculate the distance ***D*** . 

***D*** **=** the distance between current node and predecessor node **+** the predecessor's shortest distance. 

(If one node can't be reached from the current node, then ***D***=∞ )

For each node i, if ***D*** is smaller than the previously stored distance of i, then update the stored distance by ***D***. Otherwise, keep the previous stored distance unchanged.

After checking all the neighbour nodes (all the non-visited nodes of the current node), select one **non-visited** node which has the **smallest** stored distance as the next current node.

## Step: 3 -- Loop
Return to step 2, unless the target node has been reached.

---

I prepare 2 examples here, a simple one and a more complex one.

## Example 1:
Find the shortest path from 1 to 5.
![example_1](https://i.loli.net/2020/04/30/HUD1s78WgMXVuOt.gif)

## Round 1:

>    Current node:  1.

 -Start from node 1, so we have 3 non-visited neighour nodes: 2 3 6, their distance D is: [7 9 14]. 
 
 -So now the **stored distance** is : 
 
 |NODE|node 1* |node 2|node 3|node 4|node 5|node 6|
|--|--|--|--|--|--|--|
|**DISTANCE**|0| 7 | 9 |∞|∞|14|
|**PATH**|--|through node 1| through node 1 |-|-|-|


 (the star mark : visited node)
 
 -The **smallest** non-visited node is 7, so **node 2** is the next node.
 -The shortest path to node 2: **1 --> 2**.
 

## Round 2:

  

>   Current node:  2.

   -Now we have 2 non-visited neighbour nodes: 3 4, and their distance D now is :[17 22].
   
   -The **stored distance** is:
   
|NODE|node 1* |node 2* |node 3|node 4|node 5|node 6|
|--|--|--|--|--|--|--|
|**DISTANCE**|0| 7 | 9 |22|∞|14|
|**PATH**|--|through node 1| through node 1 |through node 2|-|-|

 (the star mark : visited node)
 

 
   -The **smallest** non-visited node is 9,  so **node 3** is the next node.
   -The shortest path to node 3: **1 --> 3**. (Since the distace is 9).
   

## Round 3:

>    Current node:  3.

   -Now we have 2 non-visited neighbour nodes: 4 6, and their distance D now is :[20 11].
   
   -The **stored distance**  is: 
   
|NODE|node 1* |node 2* |node 3* |node 4|node 5|node 6|
|--|--|--|--|--|--|--|
|**DISTANCE**|0| 7 | 9 |20|∞|11|
|**PATH**|--|through node 1| through node 1 |through node 3|-|through node 3|

  (the star mark: visited node) 

 
   -The **smallest** non-visited node is 11, so **node 6** is the next node.
   -The shortest path to node 6: **1 --> 3 --> 6**.

## Round 4:

>    Current node:  6.

   -Now we **only have 1** non-visited neighbour: 5.  D is 20.

   
   -The **stored distance**  is: 
   
|NODE|node 1* |node 2* |node 3* |node 4|node 5|node 6* |
|--|--|--|--|--|--|--|
|**DISTANCE**|0| 7 | 9 |20|20|11|
|**PATH**|--|through node 1| through node 1 |through node 3|through node 6|through node 3|

  (the star mark: visited node) 


>    Since now we only have 2 nodes left, and their stored distances are equal, we can stop. They both have 20 as the shortest path. (If these two distances are not equal, we still need to go to the next round).

   -The shortest path to node 5: **1 --> 3 --> 6 --> 5**. 
   -Shortest distance is **20**.
  
---
  
## Example 2:
Find the shortest path from A to I.
![example2](https://i.loli.net/2020/04/30/usi2WDCGTexk9wg.jpg)

## Round 1:

>   Current node:  A.

  
  
  Stored distance: 
    
|NODE|node A*|node B|node C|node D|node E|node F|node G|node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**|0| 3 | ∞ |4|∞|∞|∞|∞|∞|
|**PATH**|--|through node A| - |through node A|-|-|-|-|-|

  (the star mark: visited node) 

The **smallest** non-visited node is **B**.
Node **B** is the next one.

So shortest Path to B:   **A --> B**.


## Round 2:

>   Current node:  B.

  
  Stored distance: 
    
|NODE|node A* |node B* |node C|node D|node E|node F|node G|node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**| 0|3 | 5 |4|∞|∞|∞|∞|∞|
|**PATH**|--|through node A| through node B |through node A|-|-|-|-|-|

  (the star mark: visited node) 
 
  The **smallest** non-visited node is **D**.
  Node **D** is the next one.
  
So shortest Path to D: **A --> D**. （Since the distance is 4）

## Round 3:

>   Current node:  D.
 
  
  Stored distance: 

|NODE|node A* |node B* |node C|node D* |node E|node F|node G|node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**| 0|3 | 5 |4|∞|8|∞|∞|∞|
|**PATH**|--|through node A| through node B |through node A|-|through node D|-|-|-|

  (the star mark: visited node) 
  
The **smallest** non-visited node is **C**.
Node **C** is the next one.

So shortest Path to C: **A --> B --> C**.

## Round 4:

>   Current node:  C.

  
  
  Stored distance: 

|NODE|node A* |node B* |node C* |node D* |node E|node F|node G|node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**| 0|3 | 5 |4|7|8|∞|∞|∞|
|**PATH**|--|through node A| through node B |through node A|through node C|through node D|-|-|-|

  (the star mark: visited node) 
  
The **smallest** non-visited node is **E**.
Node **E** is the next one.

So shortest Path to E: **A --> B --> C -->E**.




## Round 5:

>   Current node:  E.


  
  Stored distance: 

|NODE|node A* |node B* |node C* |node D* |node E* |node F|node G|node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**| 0|3 | 5 |4|7|8|9|∞|∞|
|**PATH**|--|through node A| through node B |through node A|through node C|through node D|through node E|-|-|

  (the star mark: visited node) 
  
The **smallest** non-visited node is **F**.
  Node **F** is the next one.
    

So shortest Path to G: **A --> D --> F**.

## Round 6:

>   Current node:  F.


  
  Stored distance: 

|NODE|node A* |node B* |node C* |node D* |node E* |node F* |node G|node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**| 0|3 | 5 |4|7|8|9|11|∞|
|**PATH**|--|through node A| through node B |through node A|through node C|through node D|through node E|through F|-|

  (the star mark: visited node) 
  
The **smallest** non-visited node is **G**.
  Node **G** is the next one.
    

So shortest Path to G: **A--> B --> C --> E --> G**.



## Round 7:

>   Current node:  G.

  
  Stored distance: 

|NODE|node A* |node B* |node C* |node D* |node E* |node F* |node G* |node H|node I| 
|--|--|--|--|--|--|--|--|--|--|
|**DISTANCE**| 0|3 | 5 |4|7|8|9|11|11|
|**PATH**|--|through node A| through node B |through node A|through node C|through node D|through node E|through node F|through node G|

  (the star mark: visited node) 
  

We get 2 equal distances again, stop.

So shortest Path to I: **A --> B --> C -->E --> G -->I**.
The distance is 11.
