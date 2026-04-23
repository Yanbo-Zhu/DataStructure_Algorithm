

from s  到 x 尽可能快 

![[04_Algorithm/image/Pasted image 20250704102053.png]]


- Dieser Ansatz funktioniert, ist aber sehr ineffizient.
- Also suchen wir uns eine Strategie, wie man zielgerichteter arbeiten kann.
	- Diese Strategie nennt man Heuristik


# 1 Heuristiken

Heuristiken sind problem-spezifische Informationen, die es erlauben eine Lösungssuche für eine bestimmte Problemklasse zielgerichteter durchzuführen
z.B. Luftlinien-Distanz zum Zielort



Manhatten Distanz 
addiert die Distanz zwischen den x-Koordinaten und den y-Koordinaten
![[04_Algorithm/image/Pasted image 20250704102349.png]]



Euklidsiche Distanz 
Berechnet die Hypotenuse der Strecke (=die Luftlinie) 
![[04_Algorithm/image/Pasted image 20250704102501.png]]


# 2 Heuristische algorithmus 

“Heuristischer Algorithmus”（中文：启发式算法）是一种在**解决问题时不追求最优解，而是追求可接受的、近似的、在合理时间内得到的解**的方法。

启发式算法 = 用“聪明的经验”来**快速**找到“够好”的解。

Heuristische Algorithmen sind Problemlösungsmethoden, die auf Erfahrungswissen, Intuition oder einfachen Faustregeln basieren, um in akzeptabler Zeit praktikable Lösungen für komplexe Probleme zu finden. Sie verzichten auf eine systematische Suche nach der optimalen Lösung und liefern stattdessen oft nur eine „gute“ oder brauchbare Lösung, insbesondere wenn exakte Algorithmen zu aufwendig oder nicht praktikabel sind. Typische Beispiele sind der Nearest-Neighbor-Ansatz, genetische Algorithmen oder Simulated Annealing. Heuristiken sind besonders nützlich, wenn vollständige Informationen fehlen oder das Problem zu groß für eine exakte Berechnung ist.
- Heuristiken bieten schnelle, oft gute Lösungen ohne Garantie.



- Nutzen eine Heuristik (also problemspezifisches Wissen).
- Können keine optimale Lösung garantieren.
- Arbeiten in der Regel effizient (aber nicht immer)


|特性|描述|
|---|---|
|非精确（不保证最优解）|得到的是近似解，可能不是最好但“够用”|
|快速|相比穷举等算法，运行速度快|
|依赖经验或规则|通常基于问题的结构或人类经验设计规则|
|用于复杂问题|多用于 NP-难 或 组合优化问题（如路径规划、调度等）|

- **旅行商问题（TSP）**：寻找最短路线访问一系列城市
    - 启发式解法如：最近邻算法（Nearest Neighbor）、贪心算法、模拟退火等
        
- **象棋AI中的走法决策**
    - 评估局面“好坏”而不是穷举所有可能，采用估值函数
        
- **搜索引擎中的网页排名**
    - 使用启发式规则估算哪些页面更相关


![[04_Algorithm/image/Pasted image 20250704102831.png]]



# 3 Heuristische algorithmus : A* alogrithmus (finden immer optimal loesung)

A* wird in zahlreichen Bereichen eingesetzt, in denen Pfadfindung oder optimale Entscheidungsfindung erforderlich ist:
- Videospiele: Für die Bewegung und Navigation von Nicht-Spieler-Charakteren (NPCs) in komplexen Umgebungen
- Robotik: Um Robotern eine effiziente Routenplanung und Hindernisumgehung zu ermöglichen
- Navigationssysteme: Für die Routenplanung in GPS- und Kartierungsanwendungen, um den kürzesten oder schnellsten Weg zu finden.
- Künstliche Intelligenz: In Bereichen wie natürlicher Sprachverarbeitung und maschinellem Lernen zur Optimierung bestimmter Entscheidungsprozesse


Wie funktioniert der A*-Algorithmus?
Der A*-Algorithmus findet den kürzesten Weg zwischen einem Startknoten und einem Zielknoten in einem Graphen, indem er sowohl die tatsächlichen Kosten bis zu einem Knoten als auch eine geschätzte Entfernung (Heuristik) zum Ziel berücksichtigt. Dadurch ist die Suche gezielter und effizienter als bei nichtinformierten Algorithmen wie Dijkstra. Da immer der Knoten mit den geringsten geschätzten Gesamtkosten erweitert wird, vermeidet A* unnötige Umwege und konzentriert die Suche auf das Ziel.


