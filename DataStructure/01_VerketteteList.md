
# 1 总览

1. **Dynamische Datenmengen**  
    Der Begriff Dynamische Datenmenge wird an Alltagsbeispielen erläutert.
    
2. **Stapel**  
    In diesem Kapitel erfahren Sie die Bedeutung des Begriffs Stapel für die Programmierung. Die Manipulationen mit Stapel-Elementen wie push und pop werden beschrieben und deren Implementierung mit Hilfe von Reihungen anhand interaktiver Animationen anschaulich erklärt.
    
3. **Warteschlangen**  
    Die Implementierung von Warteschlangen mittels Reihungen lernen Sie in diesem Kapitel. Interaktive Animationen zeigen die Wirkung der Methoden enqueue() und dequeue().
    
4. **Einfach verkettete Listen**  
    Für Datenstrukturen, deren maximale Anzahl bei der Programmierung nicht bekannt ist, sind Reihungen ungeeignet. Die Implementierung von verketteten Listen dagegen erlaubt es, Elemente durch Verweise problemlos hinzuzufügen oder zu entfernen.
    
5. **Stapel als verkettete Liste**  
    In diesem Kapitel programmieren wir einen Stapel mit Hilfe einer einfach verketteten Liste.
    
6. **Warteschlangen als verkettete Liste**  
    Eine Warteschlange wird als verkettete Liste implementiert.
    
7. **Allgemeine dynamische Datenmengen**  
    Stapel und Warteschlangen sind spezielle lineare dynamische Datenstrukturen. In allgemeinen Listen können Elemente an beliebigen Positionen eingefügt oder gelöscht werden.
    
8. **Vergleich von Reihungen und verketteten Liste**  
    Die Vor- und Nachteile bei der Implementierung von dynamischen Datenmengen mit Hilfe von Reihungen und verketteten Listen werden gegenübergestellt.
    
9. **Doppelt verkettete Listen**  
    Die Methoden Einfügen und Löschen werden für doppelt verkettete Listen programmiert.
    
10. **Iteratoren**  
    Das Konzept der Iteratoren dient dazu eine einheitliche Schnittstelle zu Containern zu definieren. In diesem Kapitel erhalten Sie einen ersten Einblick wie Zugriffsalgorithmen von Containern entkoppelt werden können.
    
11. **Java-Klassen für Listen**  
    Für die Programmierung vieler Aufgabenstellungen werden verkettete Listen benötigt. Deshalb gibt es im Paket java.util Intefaces zur Implementierung verschiedener Listenstrukturen, wie beispielsweise Stapel, verkettete Liste, Vector. In diesem Kapitel geben wir einen Überblick über die vordefinierten Interfaces und Klassen

# 2 概要 

Datenstrukturen können dynamisch verarbeitet werden, d.h. sie können während der Laufzeit verändert werden
Die meist verwendeten dynamischen Datenstrukturen sind Listen oder Bäume
Elemente können an beliebiger Position eingefügt bzw. gelöscht werden
Dynamische Verkettung der Elemente im Speicher durch Verweise


Stack and Queue
- Der Stapel (stack) ist eine lineare Datenstruktur, bei der Elemente ausschließlich an der Spitze (top) eingefügt (push) oder entfernt (pop) werden. Stapel sind damit nach der **LIFO**-Strategie (**L**ast **I**n - **F**irst **O**ut) organisiert.
- Eine Warteschlange (queue) ist eine lineare Datenstruktur, bei der Elemente am Ende (tail) eingefügt und am Anfang (head) entfernt werden. Das Einfügen wird mit enqueue bezeichnet, das Löschen mit dequeue. Warteschlangen sind nach der **FIFO**-Strategie (**F**irst **I**n - **F**irst **O**ut) organisiert.

Array 和 verlettete Liste 的适用范围 
- Sequentiell organisierte dynamische Datenmengen, wie Stapel und Warteschlange, können mit Reihungen (array) implementiert werden, wenn die maximale Anzahl der Elemente vorhersagbar ist.
- Stark dynamische Datenmengen werden mit dynamischen Datenstrukturen modelliert, von denen die einfachste verkettete Listen ((singly-linked list)) sind.

verketteten Liste 的内部结构 
Die Knotenelemente (node element) einer verketteten Liste werden durch eine rekursive Klassendefinition erzeugt. Jedes dieser Knotenelemente enthält neben dem Verweis auf ein Objekt einen Verweis auf seinen Nachfolger bei einfach verketteten Listen sowie einen weiteren Verweis auf seinen Vorgänger bei doppelt verketteten Listen.


 die Implementierung allgemeiner dynamischer Datenmengen 需要的 methode 
- Liste： Die wichtigsten Grund-Methoden für die Implementierung allgemeiner dynamischer Datenmengen mit Listen sind:
    - Test auf Leere,
    - Einfügen eines Elements (add),
    - Löschen eines Elements (remove),
    - Suchen eines Elements (search).
- Array: Bei der Implementierung mit Reihungen ist eine weitere Methode zu programmieren:
    - Test auf Voll.
    - Dummy-Knoten (sentinel) oder Header-Knoten vereinfachen die Implementierung der Einfüge- und Lösch-Methode in verketteten Listen.
- Für die Listenmanipulationen werden Zeiger (pointer) benötigt:
    - head zeigt auf das erste Listenelement,
    - current verweist auf das aktuelle Listenelement,
    - tail für doppelt verkettete Listen, um das Listenende festzuhalten.
- Ein Listen-Iterator stellt Methoden zur Verfügung, mit deren Hilfe eine Liste durchlaufen werden kann. Mehrere Iteratoren können mit derselben Liste gleichzeitig verwendet werden.


# 3 Dynamische Datenmengen

Datenstrukturen können dynamisch verarbeitet werden, d.h. sie können während der Laufzeit verändert werden
Die meist verwendeten dynamischen Datenstrukturen sind Listen oder Bäume
Elemente können an beliebiger Position eingefügt bzw. gelöscht werden
Dynamische Verkettung der Elemente im Speicher durch Verweise
Interfaces "Stack" (Last In, First Out, LIFO) und "Queue" (First In, First Out, FIFO) im Paket java.util
Stack und Queue als Array-basierte Implementierung oder verkettete Listenimplementierung

Array 不是 Dynamische Datenmengen: 
Arrays sind nicht dynamisch in dem Sinne, dass deren Länge bei der Erzeugung bestimmt ist. Die Länge des Arrays bestimmt, wie viele Elemente maximal ein Array enthalten kann. 

Verkettung: 
Bei dynamischen Datenstrukturen werden neue Elemente mit Hilfe von Verweisen im Speicher verkettet (linked). Die Größe einer dynamischen Datenstruktur wächst mit den Elementen, die hinzugefügt werden, und schrumpft mit den Elemente, die gelöscht werden. Je nachdem wie die Verkettung realisiert wird, entstehen verschiedene Arten von Datenstrukturen, von denen die bekanntesten Listen und Bäume sind. In dieser LE werden nur Listen behandelt. Datenstrukturen werden im Modul "Algorithmen und Datenstruktur" vertieft



# 4 Stapel(Stack)

## 4.1 总览 

Ein Stapel (stack) ist eine dynamische Datenstruktur, in der die Daten linear "übereinander" gespeichert werden. 
Sichtbar ist ausschließlich das Element an der Spitze des Stapels. Nur an dieser Stelle des Stapels können Elemente eingefügt oder entfernt werden. 
Der Stapel implementiert eine LIFO-Strategie ("Last In, First Out").
Bei dieser Strategie wird das Element, welches zuletzt eingefügt wurde, zuerst entfernt.




## 4.2 Implementierung eines Stapels mit Reihungen

