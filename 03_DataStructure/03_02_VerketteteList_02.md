

# 1 ADT Element/Knoten


- enthält einen Schlüssel zur eindeutigen Identifizierung, Schlüssel kann z.B sein: Index, Referenz, String …
- lässt sich immer als Integer darstellen
- die eigentlichen Daten sind bei abstrakter Betrachtung nicht wichtig
- für Operationen reicht Identifizierung aus

![[03_DataStructure/image/Pasted image 20250125214530.png]]

# 2 ADT Liste

Eine Liste ist eine sortierte Oder unsortierte Folge von Elementen. Eine Liste kann leer sein, Oder den folgenden Bedingungen genügen:
• Es gibt ein besonderes Element, das erste Element, genannt Kopf.
• Die weiteren Elemente formen wieder eine Liste, genannt Rest.

- ein paar mögliche Implementierungen:
- mit Arrays (Java: ArrayList)
- mit Knoten
	- einfach verkettet
	- doppelt verkettet
	- hierarchisch verkettet (SkipList)


![[03_DataStructure/image/Pasted image 20250125214716.png]]


![[03_DataStructure/image/Pasted image 20250125214722.png]]

# 3 Einfach verkettete Listen

![[03_DataStructure/image/Pasted image 20250125214632.png]]



# 4 Doppelt verkettete Listen


Implementierungsalgorithmen von ADT-Operationen für doppelt verkettete Listen


![[03_DataStructure/image/Pasted image 20250125215054.png]]

![[03_DataStructure/image/Pasted image 20250125215101.png]]

## 4.1 insert 

Laufzeitkomplexität 
• Einfügen am Kopf O(1)
• Einfügen am Ende O(1)
• Einfügen hinter gesuchtem Element O(n)

![[03_DataStructure/image/Pasted image 20250125220118.png]]


![[03_DataStructure/image/Pasted image 20250125215141.png]]


## 4.2 delete

Laufzeitkomplexität
• Löschen mit Vergleich O(n)
• Löschen am Kopf O(1)
• Löschen am Ende O(1)

![[03_DataStructure/image/Pasted image 20250125220342.png]]]]

![[03_DataStructure/image/Pasted image 20250125220355.png]]

## 4.3 Suchen 

• Suchen: O(n)
![[03_DataStructure/image/Pasted image 20250125220012.png]]

# 5 Laufzeiten einer einfach und doppelt verketteten Liste


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

# 6 Speicheraufwand von Listenimplementierungen

• ArrayList
- nur die Elemente O(n)
• LinkedList
- Elemente, Nachfolgerreferenzen O(2n)
• DoubleLinkedList
- Elemente, Vorgänger- und Nachfolgerreferenzen O(3n)
• aber: Referenzen haben feste Größe, die Elemente können sehr große Objekte sein
- → Speicher-Overhead für Referenzen normalerweise vernachlässigbar



# 7 通过 Liste 可以实现其他ADT

• Stack
• Queue
• PriorityQueue
• Dictionary
• Bäume

![[97_Spickzettel/image/Pasted image 20250125221632.png]]

## 7.1 Stack  (LIFO)

![[97_Spickzettel/image/Pasted image 20250125221718.png]]

Ein Stapel bzw. Keller Oder stack ist eine lineare Datenstruktur von
Elementen, bei der das Lesen, Einfügen und Löschen von Elementen nur an einem Ende (top Of stack) vorgenommen werden kann. Diese Modifikationsstrategie Wird auch last-in first-out (LIFO) genannt.


## 7.2 Queue (FIFO)

Eine Warteschlange bzw. queue ist eine lineare Datenstruktur von Elementen, bei der das Einfügen von Elementen nur am Ende und das Lesen und Löschen nur am Anfang vorgenommen werden kann.

Diese Modifikationsstrategie Wird auch first-in first-out (FIFO) genannt.


![[97_Spickzettel/image/Pasted image 20250125221826.png]]

## 7.3 PriorityQueue

Eine Prioritäts-Warteschlange bzw. priority queue ist eine sortierte Datenstruktur von Elementen, bei der das Einfügen von Elementen entsprechend der Sortierung und das Lesen und Löschen nur am Anfang vorgenommen werden kann.

SIMO - Prinzip (sort in, max out)

![[97_Spickzettel/image/Pasted image 20250125222036.png]]

## 7.4 Dictionary 

Ein Lexikon bzw. dictionary, auch assoziatives Array, ist eine Datenstruktur zum Speichern und Verwalten von Elementen. Die Elemente bestehen aus einem Schlüssel (key) und den weiteren Daten. 

Auf sie Wird ausschließlich über ihren Schlüssel zugegriffen, jeder Schlüssel darf maximal einmal vorkommen.


• Key/Value-Prinzip
• Key = unabhängiger, verallgemeinerter Index

![[03_DataStructure/image/Pasted image 20250125222237.png]]







