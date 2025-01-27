
# 1 Algorithmus

## 1.1 a

a) Ist fur die Ausfuehrung eines Algorithmus folgendes erforderlich? Erlaeutern Sie jeweils warum oder warum nicht.
• Computer:
• Programm:
• Eingabe:
• Ausgabe:

---

**Computer:**
- **Erforderlich?** Nein.
- **Erläuterung:** Algorithmen sind abstrakte Konzepte und können unabhängig von einem Computer existieren. Sie können auch von Menschen "ausgeführt" werden, z. B. durch manuelles Berechnen. Allerdings wird ein Computer benötigt, wenn der Algorithmus automatisiert oder effizient auf großen Datenmengen ausgeführt werden soll.

**Programm:**
- **Erforderlich?** Nein.
- **Erläuterung:** Ein Algorithmus ist eine präzise Folge von Anweisungen und kann in natürlicher Sprache, Pseudocode oder Diagrammen dargestellt werden. Ein Programm ist lediglich eine Möglichkeit, einen Algorithmus in einer für Maschinen verständlichen Form (z. B. in einer Programmiersprache) umzusetzen.

**Eingabe:**
- **Erforderlich?** Ja, meistens.
- **Erläuterung:** Die meisten Algorithmen benötigen Eingaben, um eine sinnvolle Ausgabe zu erzeugen. Es gibt jedoch Algorithmen (z. B. Konstantberechnungen oder Simulationen), die ohne externe Eingaben funktionieren, indem sie mit festen Werten arbeiten.

**Ausgabe:**
- **Erforderlich?** Nein, aber üblich.
- **Erläuterung:** Algorithmen liefern häufig eine Ausgabe, da sie in der Regel entwickelt werden, um Probleme zu lösen oder Ergebnisse zu berechnen. Es gibt jedoch Algorithmen, die nur interne Berechnungen durchführen oder Nebenwirkungen erzeugen (z. B. Zustandsänderungen in einem System), ohne explizit eine Ausgabe zurückzugeben.



## 1.2 b

(b) Ist Sortieren durch Raten einer Permutation ein effizienter Algorithmus? Erlautern Sie die

Nein, es ist kein effizienter Algorithmus.

Das **"Raten einer Permutation"** beschreibt eine naive und extrem ineffiziente Methode, um eine Liste zu sortieren. Hierbei wird einfach jede mögliche Anordnung (Permutation) der Liste überprüft, bis die richtige (sortierte) gefunden wird.

"Sortieren durch Raten einer Permutation" bedeutet, alle möglichen Permutationen der gegebenen Liste zu generieren und zu prüfen, welche Permutation die geordnete (sortierte) Version der Liste ist.

**Laufzeitkomplexität:**
- Die Anzahl der Permutationen einer Liste mit n Elementen beträgt n!n!n! (Fakultät von nnn).
- Das Prüfen jeder Permutation, um festzustellen, ob sie sortiert ist, dauert O(n).
- Die Gesamtzeitkomplexität ist daher O(n⋅n!), was extrem ineffizient ist.

**Vergleich mit effizienten Algorithmen:**
- Effiziente Sortieralgorithmen wie Quicksort, Mergesort oder Heapsort haben eine Zeitkomplexität von O(nlog⁡n), was für große n viel schneller ist als n!.

**Ablauf:**
1. **Generiere alle Permutationen:**
    - Für eine Liste der Länge nnn gibt es n!n!n! mögliche Permutationen (Fakultät von nnn).
    - Beispiel: Für die Liste [3,1,2][3, 1, 2][3,1,2] wären die Permutationen [3,1,2][3, 1, 2][3,1,2], [3,2,1][3, 2, 1][3,2,1], [1,3,2][1, 3, 2][1,3,2], [1,2,3][1, 2, 3][1,2,3], [2,3,1][2, 3, 1][2,3,1], [2,1,3][2, 1, 3][2,1,3].
2. **Prüfe jede Permutation:**
    - Jede generierte Permutation wird darauf überprüft, ob sie sortiert ist.
    - Beispiel: Für die obige Liste ist die sortierte Permutation [1,2,3][1, 2, 3][1,2,3].


