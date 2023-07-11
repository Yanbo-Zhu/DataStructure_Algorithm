
# 1 基本理论

Was ist Rekursion?

Wenn sich Probleme in fast identische Teilprobleme zerlegen lassen, dann sind diese oftmals durch rekursive Algorithmen lösbar. 
Die Ergebnisse aus der Lösung der Teilprobleme werden zur Lösung des Gesamtproblems zusammengesetzt. Das Wort Rekursion stammt vom lateinischen Wort recurrere ab, was mit rückschreiten übersetzt wird.

什么时候使用 rekusion
Wann ist es sinnvoll Rekursion einzusetzen? 
Wenn sich ein Problem in fast identische Teilprobleme unterteilen läßt.   dann sind diese oftmals durch rekursive Algorithmen lösbar. 

Warum ist eine gute Lesbarkeit von Programmen wichtig?
Zur besseren Wartung und Erweiterbarkeit


Vorteil:
- Meist kürzer und übersichtlicher als iterative Lösungen (Verwendung von Schleifen)
- Rekursion eignet sich gut zur Verarbeitung und Traversierung von Datenstrukturen wie Bäumen, Graphen oder Listen

Nachteil:
- Kann zu einem höheren Speicherbedarf führen, da bei jedem Aufruf neuer Speicher allokiert wird (Stack-Speicherung)
- Evtl. laufzeitintensiv


## 1.1 Direkte und indirekte rekursive Aufrufe

Bei der direkten Rekursion ruft sich eine Methode selbst auf. 
Bei der indirekten Rekursion dagegen, ruft eine Methode eine andere Methode auf. Diese ruft dann wieder die erste Methode direkt oder indirekt auf. 

```java
// Indirekte Rekursion
public static int med1(Parameter) {
med2(Parameter);
}
public static int med2(Parameter) {
med1(Parameter);
}


// Direkte Rekursion
public static int med1(Parameter) {
med1(Parameter);
}


```


```java
/**
 * Klasse zur Demonstration indirekter Rekursion. Die Methoden 
 * indirektEins und indirektZwei rufen sich gegenseitig an. 
 * Der Parameter i wird inkrementiert.
 * Sobald er positiv ist, terminiert die Rekursion.
 * 
 * @author Maibaum / Geiger / merceron
 * 
 */

public class Indirekt {

    public static void main(String args[]) {
        indirektEins("Start", -5); // Methodenaufruf
    }

    /**
     * Diese Methode ruft indirektZweis auf, und wird von 
     * indirektZwei aufgerufen. Sie kontrolliert die 
     * rekursive Aufrufe mit dem Parameter i.
     * 
     * @param textEins
     * @param i
     *            eine ganze Zahl zum Kontrollieren der 
     *            rekursiven Aufrufe
     */
    static void indirektEins(String textEins, int i) {
        if (i <= 0) {
            System.out.println(textEins + i);
            indirektZwei("Text von Methode 2: ", i + 1);
            // indirekt rekursiver Aufruf

        }
    }

    /**
     * Diese Methode ruft indirektEins auf, und wird 
     * von indirektEins aufgerufen. Der Parameter i wird 
     * einfach weiter gereicht.
     * 
     * @param textZwei
     * @param i
     *            eine ganze Zahl
     */

    static void indirektZwei(String textZwei, int i) {
        System.out.print(textZwei + i);
        indirektEins(" | Text von Methode 1: ", i);
        // indirekt rekursiver Aufruf
    }
}
```


## 1.2 Vergleich von Rekursion und Iteration
Es gibt unterschiedliche Arten von Rekursionen. Manche Rekursionsarten können leicht durch iterative Lösungen ersetzt werden, andere lassen sich nur mit einem sehr hohen Programmieraufwand iterativ lösen.
Iterative Lösungen können rekursiv implementiert werden

要尽量使用 rekusive, 不用 iterative, 因为 他 fehleranfälliger 
die Regel: Problemstellungen, die von Natur aus rekursiv sind, sollen rekursiv programmiert werden und sind keinesfalls durch eine iterative Lösung zu ersetzen. Da iterative Lösungen einen umfangreicheren Programmcode erfordern, sind diese fehleranfälliger und schlechter wartbar als rekursive. 

```java
// Iteration
public static void printTxt(
String txt) {
int i = 1;
while(i <= 10) {
System.out.println(i++ +
" " + txt);
}
System.out.println("stop");
}

// Rekursion
public static void printTxt(
int i, String txt) {
if(i > 10) {
System.out.println("stop");
return;
}
System.out.println(i + " " + txt);
printTxtReku(i+=1, txt);
}
```

```java


/** 
 * Rekursiver Algorithmus zur Fakultätsberechnung
 */
static int rekursiv(int zahl) {
  if (zahl == 1 || zahl == 0) { // Abbruch bei 1
    return 1;
  }
  else{
  	return zahl * rekursiv(zahl - 1); //rekursiver Aufruf
  }
}


/** 
 * Iterativer Algorithmus zur Fakultätsberechnung
 */
static int iterativ(int zahl) {
  int i = 1;           // Schleifenvariable vereinbaren
  int f = 1;           // Variable für Zwischenprodukt
  while (i <= zahl) {  // Berechnungsschleife
    f = i * f;         // Teilprodukt
    i++;               // Schleifenzaehler erhoehen
  }
  return f;           //  Rueckgabe des Fakultaetswertes
}


```


