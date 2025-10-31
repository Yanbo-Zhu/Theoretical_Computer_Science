

# 1 Nichtdeterministische endliche Automaten_NEA 的定义

Der _Nichtdeterminismus_ erweitert das Konzept der deterministischen Verarbeitungsweise. Bezogen auf endliche Automaten bedeutet die deterministische Verarbeitungsweise, dass je Zustand und gelesenem Zeichen genau ein Folgezustand definiert ist. 

Ein nichtdeterministischer endlicher Automat lässt dagegen je Zustand und gelesenem Zeichen **keinen** bis **mehrere Folgezustände** zu. 
Des weiteren kann es auch Zustandsüberführungen geben, ohne dass ein Zeichen des Eingabebandes gelesen wird, so genannte ϵ**-Überführungen**. Betrachte dazu das [Beispiel NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_NEA).

非确定性扩展了确定性处理方式的概念。  
对于有限自动机而言，**确定性处理方式**意味着对于每一个状态和读取的字符，**恰好有一个后续状态**被定义。

而**非确定性有限自动机**则允许对于每一个状态和读取的字符，存在 **零个、一个或多个后续状态**。  
此外，还可以存在在不读取输入带上任何字符的情况下进行的状态转换，这种转换称为 **ε-转换**。

请参考 NEA 的示例以进一步理解。


![](image/TIO_29NEA_N.png)

Es handelt sich um einen nichtdeterministischen endlichen Automaten, weil der Zustand A eine ϵ-Überführung hat und der Zustand B für die Eingabe a keinen Folgezustand und für die Eingabe b zwei Folgezustände hat.


这是一个**非确定性有限自动机**，因为状态 **A** 存在 **ε-转换**，而状态 **B** 对输入 **a** 没有后续状态，对输入 **b** 则有两个后续状态。

----

> 还是有一个限定条件就是 但是同一个 zustand 同一个 zeichenn, 只能向 同一个 zustand, 下去就是不成立的 （这条是错误的）

damit kann nicht garantiert werden, dass b der vorletzte Buchstabe ist
![](image/Pasted%20image%2020251031163403.png)

Eb:  letzte Zeichen muss b sein
Ea:  letzte Zeichen muss a sein


----

# 2 **非确定性有限自动机（NEA, Nichtdeterministischer Endlicher Automat）**与**确定性有限自动机（DEA, Deterministischer Endlicher Automat）**在定义和行为上的区别。





Neben der Einführung einer formalen Notation für nichtdeterministische endliche Automaten ist seine Arbeitsweise im Hinblick auf die Zustandsübergänge zu spezifizieren. Darüber hinaus ist die Beziehung zwischen deterministischen und nichtdeterministischen endlichen Automaten bzgl. der von ihnen erkennbaren Sprachen und Sprachfamilien zu analysieren.

Gegenüber der Definition von deterministischen endlichen Automaten sind zwei Erweiterungen für nichtdeterministische endliche Automaten in der Überführungsfunktion notwendig. Die Möglichkeit von ϵ-Überführungen wird formal dadurch ausgedrückt, dass im Argument auch das leere Wort als Eingabezeichen zugelassen wird, Σϵ:=Σ∪{ϵ}. Die Potenzmenge 𝒫(Q) als Wertebereich erlaubt es weiterhin, keinen oder mehrere Folgezustände zu spezifizieren. Die Folgezustände werden zu der jeweiligen Teilmenge von Q zusammengefasst.

![[Pasted image 20251031223110.png]]



 这段话的总体意思
在讨论 **非确定性有限自动机（NEA）** 时，需要：
- 给出它的**形式化定义**；
- 说明它在**状态转移（Zustandsübergänge）**方面是如何工作的；
- 并分析它与**确定性有限自动机（DEA）**之间的关系——特别是它们识别的语言（Sprache）和语言家族（Sprachfamilien）之间的区别与联系。


非确定性有限自动机（NEA）比确定性自动机（DEA）“看起来更灵活”，  
因为它可以有多个可能的转移和空转移（ε）。  
但在识别能力上，它们是等价的——都识别**正规语言**。

## 2.1 总结

|特性|DEA|NEA|
|---|---|---|
|转移函数|δ: Q × Σ → Q|δ: Q × (Σ ∪ {ε}) → 𝒫(Q)|
|下一个状态|唯一|多个或没有|
|ε 转移|不允许|允许|
|是否更强大|❌ 否|❌ 识别的语言相同（正规语言）|
|接受条件|唯一路径到达终止状态|至少一条路径到达终止状态|


## 2.2 与确定性自动机的区别：转移函数的两大扩展

 1 对于 DEA（确定性有限自动机）：