## 1.3 c
(c) Welche der folgenden Eigenschaften werden von Algorithmen ublicherweise gefordert? Unterstreichen Sie die korrekten Eigenschaften:

Eine Festlegung des Folgeschrittes nach jedem Schritt, ausschliesslich effektiv ausfuhrbare Operationen, maximal 100 Zeilen, endliche Beschreibung, Beschreibung mit ASCII- oder Unicode-Zeichen, hat mindestens zwei Eingaben, alle Anweisungen werden bei jeder Eingabe mindestens einmal ausgefuhrt, ist beweisbar korrekt.

- A determination of the next step after each step
- Only effectively executable operations
- Maximum of 100 lines
- Finite description
- Description using ASCII or Unicode characters
- Has at least two inputs
- All instructions are executed at least once for every input
- Is provably correct

---

答案

Von Algorithmen werden üblicherweise die folgenden Eigenschaften gefordert (korrekt unterstrichen):
- **Eine Festlegung des Folgeschrittes nach jedem Schritt**
- **Ausschließlich effektiv ausführbare Operationen**
- **Endliche Beschreibung**
- **Ist beweisbar korrekt**

**Begründung:**
- **Festlegung des Folgeschrittes:** Algorithmen müssen deterministisch oder klar definiert sein, um einen Zustand zum nächsten überführen zu können.
- **Effektiv ausführbare Operationen:** Alle Schritte eines Algorithmus müssen von einer Maschine oder Person ausführbar sein.
- **Endliche Beschreibung:** Ein Algorithmus muss mit einer begrenzten Menge von Anweisungen beschrieben werden können.
- **Beweisbare Korrektheit:** Algorithmen sollten theoretisch nachweisbar korrekt sein, d. h., sie liefern für jede gültige Eingabe das erwartete Ergebnis.

Die folgenden Eigenschaften sind **nicht erforderlich**:
- **Maximal 100 Zeilen:** Die Länge eines Algorithmus ist irrelevant, solange er seine Aufgabe korrekt erfüllt.
- **Beschreibung mit ASCII- oder Unicode-Zeichen:** Algorithmen können in jeder geeigneten Darstellung beschrieben werden.
- **Hat mindestens zwei Eingaben:** Ein Algorithmus kann mit einer oder mehreren Eingaben arbeiten.
- **Alle Anweisungen werden bei jeder Eingabe mindestens einmal ausgeführt:** Manche Anweisungen (z. B. in Schleifen oder bedingten Anweisungen) werden möglicherweise nicht bei jeder Eingabe ausgeführt.


# 2 Doppelt verkettete Liste

Die folgenden Algorithmen agieren alle auf einer doppelt verketteten Liste. Bestimmen Sie jeweils, was der Algorithmus macht und welche Komplexitaet er hat (abhaengig von der Laenge der Liste n).
Gibt es Faelle, in denen der Algorithmus nicht korrekt funktioniert?

## 2.1 Algorithmus 1.1 (A1)

![[98_ESAundProklausur/image/Pasted image 20250120102050.png]]

Algorithmus 1.1 (A1)
Eingabe: l: Liste, x: Zahl
Ausgabe: ??
A1(l; x)
1 y   l:head
2 while y 6= nil ^ y:key 6= x do
3 y   y:next
4 return y

Suchen Funktion 

Komplexität: 
- **O(n)** im Worst Case, wobei nnn die Anzahl der Knoten in der Liste ist. Dies tritt ein, wenn der gesuchte Wert entweder am Ende der Liste liegt oder nicht in der Liste enthalten ist.
- **O(k)** im Best Case, wobei kkk die Position des gesuchten Knotens vom Anfang der Liste ist (falls er früh gefunden wird).

Die Funktion ist **korrekt**, da sie:
- Den Kopf der Liste als Startpunkt nimmt und jeden Knoten linear besucht.
- Den Schlüssel des aktuellen Knotens mit xxx vergleicht und, falls er übereinstimmt, den Knoten zurückgibt.
- Falls kein passender Knoten gefunden wird, endet die Schleife bei y=nily = \text{nil}y=nil, und die Funktion gibt korrekt nil\text{nil}nil zurück.



