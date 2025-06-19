

# 1 重点 


Hash-Tabellen
- Was ist offenes/geschlossenes Hashing

![[03_DataStructure/image/Pasted image 20250125173608.png]]

Hash-Funktionen
- Was ist eine gute/schlechte Hashfunktion?
- Was ist der Belegungsfaktor
- Was sind Kollisionen?
- Was ist Sondieren und warum braucht man das?
- Warum Hashing? Vorteil gegenüber was?


# 2 Überblick

- to hash: zerhacken hash function: Streuwertfunktion
- bildet potentiell große Eingabemenge auf kleine Zielmenge ab
- „häckselt“ die Eingabedaten in die kleine Zielmenge hinein
- Wozu? Effiziente Methode, Daten im Speicher schnell abzulegen und zu finden, ohne:
	- sortieren zu müssen
	- Sortierung zu erhalten

# 3 Key/value 


## 3.1 Motivation

- viele Programme / Anwendungen benötigen datenbankartige Speicherstrukturen
- typische Operationen:
	- Einfügen
	- Suchen
	- Ändern
	- Löschen
	- Sortieren
- wenn die Daten (Value) einen (eindeutigen) Schlüssel (Key) haben, kann man den ADT Dictionary benutzen
- Grundidee: Key/Value-Pair


## 3.2 ADT Dictionary 

- Diese Definition ADT Lexikon erlaubt nur eine eineindeutige Zuordnung von Key/Value
- Ein Lexikon bzw. dictionary, auch assoziatives Array, ist eine Datenstruktur zum Speichern und Verwalten von Elementen. Die Elemente bestehen aus einem Schlüssel (key) und den weiteren Daten. Auf sie Wird ausschließlich über ihren Schlussel  zugegriffen, •eder Schlüssel darf maximal einmal vorkommen.


![[03_DataStructure/image/Pasted image 20250126213901.png]]

Member() and Retrieve()
![[03_DataStructure/image/Pasted image 20250126213844.png]]


---

Existenzfälle:
- Key existiert nicht, Value existiert nicht : 这种情况允许存在 
- Key existiert nicht, Value existiert  : 这种情况不允许存在 
- Key existiert, aber Value nicht:  这种情况允许存在 
- Key und Value existieren : 这种情况允许存在 

---

Was ist eigentlich ein Dictionary?
• Menge von Key-Value-Paaren
• Key und Value können beliebiger Datentyp sein (die Datentypen müssen also nur Vergleichbarkeit implementieren)
• Mehrere Keys können auf dasselbe Value zeigen?   ja,   auf dasselbe Object verweisen
• Jeder Key zeigt auf sein Value? ja
• Ein Key kann mehrere Values haben?  Ja,   alle value in eine List.   Es ist erlaubt
• Ein Key kann nur ein Value haben? ja 


# 4 Adresstabellen



![[03_DataStructure/image/Pasted image 20250126214502.png]]


## 4.1 Laufzeit (O(1))

![[03_DataStructure/image/Pasted image 20250126222926.png]]




## 4.2 Wie ADT Dictionary implementieren

![[03_DataStructure/image/Pasted image 20250126214539.png]]


![[03_DataStructure/image/Pasted image 20250126214521.png]]


## 4.3 Probleme mit direkter Adressierung

![[03_DataStructure/image/Pasted image 20250126214628.png]]

![[03_DataStructure/image/Pasted image 20250126214734.png]]


# 5 Hashtabellen

- Adresstabelle mit direkter Adressierung: eingeschränkte Praktikabilität
- Adresstabelle mit indirekter Adressierung: ADT Dictionary
- großen Schlüsselraum auf kleinen Hashraum abbilden (nicht injektive Abbildung)
- Folgeproblem: Kollisionen  h(k1) = h(k2)

![[03_DataStructure/image/Pasted image 20250126220114.png]]

zwei key has dasselbe hashvalue
Kollision: Hash(k1) = hash (k2)
这种情况 建一个 key-chain



## 5.1 Adresstabellen mit indirektem Zugriff

![[03_DataStructure/image/Pasted image 20250126214749.png]]


## 5.2 Kollisionen

![[03_DataStructure/image/Pasted image 20250126214818.png]]

## 5.3 Indirect Retrieve/Insert/Delete

Werden die Kollisionen in Hashtabellen durch unsortierte doppelt verkettete Listen aufgelöst, dann lassen Sich die Such-, Einfüge- und Löschoperationen unter Benutzung der entsprechenden Listen-operationen 

![[03_DataStructure/image/Pasted image 20250126214911.png]]


## 5.4 Laufzeitbetrachtung

abhängig von „gutem“ Einsortieren, a.k.a. guter Hashfunktion
Jeder key has nicht mehr ein value

1  Besten fall
O(1)
每个 hashvalue 的位置 都只对应一个 datesatz(一个 key-value pair)

2 schlimmste Fall
die am schlimmsten einsortiert das heißt die würde immer Kollision produzieren
O(n)
就是 所有 key 对应的 hash value 都是相同的,  所有的 key-value-pair 都连在了同一个 list 上面