它的转移函数定义为：
δ:Q×Σ→Q\delta: Q \times \Sigma \to Qδ:Q×Σ→Q

也就是说：
- 对于每个状态 q∈Qq \in Qq∈Q 和输入符号 a∈Σa \in \Sigmaa∈Σ，  
    自动机只有**唯一**一个后继状态 δ(q,a)\delta(q, a)δ(q,a)。




2 对于 NEA（非确定性有限自动机）：

我们在转移函数上进行两项扩展：

1️⃣ **允许 ε-Überführungen（ε 转移）**
- 意思是：自动机可以在不读取任何输入符号的情况下，从一个状态跳到另一个状态。
- 形式上写作：

    Σε:=Σ∪{ε}\Sigma_\varepsilon := \Sigma \cup \{\varepsilon\}Σε​:=Σ∪{ε}

![[Pasted image 20251031222327.png]]

这表示：在输入符号集合 Σ 的基础上，再加上一个“空输入”符号 ε。  
因此转移函数可以在没有输入的情况下进行状态变化。


2️⃣ **允许多个或没有后继状态（非确定性）**

![[Pasted image 20251031222415.png]]

- 这意味着：对给定的状态和输入符号，NEA 可能有多个可能的后续状态，或者根本没有。
- 为了表达这种可能性，转移函数的输出不再是单一状态，而是**状态集合**的幂集：
![[Pasted image 20251031222350.png]]
其中 P(Q)\mathcal{P}(Q)P(Q) 是 Q 的**幂集**（即所有子集的集合）。  
例如：

- 如果 δ(q,a)={q1,q2}\delta(q, a) = \{q_1, q_2\}δ(q,a)={q1​,q2​}，表示自动机可以同时“分支”到状态 q1q_1q1​ 和 q2q_2q2​。
	
- 如果 δ(q,a)=∅\delta(q, a) = \emptysetδ(q,a)=∅，表示自动机在该输入下无法继续。


## 2.3 非确定性自动机的“工作方式”

- 在 NEA 中，一个输入字符串可能对应多条不同的状态路径；
- 如果至少存在**一条路径**能够到达接受状态（Endzustand），则输入字符串被接受；
- 换句话说：**NEA 是“存在性”意义上的接受机制**（existential acceptance）。

## 2.4 4️ NEA 与 DEA 的关系

- 尽管 NEA 看起来“更强大”，但事实是：
    > **每一个 NEA 都可以被一个等价的 DEA 模拟。**
- 它们识别**完全相同的语言类**：  
    即**正规语言（reguläre Sprachen）**。
- 这种等价性可以通过所谓的 **Potenzmengenkonstruktion（幂集构造法）** 来证明：
    - 把 NEA 的每个可能状态集合看作 DEA 的一个“复合状态”；
    - 这样就能把一个 NEA 转换成等价的 DEA。



# 3 Tupel in **Nichtdeterministischer endlicher Automat**


```
Ein

5

-Tupel

N=(Q,Σ,δ,q0,F)

heisst nichtdeterministischer endlicher Automat (NEA), falls gilt:

- Q ist eine endliche nicht-leere Menge, die Zustandsmenge
    
- Σ ist ein Alphabet, das Eingabealphabet
    
- δ:Q×Σϵ→𝒫(Q) ist eine Funktion, die Zustandsüberführungsfunktion oder auch Überführungsfunktion
    
- q0∈Q ist der Startzustand
    
- F⊆Q ist die Menge der Endzustände
```


非确定性有限自动机（NFA）的状态转移函数也可以用**状态转移表**的形式来表示（见示例表“非确定性有限自动机的状态转移表”）。

为了表示**某个输入符号下的状态转移未定义**，其函数值被指定为**空集**。
此外，将转移表表示为**矩阵**的形式也是常见的做法。
示例“NEA2”再次展示了前面示例“NEA”的状态转移表。


![[Pasted image 20251031223153.png]]



## 3.1 Beispiel NEA2

N=({A,B,C,D},{a,b},δ,A,{A}) sei ein nichtdeterministischer endlicher Automat mit der Überführungsfunktion δ.


|     | δ:  | a   | b     | ϵ   |
| --- | --- | --- | ----- | --- |
|     | →*A | {C} | {A}   | {B} |
|     | B   | ∅   | {A,B} | ∅   |
|     | C   | {D} | {C}   | ∅   |
|     | D   | {A} | {D}   | ∅   |