## 2.2 Algorithmus 1.2 (A2)

![[98_ESAundProklausur/image/Pasted image 20250120102117.png]]

Algorithmus 1.2 (A2)
Eingabe: l: Liste, x: Zahl
Ausgabe: ??
A2(l; x)
11 y   l:head
12 z   0
13 while y 6= nil do
14 y   y:next
15 z   z + 1
16 return z


Die Funktion berechnet die Länge der Liste lll und gibt diese zurück.

**O(n)** im Worst Case, wobei nnn die Anzahl der Knoten in der Liste ist. Jeder Knoten wird genau einmal besucht, bis die Liste vollständig durchlaufen ist.

Die Funktion ist korrekt, da sie die Liste systematisch durchläuft und die Anzahl der Knoten zählt. xxx hat keine Relevanz für den Algorithmus.

## 2.3 Algorithmus 1.3 (A3)

![[98_ESAundProklausur/image/Pasted image 20250120102131.png]]

Algorithmus 1.3 (A3)
Eingabe: l: Liste, x: Zahl
Ausgabe: ??
A3(l; x)
21 y   l:tail
22 z   0
23 while z < x do
24 y   y:prev
25 z   z + 1
26 return y


find the  x-th element form End of the List L 
Die Funktion A3(l,x)A3(l, x)A3(l,x) gibt den **x-ten Knoten von hinten** einer doppelt verketteten Liste l zurück. Wenn x größer als die Länge der Liste ist, wird eine falsche Referenz oder ein ungültiger Wert zurückgegeben (abhängig von der Implementierung).

**O(x)** im Worst Case, da x Schritte von l.taill aus durchgeführt werden. Die restliche Liste wird nicht durchsucht.


Nicht Korrekt,  wenn  x > length of List l 



## 2.4 Algorithmus 1.4 (A4)

![[98_ESAundProklausur/image/Pasted image 20250120102146.png]]

Algorithmus 1.4 (A4)
Eingabe: l: Liste, x: Zahl
Ausgabe: ??
A4(l; x)
31 y   l:head
32 while y 6= nil ^ y:key 6= x do
33 y   y:next
34 repeat
35 y:prev:next   y:next
36 y:next:prev   y:prev
37 return y

Der Algorithmus A4(l,x)A4(l, x)A4(l,x) durchsucht eine doppelt verkettete Liste lll nach einem Knoten mit dem Schlüssel xxx und entfernt ihn, falls er gefunden wird. Anschließend gibt er diesen Knoten zurück.

**O(n)** im Worst Case, da der Algorithmus die Liste linear durchsucht, bis der Knoten yyy gefunden wird oder das Ende der Liste erreicht ist.

**Korrektheit:**
- Korrekt, wenn die Liste doppelt verkettet ist und korrekt implementiert wurde.
- Robust für leere Listen und nicht vorhandene Schlüssel.


# 3 Analyse von Algorithmen

Gegeben sei der folgende Algorithmus zur Bestimmung, ob ein Feld ueberall ohne Luecken steigendoder fallend ist (Beispiel: (1, 2, 3, 2, 3) !true, (1, 2, 4, 3) !false):

![[98_ESAundProklausur/image/Pasted image 20250120102605.png]]

Gegeben sei der folgende Algorithmus zur Bestimmung, ob ein Feld uberall ohne Lucken steigend
oder fallend ist (Beispiel: (1; 2; 3; 2; 3) !true, (1; 2; 4; 3) !false):
Algorithmus 2.5 (NoGap1)
Eingabe: A = (a1; : : : ; an) mit ai; i; n 2 N; 1  i  n; x 2 N
Ausgabe: true wenn ai = ai + 1  1 alle 1  i < n
NoGap1(A)
1 for i   2 to n 􀀀 1 do
2 for j   i 􀀀 1 to i + 1 do
3 if j  1 ^ j  n ^ j A[i] 􀀀 A[j] j  2 then
4 return false
5 return true


```python
for i <- 2 to n-1 do
	for j <- i-1 to i+1 do
		if j >= 1 and j <= n and  |A[i] - A[j]| >= 2 then
			return false
return true
```

