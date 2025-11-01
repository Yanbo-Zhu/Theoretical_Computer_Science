
# 1 

![[Pasted image 20251101135713.png]]


L1 = {$\epsilon$, 0, 00, 000, . . .} 
L2 = {$\epsilon$, 1, 11, 111, . . .}


(a) $L_1 \bigcup L_2$ = {$\epsilon$, 0, 00, . . . , 1, 11, . . .} = $\{w | w = 0^i ,  w = 1^i \ mit \ i \in N_0\}$
(b) L1 $\bigcap$ L2 = {$\epsilon$}
(c) L1 \ L2 = {0, 00, 000, . . .} = $\{0^i | i \in N\}$
(d) $L1 \bigcap \Sigma^*$  = L1
(e) (L1 $\bigcup$ L2) & $\Sigma^3$ = {000, 111}

# 2 

![[Pasted image 20251101140610.png]]


DeUinieren Sie für die folgenden Sprachen DEA’s, die diese Sprachen über dem Alphabet
Σ = {0,1} akzeptieren. Stellen Sie dabei die DEA’s durch den Zustandsgraph dar.

(a) L1 = {w |w enthält nur Nullen, wenigstens eine}
![[Pasted image 20251101152341.png]]


(b) L2 = {w |w ist das leere Wort oder enthält nur Nullen}
![[Pasted image 20251101152356.png]]

(c) L3 = {w |w enthält eine durch 3 teilbare Anzahl von Einsen}
![[Pasted image 20251101152407.png]]


(d) L4 = {w |w enthä lt irgendwo 000}
![[Pasted image 20251101152415.png]]

(e) L5 = {w |w enthält eine gerade Anzahl von Nullen und eine gerade Anzahl von Einsen}
![[Pasted image 20251101152427.png]]

# 3 #

Ein NEA kann **nichtdeterministisch raten**, welche Ziffer im Wort die „erste Vorkommensstelle“ der späteren letzten Ziffer ist.

- Beim Einlesen des Wortes bleibt der Automat zunächst im Startzustand `q0`.
    
- Wenn ein Zeichen `a ∈ {0,1,2,3}` gelesen wird, **kann** der Automat (nichtdeterministisch) in einen speziellen Zustand `s_a` übergehen, der bedeutet:  
    _„Wir haben ein früheres `a` gesehen und merken uns dieses Symbol.“_
    
- In `s_a` liest der Automat alle weiteren Zeichen und **wartet auf ein weiteres `a`**.  
    Sobald erneut `a` gelesen wird, kann der Automat in den akzeptierenden Zustand `q_acc` übergehen.  
    Wenn dieses `a` zugleich das letzte Zeichen des Wortes ist, wird das Wort akzeptiert.
    
- Gibt es kein solches `a`, das doppelt vorkommt (also die letzte Ziffer ist neu), gibt es keine akzeptierende Pfadführung.



## 3.1 Formale Beschreibung

- **Alphabet:** Σ={0,1,2,3}
    
- **Zustandsmenge:**  
    Q={q0,s0,s1,s2,s3,q_end}
    
- **Startzustand:** q0
    
- **Akzeptierende Zustände:** {q_end}
    
- **Übergänge:**
    1. `q0` → `q0` mit `0,1,2,3` (normales Weiterlesen)
    2. `q0` → `s0` mit `0`; `q0` → `s1` mit `1`; `q0` → `s2` mit `2`; `q0` → `s3` mit `3`  
        (nichtdeterministisch kann der Automat „merken“, welches Symbol er gesehen hat)
    3. Für jedes `s_a`:
        - `s_a` → `s_a` mit `0,1,2,3` (beliebige Zeichen weiterlesen)
        - `s_a` → `q_end` mit `a` (zweites Vorkommen des gemerkten Zeichens)
        
Der akzeptierende Zustand `q_end` hat keine ausgehenden Kanten – Akzeptanz gilt nur, wenn das Wort an dieser Stelle endet.

## 3.2 Zustandsgraph

![[Pasted image 20251101152456.png]]


# 4 #

![[Pasted image 20251101152507.png]]




## 4.1 Zustandmenge R
![[Pasted image 20251101152729.png]]


## 4.2 Ohne Berücksichtigung von  $\epsilon$-Überführungen： Übergangstabelle

![[Pasted image 20251101152746.png]]


## 4.3 Unter Berücksichtigung von  $\epsilon$-Überführungen


Die  Zustandsmengen E(R) und die Überführungsfunktion $\delta(R,x)$ sind für jedes $R \in Q'$ und $x \in \{a,b,c\}$  zu construieren

E(R) := {q | q ist von R über keine oder mehrere $\epsilon$ -Überführungen erreichbar }

![[Pasted image 20251101152753.png]]

## 4.4 $\delta’(R,x)$

![[Pasted image 20251101152809.png]]

## 4.5 Zustandsgraph

Startzustand von NEA:  {qa}   => Startzustand von Äquivalenten DEA : {qa,qb}
Endzustand von NEA:  {qa}, {qb}, {qc}   => Startzustand von Äquivalenten DEA : {qa}, {qb}, {qc} , {qa, qb}, {qb, qc}, {qa, qc}, {qa, qb, qc}


![[Pasted image 20251101152818.png]]


