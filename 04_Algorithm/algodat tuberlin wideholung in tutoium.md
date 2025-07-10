

# 1 max-min suche

## 1.1 例子

![[04_Algorithm/image/Pasted image 20250710125323.png]]


![[04_Algorithm/image/Pasted image 20250710125546.png]]



# 2 Alpha Beta 

![[04_Algorithm/image/Pasted image 20250710125145.png]]

![[04_Algorithm/image/Pasted image 20250710125637.png]]



![[04_Algorithm/image/Pasted image 20250710125716.png]]


![[04_Algorithm/image/Pasted image 20250710125223.png]]


in pink layer ( minimal layer) , suche nur beata , setzen beta mit  minimale weter 
in blau layer, such ein aplha weter, setzen  alpha weter mit max value 


![[04_Algorithm/image/Pasted image 20250710130111.png]]

![[04_Algorithm/image/Pasted image 20250710130248.png]]

---

3> -unendlich,     dan aplha als 3 

![[04_Algorithm/image/Pasted image 20250710130457.png]]

---



![[04_Algorithm/image/Pasted image 20250710130602.png]]

![[04_Algorithm/image/Pasted image 20250710130713.png]]

2  是因为 1 2 中 2 比较大, 写2 只是写法问题   写的不是 3,. 写的 是 两个 konte  中的最大值 
但其实 aphla 在 更新后 应该是 3 , 不是2 

![[04_Algorithm/image/Pasted image 20250710131210.png]]


---

![[04_Algorithm/image/Pasted image 20250710130724.png]]


---

![[04_Algorithm/image/Pasted image 20250710130915.png]]

![[04_Algorithm/image/Pasted image 20250710131342.png]]

# 3 topologischer Sortierung   und Tiefsuche 


例子 kleider sortieren 


Erstellen sie für folgende Kleidungsstücke Knoten und Kanten in einem gerichteten Graphen, wobei eine Kante bedeutet, dass der Startknoten vor dem Endknoten angezogen werden muss:
Unterhemd (0), Socken (1), Krawatte (2), Gürtel (3), Schuhe (4), Hose (5), Sakko (6), Unterhose (7).

Geben sie anschließend eine Topologische Sortierung und eine Beispiel reihenfolge für das Anziehen an, indem sie den folgenden Code per Hand simulieren. Wie muss dafür die Methode public void mystery angepasst werden? Für welche Graphen funktioniert der Algorithmus?


**请根据以下衣物为一个有向图创建节点和边，其中一条边表示：起始节点代表的衣物必须在目标节点代表的衣物之前穿上：**

- Unterhemd (背心，编号0)
    
- Socken (袜子，编号1)
    
- Krawatte (领带，编号2)
    
- Gürtel (腰带，编号3)
    
- Schuhe (鞋子，编号4)
    
- Hose (裤子，编号5)
    
- Sakko (西装外套，编号6)
    
- Unterhose (内裤，编号7)


然后给出一个拓扑排序（也就是说，给出一种满足所有先后顺序要求的穿衣顺序），并通过手动模拟以下代码给出一个示例的穿衣顺序。

为了实现这一点，方法 public void mystery 需要怎样进行调整？该算法适用于哪类图？



![[04_Algorithm/image/Pasted image 20250710131748.png]]


---

![[04_Algorithm/image/Pasted image 20250710131812.png]]

fur nicht nicht besucht ,     fugen eine mystery ein 

---


Wie muss man mystery noch anpassen ? 
![[04_Algorithm/image/Pasted image 20250710131830.png]]

Das ist ein Tiefsuche 

laufzeit von Tiefsuche : 
![[04_Algorithm/image/Pasted image 20250710132354.png]]

jede konte wird nur 1 mal geschaut 
jeder kante wird 2 mal geschaut,  一个 kante 链接 2 个 konte . 每个 konte wird nur 1 mal geschaut , 所以 每个 

![[04_Algorithm/image/Pasted image 20250710132428.png]]




---
Hier muss noch der Stack übergeben werden.
 Und dann sobald wir einen Knoten fertig abgearbeitet haben dann fügen wir diesen diesen Knoten noch aus unserem Stack hinzu.

PreOrder 
postOrder

![[04_Algorithm/image/Pasted image 20250710132537.png]]


这个 stack.push(v) 为 postorder


---


![[04_Algorithm/image/Pasted image 20250710132641.png]]


---


see sakko 

![[04_Algorithm/image/Pasted image 20250710132908.png]]


![[04_Algorithm/image/Pasted image 20250710132942.png]]


---
see krawatte 

![[04_Algorithm/image/Pasted image 20250710133023.png]]


![[04_Algorithm/image/Pasted image 20250710133036.png]]

---

see unterhemd 

![[04_Algorithm/image/Pasted image 20250710133109.png]]


---

see socken 

ruft mystery mit sokcemn 

![[04_Algorithm/image/Pasted image 20250710133152.png]]


 会自动 向下看  see schuhe
![[04_Algorithm/image/Pasted image 20250710133219.png]]



看完后 jiang schuhe 加入到 stack 

![[04_Algorithm/image/Pasted image 20250710133244.png]]



---

see Gurtel 

![[04_Algorithm/image/Pasted image 20250710133346.png]]

gurtel habe untergeordnete konte 

---


see hose 

![[04_Algorithm/image/Pasted image 20250710133423.png]]


----

see  unterhose 

![[04_Algorithm/image/Pasted image 20250710133448.png]]


---

先进后出
stack 的返回的时候, 先返回输出 unterhose, 然后 hose, gurtel 

stack.pop()

![[04_Algorithm/image/Pasted image 20250710133557.png]]


# 4 Graph 

Graphen
Darstellung:
1. Ungerichtete Graphen
2. Gerichtete Graphen
3. Gewichtete Graphen

Algorithmen:
1. Breiten- und Tiefensuche
2. Prim/Kruskal
3. Dijsktra/Bellman-Ford



# 5 BellFord 

![[04_Algorithm/image/Pasted image 20250710133843.png]]

---

Runde 1 

![[04_Algorithm/image/Pasted image 20250710134103.png]]

![[04_Algorithm/image/Pasted image 20250710134138.png]]

---

Runde 2 

只能看 a or b  能到达的点 

![[04_Algorithm/image/Pasted image 20250710134308.png]]


![[04_Algorithm/image/Pasted image 20250710134453.png]]

---

只能看 abcde 能直接接触道德点 

![[04_Algorithm/image/Pasted image 20250710134708.png]]


![[04_Algorithm/image/Pasted image 20250710134801.png]]


![[04_Algorithm/image/Pasted image 20250710134826.png]]


----

iteration 4 5 6 7 中 kantegewichte 不在会有改变了 





