
当看「时间」二字，我们肯定可以想到将该算法程序运行一篇，通过运行的时间很容易就知道复杂度了。
这种方式可以吗？当然可以，不过它也有很多弊端。
比如程序员小吴的老式电脑处理10w数据使冒泡排序要几秒，但读者的iMac Pro 可能只需要0.1s，这样的结果误差就很大了。更何况，有的算法运行时间要很久，根本没办法没时间去完整的运行，还是比如猴子排序：）。
那有什么方法可以严谨的进行算法的时间复杂度分析呢？
有的!


# 1 什么是大O


Big O notation (with a capital letter O, not a zero), also called Landau's symbol, is a symbolism used in complexity theory, 
The letter O is used because the rate of growth of a function is also called its order.

 远古的程序员大佬们提出了通用的方法：「 大O符号表示法 」，即 **T(n) = O(f(n))**。
其中 n 表示数据规模 ，O(f(n))表示运行算法所需要执行的指令数，和f(n)成正比。

大O表示法：算法的时间复杂度通常用大O符号表述，定义为 `**T[n] = O(f(n)) **`。称函数T(n)以f(n)为界或者称T(n)受限于f(n)。
如果一个问题的规模是n，解这一问题的某一算法所需要的时间为T(n)。T(n)称为这一算法的“时间复杂度”。

> 上面公式中用到的 Landau符号是由德国数论学家保罗·巴赫曼（Paul Bachmann）在其1892年的著作《解析数论》首先引入，由另一位德国数论学家艾德蒙·朗道（Edmund Landau）推广。Landau符号的作用在于用简单的函数来描述复杂函数行为，给出一个上或下（确）界。在计算算法复杂度时一般只用到大O符号，Landau符号体系中的小o符号、Θ符号等等比较不常用。这里的O，最初是用大写希腊字母，但现在都用大写英语字母O；小o符号也是用小写英语字母o，Θ符号则维持大写希腊字母Θ。

注：本文用到的算法中的界限指的是最低的上界。


大O符号是一种算法「复杂度」的「相对」「表示」方式。

这个句子里有一些重要而严谨的用词：

- 相对(relative)：你只能比较相同的事物。你不能把一个做算数乘法的算法和排序整数列表的算法进行比较。但是，比较2个算法所做的算术操作（一个做乘法，一个做加法）将会告诉你一些有意义的东西；
    
- 表示(representation)：大O(用它最简单的形式)把算法间的比较简化为了一个单一变量。这个变量的选择基于观察或假设。例如，排序算法之间的对比通常是基于比较操作(比较2个结点来决定这2个结点的相对顺序)。这里面就假设了比较操作的计算开销很大。但是，如果比较操作的计算开销不大，而交换操作的计算开销很大，又会怎么样呢？这就改变了先前的比较方式；
    
- 复杂度(complexity)：如果排序10,000个元素花费了我1秒，那么排序1百万个元素会花多少时间？在这个例子里，复杂度就是相对其他东西的度量结果。



# 2 符号 

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






# 3 念法 


## 3.1 中文

![[02_复杂度/image/Pasted image 20240818202203.png]]

- 常数阶O(1)
- 对数阶O(log n)
- 线性阶O(n)
- 线性对数阶O(nlogn)
- 平方阶O(n²)
- O(2^n)
- O(n!)


## 3.2 英文


![[02_复杂度/image/Pasted image 20250119182030.png]]

 < O (2^n)  < O (n!)
 
---


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


---

0 增长项

Growth term  增长项
- rate of growth 增长率
- order of growth 增长次幂
- order of magnitude 数量级 


---


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


## 3.3 德语



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


# 4 常见的复杂度量级


