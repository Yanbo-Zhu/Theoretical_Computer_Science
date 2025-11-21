
Die kontextfreien Sprachen wurden im vorangehenden Abschnitt mittels eines generativen Verfahrens eingeführt, den kontextfreien Grammatiken. Es gibt für diese Sprachfamilie nun ebenso ein analysierendes bzw. erkennendes Verfahren wie für die regulären Sprachen. Dazu wird das Modell des endlichen Automaten erweitert, so dass diese auch rekursive Strukturen erkennen können. Diese Erweiterung führt zu den so genannten _Kellerautomaten_. Der endlichen Steuereinheit und dem Eingabeband des bisherigen Automatenmodells wird ein Stapelspeicher – auch _Keller_ oder _Stack_ genannt – hinzugefügt (Abbildung [Abb. 4.7 Kellerautomat](https://vfhti.eduloop.de/loop/Kellerautomaten#fig_KA "Abb. 4.7 Kellerautomat")).



![[600px-TIO_47Kellerautomat.png]]


Ein Stapelspeicher zeichnet sich dadurch aus, dass auf diesen ausschließlich über eine Speicherzelle zugegriffen werden kann, wie z. B. bei einem Bücherstapel, nämlich oben. Ein Zeichen kann nur oben neu hineingeschrieben werden, die bisher gespeicherten Zeichen befinden sich damit jeweils eine Speicherzelle weiter unten im Stapelspeicher. Auch ein lesender Zugriff kann nur auf die oberste Speicherzelle erfolgen. Bei diesem Automatenmodell ist mit dem Lesen eines Zeichens auch seine Löschung verbunden, die darunter gespeicherten Zeichen befinden sich damit dann eine Speicherzelle weiter oben.

Der Keller eines Kellerautomaten zeichnet sich weiterhin dadurch aus, dass er eine unbeschränkte Speicherkapazität aufweist. Es können in ihm also beliebig viele Zeichen gespeichert werden. Da er aber zum Startzeitpunkt leer ist und in jedem Takt nur ein Zeichen hinzukommen kann, wird er nach endlich vielen Takten auch nur endlich viele Zeichen enthalten. Der Keller weist also eine so genannte _potentiell unendliche_ Speicherkapazität auf.

Der Kellerautomat wird hier als ein nichtdeterministischer Automat eingeführt. Es gibt natürlich auch die deterministische Variante mit den entsprechnden Einschränkungen wie beim endlichen Automaten auch. Die deterministischen Kellerautomaten können aber gegenüber den nichtdeterministischen Kellerautomaten nur eine echt kleinere Sprachfamilie erkennen.

In Compilern erfolgt die Syntaxanalyse und die Steuerung des gesamten Übersetzungsprozesses eines Programmes durch einen so genannten _Parser_. Der Parser entspricht dem Berechnungsmodell eines deterministischen Kellerautomaten. Nicht nur bei Programmiersprachen sondern auch bei Markierungssprachen wie z.B. XML oder bei natürlichen Sprachen wird die Analyse und Übersetzung entsprechend der Arbeitsweise dieses Automatentypes durchgeführt. Dennoch werden die Kellerautomaten hier nur in der allgemeineren nichtdeterministischen Variante betrachtet.


# 1 Kellerautomat Definiation  


**Kellerautomat**

Ein Kellerautomat (KA) ist ein 6-Tupel (Q,Σ,Γ,δ,q0,F) mit

1. Q ist eine nichtleere, endlich Zustandsmenge,
2. Σ ist das Eingabealphabet,
3. Γ ist das Kelleralphabet,
4. δ:Q×Σϵ×Γϵ→𝒫(Q×Γϵ) ist die Überführungsfunktion,
5. q0∈Q ist der Startzustand, und
6. F⊆Q ist die Menge von End- bzw. akzeptierenden Zuständen.

![[Pasted image 20251121204555.png]]



Ein Kellerautomat arbeitet nun wie ein endlicher Automat, nur dass bei seinen Überführungen der Keller zu berücksichtigen ist. Er befindet sich zu Beginn im Startzustand. Auf dem Eingabeband steht das abzuarbeitende Wort, der Lesekopf befindet sich auf dem ersten Zeichen, der Keller ist leer.

In Abhängigkeit von seinem aktuellen Zustand, dem Zeichen auf dem Eingabeband und dem obersten Zeichen im Keller geht er in einen Folgezustand über, rückt auf dem Eingabeband den Lesekopf um ein Feld weiter und ersetzt das oberste Kellerzeichen durch ein – möglicherweise auch leeres – Zeichen aus dem Kelleralphabet. Der restliche Kellerinhalt bleibt unverändert bestehen.

Ein Kellerautomat kann alternativ dazu auch eine so genannte ϵ-Überführung ausführen: Unabhängig vom aktuellen Zeichen auf dem Eingabeband, nur abhängig von seinem aktuellen Zustand und dem obersten Zeichen im Keller erfolgen die oben beschriebenen Aktionen. Der Lesekopf bleibt dann aber auf dem Feld stehen.

Ein Kellerautomat beendet seine Arbeit, wenn das Eingabeband abgearbeitet ist. Er akzeptiert oder erkennt seine Eingabe, wenn er sich dann in einem Endzustand befindet, andernfalls akzeptiert er seine Eingabe nicht. Er bleibt auch stehen, wenn sein Überführungsverhalten für ein vorliegendes Tripel aus Q×Σϵ×Γϵ nicht definiert ist. Er akzeptiert dann die Eingabe nicht.

Bei all dem ist zu berücksichtigen, dass der Kellerautomat nichtdeterministisch arbeitet. Er kann sich also je Berechnungsschritt in mehrere Berechnungspfade aufspalten. Die Eingabe wird genau dann akzeptiert, wenn die Eingabe auf mindestens einem der Berechnungspfade akzeptiert wird.


# 2 Berechnung eines Kellerautomaten

![[Pasted image 20251121204729.png]]


In Definition [Kellerautomat](https://vfhti.eduloop.de/loop/Kellerautomaten#def_CompPDA) wird das zu analysierende Wort w als w=y1…ym geschrieben, mit yi∈Σϵ, 1≤i≤m. Analog zu den nichtdeterministischen endlichen Automaten kann hier nun wieder an einigen Positionen ein ϵ auftreten. Diese eingefügten ϵ markieren wieder nur die Positionen der ϵ-Überführungen, sie bedeuten nicht, dass an diesen Stellen in der Eingabe ein ϵ steht.


## 2.1 Beispiel 1

![[Pasted image 20251121205013.png]]


![[Pasted image 20251121205507.png]]

![[Pasted image 20251121210631.png]]

Ein Kellerautomat kann nun auch durch einen _Überführungsgraphen_ dargestellt werden: Die Zustände werden als Knoten dargestellt. Ein Pfeil kennzeichnet den Startzustand. Ein zusätzlicher Kreis kennzeichnet die Endzustände. Die gerichteten Kanten definieren die Überführungen. Die Kantenmarkierung x,a→b von Zustand q nach q′ hat dabei die Bedeutung (q′,b)∈δ(q,x,a). In Abbildung [Abb. 4.8 Kellerautomat K_1, der die Sprache {a^nb^n|n ∈ n_0}](https://vfhti.eduloop.de/loop/Kellerautomaten#fig_PDA-Graph1 "Abb. 4.8 Kellerautomat K_1, der die Sprache {a^nb^n|n ∈ n_0}") ist der Kellerautomat aus Beispiel [Kellerautomat K_1](https://vfhti.eduloop.de/loop/Kellerautomaten#bsp_CFL1) als Überführungsgraph dargestellt.


## 2.2 Beispiel 2

![[Pasted image 20251121211751.png]]


![[Pasted image 20251121212131.png]]

![[Pasted image 20251121212141.png]]

Das Modell eines Kellerautomaten kann also bei der Erkennung bzw. der Analyse von Klammerausdrücken jeder Art eingesetzt werden, z. B. arithmetische, logische und relationale Ausdrücke wie sie in Programmiersprachen vorkommen. Darüber hinaus kann auch ein gesamtes Programm einer höheren Programmiersprache als eine geklammerte Struktur aufgefaßt werden (Abbildung [Abb. 4.10 Struktur der Programmiersprache Java](https://vfhti.eduloop.de/loop/Kellerautomaten#fig_ProgStrukt "Abb. 4.10 Struktur der Programmiersprache Java")), so dass die Syntaxanalyse von Programmen in einem Compiler mit Hilfe des Modells eines Kellerautomaten durchgeführt wird.

![[Pasted image 20251121212153.png]]\\

Neben der Erkennung von Klammerstrukturen wird ein Kellerautomat auch zur Erkennung von Spiegelstrukturen eingesetzt. Eine Spiegelstruktur kann als eine spezielle Klammerstruktur aufgefaßt werden, denn sie hat nur genau in der Wortmitte eine Spiegel- bzw. Symmetrieachse, wie z.B. die Sprache L={wxwR∣w∈{a,b}*} über dem Alphabet {a,b,x}.

Eingangs war schon erwähnt worden, dass die Kellerautomaten genau die kontextfreien Sprachen erkennen können. Zu jedem Kellerautomaten muss also eine äquivalente kontextfreie Grammatik existieren und zu jeder kontextfreien Grammatik ein äquivalenter Kellerautomat. Der Beweis zu dem Satz [Kontextfreie Sprachen und Kellerautomaten](https://vfhti.eduloop.de/loop/Kellerautomaten#satz_PDA), der genau diese Äquivalenz ausdrückt, erfolgt durch zwei solche Konstruktionen (Lemmas [Kontextfreie Sprachen und Kellerautomaten 1](https://vfhti.eduloop.de/loop/Kellerautomaten#lem_PDA1) und [Kontextfreie Sprachen und Kellerautomaten 2](https://vfhti.eduloop.de/loop/Kellerautomaten#lem_PDA2)).


# 3 Satz1: Kontextfreie Sprachen und Kellerautomat

## 3.1 Lemma: Eine Sprache ist genau dann kontextfrei, wenn es einen Kellerautomaten gibt, der sie erkennt.

![[Pasted image 20251121212349.png]]


![[Pasted image 20251121212400.png]]


Beispiel
![[Pasted image 20251121212414.png]]

![[Pasted image 20251121212422.png]]

![[Pasted image 20251121212444.png]]


## 3.2 Lemma:  Eine Sprache ist kontextfrei, wenn es einen Kellerautomaten gibt, der sie erkennt. 


Beweis 
![[Pasted image 20251121212541.png]]

Beispiel 
![[Pasted image 20251121212553.png]]

# 4 Satz2: **Reguläre Sprache und kontextfrei**

Jede reguläre Sprache ist kontextfrei. Es gilt darüber hinaus ℒreg⊂ℒkf.

![[Pasted image 20251121212622.png]]


# 5 Beziehung zwischen den Sprachfamilien

Welche Beziehung besteht zwischen den Sprachfamilien deren Sprachen von regulären Ausdrücken repräsentiert, von kontextfreien Grammatiken erzeugt, von deterministischen und von nichtdeterministischen Kellerautomaten erkannt werden können?

![[Pasted image 20251121214608.png]]

⭐ Beziehung zwischen den vier Sprachfamilien

Wir betrachten vier Klassen:

1. **Reguläre Ausdrücke** → **reguläre Sprachen**
    
2. **Kontextfreie Grammatiken (CFG)** → **kontextfreie Sprachen**
    
3. **Deterministische Kellerautomaten (DPDA)** → **deterministisch kontextfreie Sprachen (DCFL)**
    
4. **Nichtdeterministische Kellerautomaten (NPDA)** → **alle kontextfreien Sprachen (CFL)**
    

Diese Sprachfamilien stehen in einer **echten Hierarchie**:

---

⭐ Endergebnis (Merksatz)

REG⊊DCFL⊊CFL\text{REG} \subsetneq \text{DCFL} \subsetneq \text{CFL}REG⊊DCFL⊊CFL

wo:
- **REG** = reguläre Sprachen
- **DCFL** = deterministisch kontextfreie Sprachen
- **CFL** = kontextfreie Sprachen

---

⭐ Erklärung der Beziehungen

**1. Reguläre Sprache ⊂ deterministisch kontextfreie Sprache (echte Teilmenge)**
- Jede reguläre Sprache kann von einem **DPDA** erkannt werden.
- Beispiel:
    - REG: a∗b∗a^* b^*a∗b∗
    - Diese ist auch deterministisch kontextfrei.

Aber:
- **nicht alle DCFLs sind regulär**, z. B.

{anbn∣n≥1}\{ a^n b^n \mid n \ge 1 \}{anbn∣n≥1}

Das ist deterministisch kontextfrei (DPDA möglich), aber nicht regulär.

![[Pasted image 20251121215022.png]]



---

**2. DCFL ⊂ CFL (ebenfalls echte Teilmenge)**
- Jede Sprache, die ein **DPDA** erkennt, kann auch ein **NPDA** erkennen  
    (deterministisch ⇒ nichtdeterministisch immer möglich).
- Aber: Es gibt kontextfreie Sprachen, die **nicht deterministisch erkennbar** sind:

Beispiel:
{aibjck∣i=j oder j=k}\{ a^i b^j c^k \mid i = j \text{ oder } j = k \}{aibjck∣i=j oder j=k}
oder klassisch:
{wwR∣w∈{a,b}∗}\{ ww^R \mid w \in \{a, b\}^* \}{wwR∣w∈{a,b}∗}
Diese Sprachen sind CFL, aber **keine DCFL**, weil ein DPDA nicht genug deterministisch auswählen kann, wo die Mitte des Wortes ist.

![[Pasted image 20251121215035.png]]

---

**3. CFL = Sprachen, die von nichtdeterministischen Kellerautomaten (NPDA) erkannt werden**
- Kontextsfreie Grammatiken (CFG) erzeugen genau die gleichen Sprachen,
- die NPDA erkennen können.

Formaler Satz:

CFL=L(CFG)=L(NPDA)\
Kontextfreie Grammatik ↔ NPDA  
→ **vollständig äquivalent**


# 6 
## 6.1 Kellerautomat 是什么

德语 **Kellerautomat**（缩写 KA）  
= 英语 **Pushdown Automaton（PDA）**  
= 中文 **下推自动机 / 栈自动机**

它是一种**有限状态机 + 一个栈（Keller, Stack）**的自动机。

`有限状态机（有限记忆） + 栈（无限记忆）`

因为多了一个“栈”，它的计算能力比有限自动机（DFA/NFA）更强，可以识别：

✔ **所有正则语言**  
✔ **所有上下文无关语言（CFL）**



## 6.2 Kellerautomat 为什么和上下文无关文法有关？

非常重要：

> **上下文无关文法（CFG）与下推自动机（PDA）具有完全相同的表达能力。**

这两者是 **等价的**：
- 每一个 CFG 都可以构造出一个识别同样语言的 PDA
- 每一个 PDA 都可以转换成一个生成同样语言的 CFG

因此：

🔸 **CFG 用“产生式”来生成句子**  
🔸 **PDA 用“状态 + 栈操作”来识别句子**

他们解决的是同一类语言：

➡ **上下文无关语言（Context-free Languages, CFL）**


## 6.3 Kellerautomat 如何工作？

PDA 的栈用于：
- 当看到左括号 "(" 就把符号压栈
- 当看到右括号 ")" 就从栈弹出符号
- 如果栈能正确平衡，就说明表达式合法

例如识别：
```
a^n b^n   = { aⁿ bⁿ | n ≥ 1 }
```

工作方式：
1. 每读一个 `a`，向栈中压入一个符号
2. 每读一个 `b`，从栈中弹出一个符号
3. 如果最后栈为空 → 接受    

有限自动机做不到这个语言，因为它没有“记忆能力”，但 PDA 有栈，所以能做到。


我们要识别：

L={anbn∣n≥1}L = \{ a^n b^n \mid n \ge 1 \}L={anbn∣n≥1}

例如：
- `ab` (n=1)
- `aabb` (n=2)
- `aaabbb` (n=3)
- ……

所有这些字符串有一个特点：

> **先若干个 a，然后同样数量的 b。**

有限自动机做不到，因为它不能“记住”前面有多少个 a。

但 PDA（Kellerautomat）可以，因为它有 **栈（Keller）**。

---

PDA 的核心思想

我们用栈来“记住”看到多少个 a：
1. **读到一个 a → 压入一个栈符号（例如 X）**  栈中 X 的数量 = a 的数量
2. **读到一个 b → 从栈弹出一个符号**  每读一个 b 就消耗一个 X
3. 最终:  输入读完, 栈变空

则接受这个字符串。



## 6.4 Kellerautomaten 和 CFG 的关系总结

| 项目   | Kellerautomat (PDA) | Kontextfreie Grammatik (CFG) |
| ---- | ------------------- | ---------------------------- |
| 作用   | 识别语言                | 生成语言                         |
| 内部结构 | 有限状态 + 栈            | 产生式规则                        |
| 表达能力 | 上下文无关语言 (CFL)       | 上下文无关语言 (CFL)                |
| 等价性  | ✔ 与 CFG 等价          | ✔ 与 PDA 等价                   |

📘 **CFG** 就像一位老师在“讲故事”（生成字符串）  
📗 **PDA** 就像一位老师在“听故事”（检查是否符合规则）

两者说的是同一种语言（CFL）。