- Berechnet den kürzesten Pfad zwischen zwei Knoten in einem Graphen
- Idee: Wir haben eine Heuristik, welche die Distanz zum Ziel abschätzt.
- Verwendet zwei Kosten:
	- Vorwärtskosten: Abgeschätzt durch eine Heuristik `h(v),` beschreibt die Restdistanz zum Ziel
	- Rückwärtskosten: Schrittweise beim Programmablauf aktualisiert, beschreibt die Distanz dist(v) zum Start zu einem Knoten


A* Vorgehen
- Findet den Kürzesten Pfad von einem Startknoten zum Ziel
- Funktioniert gleich wie Dijsktra (mit einer Priority Queue)
- Wählt den nächsten Knoten mit der kleinsten Distanz f(v):  `f(v) = dist(v) + h(v)`
	- h(v)  ist Heuristik Wert : meine Schatzwert von diesen Knote bis Zilekonte 有可能不准 


A* Vorgehen (genauer)
1. Startknoten in die Priority-Queue einfügen
2. Wiederholen bis Priority-Queue leer oder Zielknoten gefunden:
	1. i. erstes Element aus der Queue nehmen
	2. ii. Element als besucht markieren
	3. iii. Distanz ( `dist(v) + h(v)` ) zu allen Nachbarn aktualisieren (wenn ein kürzester Weg zu den Knoten gefunden wurde)
	4. iv. die Nachbarn, die noch nicht in der PQ sind oder besucht wurden, hinzufügen.


---
https://kindly-surf-14f.notion.site/Tutorium-9-Heuristik-Approximierbarkeit-und-A-Algorithmus-22362e2f151b8049907be7925fcf9b8b

![[04_Algorithm/image/Pasted image 20250704171230.png]]




## 3.1 Dijkstra , Best-First, A* 比较 

![[04_Algorithm/image/Pasted image 20250704103217.png]]

Best-First: 
- immer das konte auswahlen, die mit kleinst heutistisch Wert 

A* algorithmus:
- f(v) =  dijkstra 的distance +  heutistisch Wert 
- h(u) =1   说明的是   从这u点到 zielort 的预测的距离, Restdistanz zum Zie. Eine Heuristik, welche die Distanz zum Ziel abschätzt

Dikstra algorithmus

## 3.2 h(w)=0
h(w)=0 说明: im Beispiel, das a* algorithmus verhaeltet wie gleich wie Dijkstra   

![[04_Algorithm/image/Pasted image 20250704103731.png]]


spt: shortest pass tree : die konten, die schon abgearbeitet ist 

pq : priority queue 


![[04_Algorithm/image/Pasted image 20250704104032.png]]


![[04_Algorithm/image/Pasted image 20250704104050.png]]



c 4 B : a -> b -> c 为 4 
![[04_Algorithm/image/Pasted image 20250704104207.png]]



![[04_Algorithm/image/Pasted image 20250704104257.png]]


![[04_Algorithm/image/Pasted image 20250704104336.png]]



![[04_Algorithm/image/Pasted image 20250704104435.png]]


## 3.3 h(w) 比较小

![[04_Algorithm/image/Pasted image 20250704104859.png]]



![[04_Algorithm/image/Pasted image 20250704105004.png]]


B <- A  5: 3+ 2    
C 7 a:   6 + 1 

==但是  spt 中的值 要将 h(v) 减去, 只登记实际的 distance==      5 - h(w) = 5 -3  =4 

![[04_Algorithm/image/Pasted image 20250704105140.png]]


---


![[04_Algorithm/image/Pasted image 20250704105352.png]]


将 d 5 a 搬到 spt,   5 -1  = 4   , 1 为 d 的 h(2), 登记 为  d 4 a 

![[04_Algorithm/image/Pasted image 20250704105511.png]]


---


![[04_Algorithm/image/Pasted image 20250704105532.png]]


---


![[04_Algorithm/image/Pasted image 20250704105600.png]]


![[04_Algorithm/image/Pasted image 20250704105616.png]]


![[04_Algorithm/image/Pasted image 20250704105649.png]]

Warum, nachdem man C 4 B in SRT eingeschrieben hat, hat man D nochmal nicht überprüft?
因为 d 4 a 已经登记了 , 不在 被砍了 


---

找到最终的最优路径 


