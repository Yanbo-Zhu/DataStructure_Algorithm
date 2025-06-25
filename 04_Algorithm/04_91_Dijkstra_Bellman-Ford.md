

Kantengewichtete Digraphen, Dijkstra, Bellman-Ford

wozu benoetiget Dijkstra Bellmann-Ford-Algorithmus
Finden kuerzester Pfade 

Auf welchen Graphen funktionieren diese Algotrithemen 
- Gerichtete Graph  
- keine negative zyklen  (negative, zyklen   gewichte always -, , 就是说更快 , 这样不好 , 找不到最快的距离了, )
	- **负权环（negative weight cycles）** 
	- 不同于 负权边（negative weights）


# 1 Dijkstra



Funktionsweise von Dijkastra 

![[04_Algorithm/image/Pasted image 20250625162058.png]]

## 1.1 Beispiel 

![[04_Algorithm/image/Pasted image 20250625221759.png]]

![[04_Algorithm/image/Pasted image 20250625221902.png]]


# 2 Bellmann-Ford 


![[04_Algorithm/image/Pasted image 20250625163729.png]]


假设图中有 `V` 个顶点，`E` 条边：

1. **初始化**：
    - 源点 `s` 到自己的距离为 `0`
    - 其他所有点的距离初始化为 `∞`
2. **重复 V-1 次**：
    - 对图中每一条边 `(u, v, w)`：
        - 如果 `dist[u] + w < dist[v]`，就更新 `dist[v] = dist[u] + w`
            
3. **检查负权环**（可选）：
    - 再对每一条边尝试一次，如果还能更新距离，说明有负权环。


Bellman-Ford 算法非常适合用在：
- 图中包含负权边的情况
- 需要检测负权环的场景
- 不要求极高效率时（图不是太大）

|优点|描述|
|---|---|
|支持负权边|Dijkstra 不支持这一点|
|可检测负权环|如果发现可以无限变短，说明图中有负权环|
|实现简单|核心逻辑只涉及边的松弛操作|

|缺点|描述|
|---|---|
|时间复杂度较高|O(V × E)，比 Dijkstra 慢|
|不适合稠密图|边太多会导致效率低下|

- 时间复杂度：`O(V × E)`
- 空间复杂度：`O(V)`


例子

边：        权重：
A → B       4  
A → C       2  
B → C      -3  
C → D       2  

| 顶点  | 初始距离 | 第1轮 | 第2轮 | 第3轮 |
| --- | ---- | --- | --- | --- |
| A   | 0    | 0   | 0   | 0   |
| B   | ∞    | 4   | 4   | 4   |
| C   | ∞    | 2   | 1   | 1   |
| D   | ∞    | ∞   | 3   | 3   |
|     |      |     |     |     |


## 2.1 Beispiel 

![[04_Algorithm/image/Pasted image 20250625221825.png]]

![[04_Algorithm/image/Pasted image 20250625221838.png]]


![[04_Algorithm/image/Pasted image 20250625221852.png]]

# 3 两种算法的比较 

|特性|Bellman-Ford|Dijkstra|
|---|---|---|
|支持负权边|✅ 是|❌ 否|
|检测负权环|✅ 是|❌ 否|
|效率|⛔ 较慢|✅ 更快（用优先队列）|
|实现复杂度|✅ 简单|稍复杂（需要堆）|