- Da die Indizierung einer Reihung mit 0 beginnt, ist die letzte Position der Reihung length -1.  index 从 0 开始
- sowie als Referenz auf die Spitze (top) - werden zwei weitere Methoden benötigt:
	- **empty:** prüft, ob der Stapel leer ist,
	- **full:** prüft, ob der Stapel voll ist.

![[DataStructure/image/Pasted image 20230626150019.png]]

![[DataStructure/image/Pasted image 20230626154510.png]]

## 4.3 Stapel-Schnittstelle `interface Stack<E>` 

Im Folgenden sehen Sie den Programmcode. In den Quellcode-Kommentaren erfahren Sie welche Funktionalität die einzelnen Methoden besitzen. Der generische Parameter E erlaubt erst bei der Instanziierung, den Typ der Objekte zu wählen, die gestapelt werden. 

Interface Stack.java
```java


/**
 * Ueberschrift: Stapel-Schnittstelle 
 * Beschreibung: Schnittstelle zur
 * Implementierung des Stapel 
 * Copyright: Copyright (c) 2002 
 * Organisation: BHT-Berlin (Projektgruppe VFH) 
 * 
 * Eine Schnittstelle macht keine Annahme ueber
 * die Implementierung daher der Name Stack.
 * 
 * @author M. Esponda - Agathe Merceron Oktober 2007
 * @version 1.0
 */
public interface Stack<E> {

    /**
     * Falls der Stapel noch nicht voll ist, wird das Element 'e' dem 
     * Stapel als oberstes Element hinzugefuegt, andernfalls wird ein
     * FullStackException-Objekt erzeugt.
     * 
     * @param e zu speicherndes Element
     * @throws FullStackException
     */
    public void push(E e) throws FullStackException;

    /**
     * Falls der Stapel nicht leer ist, wird das oberste Element des Stapels
     * entfernt und als Ergebnis zurueckgegeben, andernfalls wird ein
     * EmptyStackException-Objekt erzeugt.
     * 
     * @return entferntes Element
     * @throws EmptyStackException
     */
    public E pop() throws EmptyStackException;

    /**
     * Ueberprueft, ob der Stapel leer ist.
     * 
     * @return true falls der Stapel leer ist, false sonst
     */
    public boolean empty();

    /**
     * Ueberprueft, ob der Stapel voll ist.
     * 
     * @return true falls der Stapel voll ist, false sonst
     */
    public boolean full();
    
    /**
     * Liefert eine Darstellung des Stapels als Zeichenkette.
     * 
     * @return die Darstellung als Zeichenkette.
     */
    @Override
    public String toString();
}
```

An einem Programmbeispiel schauen wir uns die Implementierung des Stapel-Interface und zweier möglicher Konstruktoren an:
```java
public class ArrayStack<E> implements Stack<E> {

     // Instanzvariablen
     private int top; // zeigt immer auf oberstes Element im Stapel
     private E[] stack; // die Stapel Elemente werden gespeichert

     // Konstruktoren

     /**
      * Ein leerer Stapel mit der Groesse max. wird erzeugt.
      *
      * @param max maximale Anzahl der Elemente im Stapel
      */
     public ArrayStack(int max) {
         top = -1;  // Initialwert fuer leeren Stapel
         stack = (E[]) new Object[max];
     }

     /**
      * Ein leerer Stapel mit Platz fuer 100 Objekte wird erzeugt.
      */
     public ArrayStack() {
         this(100);  // erster Konstruktur wird aufgerufen
     }

     // Methoden
     // ...
```

## 4.4 Method

- push (element): Fügt ein Element oben auf den Stapel hinzu. zum Einfügen eines Elementes oben an der Spitze des Stapels,
- pop(): Entfernt und gibt das oberste Element des Stapels zurück. zum Entfernen des obersten Elementes vom Stapel.
- peek(): Gibt das oberste Element des Stapels zurück, ohne es zu entfernen
- isEmpty(): Überprüft, ob der Stapel leer ist、
- empty(): prüft, ob der Stapel leer ist,
- full(): prüft, ob der Stapel voll ist.



### 4.4.1 empty-Methoden

返回 boolean value ,  通过 top 和 -1 作比较 

Wir wollen die Methode empty so implementieren, dass ein Stapel dann leer ist, sobald top auf einen Index mit dem Wert -1 verweist. Das ist kein gültiger Reihungsindex (array index). Dieser Sachverhalt ist in der folgenden Abbildung dargestellt:

![[DataStructure/image/Pasted image 20230626150707.png]]

```java
/**
 * Ueberprueft, ob der Stapel leer ist.
 *
 * @return boolean true falls der Stapel leer ist, false sonst
 */
public boolean empty() {
    return (top == -1);
} 
```

### 4.4.2 full-Methoden

返回 boolean value , 

Die full-Methode ist ebenfalls über die Index-Abfrage schnell zu programmieren. Ein Stapel ist voll, wenn der Wert im top der größte Index der Reihung (stack.length-1) ist.

![[DataStructure/image/Pasted image 20230626150744.png]]

```java


/**
 * Ueberprueft, ob der Stapel voll ist.
 *
 * @return boolean true falls der Stapel voll ist, false sonst
 */
public boolean full() {
    return !(top < stack.length-1);
}


```

### 4.4.3 push-Methode

Mit der push-Methode wird dem Stapel ein weiteres Element hinzugefügt. 

Deshalb muss zunächst geprüft werden, ob der Stapel nicht voll ist.  需要检查 stack 满没满 
- Ist noch "Platz" im Stapel, wird der Wert in top um eins erhöht und an dieser Position in der Reihung eine Referenz auf ein neues Objekt gespeichert.
- Wenn der Stapel voll ist, wollen wir eine FullStackException auslösen. 

![[DataStructure/image/Pasted image 20230626151541.png]]

### 4.4.4 pop-Methode


Mit der pop-Methode wird das oberste Element aus dem Stapel entfernt. Vor dem Löschen muss zuerst geprüft werden, ob der Stapel mindestens ein Element enthält.
- Ist der Stapel nicht leer, wird der Wert in top um 1 verringert. 
	- Die Spitze des Stapels ist damit um 1 niedriger. 
	- 会抛出 最上面那个 Objekt Da die zu entfernenden Stapelelemente voraussichtlich von der rufenden Methode weiterverarbeitet werden, gibt die pop-Methode eine Referenz auf das entfernte Objekt als Ergebnis zurück.
- Ist der Stapel leer, lösen wir eine EmptyStackException aus.|


# 5 Warteschlange (Queue)

in der Elemente ausschließlich am Ende hinzugefügt und am Anfang entfernt werden. 
Warteschlangen implementieren eine FIFO-Strategie (First In, First Out). Das erste Element wird als erstes entfernt. 
Für die Bezeichnung des Anfangs der Warteschlange ist der Begriff head üblich, während mit tail das Ende benannt wird.

## 5.1 Implementierung einer Warteschlange mit Hilfe von Reihungen

![[DataStructure/image/Pasted image 20230626153212.png]]


![[DataStructure/image/Pasted image 20230626154530.png]]

![[DataStructure/image/Pasted image 20230626154556.png]]

## 5.2 Ring-Struktur/Zirkuläre Datenstruktur
Die Ring-Struktur entsteht dadurch, dass die Zeiger head und tail auf den leeren Reihungsanfang gesetzt werden, wenn diese das Reihungsende erreichen. Dadurch wird es möglich die leeren Reihungsplätze, die durch das Entfernen von Elementen am Anfang der Warteschlange entstanden, erneut mit Elementen zu füllen