(a) Bestimmen Sie die Eingabegröße bzw. die Eingabegrößen.
(b) Welches ist die grundlegende Anweisung zur Bestimmung der Zeitkomplexität bei NoGap1?
(c) Wie häufig wird die grundlegende Anweisung im schlechtesten Fall ausgeführt (exakt)?
(d) Geben Sie die Zeitkomplexität im schlechtesten Fall in asymptotischer Notation an, ohne Beweis.
(e) Welche Eingaben führen zum schlechtesten Fall, welche Eingaben sind schneller verarbeitet?
(f) Gibt es Fälle, in denen der Algorithmus nicht korrekt funktioniert?
(g) Gibt es einen Algorithmus, der dieselbe Aufgabe im schlechtesten Fall effizienter löst? Welcher? Welche Komplexität?Z


## 3.1 a
Bestimmen Sie die Eingabegröße bzw. die Eingabegrößen.

A = (a1; : : : ; an) mit Length n 


## 3.2 b
Welches ist die grundlegende Anweisung zur Bestimmung der Zeitkomplexität bei NoGap1?

Zeile 3 
`if j  1 ^ j  n ^ j A[i] 􀀀 A[j] j  2 `


## 3.3 c
Wie häufig wird die grundlegende Anweisung im schlechtesten Fall ausgeführt (exakt)?

3 ( n -2 )  =  3n -6 

## 3.4 d
(d) Geben Sie die Zeitkomplexität im schlechtesten Fall in asymptotischer Notation an, ohne Beweis.

O(n)

## 3.5 e
(e) Welche Eingaben führen zum schlechtesten Fall, welche Eingaben sind schneller verarbeitet?

Der schlechteste Fall tritt ein, wenn die Bedingung in der `if`-Anweisung nie erfüllt ist, sodass der Algorithmus **die gesamte Schleife** vollständig durchläuft. Dies geschieht, wenn das Array AAA durchgängig die Bedingung ∣A[i]−A[j]∣<2|A[i] - A[j]| < 2∣A[i]−A[j]∣<2 erfüllt. Beispiele:
A=(1,2,3,2,3)oderA=(5,6,5,6,5).

---


Der Algorithmus terminiert schneller, wenn die Bedingung ∣A[i]−A[j]∣≥2|A[i] - A[j]| \geq 2∣A[i]−A[j]∣≥2 früh erfüllt wird, da er dann `false` zurückgibt und nicht weiter iteriert. Dies geschieht, wenn bereits ein früher Wert im Array eine Differenz von 2 oder mehr aufweist. Beispiele:

A=(1,2,4,3)  (Abbruch in der zweiten Iteration).


## 3.6 f
(f) Gibt es Fälle, in denen der Algorithmus nicht korrekt funktioniert?

**Leere oder zu kurze Arrays:**  
Wenn n<2  ist der Algorithmus nicht anwendbar, da die Schleifen nicht korrekt initialisiert werden können.

## 3.7 g
(g) Gibt es einen Algorithmus, der dieselbe Aufgabe im schlechtesten Fall effizienter löst? Welcher? Welche Komplexität?


```python
for i <- 2 to n-1 do
	for j <- i-1 to i+1 do
		if j >= 1 and j <= n and  |A[i] - A[j]| >= 2 then
			return false
return true
```


Der gegebene Algorithmus hat eine **Zeitkomplexität von O(n)O(n)O(n)** im schlechtesten Fall, da er jeden Eintrag im Array AAA maximal 3-mal prüft. Es ist daher **schwer, einen effizienteren Algorithmus** für diese Aufgabe zu finden, da der Algorithmus bereits linear ist.

Ein alternativer Ansatz könnte sein:
1. Den Abstand zwischen aufeinanderfolgenden Elementen direkt zu prüfen, statt eine verschachtelte Schleife zu verwenden.
2. Diese Überprüfung läuft in einer **einfachen Schleife über das Array A:**

---

**Optimierter Algorithmus:**

```
def NoGapOptimized(A):
    for i in range(1, len(A)):
        if abs(A[i] - A[i-1]) >= 2:
            return False
    return True
```

