
![](image/Pasted%20image%2020250619121637.png)

![](image/Pasted%20image%2020250619121612.png)



# 1 Spannbaum

- Teilgraph eines Graphen, der ein Baum ist und alle Knoten enthält
- Baum ist azyklisch und zusammenhängend
- Spannbaum? Nein, nicht zu- sammenhängend
	- Es kann also unter- schiedliche Spann- bäume für einen Graphen geben

![[04_Algorithm/image/Pasted image 20250625221254.png]]

# 2 Graph
Was ist eigentlich ein Graph?
• Tupel aus Knoten (Vertices, V) und Kanten (Edges, E)
• Speicherung der Knoten recht simpel:
	• V = {0,1,2,3}
• Wie speichert man Kanten?
	• Knotenpaare
	• Adjazenzmatrix:
	• Adjazenzlisten
	• Doppelt verkettete Pfeilliste
		• Wie Adjazenzliste, aber als Liste, statt als Array

![[04_Algorithm/image/Pasted image 20250625221411.png]]


# 3 Gewichtet Graph

![](image/Pasted%20image%2020250619121856.png)



![](image/Pasted%20image%2020250619121938.png)

# 4 Äquivalenzrelation

- Objekte stehen zueinander in Beziehung
- reflexiv: ein Objekt steht mit sich selbst in Beziehung
- symmetrisch: Wenn A mit B in Beziehung → auch B mit A
- transitiv: Wenn A mit B in Beziehung und B mit C → auch A mit C
- Äquivalenzrelation teilt Menge in disjunkte Äquivalenzklassen
	- ![[04_Algorithm/image/Pasted image 20250625221016.png]]
- Auf Graphen
	- ungerichtete Kante ist Äquivalenzrelation zwischen 2 Knoten
	- Äquivalenzklassen werden Zusammenhangskomponenten genannt

1 
Beispiel: Wir definieren eine Äquivalenzrelation über geometrische Formen: „Zwei geometrische Formen sind äquivalent, wenn sie sich maximal nur durch Drehung und Skalierung unterscheiden.“

![[04_Algorithm/image/Pasted image 20250625220957.png]]


# 5 Union Find 

Union Find: Datenstruktur, die Zusammenhangskomponenten speicher

![](image/Pasted%20image%2020250619122157.png)


![](image/Pasted%20image%2020250619122331.png)


0,1,5,2,3 是一个 komponent. 67 是一个 komponenten 

每一个 komponent 选一个 repreasentant wert, 可以是 6 或是7 ， 不一定是最小值 


---
## 5.1 Union Find API 

![](image/Pasted%20image%2020250619122627.png)


## 5.2 Union-Find Funktion 

![[04_Algorithm/image/Pasted image 20250625111711.png]]


![[04_Algorithm/image/Pasted image 20250625111744.png]]

Wie ist Representative identifiziert?: 
kleinste Element 





![[04_Algorithm/image/Pasted image 20250625111809.png]]









## 5.3 Union Find Simlution 

![](image/Pasted%20image%2020250619122715.png)

A klasse 的 Reprasentant 为 0 value 
B klasse 的 Reprasentant 为1  value 
C klasse 的 Reprasentant 为3   value 



![](image/Pasted%20image%2020250619122816.png)


![](image/Pasted%20image%2020250619122925.png)



## 5.4 Implementation von Union 

![](image/Pasted%20image%2020250619123109.png)


Fehler in code 
我们用 union(0,2) 在 `[0,0,2]`
然后 得到的结果 为 `[2,0,2 ]`, 是我们不想要的 。 我们想要的结果是 `[0,0,0]`

1 
![](image/Pasted%20image%2020250619123307.png)

2
![](image/Pasted%20image%2020250619123415.png)


3 
![](image/Pasted%20image%2020250619123434.png)


![](image/Pasted%20image%2020250619123458.png)



![](image/Pasted%20image%2020250619123553.png)


---

Richtige Implementation von Union 

![](image/Pasted%20image%2020250619123608.png)


# 6 Minimale Spinnbaum 

Spannbaum mit minimaler Summe der Kantengewichte

![[04_Algorithm/image/Pasted image 20250625104318.png]]


![[04_Algorithm/image/Pasted image 20250625104353.png]]


![](image/Pasted%20image%2020250619123844.png)


![](image/Pasted%20image%2020250619124030.png)

Keinen zyklus 


![](image/Pasted%20image%2020250619124105.png)



![](image/Pasted%20image%2020250619124135.png)

