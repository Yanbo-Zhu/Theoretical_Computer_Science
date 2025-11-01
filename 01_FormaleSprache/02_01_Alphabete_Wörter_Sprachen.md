


Zu den formalen Sprachen gehören u. a. die mathematische und chemische Formelsprache und insbesondere auch die Programmiersprachen, wie z. B. Pascal oder Java. Hier stehen allerdings formale Sprachen und ihre Eigenschaften auf einer noch abstrakteren Ebene im Mittelpunkt der Betrachtung. Programmiersprachen werden dann lediglich zur beispielhaften Konkretisierung herangezogen.


Eine _formale Sprache_ – oder kurz eine _Sprache_ – wird aufbauend auf den Begriffen _Alphabet_ und _Wort_ definiert .


# 1 Alphabet Σ 


Ein **Alphabet** ist eine nichtleere, endliche Menge von **Zeichen**.

Zeichen haben die Länge 1.


|   |
|---|
|{a, b, c, . . . , z}|
|{α, β, γ, . . . , ω}|
|{0, 1}|


![](image/Pasted%20image%2020251031132119.png)




# 2 Wort w

Ein **Wort** über einem Alphabet ist eine endliche Zeichenfolge, die aus keinem oder endlich vielen Zeichen des Alphabets zusammengesetzt ist. Die Zeichen werden unmittelbar hintereinander geschrieben.

Die Zeichenfolge, die aus keinem Zeichen besteht, heißt **leeres Wort** und wird mit  ϵ  bezeichnet (gesprochen: Epsilon).

Beispiel

|            |                                    |
| ---------- | ---------------------------------- |
| informatik | ist Wort über {a, b, c, . . . , z} |
| rxyzzwzyq  | ist Wort über {a, b, c, . . . , z} |
| 0110010    | ist Wort über {0, 1}               |
| 0          | ist Wort über {0, 1}               |
| ϵ          | ist Wort über jedem Alphabet       |

![](image/Pasted%20image%2020251031135216.png)


## 2.1 leeres Wort ϵ  Epsilon

**leeres Wort** und wird mit  ϵ
 leere Sprache ∅
## 2.2 **Länge eines Wortes** | w | 
Die **Länge eines Wortes** w über einem Alphabet ist die Anzahl seiner Zeichen, geschrieben ∣w∣.


|   |   |
|---|---|
|∣informatik∣|= 10|
|∣rxyzzwzyq∣|= 9|
|∣0110010∣|= 7|
|∣0∣|= 1|
|∣ϵ∣|= 0|

## 2.3 Die Menge der natürlichen Zahlen  ℕ0

Die Menge der natürlichen Zahlen wird wie folgt definiert verwendet: 
ℕ:={1,2,3,…}
ℕ0:={0,1,2,…}


## 2.4 Alphabet - formale Darstellung

Es sei Σ ein Alphabet. Dann wird Σn wie folgt definiert: 
Σn:={w∣w ist Wort über Σ,|w|=n,n∈ℕ0}


![](image/Pasted%20image%2020251031132451.png)


Zu beachten ist in dem Beispiel, dass {0,1} einmal das Alphabet und einmal die Menge der Wörter der Länge 1 über dem Alphabet {0,1} ist.

![](image/Pasted%20image%2020251031132527.png)

Zu beachten ist in dem Beispiel, dass {0,1} einmal das Alphabet und einmal die Menge der Wörter der Länge 1 über dem Alphabet {0,1} ist.
需要注意的是，在这个例子中，**{0,1}** 既表示**字母表（Alphabet）**，又表示在该字母表 **{0,1}** 上由**长度为 1** 的所有单词组成的**集合**。


# 3 Wortmenge

## 3.1 ${\Sigma}^3$

这里面的每个 element  都有三个字母组成

![[Pasted image 20251101085045.png]]

![[Pasted image 20251101084348.png]]

![[Pasted image 20251101085131.png]]
## 3.2 Menge aller Wörter Σ*, Σ+

