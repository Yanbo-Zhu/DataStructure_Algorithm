




![[04_Algorithm/image/Pasted image 20250703161707.png]]


# 1 Approximative Algorithmen 

很多组合优化问题（如旅行商问题、顶点覆盖问题、集合覆盖问题等）在理论上很难在合理时间内求出最优解。如果强行求解，会导致**指数级时间复杂度**，对实际应用来说不可行。

因此，我们引入近似算法，它们虽然**不保证最优解**，但：
- 能**快速运行**（通常为多项式时间）    
- 返回的解质量可以**有界地接近最优解**


sind spezielle Algorithmen zur Lösung von Optimierungsproblemen, bei denen exakte Lösungen zu aufwendig oder unmöglich zu berechnen sind. Sie liefern eine Lösung, die garantiert innerhalb eines bestimmten Faktors (dem Approximationsfaktor p) von der optimalen Lösung liegt. Zum Beispiel garantiert ein 2-approximativer Algorithmus, dass die gefundene Lösung höchstens doppelt so schlecht wie die optimale Lösung ist Optimierungsprobleme werden nach ihrer Approximierbarkeit in folgende drei Hauptkategorien eingeteilt:

1. beliebig gut approximierbare Probleme:
	1. Für diese Probleme existieren Algorithmen, die für jede gewünschte Genauigkeit (d.h. für jedes beliebig kleines $ρ > 1$) eine Lösung mit entsprechend kleiner Abweichung zur optimalen Lösung in
	2. polynomieller Zeit liefern können.
2. APX-Probleme:
	1. Für diese Probleme gibt es Approximationsalgorithmen mit einem festen Approximationsfaktor ρ > 1
	2. Die Lösung kann also nur bis zu einem bestimmten Grad an die optimale Lösung angenähert werden.
	3. Beispiele: Das Vertex-Cover-Problem
3. Nicht-approximierbare Probleme:
	1. Für diese Probleme existiert kein effizienter Algorithmus, der eine Lösung mit garantiertem Approximationsfaktor liefern kann.
	2. Beispiele: Einige spezielle Varianten des Clique-Problems oder des Subset-Sum-Problems


Approximationsalgorithmen bieten Lösungen mit garantierter Qualität und sind besonders für Optimierungsprobleme relevant


---


---

近似比 (Approximationsfaktor)
近似算法的质量通过**近似比（Approximationsfaktor）**来衡量：

- 对于一个**最小化问题**（如最小顶点覆盖）：
    
    近似比=近似解最优解≥1\text{近似比} = \frac{\text{近似解}}{\text{最优解}} \ge 1近似比=最优解近似解​≥1
- 对于一个**最大化问题**（如最大割问题）：
    
    近似比=最优解近似解≥1\text{近似比} = \frac{\text{最优解}}{\text{近似解}} \ge 1近似比=近似解最优解​≥1

![[04_Algorithm/image/Pasted image 20250703163252.png]]


---


顶点覆盖问题（Vertex Cover）

> 给定一个图，选出最少的点集合，使得图中每条边至少有一个端点被选中。
- 贪心算法的策略：每次选择当前连最多边的顶点。
- 可以证明这个贪心算法是一个 **2-近似算法**：返回的解最多是最优解的两倍大。


旅行商问题（TSP）——满足三角不等式的情况
> 寻找一条最短路径，遍历所有城市一次后返回起点。
- 使用 **最小生成树（MST）** 来近似，构造一个回路。
- 该算法是一个 **2-近似算法**（前提是满足三角不等式）。


常见的近似策略
- **Greedy（贪心）**：每次做局部最优选择
- **LP-Rounding**：先解线性规划的松弛，再四舍五入
- **Primal-Dual** 方法    
- **Local Search（局部搜索）**



| 特点     | 描述                        |
| ------ | ------------------------- |
| 输入     | NP-schwer 问题              |
| 输出     | 接近最优解                     |
| 运行时间   | 多项式时间                     |
| 优劣衡量标准 | 近似比（Approximationsfaktor） |
| 应用示例   | 顶点覆盖、集合覆盖、TSP、背包问题等       |




## 1.1 **Polynomial Time**（多项式时间

> 一个算法的运行时间随着输入规模 nnn 的增加，最多像 nkn^knk 这样增长（其中 kkk 是常数）。


![[04_Algorithm/image/Pasted image 20250703163815.png]]




用数学术语表示：
## 1.2 NP


很好的问题！在计算机科学中，**NP** 是一个非常重要的复杂度类，它是 “**Nichtdeterministisch Polynomialzeit**” 的缩写，德语的意思是“非确定性多项式时间”（英语：_nondeterministic polynomial time_）。



|术语|解释|
|---|---|
|**P**|所有能在多项式时间内解决的问题（即“求解也很快”）|
|**NP**|所有能在多项式时间内验证解的问题|
|**NP-schwer (NP-hard)**|比 NP 问题还要难的问题，**不要求验证也要快**|
|**NP-vollständig (NP-complete)**|最难的 NP 问题：如果你能快速解决一个 NP-complete 问题，就能快速解决所有 NP 问题（也就是 P = NP）|


一个问题属于 **NP 类**，当且仅当：

> ✅ **给定一个候选解，可以在多项式时间内验证它是否是一个正确解。**

也就是说，**检查答案是否正确很快，但找出这个答案可能很慢**。



例子 

问题：给定一个整数集合，是否存在一个子集，它们的和等于一个目标值 S？
这就是著名的 子集和问题（Subset Sum Problem）：
找到答案：可能很难（因为要尝试很多组合）
验证答案：你给我一个子集，我只要把它们加起来，看是不是 S，这很快
因此它是一个 NP 问题。


- 你在考试中拿到一个难题（比如数学证明），要自己解出来很难。
- 但如果老师给你一个完整的解答过程，你只需要几分钟就能检查每一步是否合理。
- 所以这个问题就属于 NP：验证容易，求解难。






# 2 Heuristische algorithmus 