s schnitte 向外的的 最小的 kante 


## 6.1 Prim vs. Kruskal: Zusammenfassung

Prims Algorithmus
Bilde einen Baum ausgehend von einem Startknoten 𝑠. Füge iterativ eine der kreuzenden Kanten mit geringstem Gewicht hinzu.
从一个起始节点 𝑠 出发构建一棵树。
迭代地添加一条跨越边界的最小权重边。



Kruskals Algorithmus
Durchlaufe die Kanten nach aufsteigendem Gewicht. Füge eine Kante hinzu, wenn sie keinen Zyklus mit den bisher gewählten Kanten bildet.
按权重从小到大遍历所有边。
如果一条边与当前已选边不会形成环路，则将其加入生成树中。






## 6.2 Prim Algorithmuss 


![[04_Algorithm/image/Pasted image 20250625104433.png]]



![](image/Pasted%20image%2020250619124304.png)

![](image/Pasted%20image%2020250619124450.png)


### 6.2.1 Beispiel 
总是找 最小的 kante  向外拓展   ， ==不一定一定要从最终的找以下个。 所哟已经的连接过的点的 的kante 中找一个 最小的权重的kante 作为以下各 knoten==


prim 可以 
start punkte ganz links
![](image/Pasted%20image%2020250619134142.png)


![](image/Pasted%20image%2020250619134147.png)



---


![](image/Pasted%20image%2020250619124648.png)


![](image/Pasted%20image%2020250619124804.png)

![](image/Pasted%20image%2020250619124849.png)


![](image/Pasted%20image%2020250619124919.png)

![](image/Pasted%20image%2020250619124946.png)



![](image/Pasted%20image%2020250619125011.png)


alle konto 已经被找到， 结束搜索了 





### 6.2.2 Prims' Algorithmus Beispiel 


![[04_Algorithm/image/Pasted image 20250625104521.png]]


Um **Prim’s Algorithmus** auf den gegebenen gewichteten, ungerichteten Graphen anzuwenden, wählen wir einen Startknoten (z. B. **A**) und bauen schrittweise den **Minimalen Spannbaum (MST)** auf, indem wir **immer die günstigste Kante** (mit dem kleinsten Gewicht) zu einem noch nicht besuchten Knoten hinzufügen.



Prim’s Algorithmus Schritt für Schritt (Start bei **A**):

MST-Knoten: {A}

Mögliche Kanten: A—B(11)  
➡️ **Wähle A—B(11)**  
→ Neuer Knoten: B  
→ MST-Kanten: [A—B]



MST-Knoten: {A, B}

Mögliche Kanten:

- B—C(3)
    
- B—D(14)  
    ➡️ **Wähle B—C(3)**  
    → Neuer Knoten: C  
    → MST-Kanten: [A—B, B—C]
    



MST-Knoten: {A, B, C}

Mögliche Kanten:

- C—D(12)
    
- C—F(15)
    
- C—G(2)
    
- B—D(14)  
    ➡️ **Wähle C—G(2)**  
    → Neuer Knoten: G  
    → MST-Kanten: [A—B, B—C, C—G]
    



MST-Knoten: {A, B, C, G}

Mögliche Kanten:

- G—F(9)
    
- G—H(10)
    
- G—E(6)
    
- C—D(12)
    
- C—F(15)  
    ➡️ **Wähle G—E(6)**  
    → Neuer Knoten: E  
    → MST-Kanten: [A—B, B—C, C—G, G—E]
    



MST-Knoten: {A, B, C, G, E}

Mögliche Kanten:

- E—D(7)
    
- G—F(9)
    
- G—H(10)  
    ➡️ **Wähle E—D(7)**  
    → Neuer Knoten: D  
    → MST-Kanten: [A—B, B—C, C—G, G—E, E—D]
    



MST-Knoten: {A, B, C, G, E, D}

Mögliche Kanten:

- G—F(9)
    
- G—H(10)
    
- D—C(12)  
    ➡️ **Wähle G—F(9)**  
    → Neuer Knoten: F  
    → MST-Kanten: [A—B, B—C, C—G, G—E, E—D, G—F]
    




MST-Knoten: {A, B, C, G, E, D, F}

Mögliche Kanten:

- F—H(5)
    
- G—H(10)  
    ➡️ **Wähle F—H(5)**  
    → Neuer Knoten: H  
    → MST-Kanten: [A—B, B—C, C—G, G—E, E—D, G—F, F—H]


**Kanten im MST:**

- A—B (11)
    
- B—C (3)
    
