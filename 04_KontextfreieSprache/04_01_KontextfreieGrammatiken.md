
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


## 1.1 Grammatik 

Regeln einer Sprache 



## 1.2 **Kontextfreie Grammatik**

Warum heißt eine kontextfreie Grammatik „kontextfrei“?
In einem Ableitungsschritt  wird eine Variable unabhängig von seinen Nachbarzeichen -seinem Kontext- durch die rechte Seite einer anwendbaren Produktion ersetzt.
在一次推导步骤中，一个变量（非终结符）可以**不受其邻近符号——也就是它的上下文——的影响**，而被一个可用产生式的右侧替换。


Kontextfrei =  kontextfahig 
Antonym: Kontextabhangig 

![[Pasted image 20251114144024.png]]


V:  Menge von nicht-terminal variable 大写
SIGMA:  Terminale Symbol  小写
R: Regeln/ Production 
S: Startvariable    大写


S -> a 
S -> aA 



Charakteristisch für die kontextfreien Produktionen ist, dass die linke Seite aus genau einem Nichtterminalzeichen und die rechte Seite aus einem Wort über den Terminal- oder Nichtterminalzeichen der Grammatik besteht. Daher auch der Name, denn in einer Ableitung wird ein Nichtterminalzeichen unabhängig von seinen Nachbarzeichen – seinem Kontext – durch die rechte Seite einer anwendbaren Produktion ersetzt. Die von kontextfreien Grammatiken erzeugten Sprachen werden nun auch _kontextfreie Sprachen_ genannt.



## 1.3 Ableitung

![[Pasted image 20251114144117.png]]


## 1.4 Sprache einer Grammatik

![[Pasted image 20251114144133.png]]

## 1.5 Kontextfreie Sprache

Eine Sprache wird kontextfreie Sprache genannt, wenn es eine kontextfreie Grammatik gibt, die sie erzeugt. Die Klasse oder Sprachfamilie der kontextfreien Sprachen wird mit ℒ_kf bezeichnet.

![[Pasted image 20251114144202.png]]

![[Pasted image 20251114144221.png]]

Die Sprache L(G1) ist also kontextfrei. Zur Erinnerung, im [Beispiel nichtregulärer Sprache](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen "Eigenschaften Regulärer Sprachen") wurde gezeigt, dass diese Sprache nicht regulär ist.

Zur Veranschaulichung von Ableitungen insbesondere in den einleitend genannten Anwendungen haben sich _Ableitungsbäume_ als sehr hilfreich erwiesen. Sie sollen deshalb hier in allgemeiner Form eingeführt werden.

## 1.6 **Ableitungsbaum**

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


## 1.7 Ein- und Mehrdeutigkeit

**歧义和歧义**

那是 G上下文无关文法。

- G这意味着，如果它适用于每个单词，则含义明确无误。 w∈L(G)推导树只有一个。
- G如果它是一个词，则表示含义模糊。 w∈L(G)具有多个推导树。

一种与上下文无关的语言 L如果没有明确的、与上下文无关的语法，那么它本身就是有歧义的。 L给予。



![[Pasted image 20251114144524.png]]

`Die Grammatik G4 ist also mehrdeutig, denn z.B. das Wort a+a*a hat zwei Ableitungsbäume. Die Sprache L(G4) ist aber nicht inhärent mehrdeutig, betrachte dazu die Grammatik G5 in Beispiel [Kontextfreie Grammatik 4](https://vfhti.eduloop.de/loop/Kontextfreie_Grammatiken#bsp_KfGr4). Diese Grammatik ist äquivalent zu G4, d.h. L(G4)=L(G5), und eindeutig, was hier nicht bewiesen wird. Es gibt natürlich aber inhärent mehrdeutige Sprachen.`



![[Pasted image 20251114144536.png]]

![[Pasted image 20251114144601.png]]

Abschließend in diesem Abschnitt wird noch eine Normalform für kontextfreie Grammatiken eingeführt, die _Chomsky Normalform_. Durch eine solche Normierung kann die Anwendung kontextfreier Grammatiken und die Herleitung von Eigenschaften kontextfreier Sprachen vereinfacht werden. So wird die hier definierte Normalform später zum Beweis des Pumping Lemmas für kontextfreie Sprachen benötigt.


## 1.8 Chomsky Normalform



![[Pasted image 20251114144630.png]]

Eine kontextfreie Grammatik (V,Σ,R,S) ist in Chomsky Normalform, wenn die Regeln von der folgenden Form sind:

|     |     |     |
| --- | --- | --- |
| A   | →   | BC  |
| A   | →   | a   |

wobei a∈Σ und A,B,C∈V, und B und C dürfen nicht die Startvariable sein. Zusätzlich ist die Regel S→ϵ erlaubt.


> **Chomsky Normalform**: Jede kontextfreie Sprache kann durch eine kontextfreie Grammatik in Chomsky Normalform generiert werden.

---

**Chomsky Normalform（CNF）** 是一种对 **上下文无关文法（CFG）** 的标准化形式。

一个 CFG 若在 CNF 中，则所有产生式必须满足：

**1. 形如 A → BC**
- A, B, C 是非终结符
- B 和 C **不能是开始符号**
- 右侧只有两个非终结符

**2. 或者形如 A → a**
- a 是一个终结符
- 右侧只能是一个终结符

**3. 或者允许一种特殊情况：ε 产生式**
只有当开始符号 S 可以推出 ε（空串）时，才允许： **S → ε**

**CNF = 每条产生式只有两种形态：**
① A → BC（两个非终结符）
② A → a（一个终结符）
特例：S → ε（仅限空串）