## 1.3 Merkmale der linearen Rekursion (linear recursion) 

jeder Aufruf löst (maximal) einen weiteren Aufruf aus und
die Anzahl rekursiver Aufrufe ist linear abhängig von den Kontrollvariablen.


## 1.4 Speicherverwaltung

Iterativ programmierte Methoden benutzen einen festen Speicherbereich während der Abarbeitung, während bei rekursiven Methoden bei jedem Methodenaufruf erneut Speicherbereich bereitgestellt wird. Rekursive Methoden benötigen demzufolge bedeutend mehr Speicher während der Laufzeit. 
Der Laufzeitspeicher ist als ==Stapel (stack)== organisiert und wird deshalb als Laufzeitstack bezeichnet. Mit Rekursion kann dieser Speichermechanismus zur Übergabe von Variablenwerten elegant ausgenutzt werden.

 
- Eine rekursive Methode wird über einen Stack verwaltet
	- Stack Datenstruktur, in der die Daten linear „übereinander“ gespeichert werden
	- Zugriff auf das letzte Element, was gespeichert wurden 最开始进来的, 最后才被拿出去.   盘子往上累加, 但是 最上面的先出去 
	- Von „oben“ nach „unten“ vom Stack gelesen und freigegeben, d.h. LIFOStrategi) („Last In, First Out“)    最后进来的, 最先被拿出去 , last in. first out 
	- Schnelle Speicherung

**Vorteile der Rekursion**
- Eine rekursive Lösung ist natürlicher und dadurch klarer als eine iterative Lösung.
- Eine rekursive Lösung ist deutlich kürzer als die iterative Variante.
- Die Korrektheit rekursiver Lösungen ist meist leichter zu überprüfen.

**Nachteile**
- Die rekursive Lösung benötigt mehr Speicherplatz. Sie kann dabei den Laufzeitstack effizient ausnutzen.
- Bei großer Rekursionstiefe steigt die Laufzeit stark an.

Bei der Programmierung rekursiver Methoden müssen Sie mit einer Abbruchbedingung (termination condition) dafür sorgen, dass die Rekursion endet.

# 2 Rekursive Algorithmen


Rekursive Algorithmen spielen in der Mathematik und in der Informatik eine große Rolle. Manche Problemstellungen sind von Natur aus rekursiv, wie beispielsweise die Fakultäts­berechnung.

Weitere rekursive Beschreibungen in der Mathematik sind:
- **Definition der natürlichen Zahlen:**  
    0 ist eine natürliche Zahl.  
    Der Nachfolger einer natürlichen Zahl ist wieder eine natürliche Zahl.  
      
- **Die Multiplikation mit einer natürlichen Zahl wird auf die Addition zurückgeführt:**  
    Das n-fache einer Zahl ist das (n-1)-fache der Zahl plus der ursprünglichen Zahl.  
    Ende der Rekursion: Das 1-fache einer Zahl ist die Zahl selbst.  
      
- **Die Potenzierung mit einem natürlichen Exponenten wird auf die Multiplikation zurückgeführt:**  
    Die n-te Potenz einer Zahl ist die (n-1)-te Potenz der Zahl multipliziert mit der Zahl. Ende der Rekursion: Die 1-te Potenz einer Zahl ist die Zahl selbst.


## 2.1 例子 Quicksort

Quicksort ist eine typische Anwendung des Prinzips Divide-&-Conquer, zu deutsch teile und herrsche. Alle Probleme dieser Art lassen sich rekursiv am besten lösen.  
Quicksort ist ein Sortieralgorithmus (sorting algorithm). Er sortiert eine Sequenz fester Länge von ungeordneten Elementen.  
  
**Ablauf von Quicksort**  
1. Sequenz teilen in zwei Bereiche;  
2. Mittleres Element an mittlerer Position (Median) auswählen;  
3. Sequenz am Median trennen in zwei Bereiche (willkürlich vorne, hinten);  
4. Alle Elemente > Median vom vorderen in den hinteren Bereich verschieben;  
5. Entsprechend Elemente < Median vom hinteren in den vorderen Bereich;  
4. Prozess mit beiden Bereichen getrennt wiederholen;  
7. Ende, wenn nur noch 1 Element im Bereich.

Der folgende Quellcode zeigt die Implementierung des Quicksort-Algorithmus in Java. Die fliegenden Fenster zeigen Ihnen Erläuterungen zu den Programmabschnitten.

```java
/**
  * QuickSort.java
  * Programm sortiert
  * Sequenz fester Länge von ungeordneten Elementen.
  * @author Görlitz
  * @version 2.0, 12/2001
  */

class QuickSort {

    /**
     * Sortiert Sequenz fester Länge von ungeordneten Elementen.
     * Quicksort, nach C.A.R. Hoare
     */
    public static void quick(int[] reihe, int u, int o) {
        int i = u, j = o, median;
        median = reihe[(u + o) >> 1];
        do {
            while (reihe[i] < median) {
                i++;
            }
            while (median < reihe[j]) {
                j--;
            }

    	    if (i <= j) {
    	        int temp = reihe[j];
    	        reihe[j] = reihe[i];
    	        reihe[i] = temp;
    	        i++;
    	        j--;
    	    }
        } while (i < j);

    	if (u < j) {
            quick(reihe, u, j);
        }

        if (i < o) {
            quick(reihe, i, o);
        }

    }
}

```