WrapAround-Verfahren
Für einen Stack und für Queue
Neue Elemente an den Anfang des zugewiesenen Speichers, sobald das Ende erreicht ist
Effiziente Verwendung eines begrenzten Speicherbereichs, indem Elemente zyklisch wiederverwendet werden
Sorgfältige Verwaltung von Indexpositionen und Bedingungen für Hinzufügen und Entfernen von Elementen sorgfältig

tail 到 array 最后的时候， 就会弹跳到一开头
![[DataStructure/image/Pasted image 20230626153503.png]]

![[DataStructure/image/Pasted image 20230626154641.png]]


## 5.3 Warteschlangen-Schnittstelle `public interface QueueGen<E>`

Für die Warteschlange implementieren wir eine Methode head, die einen Verweis auf das erste Element der Warteschlange zurückgibt. Mit dieser Methode können wir im Gegensatz zu dequeue den Inhalt des Elements lesen ohne es zu löschen.

Die Elemente der Warteschlange sind vom generischen Typ E.


Interface QueueGen.java
```java
/**
 * Warteschlange-Schnittstelle - Schnittstelle zur Implementierung der
 * Warteschlange
 * 
 * Da das Paket java.util schon das Interface Queue enthaelt
 * wird dieses Interface QueueGen genannt (Gen wie Generisch).
 * 
 * @author A. Merceron
 * @version 1.1, 09/2009
 */
public interface QueueGen<E> {

    /**
     * Wenn die Warteschlange nicht voll ist, wird das Element 'e' als letztes
     * Element der Warteschlange eingefuegt, ansonsten wird ein
     * FullQueueException-Objekt erzeugt.
     * 
     * @param e zu speicherndes Element
     * @throws FullQueueException
     */
    public void enqueue(E e) throws FullQueueException;

    /**
     * Wenn die Warteschlange nicht leer ist, wird das erste Element der
     * Warteschlange entfernt und als Ergebnis zurueckgegeben, andernfalls wird
     * ein EmptyQueueException-Objekt erzeugt.
     * 
     * @return entferntes Element
     * @throws EmptyQueueException
     */
    public E dequeue() throws EmptyQueueException;

    /**
     * Wenn die Warteschlange nicht leer ist, wird das erste Element der
     * Warteschlange gelesen und als Ergebnis zurueckgegeben, ansonsten wird ein
     * EmptyQueueException-Objekt erzeugt.
     * 
     * @return erstes Element der Warteschlange
     * @throws EmptyQueueException
     */
    public E head() throws EmptyQueueException;

    /**
     * Ueberprueft, ob die Warteschlange leer ist.
     * 
     * @return boolean true wenn die Warteschlange leer ist, false sonst.
     */
    public boolean empty();

    /**
     * Ueberprueft, ob die Warteschlange voll ist.
     * 
     * @return boolean true wenn die Warteschlange voll ist, false sonst.
     */
    public boolean full();

    /**
     * Liefert eine Darstellung der Warteschlange als Zeichenkette.
     * 
     * @return die Darstellung als Zeichenkette.
     */
    @Override
    public String toString();
}
```


An einem Programmbeispiel schauen wir uns die Implementierung des Warteschlangen-Interface und zweier möglicher Konstruktoren an:
ArrayQueueGen.java
```java
public class ArrayQueueGen<E> implements QueueGen<E> {

     // Instanzvariablen
     // Fuer die Implementierung unseres Stapels benutzen wir eine Reihung (queue),
     // in der die Queue-Elemente gespeichert werden und zwei Zeiger (head und tail),
     // die auf das erste Element (head) bzw. den ersten freien Platz in der 
     // Queue (tail) zeigen.
     private int head; // erstes Element in der Queue
     private int tail; // erster freie Platz
     private E[] queue; // Hier werden die Warteschlangen Elemente gespeichert

     // Konstruktoren

     /**
      * Eine leere Queue wird mit der Groesse max. erzeugt
      *
      * @param max
      *            maximale Anzahl der Elemente in der Warteschlange
      */
     public ArrayQueueGen(int max) {
         head = 0; // Initialwert fuer leere Warteschlange
         tail = 0; // Initialwert fuer leere Warteschlange
         queue = (E[]) new Object[max];
     }

     /**
      * Ein leere Queue mit Platz fuer 100 Objekte wird erzeugt.
      */
     public ArrayQueueGen() {
         this(100); // erster Konstruktur wird aufgerufen
     }

     // Methoden
     // ...
```

## 5.4 Methode

- enqueue für das Einfügen 
- dequeue für das Löschen.

- offer(element): Fügt ein Element am Ende der Queue hinzu
- poll(): Entfernt und gibt das Element am Anfang der Queue zurück

- peek() und  head():  Gibt das Element am Anfang der Queue zurück, ohne es zu entfernen
	- Um das aktuelle Element aus der Warteschlange zu lesen, ohne es zu löschen, wird die Methode head() implementiert. 
	- Wenn die Warteschlange nicht leer ist, wird das aktuelle Element (Zeiger head) der Warteschlange gelesen und als Ergebnis (return value) zurückgegeben. 
	- Ist die Warteschlange leer, wird die entsprechende Ausnahme ausgelöst.
- isEmpty() und empty(): Überprüft, ob die Queue leer ist. Ueberprueft, ob die Warteschlange leer ist, @return boolean true wenn die Warteschlange leer ist, false sonst.
- full(): Liefert eine Darstellung der Warteschlange als Zeichenkette, @return die Darstellung als Zeichenkette


### 5.4.1 Die empty-methode （return boolean value ）

head 和 tail 的位置一样 Die Warteschlange ist leer, wenn head und tail auf die gleiche Position in der Reihung zeigen.
```java
public boolean empty() {
    return head == tail;
}  

```

### 5.4.2 full-Methode (return boolean value )
Wir werden den Zustand full so definieren, dass die Warteschlange dann voll ist, 
- wenn head auf die erste Position und tail auf die letzte Position der Reihung zeigt 
- oder tail eine Position von head entfernt liegt.
就是 说 full 的定义是  queue 中还有一个为空的 

```java
public boolean full() {
    return ((tail == queue.length -1) && (head == 0))
            || (head == (tail + 1)) ;
} 
```

![[DataStructure/image/Pasted image 20230626155524.png]]


### 5.4.3 enqueue


Ein neues Element kann erst in die Warteschlange (queue) eingefügt werden, nachdem überprüft wurde, ob die Warteschlange bereits voll ist.  先会检查voll 了没有 
- Wenn die Warteschlange nicht ganz gefüllt ist, wird die Referenz des neuen Elements an der Position gespeichert, auf die tail zeigt. 
	- Danach muss tail zur nächsten leeren Position der Warteschlange bewegt werden.
	- Wenn tail auf die letzte Position von queue zeigt, wird tail zur ersten Position von queue bewegt (WrapAround-Verfahren), sonst wird tail nur um eine Position weiter bewegt.
- Sobald die Warteschlange voll ist und kein Element mehr eingefügt werden kann, wird die entsprechende Ausnahme (exception) ausgelöst.

![[DataStructure/image/Pasted image 20230626160137.png]]


### 5.4.4 head()

 peek() und  head():  Gibt das Element am Anfang der Queue zurück, ohne es zu entfernen
	- Um das aktuelle Element aus der Warteschlange zu lesen, ohne es zu löschen, wird die Methode head() implementiert. 
	- Wenn die Warteschlange nicht leer ist, wird das aktuelle Element (Zeiger head) der Warteschlange gelesen und als Ergebnis (return value) zurückgegeben. 
	- Ist die Warteschlange leer, wird die entsprechende Ausnahme ausgelöst.

```java


public E head() throws EmptyQueueException {
    if (!empty()) {
        return queue[head];
    } else {
        throw new EmptyQueueException("Die Queue ist leer");
    }
}


```


### 5.4.5 dequeyue 