![[Pasted image 20251121213913.png]]


![[Pasted image 20251121213934.png]]



### 1.8.1 Beweis

![[Pasted image 20251114144717.png]]


![[Pasted image 20251114144729.png]]

![[Pasted image 20251114144740.png]]


![[Pasted image 20251114144748.png]]



# 2 例子 
V:  Menge von nicht-terminal variable 大写
SIGMA:  Terminale Symbol  小写
R: Regeln/ Production 
S: Startvariable    大写


S -> a 
S -> aA 


## 2.1 例子 

![[Pasted image 20251121161833.png]]


L(G)  Language von Grammtik  

1 
das Grammatik erzeugt aab
![[Pasted image 20251121162304.png]]


2 
Das Grammatik kann  "ab" erzeugen 
S-> aS ,  S->A, A->b  . dann ergibt sich ab 
![[Pasted image 20251121162824.png]]


3 die Sprache von dem  Grammatik, welche Wort erzeugt das Grammtik 
$(a|a^*|a^*b|b)$

ein a oder 
ein b 
oder beliebige a dan b

Genau dann muss es doch nciht auf b enden


![[Pasted image 20251121164026.png]]\
keine b, oder b, ansonsten a muss das Ende des Worteres sein 

Finde auch beliebig viele beinhaltet auch keins, ja


## 2.2 例子 

![[Pasted image 20251121164527.png]]



(a* | b*) b
`(ab)*b`

## 2.3 例子 

erzeigt eine Kontextfreie Grammatik 
![[Pasted image 20251121165015.png]]

代表 a 和 b 出现的次数一样 

Grammatik 应该是这样 
```
S --> ab
S --> aSb
```


---

代表 a 和 b 出现的次数可以不一样 

![[Pasted image 20251121165231.png]]

S -> aS , S -> aX, X -> bX , X -> b  是对的 

![[Pasted image 20251121165809.png]]

---

S -> aS , S -> X, X -> bX , X -> b   这样有个 
stimmt das a am anfang könnte übersprungen werden
 Die hat eine Sache die nicht genau der Aufgabenstellung entspricht reicht einen eine Rahmenbedingungen welche wäre das.


## 2.4 

![[Pasted image 20251121165859.png]]

都是 n 

如何构建 grammtik 

## 2.5 

![[Pasted image 20251121170010.png]]


如何构造 grammatik 


```
S -> aSa, S -> bSb, S->bb, S ->aa
```





# 3 


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

## 3.1 不依赖上下文

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


## 3.2 上下文有关规则（Context-Sensitive Grammar）


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


## 3.3 推导树 （Parse Tree）

**推导树是一棵树，表示根据文法规则一步步把非终结符展开，最终生成句子的过程。**

它展示：

- 根节点：文法的开始符号
    
- 内部节点：非终结符
    
- 叶子节点：终结符（实际句子中的符号）
    
- 每一条展开规则都对应文法的一条产生式
    

推导树直观地告诉你：  
“这个句子是怎么一步一步依据文法规则生成出来的”。


|名称|说明|
|---|---|
|根节点|文法开始符号（如 S）|
|内部节点|文法非终结符（如 S, A, B）|
|叶子节点|文法终结符（如 a, b, +, id）|
|子树|代表一次产生式的使用|
|从左到右的叶子序列|就是句子本身|


### 3.3.1 一个简单示例

文法：

```
S → AB
A → a
B → b
```

句子：`ab`

推导树
```
      S
     / \
    A   B
    |   |
    a   b
```


解释：
- S 用规则 `S → AB`
- A 用规则 `A → a`
- B 用规则 `B → b`
- 最终 leaf 是 `a b`，就是生成出的句子



```
E → E + T | T
T → a
```


---

文法
```
E → E + T | T
T → a
```

句子: a + a

一种推导树：
```
        E
       /|\
      E + T
      |   |
      T   a
      |
      a
```

叶子节点从左到右： a + a


---

推导树可以用于：

✔ 证明一句话可以由文法生成
构造出推导树，就是证明这个句子是该文法的合法串。

✔ 分析语法结构（编译器语法分析）
编译原理里，语法分析器（parser）内部就是在构造推导树。

✔ 区分二义性
如果一个句子有多个不同的推导树，说明文法是二义性的（ambiguous）。


## 3.4 歧义（Ambiguity）

■ 文法 G 是无歧义的，当且仅当：

对于每个句子 
w∈L(G)
w∈L(G)，
只有一个推导树。

■ 文法 G 是有歧义的，当且仅当：

存在一个句子 
w∈L(G)
w∈L(G)，
具有两个或更多推导树。

■ 一个上下文无关语言 L 是固有歧义的，如果：

不存在任何无歧义的上下文无关文法 G，使得

L=L(G)
L=L(G)。


---

1 文法的歧义（Ambiguous Grammar）

一个上下文无关文法 G 是有歧义的（ambiguous），如果：

存在至少一个句子 
w∈L(G)
w∈L(G)
具有不止一个推导树（parse tree）或不止一个最左推导（leftmost derivation）。

也就是说，只要某个句子有两种不同的语法结构，那么文法就是有歧义的。

---

2 文法的非歧义性（Unambiguous Grammar）

文法 G 是无歧义的（unambiguous），如果：

对于 每个句子 
w∈L(G)
w∈L(G)，
G 都只有一个推导树（唯一的结构解释）。

---

3 语言的歧义（Ambiguous Language vs. Inherently Ambiguous Language）

注意：

文法（Grammar）可以是歧义的

语言（Language）也可能本身就具备歧义性

两者不是同一回事。

