
# 1 Verification: Zusicherungen

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

# 2 Komplexität
## 2.1 Asymptotische Notation
### 2.1.1 符号 

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

### 2.1.2 念法 
#### 2.1.2.1 中文

![[02_复杂度/image/Pasted image 20240818202203.png]]

- 常数阶O(1)
- 对数阶O(log n)
- 线性阶O(n)
- 线性对数阶O(nlogn)
- 平方阶O(n²)
- O(2^n)
- O(n!)
#### 2.1.2.2 英文

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

#### 2.1.2.3 德语

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

# 3 Logarithmen

• Potenzen: ab = c
• a = Basis
• b = Exponent
• c = Potenz(wert)

- spezielle Bezeichnungen
	- ln = loge
	- lg = log10
	- ld(lb) = log2

![[97_Spickzettel/image/Pasted image 20250125202133.png]]

## 3.1 等比函数 求和

公比 q≠1

若等比数列的首项为 aaa，公比为 q，前 n 项和 $S_n$ 的公式为：

![[02_复杂度/image/Pasted image 20250120192335.png]]

- a 是首项
- q 是公比
- n 是项数

----

公比 q=1

当 q=1 时，等比数列退化为常数列，每一项都等于 a。因此前 n 项和公式为：

$S_n$=a⋅n,  q=1




## 3.2 计算复杂度 Ubung 

### 3.2.1 

Merke:
- wähle richtige Ungleichung
- finde c und n0 (durch geschickte Abschätzungen)
- Anwendung - oder zeige, es gibt kein c und n0

![[02_复杂度/image/Pasted image 20250119182745.png]]

![[02_复杂度/image/Pasted image 20250119182810.png]]

### 3.2.2 

![[02_复杂度/image/Pasted image 20250119182837.png]]

## 3.3 Time complexity: Best/Worst/Average 

![[02_复杂度/image/Pasted image 20250119174402.png]]

Cases der grundlegenden Anweisungen
- $E_n$: Die Menge seiner Eingaben der Eingabegröße $n \in N_0$  
- Anzahl möglicher Eingaben $|E_n|$
- $e\in E_n$ eine Einagbe 
- W, B:  Worst and Best
	- Grenzen des Eingaberaums
- A: Average 
	- gewichtete Summe über alle möglichen Eingaben
# 4 Recursion 

linearen Rekursion: 
non-linearen Rekursion: Merge Sort: Divide und Conquer 
## 4.1 Master-Theorem 

![[04_Algorithm/image/Pasted image 20250119193621.png]]

![[04_Algorithm/image/Pasted image 20250119193955.png]]


# 5 Suchen


## 5.1 Sequentielle Suche Zeitkomplizität 

Daten unsortiert: optimal  $\Theta(n)$
Daten sortiert: nicht optimal, dann binäre Suche optimal $\Theta(log n)$



# 6 Sort 

通常用 worst case 的时间复杂度, 来代表这个算法的复杂度, 大多数 suche arlgo Average case 的时间复杂度 是 worst case 的一半

![[97_Spickzettel/image/Pasted image 20250119174128.png]]



## 6.1 BubbleSort



![[04_Algorithm/image/Pasted image 20250125202751.png]]


![[04_Algorithm/image/Pasted image 20250125202843.png]]


## 6.2 BubbleSortAdvanced 



对冒泡排序的一个改进就是在每趟排序时判断是否发生交换，如果一次交换都没有发生，则数组已经有序，可以不用继续剩下的趟数直接退出。

schon sortiert! Also nur ein Durchlauf um festzustellen, dass nichts mehr vertauscht wird
→ Flag hinzufügen, um Vertauschung in einer Sequenz zu bemerken



Flag b vor jeder Sequenz resetten

![[04_Algorithm/image/Pasted image 20250125203050.png]]



![[04_Algorithm/image/Pasted image 20250125203107.png]]

![[04_Algorithm/image/Pasted image 20250125203113.png]]


## 6.3 Insertion Sort

![[04_Algorithm/image/Pasted image 20250125203910.png]]

![[04_Algorithm/image/Pasted image 20250125204212.png]]


## 6.4 MergeSort 



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





# 7 Abstrakte Datentypen Zusammenhänge:

![[03_DataStructure/image/Pasted image 20250125213838.png]]


![[03_DataStructure/image/Pasted image 20250125213903.png]]



# 8 VerketteteList


![[03_DataStructure/image/Pasted image 20250125214716.png]]




## 8.1 Speicheraufwand von Listenimplementierungen

• ArrayList
- nur die Elemente O(n)
• LinkedList
- Elemente, Nachfolgerreferenzen O(2n)
• DoubleLinkedList
- Elemente, Vorgänger- und Nachfolgerreferenzen O(3n)
• aber: Referenzen haben feste Größe, die Elemente können sehr große Objekte sein
- → Speicher-Overhead für Referenzen normalerweise vernachlässigbar




## 8.2 Doppelt verkettete Listen


Implementierungsalgorithmen von ADT-Operationen für doppelt verkettete Listen


![[03_DataStructure/image/Pasted image 20250125215054.png]]

![[03_DataStructure/image/Pasted image 20250125215101.png]]

### 8.2.1 insert 

Laufzeitkomplexität 
• Einfügen am Kopf O(1)
• Einfügen am Ende O(1)
• Einfügen hinter gesuchtem Element O(n)

![[03_DataStructure/image/Pasted image 20250125220118.png]]


Insert this element als first element , replace the orignal first one
Insert this element as last  element , replace the orignal last one
![[03_DataStructure/image/Pasted image 20250125215141.png]]


### 8.2.2 delete

Laufzeitkomplexität
• Löschen mit Vergleich O(n)
• Löschen am Kopf O(1)
• Löschen am Ende O(1)

![[03_DataStructure/image/Pasted image 20250125220342.png]]]]

![[03_DataStructure/image/Pasted image 20250125220355.png]]

### 8.2.3 Suchen 

• Suchen: O(n)
![[03_DataStructure/image/Pasted image 20250125220012.png]]

Wenn x.key 不是我们想找的 k, 就找下一个
Wenn in liste keine zu suchende value,  最终的X = x.next  x=the last element,  `<the last element>.next = NIL`

## 8.3 Laufzeiten einer einfach und doppelt verketteten Liste


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

## 8.4 通过 Liste 可以实现其他ADT

• Stack
• Queue
• PriorityQueue
• Dictionary
• Bäume

### 8.4.1 Stack  (LIFO)

![[97_Spickzettel/image/Pasted image 20250125221718.png]]

Ein Stapel bzw. Keller Oder stack ist eine lineare Datenstruktur von
Elementen, bei der das Lesen, Einfügen und Löschen von Elementen nur an einem Ende (top Of stack) vorgenommen werden kann. Diese Modifikationsstrategie Wird auch last-in first-out (LIFO) genannt.


### 8.4.2 Queue (FIFO)

Eine Warteschlange bzw. queue ist eine lineare Datenstruktur von Elementen, bei der das Einfügen von Elementen nur am Ende und das Lesen und Löschen nur am Anfang vorgenommen werden kann.

Diese Modifikationsstrategie Wird auch first-in first-out (FIFO) genannt.


![[97_Spickzettel/image/Pasted image 20250125221826.png]]

