
Bisher sind zwei Konzepte zur Definition regulärer Sprachen betrachtet worden, ein die Wörter der Sprache _analysierendes_ Konzept durch endliche Automaten und ein die Wörter _beschreibendes_ Konzept durch reguläre Ausdrücke. In diesem Abschnitt soll dem ein weiteres grundlegendes Konzept hinzugefügt werden, ein _generierendes_ Konzept. Die Wörter einer Sprache werden mittels _Grammatiken_ generiert.

Weiterhin wurde gezeigt, dass es Sprachen gibt, die nicht regulär sind. Die _kontextfreien Grammatiken_ – es handelt sich dabei um einen speziellen Grammatiktyp – sind in der Lage, auch rekursive Strukturen in Sprachen zu beschreiben. Sie sind also mächtiger als die bisher betrachteten Verfahren und werden deshalb in einer Vielzahl von Anwendungen verwandt. Sprachen, die über kontextfreie Grammatiken definiert werden, werden _kontextfreie Sprachen_ genannt.

此外，我们已经看到，有一些语言不是正规语言。**上下文无关文法（kontextfreie Grammatiken）**——这是一类特殊的文法类型——能够描述语言中的递归结构。因此，它们比之前讨论的方法更强大，并因此在各种应用中被广泛使用。通过上下文无关文法定义的语言被称为**上下文无关语言（kontextfreie Sprachen）**。

Kontextfreie Grammatiken wurden zuerst im Zusammenhang mit der Beschreibung der Struktur natürlicher Sprachen studiert, um die Beziehungen von Subjekt, Prädikat und Objekt zu beschreiben. In der Informatik werden kontextfreie Grammatiken z.B. zur

- Spezifikation von arithmetischen, logischen, relationalen Ausdrücken
- Spezifikation von Blockstrukturen in Programmiersprachen (z. B. Pascal) und Markierungssprachen (z. B. HTML, XML)
- Spezifikation der Syntax in Progammiersprachen (z. B. Pascal)

herangezogen. Ihre Notation weicht allerdings häufig von der hier eingeführten ab. So werden in Programmiersprachen als kontextfreie Produktionsregeln u.a. die Backus-Naur-Form oder auch Syntaxdiagramme verwendet. In Markierungssprachen z.B. treten die Markierungen immer paarweise als öffnende und schließende Klammer in der Form <x> und </x> auf.

不过，它们的表示法通常与这里介绍的不同。例如，在程序设计语言中，上下文无关产生式规则往往采用 **BNF（Backus–Naur-Form）** 或 **语法图（Syntaxdiagramme）** 来书写。而在标记语言中，标记通常成对出现，作为打开和关闭标签，例如 `<x>` 和 `</x>`。

Zur Analyse, Interpretation oder Übersetzung solcher mittels kontextfreier Grammatiken definierter Strukturen wird ein so genannter _Parser_ oder _Syntax-Analysator_ verwendet. Das dahinter stehende Berechnungsmodell ist ein _Kellerautomat_, der im nächsten Abschnitt besprochen wird. Sobald die Struktur einer Sprache durch eine kontextfreie Grammatik definiert ist, kann automatisch ein Kellerautomat generiert werden, der genau die Wörter dieser Sprache akzeptiert.

为了分析、解释或翻译这些通过上下文无关文法定义的结构，需要使用所谓的 **解析器（Parser）或语法分析器（Syntax-Analysator）**。其背后的计算模型是 **下推自动机（Kellerautomat）**，将在下一节介绍。

一旦用上下文无关文法定义了某种语言的结构，就可以自动生成一个下推自动机，使其恰好接受该语言的所有单词。

---

**Beispiel Deutsche Sprache**

Die folgenden Regeln (Produktionsregeln oder auch Ersetzungsregeln) einer kontextfreien Grammatik definieren einen sehr vereinfachten Ausschnitt der deutschen Sprache. Sei das zugrunde liegende Alphabet Σ={␣, a, b, c, … , z, A, B, C, … , Z }.

|   |   |   |
|---|---|---|
|〈Satz〉|→|〈Substantive-Phrase〉〈Verb-Phrase〉|
|〈Substantive-Phrase〉|→|〈Substantive〉 ∣ 〈Artikel〉〈Substantive〉 ∣ 〈Pronomen〉|
|〈Verb-Phrase〉|→|〈Verb〉 ∣ 〈Verb〉〈Substantive-Phrase〉|
|〈Artikel〉|→|ein ∣ eine ∣ der ∣ die ∣ das|
|〈Substantive〉|→|Mann ∣ Hund ∣ Katze|
|〈Pronomen〉|→|ich ∣ wir|
|〈Verb〉|→|sehen ∣ mögen ∣ beißen|

Durch fortlaufende Ersetzung von Zeichen mittels dieser Regeln kann ausgehend vom Symbol 〈Satz〉 der Satz "wir sehen eine Katze" abgeleitet werden. Das Leerzeichen zwischen z.B. "wir" und "sehen" wird dadurch erhalten, dass die jeweiligen Wörter jeweils mit einem Leerzeichen abschließen.

