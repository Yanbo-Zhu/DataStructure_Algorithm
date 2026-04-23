

# 1 Beispiel 

zug 就是走一步 

Schachbrett 国际象棋的棋盘


在国际象棋或围棋等游戏中，==每一个棋盘状态可以表示为一个二维数组（如 8×8==）。
- 我们经常需要判断：“这个状态之前见过吗？”
- 为了快速查找，可以用一个哈希函数将棋盘状态转换为一个唯一的哈希值。

![[04_Algorithm/image/Pasted image 20250710121814.png]]

![[04_Algorithm/image/Pasted image 20250710121929.png]]

![[04_Algorithm/image/Pasted image 20250710122218.png]]

# 2 Hashfunktion

![[04_Algorithm/image/Pasted image 20250710122330.png]]


Ordnet jedem Wort eine eindeutige Zahl (Hashwert) zu
Ist für dieses Objekt immmer gleich
Für andere Objekte möglichst anders

attribute:  不同棋子

![[04_Algorithm/image/Pasted image 20250710122430.png]]

![[04_Algorithm/image/Pasted image 20250710122536.png]]

![[04_Algorithm/image/Pasted image 20250710122630.png]]


Also liefert hashCode nur eine Zahl die das Objekt eindeutig bestimmt? Und die wird dann in der Hash Funktion benutzt?

## 2.1 Anforderungen an Hashfunktionen
1. Surjektivität: Der ganze Wertebereich soll ausgenutzt werden.
2. Chaos: Ein geringfügig anders Objekt soll einen komplett anderen Hashwert erzeugen.
	1.  棋盘中一个棋子发生了改变, 都会导致 新的 棋盘zustand 对应的 hashcode 和一起不同 
3. Gleichverteilung: Alle Hashwerte sollen gleich oft vorkommen
4. Effizienz: Der Hashwert soll schnell und einfach zu berechnen sein.


## 2.2 Anwendungsbereiche von Hashing

- Prüfsummen: Unterschiede in Dateien (nach Übertragungen)
- Kryptologie: Hashwertberechnung oft nicht invertierbar
- Hashtabellen: Hashwert eines Objekts entspricht Position, der Hashtabelle dort entsprechen Object der position 


## 2.3 Api von Hashmaps 

![[04_Algorithm/image/Pasted image 20250710123132.png]]


# 3 Hashtabellen füllen

![[04_Algorithm/image/Pasted image 20250710123450.png]]

k  -> stelle im Alphabet

h(A) = h(1) = 11x1  mod 7  = 4
h(L) = h(12) = 11x12 mod 7  = 6 
h(G)  = h(7) = 11x7 mod 7 = 0 

--- 
h(O) = h(?) = 11x1  mod 7  = 4  , 4被占有, 则放到一下个 freistelle, 5 


结果 

Hash kollision 
![[04_Algorithm/image/Pasted image 20250710123751.png]]

![[04_Algorithm/image/Pasted image 20250710124555.png]]



---


h(D) = h(4) = 11x4  mod 7  = 2
![[04_Algorithm/image/Pasted image 20250710124715.png]]

h(A) = h(1) = 11x1  mod 7  = 4  4被占有, 则放到一下个 freistelle, 5 北站有了, 6 schon belegt,. 直到 1 是 frei 的 

![[04_Algorithm/image/Pasted image 20250710124750.png]]


---

h(t)) =  h(20)  = 11x 20 mod 7 =3 

![[04_Algorithm/image/Pasted image 20250710124830.png]]


## 3.1 Hash kollisionen 


### 3.1.1 Methode 1: Hashverfahren mit Verkettung (seperate chaining)
Überläufer werden außerhalb der Hashtabelle in einer zusätzlichen Datenstruktur gespeichert

![[04_Algorithm/image/Pasted image 20250710123835.png]]


缺点: 要在 array 找来找去 


Hashmaps - Seperate Chaining - Funktionen

![[04_Algorithm/image/Pasted image 20250710123927.png]]

array grosse >> list (竖着的 ) length 


 list  length  要> array grosse, 这个 hashtable 才是合理的 

### 3.1.2 Methode 2: Hashverfahren mit linearer Sondierung (open addressing)


Überläufer werden innerhalb der Hashtabelle an einem anderen, freien Ort gespeichert


如果一个空已经被占了, 就往下 继续找 直到找到空 

![[04_Algorithm/image/Pasted image 20250710124203.png]]

![[04_Algorithm/image/Pasted image 20250710124236.png]]

16对应的 hashcode 因为原有的位置 , 已经被占有, 16 会放在另外的位置 
remove  16对应已经被占有的位置, :必须 aufrucken 16 到这个为止 , 要不然 同样的 16 进来, 就不知道 hashtabelle 已经在 其他位置 已经存了 16 
![[04_Algorithm/image/Pasted image 20250710124347.png]]