**Komplexität:**
- **Schlechtester Fall:** O(n)O(n)O(n), da jedes Paar von Elementen genau einmal verglichen wird.
- **Effizienz:** Dieser Ansatz hat dieselbe **asymptotische Komplexität** wie der ursprüngliche Algorithmus, ist aber praktisch schneller, da er weniger Vergleiche durchführt (kein i+1i+1i+1 oder i−1i-1i−1).

# 4 Asymptotische Notation

Geben Sie fur jede der folgenden Funktionen an, in welcher asymptotischen Klasse sie liegt.

![[98_ESAundProklausur/image/Pasted image 20250120102659.png]]


![[98_ESAundProklausur/image/Pasted image 20250127010655.png]]


![[98_ESAundProklausur/image/Pasted image 20250127010703.png]]


![[98_ESAundProklausur/image/Pasted image 20250127010711.png]]

![[98_ESAundProklausur/image/Pasted image 20250127010720.png]]

![[98_ESAundProklausur/image/Pasted image 20250127010730.png]]



# 5 Rekursiver Algorithmus

![[98_ESAundProklausur/image/Pasted image 20250127014034.png]]

a) Stellen Sie die Rekursionsgleichung zur Bestimmung der Zeitkomplexität des Algorithmus Re-kAlg6 in Abhängigkeit von der Eingabegrösse auf und geben Sie an, welches die für die Zeitkomplexität relevante Eingabegröße ist. (Vernachlassigen Sie dabei die Gaussklammern.)

Eingabegröße =n 

T(n) = 1 , falls n =1 

b =5 , c =2, f(n) = n^2


(b) Bestimmen Sie die Zeitkomplexität des Algorithmus RekAlg6.

k =2 
b(1/c)^k =   5/4 > 1

a= ln5/ ln 2 


# 6 Min-Heap

Ein Feld von paarweise verschiedenen Schlüsseln ist mit dem Algorithmus Heapsort absteigend zu sortieren. Dazu wird zunächst ein Min-Heap erzeugt. Gegeben seien die Algorithmen Build-Min-Heap und Heapify-Min. Betrachte das Feld A = 8, 3, 7, 6, 5, 4, 2, 1

![[98_ESAundProklausur/image/Pasted image 20250120103438.png]]

(a) Wie viele Schlüsselvergleiche sind in der Heap-Konstruktions-Phase (Algorithmus Build-Min-Heap) für A durchzuführen?
(b) Geben Sie das Feld A nach der Heap-Konstruktions-Phase an.
(c) Ist ein aufsteigend sortiertes Feld ein bester Fall, schlechtester Fall oder mittlerer Fall für den Algorithmus Build-Min-Heap? Wie ist die gegebene Eingabe im Vergleich einzuschätzen?
Begründen Sie Ihre Antwort.
(d) Welche Höhe hat ein Min-Heap, der n Elemente enthält? Geben Sie die Höhe exakt als Funktion von n an. Welche Höhe hat demzufolge der oben konstruierte Heap des Feldes A (Hinweis: Ein Heap mit n = 1 hat die Höhe h = 0)?


# 7 Hashing

Betrachte eine Hashtabelle `T[0..11]` mit offener Adressierung und einer Hashfunktion mit linearer Sondierung, i = 0, 1, 2, . . . . 
Die in die Hashtabelle einzutragenden Datensätze bestehen nur aus den Schlüsseln $k \in N$ 

![[98_ESAundProklausur/image/Pasted image 20250120104116.png]]

Die Hashtabelle ist initial leer.
(a) Fügen Sie in dieser Reihenfolge die Schlüssel 1, 5, 12, 4, 10, 3 ein. Wo werden diese Schlüssel in der Hashtabelle T eingefügt?
(b) Löschen Sie den Schlüssel 1 in der Hashtabelle. Wie wird der entsprechende Eintrag in der Hashtabelle verändert? Begründung in eigenen Worten!
(c) Handelt es sich bei der gegebenen Hashfunktion h' um eine gute Hashfunktion? Begründung in eigenen Worten!

![[98_ESAundProklausur/image/Pasted image 20250120104701.png]]


















