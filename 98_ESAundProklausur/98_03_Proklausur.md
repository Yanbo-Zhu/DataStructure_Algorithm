
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

## 2.2 Algorithmus 1.2 (A2)

![[98_ESAundProklausur/image/Pasted image 20250120102117.png]]

## 2.3 Algorithmus 1.3 (A3)

![[98_ESAundProklausur/image/Pasted image 20250120102131.png]]


## 2.4 Algorithmus 1.4 (A4)

![[98_ESAundProklausur/image/Pasted image 20250120102146.png]]


# 3 Analyse von Algorithmen

Gegeben sei der folgende Algorithmus zur Bestimmung, ob ein Feld ueberall ohne Luecken steigendoder fallend ist (Beispiel: (1, 2, 3, 2, 3) !true, (1, 2, 4, 3) !false):

![[98_ESAundProklausur/image/Pasted image 20250120102605.png]]


(a) Bestimmen Sie die Eingabegröße bzw. die Eingabegrößen.
(b) Welches ist die grundlegende Anweisung zur Bestimmung der Zeitkomplexität bei NoGap1?
(c) Wie häufig wird die grundlegende Anweisung im schlechtesten Fall ausgeführt (exakt)?
(d) Geben Sie die Zeitkomplexität im schlechtesten Fall in asymptotischer Notation an, ohne Beweis.
(e) Welche Eingaben führen zum schlechtesten Fall, welche Eingaben sind schneller verarbeitet?
(f) Gibt es Fälle, in denen der Algorithmus nicht korrekt funktioniert?
(g) Gibt es einen Algorithmus, der dieselbe Aufgabe im schlechtesten Fall effizienter löst? Welcher? Welche Komplexität?


# 4 Asymptotische Notation

Geben Sie fur jede der folgenden Funktionen an, in welcher asymptotischen Klasse sie liegt.

![[98_ESAundProklausur/image/Pasted image 20250120102659.png]]


# 5 Rekursiver Algorithmus

a) Stellen Sie die Rekursionsgleichung zur Bestimmung der Zeitkomplexität des Algorithmus Re-kAlg6 in Abhängigkeit von der Eingabegrösse auf und geben Sie an, welches die für die Zeitkomplexität relevante Eingabegröße ist. (Vernachlassigen Sie dabei die Gaussklammern.)

(b) Bestimmen Sie die Zeitkomplexität des Algorithmus RekAlg6.


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


