Die Menge aller Wörter über dem Alphabet Σ wird mit Σ* bezeichnet und wie folgt definiert:

Σ*:=Σ0∪Σ1∪Σ2∪…

Die ϵ-freie Menge aller Wörter über Σ wird mit Σ+ bezeichnet und wie folgt definiert:

Σ+:=Σ1∪Σ2∪Σ3∪…

![](image/Pasted%20image%2020251031132653.png)


Sei Σ={0,1} ein Alphabet. Dann ist  

|   |   |   |
|---|---|---|
|Σ*|=|{ϵ,0,1,00,01,10,11,000,001,…}|
|Σ+|=|{0,1,00,01,10,11,000,001,…}|

Es gilt offensichtlich Σ*=Σ+∪{ϵ}.


![](image/Pasted%20image%2020251031132847.png)

## 3.3 $⋃_{i=0}^{2} Σ^i$

![[Pasted image 20251101085332.png]]

![[Pasted image 20251101085119.png]]

我们要找出在长度 ≤ 2 的所有单词中，哪些是回文的。

| w   | wᴿ  | 相等吗？ |
| --- | --- | ---- |
| ε   | ε   | ✅    |
| a   | a   | ✅    |
| b   | b   | ✅    |
| aa  | aa  | ✅    |
| ab  | ba  | ❌    |
| ba  | ab  | ❌    |
| bb  | bb  | ✅    |

结果为 
L={ϵ,a,b,aa,bb}

# 4 Wortordnung ⪯Σ

Ist auf einem Alphabet eine lineare Ordnung definiert, so lassen sich die Wörter über diesem Alphabet der Länge nach aufsteigend und bei gleicher Länge lexikographisch anordnen. Eine solche Ordnung wird _Wortordnung_ genannt.

如果在一个字母表上定义了**线性顺序**，  
那么就可以根据这个顺序，将该字母表上构成的所有单词按**长度递增**排列，  
并在长度相同的情况下按**字典序（lexikographisch）**排列。  
这种排列方式称为**词序（Wortordnung）**。

![](image/Pasted%20image%2020251031133232.png)


Sei Σ={a,b,c,…,z} Alphabet mit einer darauf definierten linearen Ordnung a⪯Σb⪯Σ…⪯Σz.  

Auf Σ* ergibt sich damit eine Wortordnung wie folgt: ϵ⪯a⪯b⪯…⪯z⪯aa⪯ab⪯…⪯az⪯ba⪯bb⪯…⪯zz⪯aaa⪯…

![](image/Pasted%20image%2020251031133349.png)


![](image/Pasted%20image%2020251031144013.png)


# 5 Konkatenation (Σ∗,⋅)

Auf Σ* wird nun eine Verknüpfung definiert, die _Konkatenation_ oder auch _Verkettung_ genannt wird. Dabei werden Wörter ohne ein Verknüpfungssymbol hintereinander geschrieben bzw. miteinander verkettet.

在 Σ∗Σ^*Σ∗ 上定义了一种称为**连接（Konkatenation）**或**串联（Verkettung）**的运算。  
在这种运算中，两个单词被**直接写在一起**，中间**不使用任何连接符号**，  
也就是说，它们被**首尾相接地连接起来**。

Es seien zwei Wörter v und w über dem Alphabet Σ gegeben. Die Verknüpfung Konkatenation ⋅ auf Σ* ist dann wie folgt definiert: v⋅w:=vw.
Das Wort vw heisst die Konkatenation von  v  und  w  und ist wieder ein Wort über dem Alphabet Σ.

Das leere Wort ist das neutrale Element bzgl. der Konkatenation, d. h. für beliebige Wörter w gilt: ϵw=wϵ=w.

|                        |                                         |
| ---------------------- | --------------------------------------- |
| theoretische           | ist ein Wort über {a,b,c,…,z}           |
| informatik             | ist ein Wort über {a,b,c,…,z}           |
| theoretischeinformatik | ist dann auch ein Wort über {a,b,c,…,z} |

---