- C—G (2)
    
- G—E (6)
    
- E—D (7)
    
- G—F (9)
    
- F—H (5)
    

**Gesamtkosten:**  
11 + 3 + 2 + 6 + 7 + 9 + 5 = **43**


![[04_Algorithm/image/Pasted image 20250625105400.png]]



### 6.2.3 Beispiel 3

![[04_Algorithm/image/Pasted image 20250625105640.png]]

![[04_Algorithm/image/Pasted image 20250625110211.png]]

Minimum Spanning Tree (MST)  

Key Notes:
The algorithm always selects the smallest edge that connects a node in the MST to a node outside it.

The MST is a subset of edges that connects all nodes with the minimal total weight and no cycles.

The total weight of the MST in this case is 34.

If the graph's edges were different from the assumed connections, the steps would adjust accordingly, but the methodology remains the same.

==wenn alle nachbaren schon besucht , dann algo Search fur den Konte beendet und suche xx beim andern Konto ==

![[04_Algorithm/image/Pasted image 20250625110550.png]]


![[04_Algorithm/image/Pasted image 20250625110704.png]]


## 6.3 Kruskal Algorithmus 


![[04_Algorithm/image/Pasted image 20250625112246.png]]

![[04_Algorithm/image/Pasted image 20250625112309.png]]



![](image/Pasted%20image%2020250619125142.png)


![](image/Pasted%20image%2020250619125218.png)


![](image/Pasted%20image%2020250619125304.png)


### 6.3.1 Beispiel 

![](image/Pasted%20image%2020250619125430.png)


1
![](image/Pasted%20image%2020250619125447.png)


1 最小，构建 f-g 的连接， 然后 f-g menage 的 reprenstative wert ist F 


2
![](image/Pasted%20image%2020250619125548.png)

![](image/Pasted%20image%2020250619125611.png)


3
falls es zwei kante mit 3 gibt ?   egal 随便先连接那两个 

![](image/Pasted%20image%2020250619125716.png)

4 
![](image/Pasted%20image%2020250619125749.png)


5 
![](image/Pasted%20image%2020250619125804.png)

现在又 3 个 kompnenten 

6 

![](image/Pasted%20image%2020250619125845.png)


![](image/Pasted%20image%2020250619125922.png)

### 6.3.2 Beispiel2 

![[04_Algorithm/image/Pasted image 20250625112512.png]]



![[04_Algorithm/image/Pasted image 20250625112854.png]]

![[04_Algorithm/image/Pasted image 20250625113144.png]]

# 7 Reverse Delete





# 8 Aufgabe 

## 8.1 Aufgabe 3.1 

![](image/Pasted%20image%2020250619130203.png)


welche Algorithmus hier am Besten anpassen


### 8.1.1 用 krukal ALgorithmus 

1
![](image/Pasted%20image%2020250619130447.png)


2
![](image/Pasted%20image%2020250619130515.png)



3 
![](image/Pasted%20image%2020250619130536.png)

4 
![](image/Pasted%20image%2020250619130625.png)

4 
![](image/Pasted%20image%2020250619130634.png)




## 8.2 Aufgabe 3.2 

![](image/Pasted%20image%2020250619130723.png)


Assumption: 
只想下 x 没有 被选了， 我们 满足什么条件 ， 会用 ｘ　来连接　Ｂ　和其他的　ｋｏｍｐｏｎｅｎｔ

oberschrank fur X : muss < 110   意味 会使用 connect  X 两个 menge/komponent 
![](image/Pasted%20image%2020250619131310.png)


---


oberschrank fur Y   . muss < 60    意味 下一步会使用 connect 两个 menge/komponent 
![](image/Pasted%20image%2020250619131044.png)

---


oberschrank fur Y   . muss < 60    意味 下一步会使用 connect 两个 menge/komponent  
![](image/Pasted%20image%2020250619131159.png)

![](image/Pasted%20image%2020250619131151.png)


## 8.3 Aufgabe 3.3 



### 8.3.1 prim Simulation


![](image/Pasted%20image%2020250619131504.png)


![](image/Pasted%20image%2020250619131531.png)


![](image/Pasted%20image%2020250619131632.png)


下一步 cf 还是 ce 是egal 

![](image/Pasted%20image%2020250619131643.png)



下一步 是 ab
![](image/Pasted%20image%2020250619131708.png)


### 8.3.2 Kruskal Simulation 

immer kleinest kante 

![](image/Pasted%20image%2020250619131816.png)



