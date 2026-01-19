
Während im vorangehenden Abschnitt Algorithmen zur Berechnung beliebiger Funktionen und ihre Formalisierung mittels Turingmaschinen eingeführt und diskutiert wurden, geht es in diesem Abschnitt wieder nur um Algorithmen zur Lösung von _Entscheidungsproblemen_, Problemen, die mit _Ja_ oder _Nein_ beantwortet werden können, also die Berechnung von Funktionen mit nur zwei Funktionswerten. Es sollen die grundsätzlichen Fähigkeiten und Begrenzungen algorithmischer Problemlösungen diskutiert werden, und dazu genügt es, sich auf solche Probleme zu beschränken. Die Ergebnisse lassen sich dann leicht auf komplexere Probleme übertragen.

Ziel dieses Kapitels ist es zu zeigen, dass es unentscheidbare Probleme gibt. Dies wird am Beispiel des _Halteproblems_ aufgezeigt. Vorab aber werden einige entscheidbare Probleme besprochen. Und auch hier wieder findet eine Beschränkung auf Sprachen statt. Probleme werden als so genanntes _Wortproblem_ dargestellt. Gegeben sind eine Sprache über einem Alphabet und ein Wort über diesem Alphabet, und es ist die Frage zu beantworten, ob das Wort zur Sprache gehört oder nicht.



上一节介绍并讨论了用于计算任意函数的算法及其使用图灵机的形式化方法，而本节则专注于解决_判定问题的算法——即可以用__“是”_或“_否”_回答的问题，也就是只具有两个值的函数的计算。我们将讨论算法问题求解的基本能力和局限性，为此，只需将讨论范围限定于此类问题即可。所得结果可以很容易地应用于更复杂的问题。

本章旨在论证不可判定问题的存在性。我们将以_停机问题_为例进行说明。但首先，我们将讨论一些可判定问题。同样，我们将重点讨论语言问题。这些问题将以所谓的_“字问题”_的形式呈现。给定一个基于字母表的语言和一个基于该字母表的单词，需要回答的问题是：该单词是否属于该语言？


# 1 Definition:  **Wortproblem**

Die Frage, ob ein Wort zu einer Sprache gehört oder nicht, heisst Wortproblem.

Für die Klasse der regulären Sprachen und die Klasse der kontextfreien Sprachen wird die Entscheidbarkeit des Wortproblems gezeigt. Diese Ergebnisse liefern die Grundlage dafür, dass ein Compiler von einem Programm, dessen Syntax mittels einer kontextfreien Grammatik definiert ist, entscheiden kann, ob es syntaktisch korrekt ist oder nicht, also ob das Wort zur Sprache gehört oder nicht. Das Wortproblem selbst kann wie folgt als eine Sprache dargestellt werden:  

![](image/Pasted%20image%2020260119123903.png)

LK:={⟨L,w⟩∣L ist Element einer Klasse von Sprachen K und das Wort w∈L}  

Das Problem, ob w Wort der Sprache L ist, ist äquivalent zu dem Problem, ob ⟨L,w⟩ Wort der Sprache LK ist. Kann nun gezeigt werden, dass LK entscheidbar ist, dann ist damit gezeigt, dass das Wortproblem für jede Sprache dieser Klasse entscheidbar ist. Es werde nun zunächst die Klasse der regulären Sprachen betrachtet.

本文证明了正则语言和上下文无关语言的词问题的可判定性。这些结果为编译器判断一个语法由上下文无关文法定义的程序是否语法正确提供了基础，即判断该词是否属于该语言。词问题本身可以用如下语言表示：  

LK：={⟨L，西⟩|L是语言类的一个元素K以及这个词西∈L}  

问题在于是否西语言的词L是，等价于“是否”的问题⟨L，西⟩语言的词LK现在可以证明：LK如果问题是可判定的，那么已经证明，对于此类语言中的每一种语言，字问题都是可判定的。现在我们首先考虑正则语言类。


# 2 Definition: **Regulärer Ausdruck Wortproblem**


LRA:={⟨R,w⟩∣R ist ein regulärer Ausdruck und w∈L(R)}.


# 3 Definition: **Regulärer Ausdruck Wortproblem**

## 3.1 Satz: Sprache $L_{RA}$  ist eine entscheidbare Sprache.