|   |   |   |
|---|---|---|
|〈Satz〉|→|〈Substantive-Phrase〉〈Verb-Phrase〉|
||→|〈Pronomen〉〈Verb-Phrase〉|
||→|wir 〈Verb-Phrase〉|
||→|wir 〈Verb〉〈Substantive-Phrase〉|
||→|wir sehen 〈Substantive-Phrase〉|
||→|wir sehen 〈Artikel〉〈Substantive〉|
||→|wir sehen eine〈Substantive〉|
||→|wir sehen eine Katze|

Der Satz "eine Katze wir sehen" hat keine Ableitung mit diesen Regeln.


# 1 Definition


## 1.1 **Kontextfreie Grammatik**

![[Pasted image 20251114144024.png]]


Charakteristisch für die kontextfreien Produktionen ist, dass die linke Seite aus genau einem Nichtterminalzeichen und die rechte Seite aus einem Wort über den Terminal- oder Nichtterminalzeichen der Grammatik besteht. Daher auch der Name, denn in einer Ableitung wird ein Nichtterminalzeichen unabhängig von seinen Nachbarzeichen – seinem Kontext – durch die rechte Seite einer anwendbaren Produktion ersetzt. Die von kontextfreien Grammatiken erzeugten Sprachen werden nun auch _kontextfreie Sprachen_ genannt.


## 1.2 Ableitung

![[Pasted image 20251114144117.png]]


## 1.3 Sprache einer Grammatik

![[Pasted image 20251114144133.png]]

## 1.4 Kontextfreie Sprache

Eine Sprache wird kontextfreie Sprache genannt, wenn es eine kontextfreie Grammatik gibt, die sie erzeugt. Die Klasse oder Sprachfamilie der kontextfreien Sprachen wird mit ℒ_kf bezeichnet.

![[Pasted image 20251114144202.png]]

![[Pasted image 20251114144221.png]]

Die Sprache L(G1) ist also kontextfrei. Zur Erinnerung, im [Beispiel nichtregulärer Sprache](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen "Eigenschaften Regulärer Sprachen") wurde gezeigt, dass diese Sprache nicht regulär ist.

Zur Veranschaulichung von Ableitungen insbesondere in den einleitend genannten Anwendungen haben sich _Ableitungsbäume_ als sehr hilfreich erwiesen. Sie sollen deshalb hier in allgemeiner Form eingeführt werden.

## 1.5 **Ableitungsbaum**

Es seien eine kontextfreie Grammatik G=(V,Σ,R,S) und eine Ableitung A⇒*w mit A∈V, w∈(V∪Σ)* gegeben. Die Darstellung der Ableitung heißt Ableitungsbaum, falls gilt:

- Alle inneren Knoten sind mit Zeichen aus V benannt.
- Alle Blätter sind mit Zeichen aus V∪Σ oder mit dem Zeichen ϵ benannt. Ein Blatt ϵ ist der einzige Kindknoten seines Vaterknotens.
- Sei w1⇒w2 ein Ableitungsschritt aus A⇒*w, der auf Anwendung der Produktion B→X1…Xn resultiert, wobei Xi∈V∪Σ, 1≤i≤n, oder X1=ϵ und n=1. Die Knoten Xi sind in der Reihenfolge von 1 bis n die Nachfolger des Knotens B.