![](image/Pasted%20image%2020250619131914.png)

![](image/Pasted%20image%2020250619131936.png)

![](image/Pasted%20image%2020250619132047.png)


![](image/Pasted%20image%2020250619132108.png)



![](image/Pasted%20image%2020250619132134.png)









# 9 Quiz

Kreuzen Sie für jeden der sechs Graphen an, ob die markierten Kanten nur durch den
Prim Algorithmus, nur durch den Kruskal Algorithmus, durch beide oder durch keinen
von beiden ausgewählt worden sein können. Dabei muss der jeweilige Algorithmus
nicht bis zum Ende durchgelaufen sein. Es können also auch die Markierungen während
der Berechnung eines MST abgebildet sein.





要回答这类题目，你通常会看到 **sechs Graphen (六个图)**，每个图中都已经**标记了一些边**。题目的要求是判断：这些被标记的边是否可能是以下哪种算法在执行 **最小生成树（MST）计算过程**中选择的结果：

- ✅ **nur Prim**（仅 Prim 算法可能选中）
    
- ✅ **nur Kruskal**（仅 Kruskal 算法可能选中）
- ✅ **beide**（两个算法都可能选中）
- ✅ **keiner**（两个算法都不可能选中）
    

并且：

> **不需要等到 MST 完全生成**，即只考虑中间步骤中可能出现的边。



**解题思路**：
你需要对每个图进行分析，判断这些标记的边是否满足以下任一算法在构造 MST 时的**边选取逻辑**：
 **Prim-Algorithmus 的边选逻辑**：
- 从某个**起始节点**开始。    
- 每一步选取从当前生成树**通向外部的、最小权重的边**。
- 总是从**已连接部分扩展**出去。
✅ 如果图中某条被标记的边不是从已连通子图出发的最小边，那 Prim 不会选它。


**Kruskal-Algorithmus 的边选逻辑**：
- 按边的权重从小到大排序。
- 每一步选一条**不会形成环的最小边**。
- 不考虑起始点，只看是否连通且不成环。

✅ 如果某条被标记的边在已选择的边集中**会形成环**，那 Kruskal 不会选它。



你该怎么做：
1. **看边是否连通构成树的一部分**。
2. **看有没有违反 Prim/Kruskal 的“选边原则”**。
3. 不需要完整 MST，只需判断这些边**是否可能在构造过程中被选中**。 MST 是 Minimum Spanning Tree（最小生成树） 的缩写。

   

---

示例问题解决方式（假设图）：

比如你看到这样一组图，图中标记了三条边：
- 图 A：三条边都从一个节点发出，且是最小权重边之一 → ✅ 可能是 Prim，也可能是 Kruskal → 选 **beide**
- 图 B：有一条边明显不是从当前连通图出发的最小边 → ❌ 不符合 Prim → 检查是否可能是 Kruskal
- 图 C：三条边组成了一个环 → ❌ Kruskal 不允许形成环 → 检查是否符合 Prim 的扩展逻辑





![](image/Pasted%20image%2020250619132828.png)


prim 起始点  rechts oben , rechts untern 
kruskal 

----




![](image/Pasted%20image%2020250619133308.png)
Prime startpunkte:   in der Mitte 
kruskal : geht nicht, 因为最上面的1 没有被选上



----


![](image/Pasted%20image%2020250619133435.png)


两个都不合适 

warum nicht prim: nicht zusammenhängend
warum nicht krukal   1 oben 没有被选中 


---


![](image/Pasted%20image%2020250619133759.png)


kruskal 可以的 
prim 不可以的 

krukal 下一步  红色的线
![](image/Pasted%20image%2020250619133923.png)


---

![](image/Pasted%20image%2020250619134013.png)


prim 可以 
start punkte ganz links
![](image/Pasted%20image%2020250619134142.png)


![](image/Pasted%20image%2020250619134147.png)

kruskal 不行 
因为 底下的1 没有被悬赏 


---


![](image/Pasted%20image%2020250619134347.png)

两个都行 

krukal , 小的 权重的 gewicht 都被纳入了 
prim: startkonte 可以是  in jedem markierten knoten






## 9.1 Quiz 2 


![[04_Algorithm/image/Pasted image 20250625113507.png]]


lineke : 
nur Prim oder keiner 
prim: Prim mit Start in mitte



Rechte: 
![[04_Algorithm/image/Pasted image 20250625114143.png]]

prim: 从 右边第二个点 
![[04_Algorithm/image/Pasted image 20250625114830.png]]


kruskal geht auch 









