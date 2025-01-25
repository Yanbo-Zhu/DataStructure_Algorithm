
# 1 Idee

- ein ADT beschreibt was passiert, aber noch nicht wie
- Beispiel: ganze Zahlen mit Addition
	- neutrales Element 0
	- inverses Element von a: -a
	- Operation: Summe zweier Elemente (aber wie bildet man die Summe?)
- Beispiel: ganze Zahlen mit Multiplikation
	- neutrales Element 1
	- inverses Element von a: 1/a
	- Operation: Produkt zweier Elemente (aber wie bildet man das Produkt?)


# 2 Zweck

- Trennung von Struktur und Implementierung
	- kann man z.B. in formalen Semantiken oder Programmverifikationen benutzen
	- algorithmische Betrachtungsweise: Vor- und Nachteile gewisser Datentypen/-strukturen (z.B. Suche in einem Baum n log(n) )
- programmatische Betrachtungsweise: garantiertes Verhalten des Interfaces (Contract)
- viele Implementierungen für einen Datentyp möglich
	- z.B. Listen in Java:
	- mit Arrays ArrayList
	- mit Referenzknoten LinkedList
- unterschiedliche Realisierungen können unterschiedliches Laufzeitverhaltendesselben abstrakten Datentypen haben

# 3 Begriffe
- abstrakter Datentyp (logische Ebene):
	- Wertebereich (Menge von Objekten) und darauf definierten Operationen, die Menge der Operationen ist die Schnittstelle
	- eine Datentypbeschreibung ohne Implementierung
-  Datenstruktur (technische Ebene):
	- Beschreibung einer Organisation über den Daten, z.B. um bestimmte Operationen effizient zu gestalten
	- konkrete Implementierung der Daten eines abstrakten Datentyps
- (konkreter) Datentyp (logische und technische Ebene):
	- fundamentale Einheit in einer Domäne (z.B. Hochsprache: primitive & eigene)
	- besitzt Eigenschaften und Fähigkeiten (z.B. Integer: ganzzahlig)
	- elementarer Datentyp kann evtl. wieder zerlegt werden (Integer -> Bitfolge)

Beispiel
• abstrakter Datentyp (logische Ebene):
- Ganzzahl a.k.a. Integer
• Datenstruktur (technische Ebene):
- Bitfolgen fester Länge `(byte[4])`
- Wrapper um ein int (Integer)
- Ganzzahlfolgen dynamischer Länge int[] (BigInteger)
• (konkreter) Datentyp (logische und technische Ebene):
- int
- Integer
- BigInteger

# 4 Zusammenhänge:

![[03_DataStructure/image/Pasted image 20250125213838.png]]


![[03_DataStructure/image/Pasted image 20250125213903.png]]


# 5 abstrakter Datentyp (ADT)

Ein abstrakter Datentyp (ADT) besteht aus einer
- Datenstruktur-Deklaration und einer
- Menge von Operationen auf dieser Datenstruktur.

Abstrakte Datentypen
• Ein abstrakter Datentyp (ADT) besteht aus einem Wertebereich (d.h. einer Menge von Objekten) und darauf definierten Operationen.
• Die Menge der Operationen bezeichnet man auch als Schnittstelle des Datentyps.
• Eine Datenstruktur ist eine Realisierung bzw. Implementierung eines ADT.

## 5.1 Operationen eines ADTs

Die Operationen eines ADTs können in drei Gruppen eingeteilt werden:
• Konstruktoren: Sie erzeugen ein neues Objekt und liefern eine Referenz darauf.
• Zugriffsfunktionen: Sie liefern Informationen über ein Objekt
• Modifikatoren: Sie modifizieren ein Objekt