Ein Ableitungsbaum mit dem Startzeichen der Grammatik als Wurzel und Blättern ausschließlich aus Terminalzeichen, also einer vollständigen Ableitung eines von der Grammatik erzeugten Wortes, ist ein wichtiger Spezialfall. In Abbildung [Ableitungsbaum für aaabbb bzgl. der Grammatik G1](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#fig_ParseTree) ist ein Ableitungsbaum für ein Wort aus Beispiel [Kontextfreie Grammatik](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#bsp_cfG1) gegeben.

![[Pasted image 20251114144258.png]]


Zu den kontextfreien Sprachen gehören auch solche, die Spiegelstrukturen mit und ohne Mittekennung oder Klammerstrukturen enthalten. Hier sei eine kontextfreie Grammatik spezifiziert, die Klammerstrukturen generiert.


![[Pasted image 20251114144352.png]]

**Kontextfreie Grammatik 3**

Es sei G4=({E},{a,+,*,(,)},R,E) mit R={E→E+E∣E*E∣(E)∣a} gegeben.

Betrachte dazu die folgenden Ableitungen:

1. E⇒E+E⇒E+E*E⇒*a+a*a
2. E⇒E*E⇒E+E*E⇒*a+a*a
3. E⇒E*E⇒(E)*E⇒(E+E)*E⇒*(a+a)*a

Die von G4 erzeugten Wörter können als arithmetische Ausdrücke interpretiert werden. Die Auswertung dieser Ausdrücke muss sich nun an ihrer Struktur orientieren, und diese wird durch den zugehörigen Ableitungsbaum bestimmt. Betrachte dazu den Ableitungsbaum der Ableitung I [Ableitungsbaum für Wort a+a*a(I)](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#fig_Ableitbaum3a).

Die Auswertung von a+a*a muss ausgehend von den Blättern zur Wurzel hin erfolgen, denn nur bei den Blättern sind die Werte des Terminalzeichens a – in Programmiersprachen spricht man dann von Identifikatoren – bekannt. Die Wurzel hält dann den Wert des gesamten Ausdrucks. Also, es wird erst das Produkt a*a gebildet und dann wird a addiert. Dies entspricht der üblichen Auswertung arithmetischer Ausdrücke, Punkt- vor Strichrechnung.

Nun wird aber der Ausdruck a+a*a auch durch die Ableitung II erzeugt. Der zugehörige Ableitungsbaum ist in Abbildung [Ableitungsbaum für Wort a+a*a(II)](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#fig_Ableitungsbaum3b) dargestellt. Hier wird erst die Summe a+a gebildet und dann a multipliziert. Dies entspricht nicht der üblichen Auswertungsreihenfolge. Wäre genau diese Auswertung erwartet, dann müßte geklammert werden (Ableitung III).

![[Pasted image 20251114144453.png]]


![[Pasted image 20251114144500.png]]

Eine Grammatik, die z. B. arithmetische Ausdrücke oder auch die Syntax einer Programmiersprache definiert, darf solche strukturellen Mehrdeutigkeiten nicht enthalten. Darüber hinaus muss sie natürlich auch die richtige Struktur definieren. Die Grammatik G4 aus Beispiel [Kontextfreie Grammatik 3](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#bsp_KfGr3) ist also nicht geeignet, um arithmetische Ausdrücke und ihre Auswertung zu spezifizieren.

Allgemein werden die Grammatik-Eigenschaften _eindeutig_ und _mehrdeutig_ wie folgt definiert.


## 1.6 Ein- und Mehrdeutigkeit

![[Pasted image 20251114144524.png]]

`Die Grammatik G4 ist also mehrdeutig, denn z.B. das Wort a+a*a hat zwei Ableitungsbäume. Die Sprache L(G4) ist aber nicht inhärent mehrdeutig, betrachte dazu die Grammatik G5 in Beispiel [Kontextfreie Grammatik 4](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#bsp_KfGr4). Diese Grammatik ist äquivalent zu G4, d.h. L(G4)=L(G5), und eindeutig, was hier nicht bewiesen wird. Es gibt natürlich aber inhärent mehrdeutige Sprachen.`





![[Pasted image 20251114144536.png]]

![[Pasted image 20251114144601.png]]

Abschließend in diesem Abschnitt wird noch eine Normalform für kontextfreie Grammatiken eingeführt, die _Chomsky Normalform_. Durch eine solche Normierung kann die Anwendung kontextfreier Grammatiken und die Herleitung von Eigenschaften kontextfreier Sprachen vereinfacht werden. So wird die hier definierte Normalform später zum Beweis des Pumping Lemmas für kontextfreie Sprachen benötigt.


## 1.7 Chomsky Normalform

![[Pasted image 20251114144630.png]]

Eine kontextfreie Grammatik (V,Σ,R,S) ist in Chomsky Normalform, wenn die Regeln von der folgenden Form sind:

|     |     |     |
| --- | --- | --- |
| A   | →   | BC  |
| A   | →   | a   |

wobei a∈Σ und A,B,C∈V, und B und C dürfen nicht die Startvariable sein. Zusätzlich ist die Regel S→ϵ erlaubt.


> **Chomsky Normalform**: Jede kontextfreie Sprache kann durch eine kontextfreie Grammatik in Chomsky Normalform generiert werden.


![[Pasted image 20251114144717.png]]


![[Pasted image 20251114144729.png]]

![[Pasted image 20251114144740.png]]


![[Pasted image 20251114144748.png]]


# 2 


**上下文无关文法是一种用来生成语言中所有合法字符串（单词、语句）的规则系统。**


一个上下文无关文法包含四个部分：

```
G = (V, Σ, R, S)

V = 非终结符（变量）
Σ = 终结符（语言的实际字符）
R = 产生式规则
S = 开始符号

```


---

## 2.1 不依赖上下文

在语言中，一个符号（非终结符）是否能被替换、替换成什么，  
**完全由它自身决定，而不由它左右的“上下文”决定。**

例如 CFG 中有规则：
```
A → abc
```

无论 A 出现在什么地方：

- `xAy`
    
- `pAq`
    
- `AAA`
    
- `S → A`
    

它都可以直接替换成 `abc`。


你不需要看 A 左边是什么，也不需要看右边是什么。  
**A 在任何上下文中都能独立替换成 abc。**

这就是“上下文无关”


## 2.2 上下文有关规则（Context-Sensitive Grammar）


```
`xAy → xαy`
```


这里意思是：

只有当 A 左边是 x 并且右边是 y 的时候，  
A 才能替换为 α。

也就是说：
- A 的替换 **依赖上下文 x 和 y**
- 没有符合上下文时不能替换

这种才叫 “上下文有关”。




