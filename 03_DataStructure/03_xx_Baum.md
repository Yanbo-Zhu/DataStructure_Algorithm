
# 1 Baum

• Graph: Knoten und Kanten
• Baum ist ein gerichteter azyklischer Graph
• jeder Knoten hat höchstens einen Elternknoten, aber viele Kindknoten
• binärer Baum: Jeder Knoten hat maximal 2 Kindknoten

![[03_DataStructure/image/Pasted image 20250125222630.png]]

# 2 Bezeichnungen


Eine binärer Baum (Binärbaum) ist eine Menge von Elementen, genannt Knoten. Ein binärer Baum kann leer sein, Oder den folgenden Bedingungen genügen:
• Es gibt ein besonderes Element, genannt Wurzel.  只有一个 wuzel 
• Die weiteren Elemente sind in zwei disjunkte Teilmengen geteilt, jede formt wieder einen binären Baum. Eine Teilmenge Wird linker Unterbaum, die andere Wird rechter Unterbaum genannt. 每个元素只最多两个 kind-element 

Bezeichnungen
• Baum hat:
- einen Wurzelknoten
- innere Knoten
- Blätter
• jeder Knoten hat maximal 2 Kindknoten
• jeder Knoten ist Wurzel eines Unterbaums

![[03_DataStructure/image/Pasted image 20250125223441.png]]


# 3 Knotenstruktur

![[03_DataStructure/image/Pasted image 20250125224027.png]]

# 4 Höhe/Ebenen/Tiefe
• jeder Knoten hat Entfernung zur Wurzel
• Anzahl der Verweise von der Wurzel aus = Ebene eines Knoten
• Anzahl der Verweise auf Wurzel von Wurzel aus? 0  , Wurzel ist Ebene 0
• Ebene nennt man auch Tiefe
• maximale Ebene/Tiefe = Höhe eines Baums
	→ Baum mit nur Wurzel hat Höhe 0

从0 开始 

![[03_DataStructure/image/Pasted image 20250125224843.png]]

# 5 Knotenanzahl

Knotenanzahl pro Ebene: $2^d$
![[03_DataStructure/image/Pasted image 20250125224957.png]]


Knotenanzahl des Baums:  $2^{h+1} - 1$

![[03_DataStructure/image/Pasted image 20250125225056.png]]


# 6 Mindesthöhe durch Knotenanzahl

Ein Binärbaum mit n Knoten hat mindestens eine Höhe von $log_{2}n$ 

![[03_DataStructure/image/Pasted image 20250125225209.png]]


# 7 Vollständigkeit (Vollständiger Baum)

![[03_DataStructure/image/Pasted image 20250125225232.png]]

# 8 Methode
## 8.1 Get Node 


Die Laufzeit dieser Zugriffsfunktionen ist weder von der Knotenanzahl noch von der Höhe des Baumes abhängig. Sie haben also eine konstante Zeitkomplexität.

![[03_DataStructure/image/Pasted image 20250125225348.png]]

### 8.1.1 Finde die Wurzel eines Baums von einem Knoten aus

Laufzeit?
- wenn HÖhe minimal O(ld n)
- wenn HÖhe maximal O(n)

![[03_DataStructure/image/Pasted image 20250125231133.png]]

![[03_DataStructure/image/Pasted image 20250125231146.png]]


## 8.2 Operation  Bei unsortiertem Binärbaum


## 8.3 Suchen 

• Bei unsortiertem Binärbaum?
- im schlimmsten Fall muss ganzer Baum durchsucht werden
- kein Vorteil der Datenstruktur gegenüber Liste
- aber höherer Verwaltungsaufwand

## 8.4 Einfugen 


• bei unsortiertem Binärbaum
- wie einfügen vor Knoten
- wie einfügen nach Knoten
• mehrere Möglichkeiten
- z.B. „Füge 4 vor 3 ein.“
- z.B. „Füge 4 nach 2 ein.“
• Beispiel rechts:
- mehrdeutige Möglichkeiten für „Füge 4 nach 2 ein.“

![[03_DataStructure/image/Pasted image 20250125231250.png]]


## 8.5 Löschen

• bei unsortiertem Binärbaum
- wie nach löschen neu gruppieren
• Beispiel rechts:
- wieder mehrere Möglichkeiten

![[03_DataStructure/image/Pasted image 20250125231317.png]]


# 9 Operation bei sortiertem Binärbaum

sortierter Binärbaum: → binärer Suchbaum

Ein binärer Suchbaum ist ein binärer Baum mit der folgenden Eigenschaft. Es sei a: ein beliebiger Knoten des binären Suchbaums.
• Ist y ein beliebiger Knoten aus dem linken Unterbaum von x, dann gilt y.key < x. key.
• Ist y ein beliebiger Knoten aus dem rechten Unterbaum von x, dann gilt y.key > x.key.


![[03_DataStructure/image/Pasted image 20250125231701.png]]



## 9.1 Suchen:
- auf jeder Ebene Entscheidung möglich, in welchem Unterbaum nicht weitergesucht werden muss

## 9.2 Einfügen / Löschen:
- Sortiereigenschaft muss erhalten bleiben

![[03_DataStructure/image/Pasted image 20250125231509.png]]


## 9.3 Traversieren Breitensuche und Tiefensuche 

traversieren: eine Route bestimmen, wobei jede Kante und jeder Knoten genau einmal besucht wird, z.B. Breiten-/oder Tiefensuche bei Bäumen


![[03_DataStructure/image/Pasted image 20250125231751.png]]