会先检查 queue 中有没有 元素。 
dequeue 的返回值为 返回的元素 

1. Bei dequeue müssen wir zuerst überprüfen, ob überhaupt ein Element in der Reihung (array) vorhanden ist. 
2. Ist mindestens ein Element vorhanden, 
	1. zeigt head auf das aktuelle Element in der Warteschlange (queue). 
	2. Wir merken uns die Adresse dieses Elements in einem neuen Objekt vom Typ E. 
	3. Danach wird der Wert von head um eins erhöht. Durch das Erhöhen wird das aktuell ausgelesene Element übersprungen und zum Überschreiben mit neuen Elementen durch die enqueue-Methode freigegeben.
	4. Entspricht der Wert von head nach der Erhöhung der Kapazität der Reihung, ist das Ende der Reihung erreicht und head muss auf die Position 0 zurückgesetzt werden (WrapAround-Verfahren).
	5. Das gemerkte Element wird als Rückgabewert (return value) von der Methode zurückgegeben. 
3. War die Warteschlange leer, wird die entsprechende Ausnahme (exception) ausgelöst.

![[DataStructure/image/Pasted image 20230626160821.png]]



# 6 Einfach verkettete Listen

1. 有很多时候 无法预先确定 某个容器的长度  Bei dynamischen Datenmengen ist es oftmals nicht möglich, die maximale Anzahl vorab zu benennen.
2. 什么是 verkettete Liste: Eine verkettete Liste (linked list) ist eine Menge von Elementen, die sequentiell organisiert ist. Einfach verkettete Listen sind dynamische Datenstrukturen (dynamic data structure), in denen jedes Element mit seinem Nachfolger verbunden ist. In solchen Strukturen kann man zur Laufzeit an beliebigen Positionen Elemente einfügen oder löschen.
3. einfach verkettete Listen
	1. In einer einfach verketteten Liste besteht jedes Element aus einer Referenz auf das zu speichernde Objekt und einer Referenz auf das nächste Element der Liste.
4. zweifach verkettete Listen 
	1. zusätzlich jeweils mit ihrem Vorgänger (predecessor) oder weiteren Nachbarn verbunden sind.

![[DataStructure/image/Pasted image 20230630145622.png]]