![[04_Algorithm/image/Pasted image 20250704105932.png]]





## 3.4 h(w) 正好和 真实的 Restdistanz 相同  


![[04_Algorithm/image/Pasted image 20250704110235.png]]

这个图的特殊之处 
h(w) 的值, 都正好是 真实的 restdistance
optimale Heuristik , wert ist immer genau die reale distance  zu zielknote 


---

![[04_Algorithm/image/Pasted image 20250704110540.png]]



先选d, 因为 7 的 值最小 
![[04_Algorithm/image/Pasted image 20250704110612.png]]

---

![[04_Algorithm/image/Pasted image 20250704110658.png]]


![[04_Algorithm/image/Pasted image 20250704110725.png]]

![[04_Algorithm/image/Pasted image 20250704110745.png]]


![[04_Algorithm/image/Pasted image 20250704110823.png]]

## 3.5 h(w) 都ueberschatzt

每个 h(w) 都ueberschatzt , 值 都要大于 这个点 到 zielkonte 的实际距离 . 这种情况 实际找到的weg zu zielkonte ist nicht optimal heuristik 

optimal heuristik :  能到 kurest weg to final zielort 

![[04_Algorithm/image/Pasted image 20250704110859.png]]


---


![[04_Algorithm/image/Pasted image 20250704111120.png]]



![[04_Algorithm/image/Pasted image 20250704111641.png]]

## 3.6 h(w) 都 zu viel ueberschatzt

每个 h(w) 都 zu viel ueberschatzt , 值 都要远大于 这个点 到 zielkonte 的实际距离 . 这种情况 实际找到的weg zu zielkonte ist jedoch optimal heuristik , 因为 ubersahctezt wert ist jedoch 符合比例 的增加 相对于 实际情况 

当 heuristisck wert 都超级大,  kleine heuristisck wert 对应的 knote 都被选上   , 于等于 best first 

best first 是 heuristisck wert  最小得值对应的 konte 被选上,  一直按照这个标准选上 


---
Kann ich dann allgemein sagen, dass wenn ich den optimalen Weg mit A* finde und eine lineartransformation anweden auf die heuristic wieder der optimale weg gefunden wird?




![[04_Algorithm/image/Pasted image 20250704111615.png]]


![[04_Algorithm/image/Pasted image 20250704111705.png]]


![[04_Algorithm/image/Pasted image 20250704111759.png]]


---


![[04_Algorithm/image/Pasted image 20250704111816.png]]


![[04_Algorithm/image/Pasted image 20250704111848.png]]



# 4 konsistent Heutistik 

Eine konsistente Heuristik h(N) (auch monotone Heuristik genannt) ist eine Funtkion welche die Distanz zum Ziel abschätzt. Sie muss dabei sicherstellen, dass die Heuristik niemals mehr verkleinert oder vergrößert wird als die tatsächliche Distanz der Kante von einem beliebigen Knoten zum Ziel. Formal erfüllt sie für jeden Knoten N und jeden Nachfolger P die Dreiecksungleichung:




![[04_Algorithm/image/Pasted image 20250704112357.png]]


Eine Heuristik wird konsistent genannt, wenn
	i. (Heuristik bei Zielknoten = 0)
	ii. für alle Knoten und mit gilt.
Also die "Distanz" von Knoten aus, über einen Nachbarn sollte immer unterschätzt werden.


![[04_Algorithm/image/Pasted image 20250704112405.png]]


![[04_Algorithm/image/Pasted image 20250704112443.png]]

---

h(N)-h(P)≤c(N,P) wobei:
- h(N) die heuristische Schätzung vom Knoten N zum Ziel ist
- c(N,P) die tatsächlichen Kosten von N nach P sind,
- h(P) die heuristische Schätzung von P zum Ziel ist

Zusätzlich gilt h(G)=0 für den Zielknoten G.

==Eine konsistente Heuristik ist immer zulässig (sie überschätzt nie die tatsächlichen Kosten zum Ziel), aber nicht jede zulässige Heuristik ist konsistent.==