![Image](https://mmbiz.qpic.cn/mmbiz_jpg/D67peceibeISTRz5ibO62oFJIY3OQIc2nQ3ehplzibAZCr5xOzzBM1icVr8PUDHq9AFmicGrGSNIhGjFLYmybFtyA3A/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



## 4.1 O(1)

![Image](https://mmbiz.qpic.cn/mmbiz_gif/D67peceibeISTRz5ibO62oFJIY3OQIc2nQuj6PnaS8BTJfAM6uhHCQdjibvWicNJbaWBia1To9WBwc43Crw64c5vPzw/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

无论代码执行了多少行，其他区域不会影响到操作，这个代码的时间复杂度都是O(1)

```
1void swapTwoInts(int &a, int &b){
2  int temp = a;
3  a = b;
4  b = temp;
5}
```

## 4.2 O(n)

![Image](https://mmbiz.qpic.cn/mmbiz_gif/D67peceibeISTRz5ibO62oFJIY3OQIc2nQvKdTsasUMxZMXMdeQKjp64LnUYzY7RDlY6hdNBefNXG8StBuJcIjaA/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

在下面这段代码，for循环里面的代码会执行 n 遍，因此它消耗的时间是随着 n 的变化而变化的，因此可以用O(n)来表示它的时间复杂度。

```
1 int sum ( int n ){
2   int ret = 0;
3   for ( int i = 0 ; i <= n ; i ++){
4      ret += i;
5   }
6   return ret;
7 }
```


特别一提的是 c * O(n) 中的 c 可能小于 1 ，比如下面这段代码：

```
1 void reverse ( string &s ) {
2     int n = s.size();
3     for (int i = 0 ; i < n/2 ; i++){
4       swap ( s[i] , s[n-1-i]);
5     }
6 }
```


## 4.3 O(n²)

![Image](https://mmbiz.qpic.cn/mmbiz_gif/D67peceibeISTRz5ibO62oFJIY3OQIc2nQAg84fYcTufuT4IcgbVA9TPJBasayybr0Ks3w5HM9gZv21Y7r5GJZ4g/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)



当存在双重循环的时候，即把 O(n) 的代码再嵌套循环一遍，它的时间复杂度就是 O(n²) 了。

```
 1 void selectionSort(int arr[],int n){
 2    for(int i = 0; i < n ; i++){
 3      int minIndex = i;
 4      for (int j = i + 1; j < n ; j++ )
 5        if (arr[j] < arr[minIndex])
 6            minIndex = j;
 7
 8      swap ( arr[i], arr[minIndex]);
 9    }
10 }
```


这里简单的推导一下

- 当 i = 0 时，第二重循环需要运行 (n - 1)  次
- 当 i = 1 时，第二重循环需要运行 (n - 2)  次
- 。。。。。。


不难得到公式：

```
(n - 1) + (n - 2) + (n - 3) + ... + 0
= (0 + n - 1) * n / 2
= O (n ^2)
```


当然并不是所有的双重循环都是 O(n²)，比如下面这段输出 30n 次 `Hello,五分钟学算法：）`的代码。

```
void printInformation (int n ){
    for (int i = 1 ; i <= n ; i++)
         for (int j = 1 ; j <= 30 ; j ++)
            cout<< "Hello,五分钟学算法：）"<< endl;
}
```

## 4.4 O(log n)

![Image](https://mmbiz.qpic.cn/mmbiz_gif/D67peceibeISTRz5ibO62oFJIY3OQIc2nQXMk4h6y9ISCibGUQGI0OibTiaT7Fb10QUKDyRcfRAFtlaJqq7hKcdhkCw/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)


```
n ist the length of arr[], 就是 arr 中有几个 元素 
假定 arr[] 中的 元素 都是已经 从小到大排序好的 

 1 int binarySearch( int arr[], int n , int target){
 2   int l = 0, r = n - 1;      
 3   while ( l <= r) { 
 4     int mid = l + (r - l) / 2;   # 中间位置的那个值的 index 
 5     if (arr[mid] == target) return mid;
 6     if (arr[mid] > target ) r = mid - 1;
 7     else l = mid + 1;
 8   }
 9   return -1;
10 }
```

在二分查找法的代码中，通过while循环，成2倍数的缩减搜索范围，也就是说需要经过 log2^n  ( = log2(n),  ) 次即可跳出循环。

Logarithm of n to the base 2:
![](02_复杂度/image/Pasted%20image%2020240812155057.png)

同样的还有下面两段代码也是 O(log n) 级别的时间复杂度。

```
 1  // 整形转成字符串
 2  string intToString ( int num ){
 3   string s = "";
 4   // n 经过几次“除以10”的操作后，等于0
 5   while (num ){
 6    s += '0' + num%10;
 7    num /= 10;
 8   }
 9   reverse(s)
10   return s;
11  }

1 void hello (int n ) {
2   // n 除以几次 2 到 1
3   for ( int sz = 1; sz < n ; sz += sz) 
4     for (int i = 1; i < n; i++)
5        cout<< "Hello,五分钟学算法：）"<< endl;
6 }
```

## 4.5 O(nlog n)

将时间复杂度为O(logn)的代码循环N遍的话，那么它的时间复杂度就是 n * O(logn)，也就是了O(nlogn)。

```
1 void hello (){
2  for( m = 1 ; m < n ; m++){   m 被循环了 n 遍
3    i = 1;
4    while( i < n ) { 这里的复杂度为  O(logn)
5        i = i * 2;    
6    }
7   }
8 }
```



# 5 计算复杂度 Ubung 

## 5.1 

Merke:
- wähle richtige Ungleichung
- finde c und n0 (durch geschickte Abschätzungen)
- Anwendung - oder zeige, es gibt kein c und n0

![[02_复杂度/image/Pasted image 20250119182745.png]]

![[02_复杂度/image/Pasted image 20250119182810.png]]


## 5.2 

![[02_复杂度/image/Pasted image 20250119182837.png]]



# 6 Optimalität

ein Algorithmus ist optimal, wenn es keinen anderen (auch noch unbekannten) Algorithmus geben kann, welcher das Problem effizienter (im Sinne einer Komplexitätsklasse) lösen kann
• Wie beweisen?
- beweise Komplexitätsklasse des Algorithmus
- zeige, dass das Problem (nicht der Algorithmus) untere Komplexitätsschranke hat
- wenn untere Schranke des Problems = Klasse des Algorithmus
	- ➔ optimal

