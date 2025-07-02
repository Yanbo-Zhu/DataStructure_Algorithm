

# 1 Tiefsuche 

![[04_Algorithm/image/Pasted image 20250625102055.png]]

![[04_Algorithm/image/Pasted image 20250625101928.png]]

![[04_Algorithm/image/Pasted image 20250625101945.png]]


![[04_Algorithm/image/Pasted image 20250625102022.png]]


# 2 BereitenSuche 



![[04_Algorithm/image/Pasted image 20250625102857.png]]



## 2.1 Example 

![[04_Algorithm/image/Pasted image 20250625102034.png]]

Vorgehen bei der Breitensuche:
1. **Start bei A** → in die Warteschlange.
2. Besuche Knoten, entferne ihn aus der Warteschlange.
3. Füge alle **noch nicht besuchten Nachbarn** in **alphabetischer Reihenfolge** zur Warteschlange hinzu.

Schritt-für-Schritt BFS:
1. **A** → Nachbarn: B, C, D → alphabetisch: **B, C, D**
    - Warteschlange: `B, C, D`
2. **B** → Nachbarn: A, C, E, G → A & C sind schon in Warteschlange oder besucht
    - Neue Nachbarn: **E, G** → alphabetisch: **E, G**
    - Warteschlange: `C, D, E, G`
3. **C** → Nachbarn: A, B, D, E, F → A, B, D, E sind bereits besucht/queued
    - Neuer Nachbar: **F**
    - Warteschlange: `D, E, G, F`
4. **D** → Nachbarn: A, C, F → alle besucht/queued
    - Warteschlange bleibt: `E, G, F`
5. **E** → Nachbarn: B, C, F, G → alle besucht/queued
    - Warteschlange: `G, F`
6. **G** → Nachbarn: B, E, H, I → B, E schon besucht
    - Neue Nachbarn: **H, I**
    - Warteschlange: `F, H, I`
7. **F** → Nachbarn: C, D, E → alle besucht
    - Warteschlange: `H, I`
8. **H** → Nachbarn: G, I → G schon besucht
    - I ist bereits in Warteschlange
    - Warteschlange: `I`
9. **I** → Nachbarn: G, H → beide schon besucht
    - Warteschlange leer → **Fertig**

![[04_Algorithm/image/Pasted image 20250625103332.png]]








