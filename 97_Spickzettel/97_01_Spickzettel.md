
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

## 2.2 计算复杂度 Ubung 

### 2.2.1 

Merke:
- wähle richtige Ungleichung
- finde c und n0 (durch geschickte Abschätzungen)
- Anwendung - oder zeige, es gibt kein c und n0

![[02_复杂度/image/Pasted image 20250119182745.png]]

![[02_复杂度/image/Pasted image 20250119182810.png]]

### 2.2.2 

![[02_复杂度/image/Pasted image 20250119182837.png]]

## 2.3 Time complexity: Best/Worst/Average 

![[02_复杂度/image/Pasted image 20250119174402.png]]

Cases der grundlegenden Anweisungen
- $E_n$: Die Menge seiner Eingaben der Eingabegröße $n \in N_0$  
- Anzahl möglicher Eingaben $|E_n|$
- $e\in E_n$ eine Einagbe 
- W, B:  Worst and Best
	- Grenzen des Eingaberaums
- A: Average 
	- gewichtete Summe über alle möglichen Eingaben
# 3 Recursion 

linearen Rekursion: 
non-linearen Rekursion: Merge Sort: Divide und Conquer 
## 3.1 Master-Theorem 

![[04_Algorithm/image/Pasted image 20250119193621.png]]

![[04_Algorithm/image/Pasted image 20250119193955.png]]

# 4 Sort 

通常用 worst case 的时间复杂度, 来代表这个算法的复杂度, 大多数 suche arlgo Average case 的时间复杂度 是 worst case 的一半

![[97_Spickzettel/image/Pasted image 20250119174128.png]]