Das Konkatenationssymbol · wird meist nicht geschrieben. Um die Identifizierbarkeit der Wörter einer Konkatenation zu erhalten, kann dann geklammert werden. Gleiches gilt zur Festlegung der Auswertungsreihenfolge bei Konkatenation von mehr als zwei Wörtern. Als Klammersymbole sind Zeichen zu wählen, die nicht im Alphabet enthalten sind.

Wird die Menge aller Wörter Σ* zusammen mit der darauf definierten Verknüpfung Konkatenation · und dem leeren Wort ϵ als eine algebraische Struktur betrachtet, so ist festzustellen, dass (Σ*,⋅) ein Monoid mit ϵ als neutralem Element ist. Es gilt also das Assoziativgesetz u(vw)=(uv)w für alle u,v,w∈Σ*.

Das Kommutativgesetz gilt dagegen i. a. nicht, also vw≠wv für einige v,w∈Σ*.

Die Operation Konkatenation kann auch auf Mengen von Wörtern erweitert werden. Die Konkatenation M1 · M2 von zwei Mengen von Wörtern ist dann die Menge aller Wörter die sich als Konkatenation eines Wortes aus M1 und eines Wortes aus M2 schreiben lässt:


![](image/Pasted%20image%2020251031133553.png)


**连接符号（·）**通常省略不写。  
为了保证在连接后的字符串中仍能**区分各个单词的边界**，可以使用**括号**来标示。  
当连接的不止两个单词时，括号还可以用来**确定运算的顺序**。  
作为括号的符号，必须选用**不属于字母表**的符号。

如果将所有单词的集合 Σ∗Σ^*Σ∗，连同定义在其上的连接运算（·）和空词 ϵϵϵ 一起视为一个代数结构，  
那么可以发现：  
(Σ∗,⋅)(Σ^*, ·)(Σ∗,⋅) 是一个**幺半群（Monoid）**，其中 ϵϵϵ 是其**单位元（neutrales Element）**。

换句话说，连接运算满足**结合律（Assoziativgesetz）**：

u(vw)=(uv)wfu¨r alle u,v,w∈Σ∗.u(vw) = (uv)w \quad \text{für alle } u, v, w \in Σ^*.u(vw)=(uv)wfu¨r alle u,v,w∈Σ∗.

但它**通常不满足交换律（Kommutativgesetz）**，即：

vw≠wvfu¨r einige v,w∈Σ∗.vw \ne wv \quad \text{für einige } v, w \in Σ^*.vw=wvfu¨r einige v,w∈Σ∗.

连接运算还可以**扩展到单词集合**上。  
两个单词集合 M1M_1M1​ 和 M2M_2M2​ 的连接（记作 M1⋅M2M_1 \cdot M_2M1​⋅M2​）定义为：  
由所有可以写成  
“来自 M1M_1M1​ 的一个单词” 与 “来自 M2M_2M2​ 的一个单词”  
**首尾相接连接而成的单词**所组成的集合。


## 5.1 Konkatenation with  leere Wort

Das leere Wort ist das neutrale Element bzgl. der Konkatenation, d. h. für beliebige Wörter w gilt εw = wε = w.


## 5.2 Konkatenation von Mengen von Wörtern M1⋅M2

Seien M1 und M2 Mengen, welche jeweils Wörter enthalten. Dann ist die Konkatenation dieser beiden Mengen definiert als

M1⋅M2:={w|∃x∈M1,∃y∈M2:w=xy}


**单词集合的连接（Konkatenation von Mengen von Wörtern）**

设 M1M_1M1​ 和 M2M_2M2​ 为包含若干单词的集合。  
则这两个集合的连接定义为：

![](image/Pasted%20image%2020251031133639.png)

也就是说，M1⋅M2M_1 \cdot M_2M1​⋅M2​ 是由所有可以写成 **“来自 M1M_1M1​ 的单词 x” 与 “来自 M2M_2M2​ 的单词 y” 连接而成的单词 w”** 所组成的集合。


# 6 Teilwort, Präfix, Suffix

