

# 1 #


![[04_Algorithm/image/Pasted image 20250718141626.png]]


heuristische Algorithen 
: heutistische Algo liedert oft gute, aber nicht norwendigersweise optimale Losung 


2 
heuristische konsistent 
![[04_Algorithm/image/Pasted image 20250718141820.png]]

answer: nicht keuristische konsistent 

3 
![[04_Algorithm/image/Pasted image 20250718141855.png]]



选第二个 


4 

![[04_Algorithm/image/Pasted image 20250718142034.png]]

选第二个 


5
![[05_TUBERLIN/image/Pasted image 20250718142146.png]]


![[05_TUBERLIN/image/Pasted image 20250718142254.png]]



选第三个 


6
![[05_TUBERLIN/image/Pasted image 20250718142428.png]]

选2 


7

![[05_TUBERLIN/image/Pasted image 20250718142514.png]]


正确答案是 

选 3,4 

- **初始化最优解（initial best solution）**  
    开始时设定一个可行解，记录其代价。
    
- **分支（Branching）**  
    将问题划分成多个子问题（例如：当前路径的下一步是哪个城市）。
    
- **限界（Bounding）**  
    对每个子问题，计算一个**最小可能代价（Lower Bound）**或**最大可能收益（Upper Bound）：
    
    - 如果这个 bound 比当前最优解还差 → 剪掉这个分支（prune）
        
    - 否则 → 保留，进入下一个分支（继续分支）
        
- **回溯（Backtrack）**  
    若该路径不行，返回上层继续尝试别的分支。


---


![[05_TUBERLIN/image/Pasted image 20250718142658.png]]


# 2 Aufgabe 4: Hashing



## 2.1 a

![[05_TUBERLIN/image/Pasted image 20250718144908.png]]

m Folgenden werden Hashtabellen zur Speicherung von Integer-Werten betrachtet, d.h., die Schl¨ussel
sind vom Typ Integer. Kollisionen werden durch Lineares Sondieren (linear probing) mit Inkrement
1 aufgel¨ost.
Die folgende Hashtabelle der Gr¨oße 10 ist durch das Einf¨ugen von Schl¨usseln mit der Hashfunktion

h(key) = hashwert 



Die Reihenfolge, in der die Schl¨ussel eingef¨ugt wurden, ist unbekannt. Aber es k¨onnen gewisse Aus-
sagen ¨uber die Reihenfolge getroffen werden.
Nennen Sie alle Schl¨ussel, die m¨oglicherweise als erstes eingef¨ugt wurden:

Alle Schl¨ussel, die einen Platz unter ihrer Hashadresse bekommen haben: 22, 13, 15, 7, 28



---


Nennen Sie alle Schl¨ussel, die m¨oglicherweise als letztes eingef¨ugt wurden:

Alle Schl¨ussel, die an keiner Position stehen, die Teil einer Sondierungsfolge eines anderen Schl¨ussel
sind: 22, 14, 7, 28


## 2.2 b

Um noch weitere Schl¨ussel zu speichern, soll die Hashtabelle auf die Gr¨oße 15 vergr¨oßert werden.
Dazu m¨ussen die Schl¨ussel aus der obigen Tabelle durch Rehashing in die neue, gr¨oßere Hashtabel-
le ¨ubertragen werden. Durchlaufen Sie die urspr¨ungliche Hashtabelle entlang der Hashadressen und
f¨ugen Sie die Schl¨ussel mit der neuen Hashfunktion hash2(k) in die untere Hashtabelle ein.

![[05_TUBERLIN/image/Pasted image 20250718145853.png]]


# 3 Breitensuche 

![[05_TUBERLIN/image/Pasted image 20250718150512.png]]


preOrder: die Konte, die noch nicht  abgearbeitet ist 

postOrder: die Konte, die schon abgearbeitet ist 

(a)
F¨uhren Sie die Breitensuche auf dem obigen Graphen G aus. Fangen Sie bei Knoten A an und
notieren Sie alle Knoten in der Reihenfolge, in der sie von der Breitensuche in die Warteschlange
geschrieben werden.
Gehen Sie dabei davon aus, dass von jedem Knoten die benachbarten Knoten in alphabetischer
Reihenfolge besucht werden. Z.B. wird die Kante B-E vom Algorithmus vor der Kante B-F bearbeitet

A, B, D, E, F, C, G, H, I, J


---


(b)
Welche Kante m¨ussten Sie hinzuf¨ugen, damit J vor G in die Warteschlange geschrieben w¨urde?
A-J oder B-J


---


(c)
Geben Sie f¨ur die Knoten v = A, F, G und J vom Graphen G einen Zyklus minimaler L¨ange an, der
den Knoten v enth¨alt, wenn er auf einem Zyklus liegt. Andernfalls geben Sie an, dass v nicht auf
einem Zyklus liegt.

a.) A liegt auf dem Kreis A,B,E,D(,A) der L¨ange 4
b.) F liegt auf dem Kreis F,C,D,G(,F) der L¨ange 4
c.) G liegt auf dem Kreis G,H,I(,G) der L¨ange 3
d.) J liegt auf keinem Kreis



# 4 Dynamically programmierung 


**(a)** 本题是关于两个给定字符串的**最短公共超序列（SCS：shortest common supersequence）**。

“超序列”指的是一个包含两个给定字符串作为**子序列**的字符串。  
原始字符串在这个超序列中**不一定是连续的**，只要字符顺序保持即可。

例如：

- 对于 “ABCC” 和 “ACDC”，一个 SCS 是 “ABCDC”。
    
- 另外两个例子：
    
    - 对于 “GLUT” 和 “ULTRA”，那么 “GLULTRA” 和 “GULUTRA” 都是 SCS。
        
    - 对于 “RASEN” 和 “KASINO”，则 “KRASEINO” 是一个 SCS。



我们给定两个字符串 `X` 和 `Y`，它们的长度分别为 `M` 和 `N`。  
请你定义一个**递归的 Opt 函数**，使得：

> `Opt(m, n)` 表示字符串 `X[:m]` 和 `Y[:n]` 的最短公共超序列的**长度**  
> （其中：`0 ≤ m ≤ M`，`0 ≤ n ≤ N`）

其中定义如下：

- `X[:m]` 表示字符串 `X` 的前 `m` 个字符（从 `X[0]` 到 `X[m-1]`）
- 特别地，`X[:0]` 表示空字符串，`X[:M]` 就是整个字符串 `X`
- `Y[:n]` 也有同样定义





一个 `(X[:m], Y[:n])` 的 SCS 可以按如下方式递归求解：
- 如果这两个子串的**最后一个字符相同**，那么我们可以：
    - 将这个公共字符添加到 `X[:m-1]` 和 `Y[:n-1]` 的 SCS 后面
- 如果它们的最后一个字符**不同**，我们有两种选择：
    - 取 `X[:m-1]` 和 `Y[:n]` 的 SCS，然后把 `X[m-1]` 加上去，或者
    - 取 `X[:m]` 和 `Y[:n-1]` 的 SCS，然后把 `Y[n-1]` 加上去
    - 从这两者中取**更短的那个**作为结果

我们据此可以定义 `Opt` 函数（你只需要算出 SCS 的长度即可，不需要返回字符串本身）。

别忘了处理**边界情况（初始值）**。