Beweis

Zum Beweis wird eine Turingmaschine T spezifiziert, die LRA entscheidet.

Informelle Beschreibung von T:

1. Analysiere die Eingabe ⟨R,w⟩ dahingehend, ob R ein regulärer Ausdruck ist und w ein Wort. Ist das nicht der Fall, so halte verwerfend.
2. Überführe den regulären Ausdruck R nach Lemma [Reguläre Sprache](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#lem_EqReFa) in einen äquivalenten NEA N.
3. Überführe N nach Satz [Konkatenation regulärer Sprachen](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_TeilmengKonstr) in einen äquivalenten DEA E.
4. Simuliere E mit der Eingabe w.
5. Endet die Simulation in einem akzeptierenden Zustand von E, so halte akzeptierend, endet die Simulation in einem nichtakzeptierenden Zustand von E, so halte verwerfend.

T hält mit jeder Eingabe nach endlich vielen Schritten an, insbesondere weil auch ein DEA immer nach endlich vielen Schritten hält. Also entscheidet T die Sprache LRA.

Aus dem vorangehenden Satz ergibt sich natürlich auch unmittelbar, dass die entsprechende Fragestellung mit einem gegebenen deterministischen oder nichtdeterministischen endlichen Automaten auch entschieden werden kann. Die Eingabeanalyse ist zu modifizieren und die jeweiligen Überführungen in die äquivalenten Modelle können entfallen.


非正式描述T：

1. 分析输入⟨拉，西⟩在这方面是否拉正则表达式是和西一个词。如果不是这样，那就轻蔑地对待它。
2. 转换正则表达式拉在引理之后，[正则语言](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#lem_EqReFa)被转化为等价的NEAN。
3. 转移N[将正则语言的](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_TeilmengKonstr)句子连接成等效的DEA后E。
4. 模拟E输入西。
5. 模拟最终是否以接受状态结束？E因此，如果模拟以非接受状态结束，它将继续以接受状态进行。E所以，不要理会它。

T对于每个输入，它在有限步后就会停止，尤其因为DEA算法在有限步后也总是停止的。因此，它决定……T语言L拉一个。

由前一句可知，相应的问题也可以用给定的确定性或非确定性有限自动机来解决。输入分析需要进行修改，而到等价模型的相应转换可以省略。

# 4 Satz: **Entscheidbarkeit regulärer Sprachen**: Jede reguläre Sprache ist entscheidbar.

Sei L eine reguläre Sprache. Dann gibt es einen regulären Ausdruck, der L repräsentiert. Seien R der reguläre Ausdruck mit L=L(R) und w ein Wort.

Informelle Beschreibung von T:

1. Führe die TM aus dem Beweis von Satz [Sprache LRA](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_FAWort) mit der Eingabe ⟨R,w⟩ aus.
2. Falls diese TM akzeptiert, dann halte akzeptierend, andernfalls halte verwerfend.

Als nächstes werde das Wortproblem für kontextfreie Sprachen betrachtet.


# 5 Definition: **Kontextfreie Grammatik Wortproblem**

LKF:={⟨G,w⟩∣G ist eine kontextfreie Grammatik und w∈L(G)}.
![](image/Pasted%20image%2020260119124121.png)

## 5.1 Satz **Entscheidbare Sprache** $L_{KF}$  :  $L_{KF}$   ist eine entscheidbare Sprache.


Beweis 

Zum Beweis wird eine Turingmaschine T spezifiziert, die LKF entscheidet.

Informelle Beschreibung von T:

1. Analysiere die Eingabe ⟨G,w ⟩ dahingehend, ob G eine kontextfreie Grammatik ist und w ein Wort. Ist das nicht der Fall, so halte verwerfend.

2. Überführe die kontextfreie Grammatik G nach Satz [Chomsky Normalform](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_ChomskyNF) in eine äquivalente Grammatik in Chomsky Normalform.

3. Liste alle Ableitungen der Länge 2n−1 auf. Dabei ist n=∣w∣.

Ausnahme: Ist n=0, dann liste alle Ableitungen der Länge 1 auf.

4. Ist unter diesen Ableitungen die Ableitung für w, dann halte akzeptierend, andernfalls halte verwerfend.

T hält mit jeder Eingabe nach endlich vielen Schritten an, insbesondere weil es nur endlich viele Ableitungen der Länge 2n−1 gibt, und Wörter der Länge n haben in Grammatiken von Chomsky Normalform ausschließlich Ableitungen dieser Länge. Eine Ausnahme bildet das leere Wort, dies wird über eine Ableitung der Länge 1 erzeugt. Also entscheidet T die Sprache LKF.

图灵机被用作证明。T已指定，LKF决定。

非正式描述T：

1. 分析输入⟨G，西 ⟩在这方面是否G上下文无关文法是和西一个词。如果不是这样，那就轻蔑地对待它。

2. 转换上下文无关文法G[根据乔姆斯基范式](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_ChomskyNF)定理，将其转化为等价的乔姆斯基范式语法。

3. 列出长度的所有导数。2n−1开启。这是n=|西|。

异常：是n=0然后列出所有长度为的导数。1在。

4. 这些导数中包括以下导数：西如果是，则持接受态度；否则，持拒绝态度。

T对于每个输入，该算法在有限步后就会停止，尤其因为长度为 的导数只有有限个。2n−1有，而且是长词。n在乔姆斯基的语法中，所有长度为 1 的推导都具有范式。例外情况是空词，它由长度为 1 的推导生成。因此，它决定了……T语言LKF。


# 6 Satz: **Kontextfreie Sprache und entscheidbar**

Jede kontextfreie Sprache ist entscheidbar.


Sei L eine kontextfreie Sprache. Dann gibt es eine kontextfreie Grammatik, die L erzeugt. Seien G die kontextfreie Grammatik mit L=L(G) und w ein Wort.

Informelle Beschreibung von T:

1. Führe die TM aus dem Beweis von Satz [Entscheidbare Sprache LKF](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_KFWort) mit der Eingabe ⟨G,w⟩ aus.
2. Falls diese TM akzeptiert, dann halte akzeptierend, andernfalls halte verwerfend.

  
Natürlich gibt es viele weitere entscheidbare Probleme im Zusammenhang mit Sprachen und auch unabhängig von Sprachen. Darauf soll hier aber nicht eingegangen werden. Bleibt für diesen Abschnitt zusammenfassend auf die Hierarchie unter den vier betrachteten Sprachfamilien hinzuweisen (Satz [Hierarchie](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_Hierarchie), Abbildung [Hierachie der Sprachfamilien](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#fig_ChomHier)).


是L一种上下文无关语言。然后还有一种上下文无关文法，它L已生成。G上下文无关文法L=L（G）和西一个词。

非正式描述T：

1. [根据可判定语言](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_KFWort)定理的证明，执行图灵机操作。[LKF](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_KFWort)输入⟨G，西⟩出去。
2. 如果此 TM 接受，则保持接受状态；否则，保持拒绝状态。

  
当然，还有许多其他问题可以解决，这些问题既包括与语言相关的问题，也包括与语言无关的问题。然而，本文不讨论这些问题。总之，本节应重点讨论所讨论的四个语系之间的层级关系（参见[“层级关系”](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_Hierarchie)句和[“语系层级关系](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#fig_ChomHier)图”）。


# 7 Satz: **Hierarchie**

ℒreg⊂ℒkf⊂ℒent⊂ℒerk

  

beweis

- ℒreg⊂ℒkf: Satz [Reguläre Sprache und kontextfrei](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_RS-DKA).
- ℒkf⊂ℒent: Die Teilmengenbeziehung ergibt sich aus Satz [Kontextfreie Sprache und entscheidbar](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_KFEntscheid) und die echte Teilmengenbeziehung aus den Beispielen [bsp_AnwPL4](https://vfhti.eduloop.de/loop/Eigenschaften_kontextfreier_Sprachen#bsp_AnwPL4 "Eigenschaften kontextfreier Sprachen") und [Beispiel TM1](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#bsp_TM1).
- ℒent⊂ℒerk: Die Teilmengenbeziehung ergibt sich aus Satz [Turing-entscheidbar und Turing-erkennbar](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#satz_TMentscheidbar). Die echte Teilmengenbeziehung wird im nächsten Abschnitt mit der Spezifikation einer Sprache gezeigt, die Turing-erkennbar aber nicht entscheidbar ist.


![](image/Pasted%20image%2020260119124500.png)