Es seien u und w Wörter über dem Alphabet Σ.
- Ein Wort u heisst **Teilwort** von w, wenn es t,v∈Σ* gibt, so dass w=tuv.
- Ein Wort u heisst **Präfix** von w, wenn es v∈Σ* gibt, so dass w=uv.
- Ein Wort u heisst **Suffix** von w, wenn es t∈Σ* gibt, so dass w=tu.    

Gilt jeweils zusätzlich u≠w, so heisst u **echtes Teilwort, Präfix bzw. Suffix** von w.

Das leere Wort ist Teilwort, Präfix bzw. Suffix eines jeden Wortes.

|   |   |
|---|---|
|form|ist Teilwort von informatik|
|100|ist Teilwort von 0110010|
|in|ist Präfix von informatik|
|10|ist Suffix von 0110010|




## 6.1 Wortpotenzen


Primär zur Schreibvereinfachung von Wortwiederholungen werden so genannte _Wortpotenzen_ als mehrfache Konkatenationen mit sich selbst eingeführt. Ggf. sind die jeweiligen Teilwörter zu klammern.

为了简化**单词重复书写**，引入了所谓的**词的幂（Wortpotenzen）**，  
即将一个单词与自身进行多次连接。  
在必要时，可以对各个部分单词使用**括号**以明确连接顺序。

![](image/Pasted%20image%2020251031134141.png)
Neben der Konkatenation sei hier noch die Spiegelung eines Wortes eingeführt.

## 6.2 Spiegelung eines Wortes

![](image/Pasted%20image%2020251031134240.png)

Wörter mit der Eigenschaft w=wR wie z. B. abba, otto oder reliefpfeiler heissen _Palindrom_.

![](image/Pasted%20image%2020251031134253.png)

具有性质 w=wRw = w^Rw=wR 的单词（即正读和反读相同的单词），  
例如 **abba**, **otto** 或 **reliefpfeiler**，称为**回文（Palindrom）**。

# 7 Sprache  L

Damit sind nun alle Begriffe eingeführt, um eine _formale Sprache_ zu definieren.

Eine (formale) Sprache L über einem Alphabet Σ ist eine Menge von Wörtern über Σ, also L⊆Σ*.

![](image/Pasted%20image%2020251031134613.png)


Eine formale Sprache ist also nichts anderes als eine Menge, deren Elemente Wörter sind. Die üblichen Mengenrelationen und -operationen können also auch auf formale Sprachen angewendet werden. Eine Semantik ist für Wörter in diesem Kontext im Gegensatz zu natürlichen Sprachen aber auch im Gegensatz zu Programmiersprachen nicht definiert.

Zu beachten ist der Unterschied zwischen ∅ und {ϵ}. 
∅ ist die leere Sprache, die kein Wort enthält, und {ϵ} ist eine Sprache, die ein Wort enthält, das leere Wort.

Ansonsten gibt es endliche Sprachen, die endlich viele Wörter enthalten, und unendliche Sprachen, die unendlich viele Wörter enthalten.

Das zentrale Problem im Zusammenhang mit formalen Sprachen ist die Entscheidung bzw. die Entscheidbarkeit, ob ein Wort zu einer Sprache gehört oder nicht (Das **Wortproblem**).

因此，**形式语言（formale Sprache）**本质上只是一个**集合**，其元素是单词。  
常见的集合关系和集合运算同样可以应用于形式语言。  
然而，与自然语言和编程语言不同，**形式语言中的单词并没有定义语义（Semantik）**。


此外，形式语言可以分为：
- **有限语言**：包含有限多个单词；
- **无限语言**：包含无限多个单词。

与形式语言相关的核心问题是**判定问题（Entscheidbarkeit）**，即**判断一个单词是否属于某个语言**（也称为**单词问题 / Wortproblem**）。

## 7.1 注意 **∅** 和 **{ϵ}** 的区别.  leere Sprache ∅

- **∅** 是**空语言**，不包含任何单词；
- **{ϵ}** 是一个语言，包含一个单词，即**空词（leeres Wort）**。