Wie aber arbeitet nun ein nichtdeterministischer endlicher Automat seine Eingabe ab, wenn er mehrere Möglichkeiten für einen Zustandübergang hat? Er spaltet sich in alle Alternativen auf und verfolgt diese Berechnungspfade unabhängig voneinander weiter. Ist für einen Zustand und eine Eingabe kein Folgezustand definiert, so terminiert dieser Berechnungspfad. 
Bei ɛ-Überführungen wird kein Eingabezeichen gelesen, der Lesekopf verbleibt auf dem aktuellen Zeichen, und der Automat geht lediglich in einen Folgezustand über. 
Führt mindestens einer von diesen Berechnungspfaden in einen Endzustand und ist dann das Eingabewort auf diesem Berechnungspfad auch vollständig abgearbeitet, so akzeptiert ein nichtdeterministischer endlicher Automat die Eingabe. Die Berechnungspfade des NEA N aus [Beispiel NEA2](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_NEA2) für eine Eingabe ist in Abbildung [Berechnung des NEA N für die Eingabe baaba](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#fig_EAComp4a) dargestellt.

Ein deterministischer endlicher Automat dagegen durchläuft für jede Eingabe nur genau einen Berechnungspfad. Im akzeptierenden Fall endet dieser in einem Endzustand, andernfalls nicht.

 Abb. 2.11: Berechnung des NEA N für die Eingabe baaba
![[Pasted image 20251031223636.png]]

Formal kann die Berechnung und das Ergebnis eines nichtdeterministischen endlichen Automaten mittels Definition [Berechnung eines NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_CompNFA) beschrieben werden.


# 4 Berechnung eines NEA


Sei N=(Q,Σ,δ,q0,F) ein nichtdeterministischer endlicher Automat. Sei w ein Wort über dem Alphabet Σ, und es könne w als w=y1y2…ym geschrieben werden, wobei jedes yi∈Σϵ, 1≤i≤m. Dann akzeptiert N das Wort w, falls eine Zustandsfolge r0,r1,…,rm in Q unter den folgenden drei Bedingungen existiert:

1. r0=q0,
    
2. ri+1∈δ(ri,yi+1), für i=0,1,…,m−1,
    
3. rm∈F.
    

Man sagt dann, dass N die Sprache L erkennt, falls L={w∣N akzeptiert w},  
geschrieben L(N)=L.

![[Pasted image 20251031223814.png]]


![[Pasted image 20251031223827.png]]


In Definition [Berechnung eines NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_CompNFA) wird das zu analysierende Wort w als w=y1…ym geschrieben, mit yi∈Σϵ, 1≤i≤m. An einigen Positionen kann hier nun ein ϵ auftreten, obwohl sonst doch gesagt war, dass in der Eingabe keine ϵ auftreten. Das gilt auch weiterhin. Die hier eingefügten ϵ markieren nur die Positionen der ϵ-Überführungen.
\\

## 4.1 Beispiel: **Berechnung eines NEA mit konkreten Eingaben**


继续以示例 NEA2 中的自动机 NNN 对输入 w1=baabaw_1=\text{baaba}w1​=baaba 的情形为例。可以把 w1w_1w1​ 用字母表 Σε\Sigma_\varepsilonΣε​ 以两种不同方式分解，使得“NEA 的计算”定义中的条件都被满足：

表格（左边为第一种分解，右边为第二种分解）表示每个时刻 iii 的状态 QQQ 以及剩余未读的子词 yi+1…ymy_{i+1}\dots y_myi+1​…ym​。

Werde weiterhin das [Beispiel NEA 2](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_NEA2) für die Eingabe w1=baaba betrachtet. Es gibt zwei Möglichkeiten w1 über dem Alphabet Σϵ zu schreiben, so dass die Bedingungen aus Definition [Berechnung eines NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_CompNFA) erfüllt sind:

|   |   |   |   |   |   |   |
|---|---|---|---|---|---|---|
|i|Q|yi+1…ym∈Σϵ*||i|Q|yi+1…ym∈Σϵ*|
|0|A|baaba||0|A|ϵbaaba|
|1|A|aaba||1|B|baaba|
|2|C|aba||2|A|aaba|
|3|D|ba||3|C|aba|
|4|D|a||4|D|ba|
|5|A|||5|D|a|
|||||6|A|

Also ist w1∈L(N).

Das Wort w2=baabaa kann aber nicht über dem Alphabet Σϵ geschrieben werden, so dass die Bedingungen aus Definition [Berechnung eines NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_CompNFA) erfüllt sind. Die Berechnungen terminieren niemals in einem Endzustand, also ist w2∉L(N).

Insgesamt bleibt ohne Beweis festzuhalten, dass N die Sprache L(N)={w∣w∈{a,b}*, |w|amod3=0} erkennt.


![[Pasted image 20251031225258.png]]


### 4.1.1 简要说明（要点）

- 两种对 w1 的写法体现了**非确定性与 ε-转移**：右侧的分解在开始处用了一个 ε（即不消耗输入就发生状态转移），因此计算路径长度不同，但最终都能到达接受状态。
- w2 无法被接受，说明无论如何分支或用 ε，都没有任何一条路径在读完全部输入后停在接受状态上。
- 最后结论：状态集合 A,B,C（或文中对应的 0,1,2）实际上在记录字符 `a` 的个数对 3 的余数，因此只有当 `a` 的个数 ≡ 0 (mod 3) 时被接受。

---

Die Beispiele [Berechnung eines DEA mit konkreten Eingaben](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_amod3konfig) und [Berechnung eines NEA mit konkreten Eingaben](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_NEA2a) haben nun gezeigt, dass die Sprache L={w∣w∈{a,b}*, |w|amod3=0} sowohl von deterministischen als auch von nichtdeterministischen endlichen Automaten erkannt werden kann. Es ist darüber hinaus leicht möglich weitere endliche Automaten – deterministische oder nichtdeterministische – zu konstruieren, die die gleiche Sprache erkennen, auch über die triviale Modifikation einer Umbenennung der Zustandsnamen hinaus. Zwei endliche Automaten sollen als äquivalent bezeichnet werden, wenn die von ihnen erkannten Sprachen gleich sind.


![[Pasted image 20251031225424.png]]

# 5 **Äquivalenz**

> Zwei endliche Automaten sollen als äquivalent bezeichnet werden, wenn die von ihnen erkannten Sprachen gleich sind.

Seien E1 und E2 deterministische oder nichtdeterministische endliche Automaten. E1 und E2 heißen äquivalent, wenn die von ihnen erkannten Sprachen gleich sind, also wenn L(E1)=L(E2) gilt.


In welcher Beziehung stehen nun aber die deterministischen endlichen Automaten und die nichtdeterministischen endlichen Automaten bzgl. der von ihnen jeweils erkennbaren Sprachen? Eine Beziehung ist trivial. Ein deterministischer endlicher Automat ist ein spezieller nichtdeterministischer endlicher Automat ([Satz Äquivalenz](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#satz_DetNdetAeq)).

设 E1和 E2是确定性或非确定性的有限自动机。  
当它们所识别的语言相同时，即

L(E1)=L(E2)

成立时，称 E1和 E2**是等价的（äquivalent）**。

---

现在的问题是：**确定性有限自动机（DEA）** 和 **非确定性有限自动机（NEA）** 在它们各自能识别的语言方面有怎样的关系？

有一种关系是显而易见的：

> **每一个确定性有限自动机都是非确定性有限自动机的一种特殊情况。**  
> （见 [等价性定理](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#satz_DetNdetAeq)


这段话的重点是阐明两类自动机（DEA 与 NEA）之间的**包含关系与等价性**：

1. **确定性自动机 (DEA)** 是 **非确定性自动机 (NEA)** 的一个特例：  
    因为 NEA 允许多个可能的状态转移（或无转移），而 DEA 对每个状态和输入符号只有一个确定的转移。  
    所以任何 DEA 都可以看作 NEA，只是它恰好没有非确定性的分支。
    
2. 接下来（在提到的 “Satz Äquivalenz” 定理中）会证明：  
    → **每一个 NEA 都存在一个等价的 DEA**，也就是说：
    
    NEA 和 DEA 识别的语言类是相同的。\text{NEA 和 DEA 识别的语言类是相同的。}NEA 和 DEA 识别的语言类是相同的。
    
    这类语言称为 **reguläre Sprachen（正规语言）**。



## 5.1 **Satz Äquivalenz**

Es sei E ein deterministischer endlicher Automat. Dann gibt es einen äquivalenten nichtdeterministischen endlichen Automat N.


**Beweis Äquivalenz**

![[Pasted image 20251031225614.png]]


Aber gilt auch die Umkehrung dieser Beziehung? Sie ergibt sich aus dem [Satz Teilmengenkonstruktion](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_TeilmengKonstr). Damit erweisen sich die Konzepte des Determinismus und des Nichtdeterminismus bei endlichen Automaten als äquivalent.

Der Beweis des Satzes [Satz Teilmengenkonstruktion](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_TeilmengKonstr) erfolgt in zwei Schritten:

- Konstruktion des gesuchten Automaten aus dem gegebenen Automaten
- Nachweis der Äquivalenz der zwei Automaten

Im ersten Teil, der Konstruktion, steckt die grundlegende Idee zum Beweis der Aussage des Satzes. Der zweite Teil verifiziert, dass die Konstruktion wirklich die Anforderungen erfüllt. Die Konstruktion liefert implizit auch einen Algorithmus zur Transformation eines Automatenmodells in ein anderes. Nach einem solchen konstruktiven Beweisprinzip sind viele weitere Aussagen der Automatentheorie bewiesen.

Die Idee in dem vorliegenden Beweis ist die _Teilmengen-Konstruktion_, bei der der deterministische Automat alle Berechnungspfade des gegebenen nichtdeterministischen endlichen Automaten parallel verfolgt. Dazu erhält er alle Zustandsteilmengen des nichtdeterministischen Automaten als Zustände. Die Zustände, in denen sich der nichtdeterministische Automat auf den unterschiedlichen Berechnungspfaden in einem Zeittakt befindet, bilden dann die Zustandsteilmenge, in der sich der deterministische Automat in diesem Zeittakt befindet. Bezogen auf diese Zustandsteilmengen sind die weiteren Komponenten des Automaten zu spezifizieren. Nach Abschluss der Konstruktion können die Zustandsteilmengen in beliebige andere Zustandsnamen umbenannt werden.

----

那么，这种关系的逆命题是否也成立呢？  
答案是肯定的，这可以通过**幂集构造定理（Satz Teilmengenkonstruktion）**得出。因此，**确定性与非确定性在有限自动机中的概念是等价的**。

该定理的证明分为两个步骤：

1. **从给定的自动机构造所需的自动机**；
    
2. **证明两个自动机是等价的**。
    

在第一步的构造部分，包含了证明定理核心思想的基本概念。第二步则验证该构造是否真正满足要求。该构造方法也隐含了一个算法，可以将一种自动机模型转换为另一种自动机模型。基于这种构造性证明原则，自动机理论中的许多其他结论也得以证明。

本证明中使用的思路是**幂集构造（Subset Construction）**：

- 在该方法中，**确定性自动机（DFA）并行地追踪给定非确定性有限自动机（NFA）的所有计算路径**；
    
- 为此，DFA 的每个状态对应 NFA 的一个**状态子集（Zustandsteilmenge）**；
    
- 在某一时刻，NFA 在不同计算路径上可能处于的所有状态组成了 DFA 的一个状态子集；
    
- 根据这些状态子集，还需要指定自动机的其他组成部分（如初始状态、接受状态和转移函数）；
    
- 构造完成后，这些状态子集可以被重新命名为任意其他状态名称。


**解释说明**

1. **幂集构造法（Subset Construction）** 是将 NFA 转换为等价 DFA 的标准方法：
    
    - NFA 的每一个可能状态集合（即在某一步可能处于的多个状态）被 DFA 看作一个单独的状态；
        
    - DFA 的转移函数则将这些状态子集映射到下一个状态子集，从而“模拟”NFA 的非确定性分支。
        
2. **核心结论**：
    
    - 通过幂集构造，可以把任意 NFA 转换为等价的 DFA；
        
    - 这说明**确定性和非确定性在识别正规语言方面是等价的**。
        
3. **额外说明**：
    
    - 该构造不仅是理论证明，也给出了一个**具体的算法**，可以将 NFA 自动机模型转换成 DFA 自动机模型；
        
    - 构造完成后，可以对 DFA 的状态子集重新命名，不影响语言识别能力。

# 6 **Satz Teilmengenkonstruktion**

Es sei N ein nichtdeterministischer endlicher Automat. Dann gibt es einen äquivalenten deterministischen endlichen Automat E.


## 6.1 Beweis Teilmengenkonstruktion


![[Pasted image 20251031230019.png]]


---

Beispiel 

Gegeben sei nochmals der nichtdeterministische endliche Automat N aus Beispiel [Berechnung eines NEA mit konkreten Eingaben](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_NEA2). Es werde dazu nach der Teilmengen-Konstruktion ([Satz Teilmengenkonstruktion](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#def_TeilmengKonstr)) ein äquivalenter deterministischer endlicher Automat E=(Q′,Σ′,δ′,q0′,F′) konstruiert.

Shritt1 
![[Pasted image 20251031230046.png]]


![[Pasted image 20251031230104.png]]


Schritt II 
![[Pasted image 20251031230119.png]]


Schritt1 : kombination
![[Pasted image 20251031230136.png]]\


Schritt 4: Test mit woerter 
![[Pasted image 20251031230202.png]]

![[TIO_211Zustandsgraph_DEA_E.png]]


---

总结 

Die Teilmengen-Konstruktion erzeugt aus n Zuständen des nichtdeterministischen endlichen Automaten 2n Zustände für den deterministischen endlichen Automaten. Die Zustandsanzahl vergrößert sich also exponentiell. An dem vorangehenden Beispiel kann aber auch leicht erkannt werden, dass sehr viele Zustände entstehen können, die dann gar nicht benötigt werden, weil sie ausgehend vom Startzustand _unerreichbar_ sind. In dem Beispiel sind ausgehend von dem Startzustand {A,B} nur die Zustände {C} und {D} erreichbar. Es gibt allerdings NEAs deren äquivalente DEAs tatsächlich alle 2n Zustände benötigen.

Um die Erzeugung dieser nicht erreichbaren Zustände zu vermeiden, kann die Konstruktion auch so modifziert werden, dass nur erreichbare Zustände konstruiert werden:


幂集构造法（Subset Construction）会将一个 **具有 nnn 个状态的非确定性有限自动机（NFA）** 转换为一个 **具有 2n2^n2n 个状态的确定性有限自动机（DFA）**。  
也就是说，状态数量呈**指数级增长**。

不过，从前面的示例中可以很容易看出，并非所有这些状态都需要，因为很多状态从**初始状态**出发是无法到达的。  
在该示例中，从初始状态 {A,B}\{A,B\}{A,B} 出发，仅有状态 {C}\{C\}{C} 和 {D}\{D\}{D} 是可达的。

然而，也存在一些 NFA，它们的等价 DFA **确实需要使用所有 2n2^n2n 个状态**。

为了避免生成这些不可达状态，可以对幂集构造进行修改，使得**只构造可达状态**：


**解释说明**
1. **指数增长问题**：
    - 标准的幂集构造会生成 NFA 状态集合的全部子集，总数为 2n2^n2n；
    - 但很多状态可能从 DFA 的初始状态出发永远无法到达，因此实际并不需要。
2. **优化方法**：
    - 通过只构造从初始状态可达的状态子集，可以**避免浪费计算资源**和存储空间；
    - 这种方法在实际实现 DFA 时非常重要，尤其是 NFA 状态数量较多时。
3. **注意**：
    - 虽然优化减少了状态数，但不会影响 DFA 的语言识别能力；
    - 仍然保证生成的 DFA 与原 NFA 等价。


## 6.2 **Beweis Teilmengenkonstruktion (Erreichbar)**

![[Pasted image 20251031230418.png]]

 List. 2.1: Berechnung von erreichbaren Zuständen und Überführungsfunktion
![[Pasted image 20251031230437.png]]

Nach Abschluss des Algorithmus ist QU leer und QR enthält alle Zustandsteilmengen, die vom Startzustand aus mit irgendeinem Eingabewort errichbar sind. Maximal ist QR=𝒫(Q), der Algorithmus terminiert also. Sollte bei diesem Verfahren als δ′(R,x) der Wert ∅ auftreten, so ist auch diese Teilmenge in QU und dann QR aufzunehmen. Diese bezeichnet den Fehlerzustand, aus dem kein akzeptierender Endzustand mehr erreicht werden kann.


# 7 NEA和DEA结合使用， 达到优化目的

Im Beispiel wird die Konstruktion wesentlich einfacher:


![[Pasted image 20251031230524.png]]
Also: QR={{A,B},{C},{D}}, somit sogar mit weniger Zuständen als der nichtdeterministische Automat. Hinweis: In diesem Fall enthält die Menge QU in jedem Schritt nur ein Element (eine Teilmenge). Im allgemeinen Fall kommen in den ersten Schritte mehrere Teilmengen dazu (je eine pro Eingabesymbol x), die dann suzessive abgearbeitet werden.


Aufgrund der Äquivalenz von deterministischen und nichtdeterministischen endlichen Automaten müssen diese nunmehr nicht weiter unterschieden werden. Was bringt dann aber der Nichtdeterminismus bei endlichen Automaten? Nun ist zwar die Implementierung von gegebenen deterministischen endlichen Automaten im Gegensatz zu nichtdeterministischen endlichen Automaten direkt möglich, aber ihr Entwurf ist häufig nicht so einfach. Vor allem ist er wegen der größeren Zustandsanzahl wesentlich aufwändiger, auch wenn nicht in allen Fällen die gegenüber der nichtdeterministischen Variante exponentielle Zustandsanzahl benötigt wird.

Werde hier nochmals das Beispiel [Alphabet eines DEAs](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_LexEA0) zur Analyse und Erkennung der elementaren Einheiten eines Programms durch das Modell eines endlichen Automaten aufgegriffen. Der Entwurf der einzelnen Automaten und ihr Zusammenfügen mittels nichtdeterministischer endlicher Automaten ist deutlich einfacher.

Die einzelnen Automaten werden zunächst als so genannte _unvollständige_ endliche Automaten – es gibt nicht zu jedem Paar aus Zustand und Eingabezeichen einen Folgezustand – konstruiert und danach werden diese nichtdeterministisch zusammengefügt (Beispiel [Zusammenfügen von endlichen Automaten zu einem NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_LexEA1)). Darauf würde der Algorithmus _Teilmengen-Konstruktion_ angewendet werden, um zu einem DEA zu gelangen. Die große Zustandsanzahl könnte ggf. durch einen Algorithmus zur Minimisierung des DEA verringert werden. Darauf soll hier aber nicht weiter eingegangen werden.

由于确定性有限自动机（DEA）和非确定性有限自动机（NEA）的**等价性**，它们之后不再需要严格区分。那么，**有限自动机中的非确定性有什么作用呢？**

虽然给定的 DEA 相对于 NEA 来说可以直接实现，但 **其设计通常并不容易**。  
尤其是，由于 DEA 状态数较多，设计工作量往往更大（虽然并非在所有情况下都需要指数级状态数）。

这里再次以示例“DEA 的字母表”为例，用有限自动机模型分析和识别程序的基本元素。  
通过 NEA 设计单个自动机并将它们组合起来要**容易得多**。

- 单个自动机首先构造为**不完整有限自动机（unvollständige endliche Automaten）**——即并非每个状态和输入符号的组合都有后继状态；
    
- 然后通过**非确定性方式组合**这些自动机（见示例“将多个有限自动机组合为 NEA”）；
    
- 接着，可以应用**幂集构造算法（Subset Construction）**将其转换为 DEA；
    
- 如果 DEA 的状态数过多，还可以使用 DEA **最小化算法**进行优化，减少状态数。  
    这里不再进一步讨论最小化算法。


 **解释说明**

1. **非确定性的优势**：
    - 在自动机设计阶段，NEA 允许**未完全定义的状态转移**和**分支计算路径**；
    - 这使得构建复杂系统（如编程语言的词法分析器）更加灵活和模块化。
2. **设计流程**：
    - 先设计多个小型 NEA（可不完整）；
    - 使用非确定性将它们组合成一个大 NEA；
    - 最后通过幂集构造转换为 DEA；
    - 可选：对 DEA 进行最小化，减少状态数。
3. **关键点**：
    - NEA **简化了自动机的设计**，尤其是在处理复杂模式或组合时；
    - DEA 虽然可直接实现，但**设计复杂、状态多**。




# 8 **Zusammenfügen von endlichen Automaten zu einem NEA**

Sei das zugrunde liegende Alphabet Σ={a,b,…,z,0,1,…,9}.

1.

Ein Identifikator bzw. Bezeichner besteht aus einem Wort w, beginnend mit einem Buchstaben und gefolgt von keinem oder endlich vielen Buchstaben oder Ziffern: w∈{a,b,…,z}{a,b,…,z,0,1,…,9}∗ Der Einfachheit halber sei auf Großbuchstaben verzichtet.

Ein unvollständiger endlicher Automat NI, der Identifikatoren akzeptiert, ist in Abbildung [Unvollständiger endlichen Automat NI](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#fig_EA-ZGraph3a) dargestellt. NI akzeptiert aber auch die reservierten Wörter als Identifikatoren.

**标识符（Identifikator）**

- 一个标识符（变量名或符号名）由一个单词 www 构成，**以字母开头，后面跟零个或有限多个字母或数字**：
    
    w∈{a,b,…,z}{a,b,…,z,0,1,…,9}∗w \in \{a,b,\dots,z\}\{a,b,\dots,z,0,1,\dots,9\}^*w∈{a,b,…,z}{a,b,…,z,0,1,…,9}∗
- 为了简单起见，这里忽略大写字母。
    
- 一个**不完整有限自动机** NININI 可以接受标识符（图示：Unvollständiger endlicher Automat NI）。
    
- 注意：NININI 同时也接受保留字作为标识符。



2.

Ganze Zahlen ohne Vorzeichen bestehen aus einem Wort w aus endlich vielen Ziffern: w∈{0,1,2,…,9}+

Ein unvollständiger endlicher Automat NZ, der solche Zahlen akzeptiert, ist in Abbildung [Unvollständiger endlichen Automat NZ](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#fig_EA-ZGraph3b) dargestellt.

**无符号整数（Ganze Zahlen ohne Vorzeichen）**

- 无符号整数由一个单词 www 构成，包含有限多个数字：
    
    w∈{0,1,2,…,9}+w \in \{0,1,2,\dots,9\}^+w∈{0,1,2,…,9}+
- 一个**不完整有限自动机** NZNZNZ 可接受这样的数字（图示：Unvollständiger endlicher Automat NZ）。



3.

Das reservierte Wort for besteht aus der Konkatenation der Zeichen f⋅o⋅r.

Ein unvollständiger endlicher Automat Nfor, der dieses Wort akzeptiert, ist in Abbildung [Unvollständiger endlichen Automat Nfor](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#fig_EA-ZGraph3c) dargestellt.

**保留字 `for`**

- 保留字 `for` 由字符串 `f⋅o⋅r` 构成。
    
- 一个**不完整有限自动机** NforNforNfor 可以接受该单词（图示：Unvollständiger endlicher Automat Nfor）。



4.

Ein lexikalischer Analysator (Scanner) besteht nun aus einer Kombination aller dieser Automaten. Ein Programm wird zeichenweise gelesen. Je nach analysiertem Präfix verzweigt ein solcher Automat in die entsprechende Alternative. Hat er eine elementare Einheit des Programms erkannt, so übersetzt er diese in ein entsprechendes Symbol, geht wieder in seinen Startzustand und beginnt mit der Analyse der verbleibenden Zeichen des Programms.

Der Zustandsgraph in Abbildung [Nichtdeterministischer endlichen Automat NLex](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#fig_EA-ZGraph3d) beschreibt einen endlichen erkennenden Automaten NLex, der eine Eingabe auf ein Identifikator, eine ganze Zahl ohne Vorzeichen oder das reservierte Wort end analysieren kann. Der Zustand, in dem der Automat anhält, signalisiert die erkannte Alternative.

Ein zu NLex äquivalenter deterministischer endlicher Automat ELex ist in Abbildung [Unvollständiger endlichen Automat NI](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#fig_EA-ZGraph3d2) dargestellt. Dieser ist allerdings nicht mittels der Teilmengen-Konstruktion konstruiert worden. Hier gelten die abkürzenden Schreibweisen wie in Beispiel [Alphabet eines DEAs](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_LexEA0) mit der Änderung xf∈{a,b,…,z}∖{f}.


**词法分析器（Lexikalischer Analysator / Scanner）**

- 词法分析器由上述所有自动机组合而成。
    
- 程序逐字符读取，根据分析到的前缀（Prefix）自动机会分支到相应的选择路径（标识符、整数或保留字）。
    
- 当识别出一个程序的基本单元（elementare Einheit）时，词法分析器将其转换为相应的符号，回到起始状态，继续分析剩余字符。
    
- 图示：`Nichtdeterministischer endlicher Automat NLex` 展示了一个 NEA NLexNLexNLex，可以识别输入是标识符、无符号整数或保留字 `end`。
    
- 停止的状态表示识别出的选项（alternative）。
    
- 与 NLexNLexNLex 等价的 DFA（确定性有限自动机）为 ELexELexELex（图示：Unvollständiger endlicher Automat NI）。
    
- 注意：这个 DFA 并不是通过幂集构造得到的。
    
- 此处使用了类似示例“DEA 字母表”的简写方式，其中
 ![[Pasted image 20251031231019.png]]






![[Pasted image 20251031230904.png]]


![[Pasted image 20251031230916.png]]

# 9 NEA 转成 DEA 的方式 例子 


![](image/Pasted%20image%2020251031163741.png)


das eine Verfahren ist teilmengenkonstruktion und
das zweite Verfahren ist die sogenannte reservation.


## 9.1 teilmengen-konstruktion


### 9.1.1 Beispiel 

![](image/Pasted%20image%2020251031171356.png)

![](image/Pasted%20image%2020251031171415.png)

![](image/Pasted%20image%2020251031171422.png)


---


1 Ohne Berucksichtung der Epsilon-Uberfuhrung

![](image/Pasted%20image%2020251031171441.png)

{A,B} ,
A-a-C,   B-a-lerrmeneg, dann A
A-b-A,  B-b-{A,B}， 融合 A 和 {A，B} 后  得到 {A,B}



---

2 Berucksichtiung der Epsilon Uberfurhungen 
![](image/Pasted%20image%2020251031171500.png)

E（R）  就是 当前zustand, 什么zeichen 也不执行得到的 zustand  （得到zustand 就是目前的zustand 本身 ）,  和执行 epislon zeichen 后的得到的zustand

![](image/Pasted%20image%2020251031171529.png)


----

3 合并 

![](image/Pasted%20image%2020251031171533.png)


Fur jede Worter  wir E() dafur

![](image/Pasted%20image%2020251031171619.png)

![](image/Pasted%20image%2020251031171622.png)

---


4

![](image/Pasted%20image%2020251031171635.png)

![](image/Pasted%20image%2020251031171641.png)


Wenn b kommt,.
![](image/Pasted%20image%2020251031171650.png)


Wenn a kommt
![](image/Pasted%20image%2020251031171658.png)


Wenn c komm 
![](image/Pasted%20image%2020251031171705.png)

Wenn d bin, und b kommt
![](image/Pasted%20image%2020251031171717.png)


Wenn d bin, un  b kommt , dann welchen ins a,
![](image/Pasted%20image%2020251031171727.png)



Und AB ist eine endlich zustand, 因为再下面中定义了 
![](image/Pasted%20image%2020251031171735.png)