Flexibilität: Die Heuristikfunktionen des Algorithmus können an verschiedene Optimierungsprobleme und Umgebungen angepasst werden. Diese muss nur konsistent sein und ist umso besser umso näher die Abschätzung an die tatsächliche Distanz zum Ziel rankommt. (siehe [Video](https://www.youtube.com/watch?v=A60q6dcoCjw))






# 5 Approximative Algorithmen (finden suboptimal Losung)

很多组合优化问题（如旅行商问题、顶点覆盖问题、集合覆盖问题等）在理论上很难在合理时间内求出最优解。如果强行求解，会导致**指数级时间复杂度**，对实际应用来说不可行。

因此，我们引入近似算法，它们虽然**不保证最优解**，但：
- 能**快速运行**（通常为多项式时间）    
- 返回的解质量可以**有界地接近最优解**


![[04_Algorithm/image/Pasted image 20250704112629.png]]


- Begnügen sich mit einer suboptimalen Lösung
- Lösungsqualität garantiert mit dem Faktor
	- Also wir können eine Lösung finden, die -mal schlechter ist als die Optimale.
- Erreichen so eine schnellere Laufzeit.
- Können z. B. auch Heuristiken verwenden



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



## 5.1 Beispiel  Traval shortest path 


旅行商问题（TSP）——满足三角不等式的情况
> 寻找一条最短路径，遍历所有城市一次后返回起点。
- 使用 **最小生成树（MST）** 来近似，构造一个回路。
- 该算法是一个 **2-近似算法**（前提是满足三角不等式）。

![[04_Algorithm/image/Pasted image 20250704112815.png]]



对角线距离 immer kleiner als die uber nachbar weg 


设定: find ein Pfad der hoechstens doppel so viel Zeit braucht wird 

---

![[04_Algorithm/image/Pasted image 20250704113048.png]]


![[04_Algorithm/image/Pasted image 20250704113102.png]]


(20+30+12 ) / 35  是 < 2 

minimal spannbaum 最小二叉数 
 Das heißt wenn wir diesen minimalen Spannung gefunden habe,  dann wissen wir schon okay es gibt keine kleinere Menge an Kanten, die Alle Knoten zu besuchen

---

![[04_Algorithm/image/Pasted image 20250704113157.png]]

1. Wir finden einen MST (z.B. mit Prim oder Kruskal)
2. Wir gehen diesen Spannbaum mit DFS durch um die Reihenfolge der Knoten zu
finden
3. Dann verbinden wir den letzten Knoten mit dem ersten Knoten
Dieser Algorithmus ist eine -Approximation des TSP Problems
Also die Tour hat maximal die zweifache Länge einer optimalen Tour
Notiz: Das TSP ist NP-Schwer



## 5.2 Kategorien Approximativer Algorithmen

1. Nicht approximierbar: Keine Algorithmen für beliebige Gütegarantie
	1. Bsp.: nicht metrisches TSP (also ohne Dreiecksungleichung)
2. Begrenzt approximierbar: Approximation bis zu einem festen Faktor möglich
	1. Bsp.: metrisches TSP (also mit Dreiecksungleichung)
3. Beliebig gut approximierbar: Lösungen beliebig nahe an optimaler Lösung
	1. Bsp.: 0/1-Rucksack (durch Skalierung der Werte)


je näher dran ich an der optimalen Lösung sein. möchte desto länger braucht dann dieser algorithmus zu finden 
 
## 5.3 **Polynomial Time**（多项式时间

> 一个算法的运行时间随着输入规模 nnn 的增加，最多像 nkn^knk 这样增长（其中 kkk 是常数）。


![[04_Algorithm/image/Pasted image 20250703163815.png]]




用数学术语表示：

## 5.4 NP Nichtdeterministisch Polynomialzeit


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



# 6 Ubung 


![[04_Algorithm/image/Pasted image 20250704113956.png]]


![[04_Algorithm/image/Pasted image 20250704114054.png]]


---

选 f(v) = dist(v) + h(v)
![[04_Algorithm/image/Pasted image 20250704114210.png]]


----

rechts 


![[04_Algorithm/image/Pasted image 20250704114255.png]]



---


三个图中 1 个 是 Best-first , 1 是 dijkstra, 一个是 a*  algrotithmus


![[04_Algorithm/image/Pasted image 20250704114341.png]]




- 左边 是 best first 因为 只有 kleisnet 被看到 
	- 数值显示的是 距离 zielort 的剩余距离 
- mitte  是 a* algrotithmus
	- 数值显示的是 距离 zielort 的的总距离, 一开始就是 15 因为加上了 heuristische wert 的距离 
- rechte 是 Dijkstra  , 因为所有点都看了 
	- 数值显示的是 距离 zielort 的的总距离,  一开始是0 是因为 没有 heuristische wert 的距离 


![[04_Algorithm/image/Pasted image 20250704114350.png]]