![[03_DataStructure/image/Pasted image 20250126215020.png]]


3 Average case 的时间复杂度 
![[03_DataStructure/image/Pasted image 20250126223218.png]]


M platz: 就是 下面 一共有多少个
![[03_DataStructure/image/Pasted image 20250126223139.png]]


n 是 这些是包含了n 个 element 
![[03_DataStructure/image/Pasted image 20250126223156.png]]


## 5.5 Belegungsfaktor

• Konsequenz aus dynamischer Belegung
• Unterbelegung
• Überbelegung
• exakte Belegung

- einfaches gleichmäßiges Hashing: sinnvolle Durchschnittsannahme für beliebige „gewünschte“ Hashfunktion
- genauere Betrachtungen dann für gewisse Klassen von Hashfunktionen

M platz: 就是 下面 一共有多少个
![[03_DataStructure/image/Pasted image 20250126223139.png]]


n 是 这些是包含了n 个 element 
![[03_DataStructure/image/Pasted image 20250126223156.png]]

![[03_DataStructure/image/Pasted image 20250126215237.png]]

---

Asymptotische Betrachtung des Belegungsfaktors
• wenn das Verhältnis von Plätzen zu Elementen gleich bleibt, bleibt auch der Zugriffsaufwand gleich
• andersrum gesagt: je voller die Hashtable, desto linearer wird der Zugriffsaufwand

![[03_DataStructure/image/Pasted image 20250126215326.png]]


# 6 Hashfunktionen

## 6.1 Definition

Gewünschte Eigenschaften:
• schnell
• kollisionsarm (gleichmäßig verteilend)
• bei kryptografischen Anwendungen: noch stärkere Anforderungen

## 6.2 Exkurs: kryptografische Hashfunktioen

- Standardanwendung: Passwortvergleich
	- Passwörter liegen nicht im Klartext, sondern nur gehasht in einer Datenbank
	- bei Passworteingabe wird der Hash gebildet und verglichen
	- bei Datenbank-Leak gehen keine Klartextpasswörter verloren

Eigenschaften:
- beliebige Eingabelänge
- feste Ausgabelänge (z.B. 128 Bit)
- Hashberechnung effizient für beliebige Eingabe
- Einwegfunktion: es ist praktisch unmöglich, aus einem Hashwert die Eingabe zu rekonstruieren
- schwache Kollisionsresistenz: es ist für eine feste Eingabe praktisch unmöglich, eine zweite Eingabe mit Kollision zu finden
- starke Kollisionsresistenz: es ist für verschiedene Eingaben praktisch unmöglich, eine Kollision zu erzeugen
- pseudozufällig: deterministisch, aber statistisch betrachtet nicht von echtem Zufall unterscheidbar

Bekannte kryptografische Hashfunktionen
• MD5 (Message-Digest Algorithm) unsicher
• SHA1 (Secure Hash Algorithm) unsicher
• SHA2, SHA3
• WEP ( Wired Equivalent Privacy) unsicher
• WPA (Wi-Fi Protected Access) unsicher
• WPA2, WPA3
• AES (Advanced Encryption Standard)

![[03_DataStructure/image/Pasted image 20250126220509.png]]


## 6.3 Konstruktion

• Wir wollen viele Elemente in einen kompakten (kleinen) Adressraum speichern.
• Wir akzeptieren Überschneidungen (Kollisionen).
• Am besten wäre gleichmäßiges Hashing.

![[03_DataStructure/image/Pasted image 20250126220533.png]]

## 6.4 Divisionsmethode

![[03_DataStructure/image/Pasted image 20250126220555.png]]

## 6.5 Multiplikationsmethode

• Schlüssel wird mit A skaliert und der ganze Teil entfernt
• dadurch wird Schlüssel auf Interval `[0, 1] `abgebildet
• schlußendlich mit Tabellengröße m multipliziert
• Wahl von A unabhängig von Wahl von m
• gute Wahl von A wichtig, möglichst irrational
• z.B. goldener Schnitt → Fibonacci-Hash

![[03_DataStructure/image/Pasted image 20250126220700.png]]


## 6.6 h(k) = ak mod m 

![[03_DataStructure/image/Pasted image 20250126220759.png]]

k mod m = (k + m) mod m
(a + b) mod n = (a mod n + b mod n) mod n.


![[03_DataStructure/image/Pasted image 20250126220822.png]]


## 6.7 Zusammenhang Divisions- und Multiplikationsmethode

![[03_DataStructure/image/Pasted image 20250126221222.png]]



# 7 Offene Adressierung

当一个 key 的 hash value 要组成一个 key kette 了, 组成一个 kette , 会增加查找难度,.  为了避免这个问题
需要 finde ich einen freien Platz in dieser Tabelle, 将这个key 存在 tablle 里  这个新的问题 , 这个就是 offene addressierung

- keine Kollisionsketten hinter einem Key mehr, sondern in der Hashtabelle selber
- entfernt dynamischen Speicherbedarf durch Ausnutzung des statisch vorhandenen
- Belegungsfaktor dann aber höchstens 1

Warum „offene Adressierung“:
weil sich die Kollisionskette über mehrere Keys verteilt

