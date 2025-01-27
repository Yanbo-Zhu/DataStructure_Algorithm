
# 1 Theorie 




# 2 Verification: Zusicherungen

![[01_基础/image/Pasted image 20250119171113.png]]

![[01_基础/image/Pasted image 20250119172118.png]]

|                                                       |                                           |
| ----------------------------------------------------- | ----------------------------------------- |
| A-> B                                                 | implikation.<br><br>意思为  A , dann b folgt |
| ![[01_基础/image/Pasted image 20250119171517.png]]      | Nicht 的意思                                 |
| ![[01_基础/image/Pasted image 20250119171524.png]]      | Fur alle 的意思                              |
| P                                                     | 啥意思 不知道                                   |
| x                                                     | 就是一个variable                              |
| <->                                                   | 代表 Dann<br><br>就是我们左边的条件, 可以得到右边的条件       |
| 倒E ![[01_基础/image/Pasted image 20250119171534.png]]   | exist 的意思                                 |
| ![[01_基础/image/Pasted image 20250119171615.png]]      | 倒着的V:  代表 und 这个 logisch relation         |
| V<br><br>正着的v                                         | 代表oder logisch relation                   |
| 倒着的T ![[01_基础/image/Pasted image 20250119171625.png]] | 代表 undefined                              |

# 3 Komplexität
## 3.1 Asymptotische Notation
### 3.1.1 符号 

Untergrenze 
 ![[02_复杂度/image/Pasted image 20250119181913.png]]

![[02_复杂度/image/Pasted image 20250119182129.png]]

----

Obergrenze
 ![[02_复杂度/image/Pasted image 20250119181926.png]]

![[02_复杂度/image/Pasted image 20250119182030.png]]

 < O (2^n)  < O (n!)
 
---

Ober- und Untergrenze
![[02_复杂度/image/Pasted image 20250119182014.png]]

就是 介于 Ober- und Untergrenze 之间 存在的函数 

![[02_复杂度/image/Pasted image 20250119182202.png]]

### 3.1.2 念法 
#### 3.1.2.1 中文

![[02_复杂度/image/Pasted image 20240818202203.png]]

- 常数阶O(1)
- 对数阶O(log n)
- 线性阶O(n)
- 线性对数阶O(nlogn)
- 平方阶O(n²)
- O(2^n)
- O(n!)
#### 3.1.2.2 英文

notation name
O(1) constant
O(log(n)) logarithmic
O((log(n))^c) polylogarithmic
O(n) linear
n^(1/2) represents the square root of n , raising a number to the power of 1/2  (one half )
O(n^2) quadratic
O(n^3)  cubed
O(n^c) polynomial
O(c^n) exponential


a constant-time algorithm is "order 1": O(1)
a linear-time algorithm is "order N": O(N)
a quadratic-time algorithm is "order N squared": O(N2)

0 增长项

Growth term  增长项
- rate of growth 增长率
- order of growth 增长次幂
- order of magnitude 数量级 

1
T(n) grows at the order of n to the power of 2. and write:T(n) = O(n^2).

"n的2次方" is "n squared" or "n to the power of 2."

2 
it grows at Logarithm of n to the base 2
logarithmic  ()
it grows logarithmically   (th 不发音 )
![](02_复杂度/image/Pasted%20image%2020240812155057.png)

3 
c is some arbitrary constant


4 
The expression n^(1/m) represents the m-th root of n. In mathematical terms, raising a number n to the power of 1/m is equivalent to finding the m-th root of n.

1/m  = one m-th

it raises m-th root of n

5 n^m 
The expression n^m represents "n raised to the power of m" or simply "n to the power of m."
it raises n to the power of m

#### 3.1.2.3 德语

- n hoch m : polynomiales wachstum
- a hoch n: exponentielle  wachstum
- ln(a): logrithmus a mit basis von e
- ld(a): logtithmus  a mit basis von 2
- i! 念为 Factorial of n , Fakultät von n