Stack: Läuft in eine Richtung head = 1. Element oder null (leere Liste) Verweis auf Nachfolger (next)
Queue: Läuft in eine Richtung head = 1. Element tail = letztes element oder null (leere Liste) Verweis auf Nachfolger (next

## 6.1 数据结构 介绍

In einer einfach verketteten Liste besteht jedes Element aus einer Referenz auf das zu speichernde Objekt und einer Referenz auf das nächste Element der Liste.

- 最后指向 null:  
	- Das letzte Element der Liste hat keinen Nachfolger (successor). Deshalb wird als Verweis null eingetragen. 
- Head: 
	- Eine Referenz verweist auf das erste Listenelement. Es ist der "Anker", an dem die ganze Liste hängt. In der folgenden Abbildung wird er mit head bezeichnet

![[DataStructure/image/Pasted image 20230626171912.png]]


### 6.1.1 每个 listNode

jedes Listenelement aus zwei Teilen besteht. 
- Zum einem aus dem gespeicherten Element und 
- Zum anderen aus dem Verweis auf das nächste Listenelement bzw. beim letzten Element aus dem Verweis auf null.

```java
class ListNode<E> {

    //Instanzvariablen
    private E element; // gespeichertes Listenelement
    private ListNode next; // Verweis auf naechstes Listenelement
    
    // Konstruktoren

    private ListNode(E e, ListNode n) {
        element = e; // Referenz auf das zu speichernde Element
        next = n;    // Referenz auf das Nachfolger-Listenelement
    }

    private ListNode(E e) {
        this(e, null);
    }

    private ListNode() {
        this(null, null);
    }

}
```

In der Klasse `ListNode<E>` definieren wir drei Konstruktoren:

- Konstruktor, dem die Referenz auf ein Element und eine Nachfolger-Referenz übergeben wird, die in dem erzeugten ListNode-Objekt abgespeichert werden
- Konstruktor, dem die Referenz auf ein Element übergeben wird, die in dem erzeugten ListNode-Objekt abgespeichert wird. Die Nachfolger-Referenz wird standardmäßig auf null gesetzt.
- Konstruktor, der ein ListNode-Objekt erzeugt, indem beide Verweise null sind. Mit diesem Konstruktor kann eine leere Liste erzeugt werden, die nur aus dem Zeiger head besteht.

Mit Hilfe dieser ListNode-Objekte können wir eine verkettete Liste erstellen, indem wir mehrere solcher Objekte erzeugen und untereinander verketten. Die Klasse ListNode werden wir als innere Klasse implementieren, weil sie nur im Zusammenhang mit der Klasse ListStack benutzt wird.


# 7 Stapel als verkettete Liste
  	
Mit Hilfe von verketteten Listen (linked list) lässt sich ein Stapel (stack) sehr einfach implementieren. Wir müssen dabei nicht mehr überprüfen, ob der Stapel voll ist – wie bei unserer Implementierung mit Hilfe von Reihungen (array).

Wir brauchen ein head-Element, das eine Referenz auf ein ListNode-Objekt ist. Mit dieser Referenz können wir bei einer push-Operation neue Elemente am Anfang der Liste einfügen und verketten oder entfernen, wenn eine pop-Operation stattfindet.


 	
## 7.1 Stapel-Schnittstellen und ihre Implementierung

 	

Als Stapel-Schnittstelle (stack interface) für die Implementierung unseres Stapel als verketteten Liste verwenden wir, wie schon bei unserer Stapelimplementierung mit Reihungen (array), die Klasse `Stack<E>.`

Bei der Implementierung der Klasse liegt der einzige Unterschied darin, dass die push-Operation keine FullStackException auslösen wird, weil der Stapel nicht voll sein kann. Bei dem Versuch ein Element zu entfernen (pop-Operation) werden wir, falls die Liste leer ist, ein EmptyStackException-Objekt erzeugen.

Für unsere Stapel-Implementierung brauchen wir eine einzige Instanzvariable head, die entweder eine Referenz auf den ersten Knoten, das heißt auf den Anfang der Liste, enthält oder den Wert null, wenn die Liste leer ist.

Ein Konstruktor wird definiert, der head mit dem Wert null initialisiert.

```java


public class ListStack<E> implements Stack<E> {

    // Instanzvariablen
    private ListNode<E> head; // zeigt immer auf das oberste Element

    // Konstruktor
    public ListStack() {
        head = null;
    }

    // Methoden
    // ...


```


## 7.2 Methode

### 7.2.1 empty

Der Stapel ist leer, wenn das head-Element den Wert null hat. 
将 head 和 null 作比较 

```java
/**
 * Ueberprueft, ob der Stapel leer ist.
 *
 * @return boolean true falls der Stapel leer ist, false sonst
 */
 public boolean empty() {
     return (head == null);
 }

```


### 7.2.2 full-Methode

Stapel als verkettete Liste  绝不会 full, 所以 full() 总是返回 false

Wie eingangs bereits erwähnt, handelt es sich bei den Verketteten Listen um dynamische Datenstrukturen. Der Stapel kann also nicht voll werden. Da unser Interface `Stack<E> `die Implementierung einer full-Methode vorsieht, werden wir diese Methode so implementieren, dass sie standardmäßig den Wert false zurückliefe

```java
/**
 * Ueberprueft, ob der Stapel voll ist.
 *
 * @return false Der Stapel als verkettete Liste kann nie voll werden.
 */
 public boolean full() {
     return false; // Standard-Rueckgabewert
 }

```

### 7.2.3 push-Methode 

将 新的 node 指向 head 的 node, 然后再移动head  

Bei der push-Operation soll ein neues Objekt an der Spitze des Stapels eingefügt werden. Zu diesem Zweck wird ein neues ListNode-Objekt erzeugt, das übergebene Objekt e wird im Konstruktor in die Instanzvariable element des ListNode-Objekts gespeichert. Dann wird das neu erzeugte ListNode-Objekt am Anfang der Liste mit dem Nachfolger-Element (successor element) verkettet.

![[DataStructure/image/Pasted image 20230629231316.png]]


Textversion: push-Methode in der einfach verketteteten Liste
1. Ein neues ListNode-Objekt wird erzeugt und die Referenz wird in die lokale Variable node gespeichert.
2. Das einzufügende Element O4 wird im Konstruktor in die Instanzvariable element des neuen ListNode-Objekt gespeichert.
3. Verkettung des neuen Elements auf das folgende Element durch Übernahme der Referenz von head in node.next.
4. head wird auf die Referenz node des neue eingefügten ListNode-Objektes gesetzt.

```java
/**
 * Ein neu erzeugtes ListNode-Objekt wird dem Stapel als
 * oberstes Element hinzugefuegt. 
 *
 * @param e zu speicherndes Element
 */
 public void push(E e) {
     // Das uebergebene Object 'e' und die Referenz auf das     
     // vorherige oberste Element des Stapels werden in dem 
     // ListNodeGen-Objekt gespeichert (Verkettung).   
     // Durch die Zuweisung in head ist das neue Objekt oben
     ListNode node = new ListNode(e);
     node.next = head;
     head = node;
 }

```


Mit Hilfe eines ListNode-Konstruktors, der als ersten Parameter das zu speichernde Objekt e und als zweiten Parameter eine Referenz auf das nachfolgende ListNode-Objekt bekommt, können wir unsere push-Operation wie folgt implementieren:
```java
 	

public void push(E e) {
    head = new ListNode(e, head);
} 


```



### 7.2.4 pop-Methode

return head 当前指向的 elemet . 就是  head.element
再将 head 指向 head.next 所在的element 

Bei der pop-Operation wird das Objekt, das sich an der Spitze des Stapels befindet, gelöscht.

Zu Beginn der pop-Operation wird geprüft, ob der Stapel leer ist. Ist das der Fall, wird ein EmptyStackException-Objekt geworfen und die pop-Operation wird abgebrochen.

Andernfalls wird, bevor das ListNode-Objekt gelöscht wird, die Objekt-Referenz, die sich in diesem Knoten (node) befindet, in der lokalen Variablen element gespeichert. Dadurch ist es möglich die Referenz des gelöschten Objektes als Ergebnis der pop-Operation zurückzugeben. Danach wird der head-Zeiger auf das nächstes Element der Liste bewegt.

Das Löschen erfolgt nur indem der head-Zeiger bewegt wird. Das entfernte ListNode-Objekt bleibt am Ende der pop-Operation ohne eine einzige Referenz, das auf es zeigt, und wird daher zu Datenmüll, der später von dem Java-"Garbage Collector" beseitigt wird.

整个流程
Textversion: pop-Methode in einer verketteten Liste (Stapel)
1. Wenn der Stapel leer ist, wird eine EmptyStackException geworfen und die pop-Operation abgebrochen.
2. Wenn die Liste leer ist, wird die Objekt-Referenz, die sich in dem obersten Knoten befindet, in die lokale Variable e gespeichert.
3. head wird die Referenz des Nachfolgerobjektes zugewiesen.
4. Die Referenz des entfernten Objektes wird als Ergebnis zurückgegeben.
5. Auf das entfernte ListNodeGen-Objekt zeigt keine Referenz mehr. Es wird zu Datenmüll, der vom "JavaGarbageCollector" beseitigt wird.


```java


/**
 * Falls der Stapel nicht leer ist, wird das oberste Element des
 * Stapels entfernt und als Ergebnis zurueckgegeben, andernfalls
 * wird ein EmptyStackException-Objekt erzeugt.
 *
 * @return entferntes Element
 * @throws EmptyStackException
 */
 public E pop() throws EmptyStackException {
     if (!empty()) {
         E e = head.element;
         head = head.next;
         return e;
     } else {
         throw new EmptyStackException("Der Stapel ist leer");
     }
 }


```


# 8 Warteschlange als verkettete Liste

first in, first out 

Mit Hilfe von verketteten Listen (linked list) lässt sich eine Warteschlange (queue) elegant implementieren. Wir benötigen dafür nur einen head- und einen tail-Zeiger, die den Zugriff auf das erste und letzte Element der Warteschlange ermöglichen.


Für die Warteschlange sollen die aus dem [Kapitel 3](https://moodle.oncampus.de/modules/ir019/onmod/GP2LST/03wschlange/wschlange.shtml) bekannten Methoden implementiert werden:

|   |   |
|---|---|
|**enqueue**|Ein neues Element wird in die Warteschlange eingefügt.|
|**dequeue**|Das erste Element der Warteschlange wird entfernt.|
|**head**|Das erste Element der Warteschlange wird nur gelesen.|
|**empty**|Es wird geprüft, ob die Warteschlange leer ist.|
|**full**|Da es sich bei der Warteschlange als verkettete Liste um einen dynamischen Datentyp handelt, liefert die **full**-Methode standardmäßig den Wert **false** zurück.|
|**toString**|Liefert eine Darstellung der Warteschlange als Zeichenkette (String).|

![[DataStructure/image/Pasted image 20230629232450.png]]


## 8.1 Warteschlangen-Schnittstelle und ihre Implementierung

Als Warteschlangen-Schnittstelle für die Implementierung unseres Stapel als verkettete Liste verwenden wir, wie schon bei unserer Stapelimplementierung mit Reihungen, die Klasse `QueueGen<E>.`
  	 
Für die Warteschlangen-Implementierung benötigen wir zwei Instanzvariablen head und tail, die eine Referenz auf das erste und letzte Element der Liste enthalten.

Der Konstruktor weist head und tail den Wert null zu.

```java
public class ListQueueGen<E> implements QueueGen<E> {

    private ListNode head; // Referenz auf erstes Listenelement
    private ListNode tail; // Referenz auf letztes Listenelement

    // Konstruktoren

    /**
     * Neue leere Warteschlange erzeugen.
     */
    public ListQueueGen() {
        head = null;
        tail = null;
    }

    /**
     * Neue Warteschlange, die das uebergebene Element
     * enthaelt, erzeugen.
     */
    public ListQueueGen(E e) {
        head = new ListNode(e);
        tail = head;
    }

    // Methoden 
    // ...  
```



## 8.2 Methode

![[DataStructure/image/Pasted image 20230629232914.png]]

### 8.2.1 empty-Methode

将 head ， tail 和 null 作比较 

Wenn die Warteschlange leer ist, dann haben head und tail jeweils den Wert null.
Es genügt lediglich zu überprüfen, ob head gleich null ist.

Zum Testen auf eine leere Warteschlange reicht der Vergleich von head mit null aus:
```java
/**
  * Ueberprueft, ob die Warteschlange leer ist.
  *
  * @return boolean
  */
 public boolean empty() {
     return head == null;
 }
```


### 8.2.2 full-Methode

Qeueu als verkettete Liste  绝不会 full, 所以 full() 总是返回 false

Wie der Stapel als verkettete Liste ist auch die Warteschlange als verkettete Liste eine dynamische Datenstruktur. Diese Warteschlange kann somit nicht voll werden. Da unser Interface` QueueGen<E> `die Implementierung einer full-Methode vorsieht, werden wir diese Methode so implementieren, dass sie standardmäßig den Wert false zurückliefert.

```java
 /**
  * Ueberprueft, ob die Warteschlange voll ist.
  *
  * @return false die Warteschlange als verkettete Liste
  *     kann nie voll werden.
  */
 public boolean full() {
     return false;
 }
```

### 8.2.3 enqueue-Methode 加元素

从 tail 处 加入元素 

In der enqueue-Operation haben wir zwei Fälle:
1. Wenn die Liste leer ist, wird das zu speichernde Element in ein ListNode-Objekt verpackt und head und tail bekommen die Referenz des neuen Knotens (node) zugewiesen.
	1. tail 和 head 都指向 这个元素
2. Wenn die Liste nicht leer ist, muss das neue ListNode-Objekt am Ende der Liste verkettet werden. Das geschieht, indem der next-Zeiger des ListNode-Objekts, auf den tail gerade zeigt, die Referenz des neuen Knotens zugewiesen bekommt. 
	1. tail.next = temp; then,   tao; = temp 


```java
/**
 * Das Element e wird als letztes Element in die Warteschlange eingefuegt.
 * Beachte: Die Methode wirft im Gegensatz zur Schnittstelle keine Exception.
 * Eine solche Implementierung ist zulaessig.
 *
 * @param e zu speicherndes Element
 */
public void enqueue(E e) {
    ListNode temp = new ListNode(e);
    // bei einer leeren Warteschlange zeigen beide Zeiger (head und tail) 
    // auf das neue Element
    if (empty()) tail = head = temp;
    else {
        // neues Element mit aktuellem Element an Position tail verketten
        tail.next = temp;
        tail = temp;
    }
}
```


Textversion: enqueue-Methode für Warteschlange (Liste)

1. Ein neues ListNode - Objekt wird erzeugt. Die Referenz des Objekts O1 (newElement) wird mit Hilfe des Konstruktors in das erzeugt ListNode - Objekt gespeichert.

Bei einer leeren Liste:
2. head und tail wird die Referenz des neu erzeugten ListNode - Objekts zugewiesen.

Wenn die Liste nicht leer ist:
1. Das Element, auf das tail zeigt, bekommt als Nachfolger das neue erzeugte ListNode - Objekt (hier im Beispiel Objekt O5).
2. tail bekommt ebenfalls die Referenz des neuen Objekts, das gleichzeitig das letzte Element ist.


### 8.2.4 dequeue-Methode  删除元素

从 head 处 删除元素 ， 把这个删除的元素 return 出来 

1 检查是否为 leer
Soll ein Objekt aus der Warteschlange entfernt (remove) werden, muss zunächst überprüft werden, ob die Warteschlange nicht leer ist. Dieses Vorgehen entspricht der Prüfung, die bei der pop-Operation einer Stapel-Implementierung als erstes erfolgt.

2 如果为 leer
Denn wenn die Warteschlange leer ist, wird ein EmptyQueueException-Objekt erzeugt und die dequeue-Operation unterbrochen.

3 如果部nicht eer 
Ist die Warteschlange nicht leer, wird die Referenz des Elements, das am Anfang der Warteschlange gespeichert ist, der lokalen Variablen temp zugewiesen. Der head Zeiger wird head.next zugewiesen (die Referenz des ersten Knotens wird mit der Referenz seines Nachfolgers ersetzt) und die Referenz des entfernten Objekts als Ergebnis der Operation zurückgegeben. 


```java


/**
 * Wenn die Warteschlange nicht leer ist, wird das erste Element der
 * Warteschlange entfernt und als Ergebnis zurueckgegeben, andernfalls wird
 * ein EmptyQueueException-Objekt erzeugt.
 *
 * @return E entferntes Element
 * @throws EmptyQueueException
 */
public E dequeue() throws EmptyQueueException {
    if (empty()) throw new EmptyQueueException();
    else {
        // Element an Position head aus der Warteschlange entfernen
        E temp = head.element;
        head = head.next; // head-Zeiger auf Element setzen, das in Next 
                          // des aktuellen head-Elements gespeichert ist
        return temp; //entferntes Element zurueckgeben 
    }
}
```


 	
Textversion
Textversion: dequeue-Methode für Warteschlange (Liste)
1. Wenn die Liste leer ist, wird eine EmptyQueueException geworfen und die dequeue-Operation abgebrochen.
2. Wenn die Liste nicht leer ist 
	1. Die Referenz des Elements, das am Anfang der Warteschlange gespeichert ist, wird der Variable temp zugewiesen.
	2. head wird die Referenz des Nachfolgerobjektes zugewiesen.
	3. Die Referenz des entfernten Objektes wird als Ergebnis zurückgegeben.
	4. Auf das entfernte ListNode-Objekt zeigt keine Refenz mehr. Es wird zu Datenmüll, der vom Java Garbage Collector beseitigt wird.


# 9 Allgemeine dynamische Datenmengen

Eine Liste ist eine Datenstruktur, die Elemente in einer Reihenfolge speichert. Wenn wir allgemeine dynamische Datenmengen (dynamic amounts of data) mit Hilfe von Listen implementieren möchten, müssen wir an einer beliebigen Stelle der Liste Elemente einfügen (insert) oder löschen (remove) können.

Wir werden eine Einfüge-Operation und eine Lösch-Operation definieren, die ein Element an der Position i einfügt oder löscht. Dafür braucht die Implementierung mit verketteten Listen ein Referenz-Objekt (in unserer Implementierung vor genannt), das sich durch die Liste bewegt und als nächstes Element das Element an der Position i hat.
![[DataStructure/image/Pasted image 20230629235034.png]]

Die Elemente einer Reihung (array) befinden sich immer nebeneinander im Speicher.
Dadurch kann ein direkter Zugriff auf die verschiedenen Elemente mit Hilfe eines Indizes erfolgen. Bei verketteten Listen ist es anders: Man hat ständig nur die Adresse eines Knotens (node). Um weitere Knoten der Liste zu erreichen, muss die Verkettung der Knoten verfolgt werden. Erst nachdem ein Knoten besucht worden ist, wird deutlich, wo sich sein Nachfolger (successor) befindet.
![[DataStructure/image/Pasted image 20230629235053.png]]



## 9.1 	Die Einfüge-Operation (中间位置插入 )

Bei jeder Einfüge-Operation muss immer genau definiert werden, wo in der Reihenfolge das neue Objekt eingefügt werden soll. Aus diesem Grund wird der Einfügen-Operation einen Index übergeben. Der Index gibt an welche Position das neue Element eingefügt (insert) werden soll.

Die insert Methode wird wie folgt implementiert.
Wenn der Index nicht gültig ist wird eine Ausnahme geworfen. Es gibt zwei Sonderfälle: das Einfügen am Index 0, das heißt am Anfang der verketten Liste und somit wird das neue Element zum head, und das Einfügen am Index size(), das heißt das neue Element wird zum tail. Sonst muss ermittelt werden anhand des übergebenen Index, wo in der Liste ein neues Element eingefügt bzw. ein bestehendes Element gelöscht werden soll. Die Hilfsmethode getVorgaenger übernimmt diese Aufgabe und gibt das Vorgänger-Element (predecessor element) des Elements an der Position i zurück. Sie wird sowohl für das Einfügen wie für das Löschen benötigt.
```java
public void insert(int i, E e) throws IndexOutOfBoundsException{
    	if (i < 0 || i > size) {
    		throw new IndexOutOfBoundsException
            ("Index "+i+" nicht gueltig.");
    	}
   
        if (i==0) {
            insertFirst(e);
            return;
        }
        else if (i== size) {
        	tail.next = new ListNode(e);
        	tail = tail.next;
        }  else {
            ListNode vor = getVorgaenger(i);
            ListNode temp = new ListNode(e, vor.next);
            vor.next = temp;
        }
        size++;
    }

private ListNode getVorgaenger(int i) {
        ListNode current = head;
        // Schleife bis ein Element vor 
        // der uebergebenen Position
        for (int j = 1; j < i; j++) {
            current = current.next;
        }
        return current;
    }

```



Textversion: Einfügen hinter dem aktuellen Element (current)

1. Ein neues ListNode - Objekt wird erzeugt und die Referenz der lokalen Variable temp zugewiesen.
2. Die Referenz des zu speichernden Objekts O5 wird der Instanzvariablen element zugewiesen.
3. Die Referenz des Nachfolgerelement von vor (vor.next) wird der Instanzvariablen next von temp zugewiesen.
4. Zum Schluss wird als Nachfolger von vor das neue ListNode - Objekt (temp) zugewiesen.


## 9.2 Die Lösch-Operation  (删除中间的某个node)

![[DataStructure/image/Pasted image 20230629235851.png]]

Ebenfalls wirft die Lösch-Operation eine Ausnahme, wenn die Position nicht gültig ist oder auch wenn die Liste leer ist. Es gibt hier auch zwei Sonderfälle. Der Sonderfall i ist 0 bedeutet, ähnlich wie bei der Methode insert, dass das erste Element gelöscht wird. Der Sonderfall i == size()-1 bedeutet, dass das letzte Element gelöscht wird und dass tail sich verändert: das vorige Element wird zum tail. Im Gegensatz zu insert, muss der Vorgänger auch in diesem Fall ermittelt werden.

Was die Anweisung: vor.next = vor.next.next; bewirkt, zeigt die Abbildung Lösch-Operation.

```java
 	
public E delete(int i) throws EmptyQueueException,
     IndexOutOfBoundsException {
        if (empty()) {
            throw new EmptyQueueException();
        }
    	if (i < 0 || i >= size) {
    		throw new IndexOutOfBoundsException
            ("Index "+i+" nicht gueltig.");
    	}
    	ListNode temp;
    	if (i == 0) {
    		temp = head;
    		head = head.next;
    	} else {
            ListNode vor =   getVorgaenger(i);
            temp = vor.next;
            // ueberpruefen, ob das letzte Element entfernt wird
            if (vor.next == tail) {
            	tail = vor;
            }
            vor.next = vor.next.next;
    	}
    		size--;
    		return temp.element;
    }

private ListNode getVorgaenger(int i) {
        ListNode current = head;
        // Schleife bis ein Element vor 
        // der uebergebenen Position
        for (int j = 1; j < i; j++) {
            current = current.next;
        }
        return current;
    }
```


## 9.3 empty-Methode (判断是否为空)

Die insert- sowie die delete-Methode prüfen die Gültigkeit des übergebenen Indexes. Es ist effizienter, nicht immer die Anzahl der Elemente der Liste dynamisch zu ermitteln, sondern sie in einem Attribut – hier size genannt – zu speichern. Dieses Attribut wird benutzt, um die Methode size() sowie die empty-Methode zu implementieren.

```java
public boolean empty() {
    return size == 0;
}
```


# 10 Vergleich von Reihungen(array) und verketteten Listen(linked list)

 	
Bei Stapel (stack) und Warteschlange (queue) haben wir die Implementierungen mit Reihung (array) und verketteter Liste (linked list) gegenübergestellt. Bereits bei diesem Vergleich haben Sie die Vor- und Nachteile der beiden Implementierungsarten erkannt. 

Bei allgemeinen verketteten Listen, bei denen an beliebiger Stelle eingefügt und gelöscht werden kann, zeigen sich die Vorteile verketteter Listen gegenüber Reihungen noch deutlicher.
verketteten Listen(linked list) 最大的优点 就是   bei denen an beliebiger Stelle eingefügt und gelöscht werden kann,

- Array 
	- 对于 wenige dynamischen Datenmengen,  Reihungen 更快 因为 需要的 speicherallocation 少， 产生的垃圾也少 
		- Implementierungen mit Hilfe von Reihungen sind in der Ausführung meist schneller, weil weniger dynamische Speicherallokation und weniger Speichermüll verursacht werden.
	- Reihungen的缺点 是 有  die maximale Größe。 
		- Der Nachteil bei Reihungen ist, dass die maximale Größe der gespeicherten Datenmenge (amount of data), die zur Laufzeit erreicht wird, vorher bekannt sein muss, während dies bei verketteten Listen nicht nötig ist.

- LinkedList
	- 插入 删除 新数据 简单 快  
		-   bei denen an beliebiger Stelle eingefügt und gelöscht werden kann,
		- Die wesentlichen Manipulationen wie Einfügen und Löschen erfordern bei Listen weniger Arbeitsschritte und sind dadurch einfacher und schneller.
	- 对于 starke dynamischen Datenmengen, verketteten Listen 更高效 ， Speicherplatz wird besser allokiert und freigegeben 
		- Implementierungen mit verketteten Listen sind bei stark dynamischen Datenmengen vorzuziehen, weil sie den Speicher effizient auslasten. Speicherplatz wird im Gegensatz zu Reihungen nach Bedarf allokiert und freigegeben.


# 11 Doppelt verkettete Listen (doubly linked list) 

## 11.1 Einfach und Doppelt verkettete Listen 对比

Einfach verkettete Listen (singly-linked list) können nur in einer Richtung durchlaufen werden. Das Bestimmen des Vorgängers (predecessor) eines Elementes erfordert ein erneutes Durchlaufen (traverse) der Liste. Einfach verkettete Listen sind fehleranfällig (prone to error). Wenn eine Referenz innerhalb der Liste zerstört wird, ist der Teil der Liste hinter dieser Referenz verloren.

## 11.2 Doppelt verkettete Listen (doubly linked list) 原理 

Mit einer doppelten Verkettung kann der Zeiger current problemlos in beide Richtungen bewegt werden. Da doppelt verkettete Listen vorwärts und rückwärts durchlaufen werden können, ist es sinnvoll einen Zeiger auf das letzte Element (tail) mitzuführen.

Doppelt verkettete Listen (doubly linked list) sind eine Lösung dieser Probleme. Jedes Element dieser Liste verweist auf seinen Nachfolger (successor) und auf seinen Vorgänger. Nennen wir die Klasse DlistNode und bezeichnen die Verweise mit next und prev, dann beschreibt folgender Programmcode das Element einer dopppelt verketteten Liste:

```java
class DListNode<E extends Comparable<? super E>> {
    private E element;
    private DListNode<E> next;
    private DListNode<E> prev;
    // Methoden...

} 
```

![[DataStructure/image/Pasted image 20230630093326.png]]

Läuft in beiden Richtung head = 1. Element. tail = letztes element. Verweis auf Nachfolger (next) und Vorgänger (pre) current = aktuelles Elemen

 Dummy-Knoten 的作用： 
 Durch das Einfügen der Dummy-Elemente vereinfachen sich die in den folgenden Abschnitten erläuterten Methoden einfügen und löschen. Jedes neue Element wird immer zwischen zwei Elemente eingefügt. ==Gäbe es keine Dummy-Knoten, dass müssten beispielsweise beim Einfügen mehrere Fälle unterschieden und programmiert werden, ==wie Einfügen innerhalb der Liste bzw. Anhängen am Anfang oder Ende.


Eine doppelt verkettete leere List
Eine doppelt verkettete leere Liste besteht lediglich aus den beiden Dummy-Elementen:
![[DataStructure/image/Pasted image 20230630093614.png]]



## 11.3 Methode 

### 11.3.1 empty-Methode
``` java 
public boolean empty() { 
    return head.next == tail;
}
```

### 11.3.2 Einfüge-Methode

Die folgende Diashow zeigt, wie ein neues Element in eine doppelt verkettete Liste (doubly linked list) eingefügt wird. Die Dummy-Elemente stellen sicher, dass jedes neues DListNode-Objekt immer zwischen zwei vorhandenen eingefügt werden kann. 
Dadurch wird die Einfüge-Operation einfacher, weil weniger Fälle zu überprüfen sind. Das neue Element wird in ein DListNode-Objekt verpackt und dieses hinter das DListNode-Objekt eingeführt – auf das current zeigt.

![[DataStructure/image/Pasted image 20230630094728.png]]

![[DataStructure/image/Pasted image 20230630094546.png]]

Die Abbildung zeigt einen Abschnitt aus der gesamten Liste und nur die Kernoperationen, die für die Verkettung nötig sind.

1. Ein neues DListNode – Objekt mit dem zu speichernden Objekt O7 wird erzeugt und die Referenz dazu in temp gespeichert.
2. temp bekommt als Vorgänger die Referenz des Objektes, auf den current zeigt.
3. Als Nachfolger bekommt temp den gleichen Nachfolger, den current hat.
4. Der Vorgänger von temp (current) bekommt als Nachfolger temp zugewiesen.
5. Der Nachfolger von temp bekommt als Vorgänger temp zugewiesen.
6. current bekommt die Referenz des neuen DListNode-Objektes (temp) zugewiesen.

### 11.3.3 Lösch-Methode

Die Diashow zeigt, wie in einer doppelt verketteten Liste (doubly linked list) das Element gelöscht wird, auf das current zeigt. Nach dem Löschen wird current auf den Listenanfang gesetzt

![[DataStructure/image/Pasted image 20230630094755.png]]

![[DataStructure/image/Pasted image 20230630094812.png]]

![[DataStructure/image/Pasted image 20230630094741.png]]

1. Mit doppelt verketteten Listen können wir genau das Objekt löschen, auf das current zeigt. Die Abbildung zeigt einen Abschnitt aus der gesamten Liste und nur die Kernoperationen, die für die Verkettung nötig sind.
2. Der Vorgänger des DListNode – Objekt, das wir löschen wollen, bekommt als Nachfolger den Nachfolger von current.
3. Der Nachfolger von current bekommt als Vorgänger den Vorgänger von current zugewiesen.
4. current wird auf den Anfang der Liste (head) gesetzt.
5. Das gelöschte DListNode-Objekt wird später von dem Java "GarbageCollector" endgültig entfernt.

## 11.4 Doppelt verkettete Zirkularlisten (doubly linked circular list) 圆周循环结构

Wir haben gesehen, dass **dummy**-Knoten (sentinel) die Anzahl der Fälle in Operationen unserer verketteten Listen reduzieren und dadurch einfacher und übersichtlicher werden. 
Daraus entsteht eine doppelt verkettete Zirkularliste (doubly linked circular list).
- 就一个 Dummy Konten : Wir können aber anstatt zweier **dummy**-Knoten nur einen verwenden, wenn wir diesen zwischen dem Kopf (head) und dem Ende der Liste (tail) verketten. 
- 不再需要 tail zeiger Wir brauchen dann keine tail-Zeiger mehr in unserer Liste, weil das letzte Element der Liste mit head.prev erreicht werden kann.

![[DataStructure/image/Pasted image 20230630101229.png]]



## 11.5 Such-Operation und wie sortiert 

需要通过 Such-Operation 找到想要的 位置， 然后再插入
实现 Such-Operation 就要先 解决 Sind die gespeicherten Objekte der Liste sortiert 的问题 

Bis jetzt haben wir nur die grundlegende Implementierungstechnik erläutert, mit der Einfüge- und Lösch-Operationen mit Hilfe von verketteten Listen realisiert werden können. Es wurde angenommen, dass die Stelle, in der das neue Objekt eingefügt oder gelöscht werden soll, bekannt war. Sobald wir eine Such-Operation realisieren wollen, stellt sich die Frage: Sind die gespeicherten Objekte der Liste sortiert? Nach welchen Kriterien kann ich die gespeicherten Objekte vergleichen?.

Wenn wir dynamische Datenmengen mit sortierten Elementen haben wollen, muss unsere Implementierung spezialisiert werden auf Operationen, die nicht mehr mit allgemeinen Objekten arbeiten, sondern nur mit Klassen von Objekten, die vergleichbar sind. D. h. die Klassen von Objekten, die wir in unserer sortierte Liste speichern, müssen mindestes eine Vergleichsoperation zur Verfügung stellen, damit sie einsortiert werden können.


sortierte Datenmengen 需要的 Grundoperation 
Die Java-Umgebung bietet die Comparable-Schnittstelle, in der nur die compareTo-Methode zu implementieren ist. Viele Klassen der Java-Umgebung implemetieren bereits diese Schnittstelle, wie zum Beispiel alle Wrapper-Klassen.  
Allgemein sortierte Datenmengen haben mindestens folgende Grundoperationen:

|   |   |
|---|---|
|**insert**|Einfüge-Operation|
|**delete**|Lösch-Operation|
|**contains**|Such-Operation|
|**isEmpty**|Test auf leere Liste|


# 12 Iteratoren

我们要对一个 dynamischer Datenmengen mittels verketteter Listen  不断地进行读取。  就会不断地 创建 zeiger。 zeiger 一旦多了 就不知道 那个 zeiger 指向那个 Konten
所以要引入 Iterator, 来帮助我们durchlaufen  Liste
 
Für die Implementierung dynamischer Datenmengen mittels verketteter Listen wurde bisher jedes Mal ein current-Zeiger als Teil der Listen-Objekte definiert. Der current-Zeiger bewegt sich durch die Liste und hält eine Position für weitere Operationen fest.

Für bestimmte Operationen müssen wir aber oft auf mehr als eine Position in der Liste zugreifen. In diesem Fall können wir mehrere solcher Zeiger (pointer) für eine Liste definieren. Leider können wir aber meistens nicht vorher wissen, wie viele davon für bestimmte Algorithmen benötigt werden.

Das Konzept der Kapselung (enclosure) wäre verletzt, wenn wir dem Programmierer erlaubten, beliebige solcher Zeiger selber zu definieren, um damit direkten Zugriff auf die Listenknoten zu haben. Die Gefahr von Programmierfehlern steigt ebenfalls, wenn mehrere Listen auf diese Weise gleichzeitig verwendet werden.

Der Programmierer kann z. B. die Knoten-Referenzen zweier verschiedener Listen verwechseln und die Listen unwiederbringlich beschädigen, weil durch die rekursive Definition der Knoten einer Liste, die Zeiger der Listen (der Zeiger auf den Listenanfang, der Zeiger der die Liste durchläuft und der Zeiger, der zwei Knoten der Liste verkettet) den gleichen Datentyp haben.

Um diese Probleme zu vermeiden, verwendet man Iteratoren. Ein Listeniterator stellt Operationen zur Verfügung, mit dessen Hilfe eine Liste durchlaufen werden kann. Mehrere Iteratoren können mit derselben Liste gleichzeitig verwendet werden. So hat der Benutzer keinen direkten Zugriff auf die Liste oder auf den Index (current-Zeiger) der Liste.


![[DataStructure/image/Pasted image 20230630102022.png]]



# 13 Java-Klassen für Listen (ArrayList und LinedList)

![[DataStructure/image/Pasted image 20230630134738.png]]

Die Klasse ArrayList verwendet dynamische Arrays (Reihungen).  <br>Die Klasse LinkedList verwendet doppelt verkettete Listen und bietet die Funktionalität der Datenstrukturen Stack (Stapel) und Queue (Warteschlangen).|