Warum „geschlossenes Hashing“:
weil die Kollisionskette nur erweitert werden kann, wenn noch Platz in der Hashtable ist

## 7.1 verschiedene Sondierungen


• Clustering: bei wiederholten Kollisionen bilden sich „Klumpen“
• z.B. quadratisches Sondieren verhindert die Cluster, die bei linearem Sondieren entstehen


![[03_DataStructure/image/Pasted image 20250126223842.png]]



### 7.1.1 Linear Sondierungen

![[03_DataStructure/image/Pasted image 20250126221807.png]]

通过 加 I 的方式 将 key 的 in table 的储存位置 mit offset manchen



## 7.2 Löschen


Vorsicht beim Löschen von Elementen!
• nur Markieren, d.h. nur logisch löschen, da sonst die Kollisionskette unterbrochen wäre
• aber logisch gelöschte Elemente können wieder beschrieben werden


Sind Elemente aus der Hashtabelle zu löschen, so dürfen diese nicht wieder mit <scshape> nil </scs
ha e> belegt werden. 
Die Plätze Sind nur als gelöscht zu markieren, da sonst die Kollisionsketten unterbrochen werden würden. 
Ein freier Platz kennzeichnet das Ende einer Kollisionskette und dahinter liegende Elemente würden nicht mehr gefunden werden. 
Als gelöscht markierte Plätze dürfen wieder besetzt werden.

## 7.3 Übung

• Sortieren Sie folgende Schlüssel ein (der Einfachheit halber sind Keys auch Values): 1, 5, 7, 3, 4
• Lösche Key 7

Sondierungsfolge
先用 h(k,0),   如果出现kollision, 用 h(k,1), 再出现 kollision, 再用 h(k,2), 以此类推 


---

Insert 1 
![[03_DataStructure/image/Pasted image 20250126221849.png]]


---

Insert 5

![[03_DataStructure/image/Pasted image 20250126221856.png]]


---

Insert 7

用 h (k,0) 出现kollision, 用下一个 sondierungsfunktion in sondierungsfolge: 3x7 mod 9 = 3   
用 h(k,1), 不出现 kollision:  3x7 +1 mod 9 = 4 

![[03_DataStructure/image/Pasted image 20250126221907.png]]

---
Insert 3
再用 h(k,0), 因为 3 没有出现 kollision

![[03_DataStructure/image/Pasted image 20250126221929.png]]


---
Insert 4  

出现kollision, 用下一个 sondierungsfunktion in sondierungsfolge

用 h(k,0), 有konllision,    3k = 12 mod9 = 3

再用 h(k,1) 还有 kollision  3k+1 =13 mod 9 = 4

再用 h(k,2), 再用 不在出现 koliision   3k+2 =14 mod 9 = 5

![[03_DataStructure/image/Pasted image 20250126221935.png]]

---

Lösche Key 7

人为 故意执行  loschne 7 之后,  pos 4 标记  值 = -1

![[03_DataStructure/image/Pasted image 20250126221942.png]]


## 7.4 Chaining vs. Offene Adressierung

Offene addressierung
152 处 先 存好 john smith
Sandra dee 应该存在 152, 但是已经有john smith, 有了 kollision. 根据与 sondierungfunktion, 存在  原本的位置  x+1 mod y , 存在原本的 位置 的 +1 处, 就是 存在 153 处 ,
Ted baker 应该存在 153, 但是已经有Sandra dee , 有了 kollision. 根据与 sondierungfunktion, 存在  原本的位置  x+1 mod y , 存在原本的 位置 的 +1 处, 就是 存在 154 处 ,

![[03_DataStructure/image/Pasted image 20250126222052.png]]

![[03_DataStructure/image/Pasted image 20250126222111.png]]


Chaining Addressierung
- Warum „geschlossene Adressierung“: weil die Kollisionskette hinter einem Key versteckt sind
- Warum „offenes Hashing“: weil die Kollisionskette hinter einem Key beliebig lang werden kann

Offene Adressierung 
- Warum „offene Adressierung“: weil sich die Kollisionskette über mehrere Keys verteilt
- Warum „geschlossenes Hashing“: weil die Kollisionskette nur erweitert werden kann, wenn noch Platz in der Hashtable ist



# 8 Array Doubling

wenn die Kapazität erschöpft ist
Dann verdoppelt die grosse von Array
Arraylength 增加后,  hashfunction  也需要改变,   modelle 2m, nicht mehr m


Idee
• ganz ähnlich zu Kapazität bei Implementierungen von dynamischen Datentypen mit Arrays
• nur wenn nötig, Anpassung der statischen Arrays im Hintergrund (amortisierte Komplexität)
• bei Hashtabellen müssen die Hashes bei Kapazitätsänderung neu berechnet werden (die neue Hashfunktion muss die neuen Plätze adressieren können, die alten Hashes müssen nicht mehr übereinstimmen)
• analoge Überlegungen bei Array Halving

![[03_DataStructure/image/Pasted image 20250126222244.png]]



![[03_DataStructure/image/Pasted image 20250126222308.png]]