|          |                                                                                                                                                                        |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| O(1)     | laufzeit komplexitat ist constant                                                                                                                                      |
| O(n)     | laufzeit komplexitat ist linear                                                                                                                                        |
| O (n^m)  | time required for an algorithm to complete is a polynomial function of the size of the input<br><br>e.g., O(n^2) ,  O(n^3)<br><br> laufzeit komplexitat ist polynomial |
| O (a^n): | laufzeit komplexitat ist exponentiell<br><br>the time required for an algorithm grows exponentially with the input size ( e.g., O(2^n), O(3^n) ).                      |

# 4 Logarithmen

• Potenzen: ab = c
• a = Basis
• b = Exponent
• c = Potenz(wert)

- spezielle Bezeichnungen
	- ln = loge
	- lg = log10
	- ld(lb) = log2

![[97_Spickzettel/image/Pasted image 20250125202133.png]]

## 4.1 等比函数 求和

公比 q≠1

若等比数列的首项为 a，公比为 q，前 n 项和 $S_n$ 的公式为：

![[02_复杂度/image/Pasted image 20250120192335.png]]

- a 是首项
- q 是公比
- n 是项数

----

公比 q=1

当 q=1 时，等比数列退化为常数列，每一项都等于 a。因此前 n 项和公式为：

$S_n$=a⋅n,  q=1


## 4.2 $i^3$ 求和

![[97_Spickzettel/image/Pasted image 20250127010050.png]]


## 4.3 $log_2(i)$ 求和

![[97_Spickzettel/image/Pasted image 20250127010531.png]]



## 4.4 计算复杂度 Ubung 

### 4.4.1 

Merke:
- wähle richtige Ungleichung
- finde c und n0 (durch geschickte Abschätzungen)
- Anwendung - oder zeige, es gibt kein c und n0

![[02_复杂度/image/Pasted image 20250119182745.png]]

![[02_复杂度/image/Pasted image 20250119182810.png]]

### 4.4.2 

![[02_复杂度/image/Pasted image 20250119182837.png]]

## 4.5 Time complexity: Best/Worst/Average 

![[02_复杂度/image/Pasted image 20250119174402.png]]

Cases der grundlegenden Anweisungen
- $E_n$: Die Menge seiner Eingaben der Eingabegröße $n \in N_0$  
- Anzahl möglicher Eingaben $|E_n|$
- $e\in E_n$ eine Einagbe 
- W, B:  Worst and Best
	- Grenzen des Eingaberaums
- A: Average 
	- gewichtete Summe über alle möglichen Eingaben
# 5 Recursion 

linearen Rekursion: 
non-linearen Rekursion: Merge Sort: Divide und Conquer 
## 5.1 Master-Theorem 

![[04_Algorithm/image/Pasted image 20250119193621.png]]

![[04_Algorithm/image/Pasted image 20250119193955.png]]


# 6 Suchen


## 6.1 Sequentielle Suche Zeitkomplizität 

Daten unsortiert: optimal  $\Theta(n)$
Daten sortiert: nicht optimal, dann binäre Suche optimal $\Theta(log n)$



# 7 Sort 

通常用 worst case 的时间复杂度, 来代表这个算法的复杂度, 大多数 suche arlgo Average case 的时间复杂度 是 worst case 的一半

![[97_Spickzettel/image/Pasted image 20250119174128.png]]



## 7.1 BubbleSort



![[04_Algorithm/image/Pasted image 20250125202751.png]]


![[04_Algorithm/image/Pasted image 20250125202843.png]]


## 7.2 BubbleSortAdvanced 



对冒泡排序的一个改进就是在每趟排序时判断是否发生交换，如果一次交换都没有发生，则数组已经有序，可以不用继续剩下的趟数直接退出。

schon sortiert! Also nur ein Durchlauf um festzustellen, dass nichts mehr vertauscht wird
→ Flag hinzufügen, um Vertauschung in einer Sequenz zu bemerken



