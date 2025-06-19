
Build Min/Max Heap, Heapify-Algorithmus

# 1 Definition

- immer möglichst der Breite nach aufgefüllter Binärbaum
- Zusicherung der Eigenschaft „aufgefüllt“
- partiell geordnet:
	- d.h. zwischen Kinder- und Elternknoten besteht eine Ordnung
	- aber Kinderknoten untereinander nicht geordnet


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


![[03_DataStructure/image/Pasted image 20250126203450.png]]

# 2 Heapify

zentraler Hilfsalgorithmus
通过这个算法将 一个 BinärerBaum/Array 改造成 BinärerHeap 

用 array 去存储 heap 的结构形式的 各个element
最终得到的结果 which一个 max-heap A, 就是最上层的值 最大,

• Heap-Eigenschaften
- Vollständigkeit
- auf/absteigende Ordnung
• das die Heap-Eigenschaft verletzendes Element i „sinkt ein“, bis Heap wieder in Ordnung ist

- 找到一个 konto, 看他和他的kind knoto 值的比较, 如果他的值小于他的 kind knoto 的值, 将他的值 和 他kindkonto 最大的那个值对调
- 往下找 再看那个对调的那个值的位置,  进行 heapify, 就是上一步, 
- 在 往下找 再看那个对调的那个值的位置,  进行 heapify, . 以此类推找到底

![[03_DataStructure/image/Pasted image 20250126203738.png]]



![[03_DataStructure/image/Pasted image 20250126203804.png]]


![[03_DataStructure/image/Pasted image 20250126203922.png]]


![[03_DataStructure/image/Pasted image 20250126203928.png]]

![[03_DataStructure/image/Pasted image 20250126203937.png]]

![[03_DataStructure/image/Pasted image 20250126203947.png]]



# 3 ADT Heap als Array

Array 中 Index 越小 , 对应的元素 越往最上层
Max-heap,  index=0 对应的元素 为最大值
min-heap,  index=0 对应的元素 为最小值


## 3.1 将一个 heap结构 存在 array 中 

Ein Heap kann nun natürlich, wie im vorangehenden Abschnitt beschrieben, als eine dynamische Datenstruktur eines binären Baumes implementiert werden. Es ist allerdings auch möglich, einen Heap in einer statischen Datenstruktur eines Feldes zu im lementieren. Die Anzahl der zu speichernden Knoten ist dann aber mit der Feldgröße nach oben beschränkt. Dieser Ansatz Wird im Folgenden verfolgt.

• A.length: Anzahl der Elemente des Feldes A.
• A.heapsize: Anzahl der Elemente im Heap. Es gilt immer A.heapsize s A-length. Für kein Element i mit A.heapsize <= i <= A.length ist `A[i]` gültig.
• LEFT (i): Liefert den Index des linken Nachfolgers des Knotens i, also 2i.
• RIGHT (i): Liefert den Index des rechten Nachfolgers des Knotens i, also 2i+1.
• PARENT (i): Liefert den Index des Vorgängers des Knotens i, also `i/2`. (取下限整数 )

![[03_DataStructure/image/Pasted image 20250126204501.png]]

![[03_DataStructure/image/Pasted image 20250126205449.png]]

1,2,3... 代表 array 中 该元素 index 的值 

## 3.2 Heap Search in Array 

![[03_DataStructure/image/Pasted image 20250126204556.png]]

![[03_DataStructure/image/Pasted image 20250126204604.png]]


![[03_DataStructure/image/Pasted image 20250126204744.png]]

![[03_DataStructure/image/Pasted image 20250126204755.png]]

## 3.3 Heap Konstruktion from Array 


![[03_DataStructure/image/Pasted image 20250126205134.png]]


==Wieso bei Knoten n/2 (取下限整数 ) anfangen?==
- das ist der letzte innere Knoten nach Breitensuche
- das ist garantiert wegen der Vollständigkeitszusicherung eines Heaps

- Breitensuche rückwärts (lückenlos nach oben wandern)
- Heapify auf jedem Element anwenden (lückenlos nach unten korrigieren
- ➔ dann muss der ganze Baum korrigiert worden sein

---

例子 

![[03_DataStructure/image/Pasted image 20250126205858.png]]


![[03_DataStructure/image/Pasted image 20250126205907.png]]


![[03_DataStructure/image/Pasted image 20250126210329.png]]


![[03_DataStructure/image/Pasted image 20250126210336.png]]


![[03_DataStructure/image/Pasted image 20250126210345.png]]

![[03_DataStructure/image/Pasted image 20250126210353.png]]


![[03_DataStructure/image/Pasted image 20250126210405.png]]



## 3.4 Heap Sort

其实就是将一个 array 中的 元素  sort , 新的 array 为一个 sorted array, 最大值在array 的最后 

将 array 先 heapify 化, 找到 之后 这个array 的最大值元素会放在 index=0 的位置, 然后 将这个 最大值元素 拿出去, 不再考虑. 组成一个新的 array, 长度减少了一个 
然后再讲 剩余的 heap 再次 heapify , 再转到最大值元素.  然后以此类推 

![[03_DataStructure/image/Pasted image 20250126210457.png]]

• bei korrektem Heap ist maximales Element in der Wurzel
• tausche mit letztem Element (das ist das letzte Blatt nach Breitensuche = letztes Element im Array)
• $e_{max}$ an letzter Stelle, letztes Element gehört jetzt nicht mehr zum Heap (bzw. Heap wird eins kleiner gemacht)
• evtl. nicht korrekter Sub-Heap bis vorletztes Element (letzte ist jetzt maximal)
• Heapify auf Sub-Heap
• jetzt stehen $e_{max-1}$,   $e_{max}$  an letzter Stelle
• usw.

A 为给出的一组 无序数组,

执行Build-heap(A) 得到 max-heap  , 得到根据 A 生成一个 符合规则的 heap,  A 中的元素的顺序也因此发生变化 在第一轮
因为上一轮 已经进行了 Build-heap(A), 得到 max-heap, A 中 第一个 元素 为值最大的.   把index=0 放在了 array 的最后面以为
然后 a.heapsize =  a.heapsize-1,  就是 以后的 iterate 不再考虑 array 的最后一位了,
然后对其他的 element , 进行 heapify
下图的观看顺序 做上倒下, 从左到右

![[03_DataStructure/image/Pasted image 20250126210807.png]]


# 4 Implementierungsdetails

通过 list 实现 heap 

• Wo prev/next implementieren? In Liste oder Element? Geht das überhaupt?


![[03_DataStructure/image/Pasted image 20250126211456.png]]


![[03_DataStructure/image/Pasted image 20250126211503.png]]


## 4.1 Single Linked 

Könnte die LinkedList noch selber machen.
Wer speichert head?


```
class LinkedList {
Data data;
LinkedList next;
}

class Node {
Data data;
Node next;
}

class LinkedList {
Node head;
}
```



![[03_DataStructure/image/Pasted image 20250126211757.png]]

## 4.2 Double Linked

Wer speichert head und tail? der „Owner“

```
class DoubleLinkedList {
	DoubleLinkedList prev;
	Data data;
	DoubleLinkedList next;
}

class Node {
	Node prev;
	Data data;
	Node next;
}

class DoubleLinkedList {
	Node head;
	Node tail;
}
```

# 5 Ownership

![[03_DataStructure/image/Pasted image 20250126211922.png]]


Sollte der Benutzer einer DoubleLinkedList* Zugriff auf die Knoten haben? (* gilt auch für andere Datenstrukturen)

![[03_DataStructure/image/Pasted image 20250126212007.png]]