Flag b vor jeder Sequenz resetten

![[04_Algorithm/image/Pasted image 20250125203050.png]]



![[04_Algorithm/image/Pasted image 20250125203107.png]]

![[04_Algorithm/image/Pasted image 20250125203113.png]]


## 7.3 Insertion Sort

![[04_Algorithm/image/Pasted image 20250125203910.png]]

![[04_Algorithm/image/Pasted image 20250125204212.png]]


## 7.4 MergeSort 



- Datenfeld rekursiv in halb so große Teile teilen
- Teilungen enden, wenn nur noch ein Datum übrig bleibt (und ist somit sortiert)
- sortierte Teilfelder wieder zusammenfügen (sortierendes Mischen)


归并排序通过分治算法，先排序好两个子数组，然后将两个子数组归并。时间复杂度为 O(NlgN）。

 归并排序从小到大排序：
 - 首先让数组中的每一个数单独成为长度为1的区间，然后两两一组有序合并，得到长度为2的有序区间，依次进行，直到合成整个区间。
 - 就是讲一个数组不断地2元分割, 分到最后不能再分, 然后再从最底层一次合并上来. , 合并的同时 完成 sortieren, 数值较小的放在左边 

![[97_Spickzettel/image/Pasted image 20250125204412.png]]


![[97_Spickzettel/image/Pasted image 20250125204439.png]]


![[97_Spickzettel/image/Pasted image 20250125204701.png]]


![[97_Spickzettel/image/Pasted image 20250125211257.png]]


## 7.5 CountingSort 


Idee
• zähle Anzahl Elemente pro Schlüssel
• ermittle Position zum Einsortieren aller Elemente eines Schlüssels (Summe aller Elemente davor)
• sortiere alle Elemente ab ihrer Position ein und verschiebe Position pro Einsetzen um eins

假定数组为 `a[a_0, …, a_(n-1)]` ，数组中存在重复数字，数组中最大数字为k，
建立两个辅助数组 `b[]` 和 `c[]`，`b[]` 用于存储排序后的结果，`c[] `用于存储临时值。
时间复杂度为 O(n+k )，适用于数字范围较小的数组。

 算法的步骤如下： 
 - 找出待排序的数组中最大和最小的元素 
 - 统计数组中每个值为i的元素出现的次数，存入数组C的第i项 
 - 对所有的计数累加（从C中的第一个元素开始，每一项和前一项相加） 
 - 反向填充目标数组：将每个元素i放在新数组的第C(i)项，每放一个元素就将C(i)减去1


Laufzeit: O (n+k)
- n 是 A 中的元素的数量 
- k 是 A 中的元素的值的 最大值 

![[04_Algorithm/image/Pasted image 20250126172554.png]]


### 7.5.1 Beispiel 

![[04_Algorithm/image/Pasted image 20250126164850.png]]



![[04_Algorithm/image/Pasted image 20250126165200.png]]


## 7.6 快速排序quickSort( Lomuto Scheme) 



- mithilfe eines Pivot-Elements Datenfeld in zwei „Mannschaften“ teilen
- beide Mannschaften sind in sich noch unsortiert, aber bzgl. des Pilots sortier
- mit beiden Mannschaften dasselbe wiederholen, bis nicht mehr geteilt werden muss

- **划分**：数组 `A[p…r] `被划分为两个子数组 `A[p…q-1]` 和 `A[q+1…r]`，使得 `A[p…q-1]` 中每个元素都小于等于 `A[q]`，而 `A[q+1…r]` 每个元素都大于 `A[q]`。划分流程见下图。
- **解决**：通过递归调用快速排序，对子数组分别排序即可。
- **合并**：因为两个子数组都已经排好序了，且已经有大小关系了，不需要做任何操作。


 在数组中随机选一个数（默认数组首个元素），数组中小于等于此数的放在左边部分，大于此数的放在右边部分，这个操作确保了这个数是处于正确位置的，
 再对左边部分数组和右边部分数组递归调用快速排序，重复这个过程。


![](https://i-blog.csdnimg.cn/blog_migrate/a5c6a1b560c5a002e1086178fd5e21d2.gif)   
![](https://i-blog.csdnimg.cn/blog_migrate/ed973c5f163bf7c3970b60ee29d365c1.png)


### 7.6.1 复杂度 


|          |           |             |             |             |           |         |
| -------- | --------- | ----------- | ----------- | ----------- | --------- | ------- |
| **排序算法** | 英文        | **平均时间复杂度** | **最坏时间复杂度** | **最好时间复杂度** | **空间复杂度** | **稳定性** |
| **快速排序** | QuickSort | O(nlogn)    | O(n²)       | O(nlogn)    | O(nlogn)  | 不稳定     |



### 7.6.2 Implementation


![[04_Algorithm/image/Pasted image 20250126180005.png]]

![[04_Algorithm/image/Pasted image 20250126181713.png]]

![[04_Algorithm/image/Pasted image 20250126180014.png]]


### 7.6.3 例子 

Gegeben sei das Zahienfeld A (7, 8, 2, 6, 5, 1, 3, 4) aufsteigend zu sortieren. A ist nach dem Algorithmus Quicksort

(a) Führen Sie die erste Teilung nach dem im Skript gegebenen Verfahren durch.
i. Geben Sie die dabei auftretenden Vertauschungen der Reihe nach an.
ii. Welches ist der erste Teilungsindex?

- Die Erste Pivot-Position的确定: 不同算法不一样, Lomuto Schema 中 是以最rechte 位置, 就是最后一位 的值 指给 erst pivot position 
- i 通过 和 p指向的value 比较, i ist fuer Suchen des vertauschte Element
- p' 指向的 value: Werte zu tauschen 


第一阶段 

![[04_Algorithm/image/Pasted image 20250126180051.png]]

![[04_Algorithm/image/Pasted image 20250126180821.png]]

---


第二阶段 

![[04_Algorithm/image/Pasted image 20250126182057.png]]



![[04_Algorithm/image/Pasted image 20250126180841.png]]


![[04_Algorithm/image/Pasted image 20250126180853.png]]


---


![[04_Algorithm/image/Pasted image 20250126180955.png]]



# 8 Abstrakte Datentypen Zusammenhänge:

![[03_DataStructure/image/Pasted image 20250125213838.png]]


![[03_DataStructure/image/Pasted image 20250125213903.png]]



# 9 VerketteteList


![[03_DataStructure/image/Pasted image 20250125214716.png]]




## 9.1 Speicheraufwand von Listenimplementierungen

• ArrayList
- nur die Elemente O(n)
• LinkedList
- Elemente, Nachfolgerreferenzen O(2n)
• DoubleLinkedList
- Elemente, Vorgänger- und Nachfolgerreferenzen O(3n)
• aber: Referenzen haben feste Größe, die Elemente können sehr große Objekte sein
- → Speicher-Overhead für Referenzen normalerweise vernachlässigbar




## 9.2 Doppelt verkettete Listen


Implementierungsalgorithmen von ADT-Operationen für doppelt verkettete Listen


![[03_DataStructure/image/Pasted image 20250125215054.png]]

![[03_DataStructure/image/Pasted image 20250125215101.png]]

### 9.2.1 insert 

Laufzeitkomplexität 
• Einfügen am Kopf O(1)
• Einfügen am Ende O(1)
• Einfügen hinter gesuchtem Element O(n)

![[03_DataStructure/image/Pasted image 20250125220118.png]]


Insert this element als first element , replace the orignal first one
Insert this element as last  element , replace the orignal last one
![[03_DataStructure/image/Pasted image 20250125215141.png]]


### 9.2.2 delete

Laufzeitkomplexität
• Löschen mit Vergleich O(n)
• Löschen am Kopf O(1)
• Löschen am Ende O(1)

![[03_DataStructure/image/Pasted image 20250125220342.png]]]]

![[03_DataStructure/image/Pasted image 20250125220355.png]]

### 9.2.3 Suchen 

• Suchen: O(n)
![[03_DataStructure/image/Pasted image 20250125220012.png]]

Wenn x.key 不是我们想找的 k, 就找下一个
Wenn in liste keine zu suchende value,  最终的X = x.next  x=the last element,  `<the last element>.next = NIL`

## 9.3 Laufzeiten einer einfach und doppelt verketteten Liste


![[03_DataStructure/image/Pasted image 20250125220754.png]]

einfach verketteten Liste
• Suchen: O(n)
• Einfügen am Kopf O(1)
• Einfügen am Ende O(n) (mit tail O(1))
• Einfügen hinter gesuchtem Element O(n)
• Löschen mit Vergleich O(n)
• Löschen am Kopf O(1)
• Löschen am Ende O(n) (tail hilft nicht!)
• Löschen von gesuchtem Element O(n)


doppelt verketteten Liste
• Suchen: O(n)
• Einfügen am Kopf O(1)
• Einfügen am Ende O(1)
• Einfügen hinter gesuchtem Element O(n)
• Löschen mit Vergleich O(n)
• Löschen am Kopf O(1)
• Löschen am Ende O(1)
• Löschen von gesuchtem Element O(n)

## 9.4 通过 Liste 可以实现其他ADT

• Stack
• Queue
• PriorityQueue
• Dictionary
• Bäume

### 9.4.1 Stack  (LIFO)

![[97_Spickzettel/image/Pasted image 20250125221718.png]]

Ein Stapel bzw. Keller Oder stack ist eine lineare Datenstruktur von
Elementen, bei der das Lesen, Einfügen und Löschen von Elementen nur an einem Ende (top Of stack) vorgenommen werden kann. Diese Modifikationsstrategie Wird auch last-in first-out (LIFO) genannt.


### 9.4.2 Queue (FIFO)

Eine Warteschlange bzw. queue ist eine lineare Datenstruktur von Elementen, bei der das Einfügen von Elementen nur am Ende und das Lesen und Löschen nur am Anfang vorgenommen werden kann.

Diese Modifikationsstrategie Wird auch first-in first-out (FIFO) genannt.


![[97_Spickzettel/image/Pasted image 20250125221826.png]]


# 10 binärer Baum 

• jeder Knoten hat maximal 2 Kindknoten
• jeder Knoten ist Wurzel eines Unterbaums

![[03_DataStructure/image/Pasted image 20250125224027.png]]


## 10.1 Knotenanzahl

Knotenanzahl pro Ebene: $2^d$
![[03_DataStructure/image/Pasted image 20250125224957.png]]


Knotenanzahl des Baums:  $2^{h+1} - 1$

![[03_DataStructure/image/Pasted image 20250125225056.png]]


## 10.2 Mindesthöhe durch Knotenanzahl

Ein Binärbaum mit n Knoten hat mindestens eine Höhe von $log_{2}n$ 

![[03_DataStructure/image/Pasted image 20250125225209.png]]


## 10.3 Vollständigkeit (Vollständiger Baum)

![[03_DataStructure/image/Pasted image 20250125225232.png]]



## 10.4 Operation bei sortiertem Binärbaum

sortierter Binärbaum: → binärer Suchbaum
左边的子节点比父节点大,  右边的子节点比父节点大 
• Ist y ein beliebiger Knoten aus dem linken Unterbaum von x, dann gilt y.key < x. key.
• Ist y ein beliebiger Knoten aus dem rechten Unterbaum von x, dann gilt y.key > x.key.

![[03_DataStructure/image/Pasted image 20250125231701.png]]



### 10.4.1 Suchen
- auf jeder Ebene Entscheidung möglich, in welchem Unterbaum nicht weitergesucht werden muss
- 左边的子节点比父节点大,  右边的子节点比父节点大, 按照这个规律从上往下搜索 

![[03_DataStructure/image/Pasted image 20250126160412.png]]



### 10.4.2 Einfügen
- Sortiereigenschaft muss erhalten bleiben
- 也是比大小
![[03_DataStructure/image/Pasted image 20250126160609.png]]

![[03_DataStructure/image/Pasted image 20250126160623.png]]


### 10.4.3 Löschen 

- Der zu löschende Knoten hat keine Nachfolger, er Wird einfach gelöscht.
- Der zu löschende Knoten hat einen Nachfolger, er Wird ausgeschnitten.


![[03_DataStructure/image/Pasted image 20250126160742.png]]

---

- Der zu löschende Knoten hat zwei Nachfolger. Sein Baum-Nachfolger Wird ausgeschnitten und die Daten des Baum-Nachfolgers werden an den eigentlich zu löschenden Knoten übertragen.
	- ==Finde das kleinste Element im rechten Unterbaum (denn das muss das nächstgrößere zu x sein)==

![[03_DataStructure/image/Pasted image 20250126160848.png]]

![[03_DataStructure/image/Pasted image 20250126160902.png]]


# 11 Binarer Heap


## 11.1 Definition

Ein binärer Heap heißt dann auch Min-Heap (bzw. Max-Heap).
- Min-heap 越往下越大
- Max-heal 越往下 越小

Ein binärer Baum heißt binärer Heap Oder kurz Heap, wenn die folgenden Eigenschaften erfüllt Sind:
- Der Baum ist mindestens bis zur Tiefe h-1 vollständig.
	- 到 h-1 层 全满 
- Alle Blätter befinden Sich auf der Tiefe h-1 Oder h.
- Alle Pfade zu den Blättern der Tiefe h befinden Sich links von den Pfaden, die zu den Blättern der Tiefe h-1 führen.
	- h 层的blatt 都在左边 
- Der Schlüssel eines jeden Knotens ist kleiner Oder gleich (bzw. größer Oder gleich) aller Knoten in den jeweiligen Unterbäumen. 
	- 两边的Kind Knoten 的值 比 eltern Knoten 的少 
- 注意 kindknoto 那个放在左边, 那个放在右边 是没有要求的 . 不一定 左边就一定大于右边


## 11.2 Heapify

用 array 去存储 heap 的结构形式的 各个element
最终得到的结果 which一个 max-heap A, 就是最上层的值 最大,

- 找到一个 konto, 看他和他的kind knoto 值的比较, 如果他的值小于他的 kind knoto 的值, 将他的值 和 他kindkonto 最大的那个值对调
- 往下找 再看那个对调的那个值的位置,  进行 heapify, 就是上一步, 
- 在 往下找 再看那个对调的那个值的位置,  进行 heapify, . 以此类推找到底

## 11.3 将一个 heap结构 存在 array 中 

• A.length: Anzahl der Elemente des Feldes A.
• A.heapsize: Anzahl der Elemente im Heap. Es gilt immer A.heapsize s A-length. Für kein Element i mit A.heapsize <= i <= A.length ist `A[i]` gültig.
• LEFT (i): Liefert den Index des linken Nachfolgers des Knotens i, also 2i.
• RIGHT (i): Liefert den Index des rechten Nachfolgers des Knotens i, also 2i+1.
• PARENT (i): Liefert den Index des Vorgängers des Knotens i, also `i/2`. (取下限整数 )

---

Build-Heap

![[03_DataStructure/image/Pasted image 20250126205134.png]]


---
Sort-Heap


A 为给出的一组 无序数组,

执行Build-heap(A) 得到 max-heap  , 得到根据 A 生成一个 符合规则的 heap,  A 中的元素的顺序也因此发生变化 在第一轮
因为上一轮 已经进行了 Build-heap(A), 得到 max-heap, A 中 第一个 元素 为值最大的.   把index=0 放在了 array 的最后面以为
然后 a.heapsize =  a.heapsize-1,  就是 以后的 iterate 不再考虑 array 的最后一位了,
然后对其他的 element , 进行 heapify
下图的观看顺序 做上倒下, 从左到右

![[03_DataStructure/image/Pasted image 20250126210807.png]]



# 12 Hashing 

## 12.1 Hashtabellen

![[03_DataStructure/image/Pasted image 20250126220114.png]]


### 12.1.1 Laufzeitbetrachtung

abhängig von „gutem“ Einsortieren, a.k.a. guter Hashfunktion
Jeder key has nicht mehr ein value

1  Besten fall
O(1)
每个 hashvalue 的位置 都只对应一个 datesatz(一个 key-value pair)

2 schlimmste Fall
die am schlimmsten einsortiert das heißt die würde immer Kollision produzieren
O(n)
就是 所有 key 对应的 hash value 都是相同的,  所有的 key-value-pair 都连在了同一个 list 上面

![[03_DataStructure/image/Pasted image 20250126215020.png]]


3 Average case 的时间复杂度 
![[03_DataStructure/image/Pasted image 20250126223218.png]]


M platz: 就是 下面 一共有多少个
![[03_DataStructure/image/Pasted image 20250126223139.png]]


n 是 这些是包含了n 个 element 
![[03_DataStructure/image/Pasted image 20250126223156.png]]


## 12.2 Hashfunktionen

### 12.2.1 Zusammenhang Divisions- und Multiplikationsmethode

Divisionsmethode: 
h(k) = ak mod m 

Multiplikationsmethode
![[97_Spickzettel/image/Pasted image 20250126221350.png]]

## 12.3 Offene Adressierung


当一个 key 的 hash value 要组成一个 key kette 了, 组成一个 kette , 会增加查找难度,.  为了避免这个问题
需要 finde ich einen freien Platz in dieser Tabelle, 将这个key 存在 tablle 里  这个新的问题 , 这个就是 offene addressierung

## 12.4 Linear Sondierungen

![[03_DataStructure/image/Pasted image 20250126221807.png]]

通过 加 I 的方式 将 key 的 in table 的储存位置 mit offset manchen



## 12.5 Chaining vs. Offene Adressierung

Offene addressierung
152 处 先 存好 john smith
Sandra dee 应该存在 152, 但是已经有john smith, 有了 kollision. 根据与 sondierungfunktion, 存在  原本的位置  x+1 mod y , 存在原本的 位置 的 +1 处, 就是 存在 153 处 ,
Ted baker 应该存在 153, 但是已经有Sandra dee , 有了 kollision. 根据与 sondierungfunktion, 存在  原本的位置  x+1 mod y , 存在原本的 位置 的 +1 处, 就是 存在 154 处 ,

![[03_DataStructure/image/Pasted image 20250126222052.png]]

![[03_DataStructure/image/Pasted image 20250126222111.png]]


Chaining Addressierung
- Warum „geschlossene Adressierung“: weil die Kollisionskette hinter einem Key versteckt sind
- Warum „offenes Hashing“: weil die Kollisionskette hinter einem Key beliebig lang werden kann

Offene Adressierung 
- Warum „offene Adressierung“: weil sich die Kollisionskette über mehrere Keys verteilt
- Warum „geschlossenes Hashing“: weil die Kollisionskette nur erweitert werden kann, wenn noch Platz in der Hashtable ist



## 12.6 Array Doubling

wenn die Kapazität erschöpft ist
Dann verdoppelt die grosse von Array
Arraylength 增加后,  hashfunction  也需要改变,   modelle 2m, nicht mehr m


![[03_DataStructure/image/Pasted image 20250126222244.png]]