

Die Formalisierung des Algorithmusbegriffs wurde 1936 aus unterschiedlichen Ansätzen entwickelt. Ein funktionenorientierter Ansatz kam von Alonzo Church, der λ-_Kalkül_, ein über ein Maschinenmodell entwickelter Ansatz stammt von Alan Turing, die heute nach ihm benannte _Turingmaschine_. Daneben gibt es weitere Algorithmus-Formalisierungen. Im Abschnitt [Deterministische Turingmaschinen](https://vfhti.eduloop.de/loop/Deterministische_Turingmaschinen "Deterministische Turingmaschinen") sind Turingmaschinen, die Sprachen erkennen bzw. entscheiden, bereits eingeführt worden. Auf das λ-Kalkül und andere Formalisierungen wird hier nicht eingegangen.

Die Turingmaschine als Sprachakzeptor berechnet nun eine Funktion mit einem Wort über dem Eingabealphabet als Argument und zwei möglichen Funktionswerten, akzeptieren oder verwerfen. Entscheidet die Turingmaschien eine Sprache, so ist diese Funktion für alle Wörter über dem Eingabealphabet definiert, man spricht dann auch von einer _totalen_ Funktion. Erkennt die Turingmaschine aber eine Sprache nur, d.h. sie hält für einige Wörter ggf. nicht an, so muss diese Funktion nicht für alle Wörter über dem Eingabealphabet definiert sein, man spricht dann von einer _partiellen_ Funktion.

Zur Berechnung von Funktionen mit mehr als zwei Funktionswerten, wie z.B. der Addition zweier Zahlen (Funktion fadd aus Beispiel [Addition zweier Zahlen](https://vfhti.eduloop.de/loop/Intuitiver_Algorithmusbegriff "Intuitiver Algorithmusbegriff")), muss das Modell der Turingmaschine um die Ausgabemöglichkeit von Funktionswerten erweitert werden. Die Ausgabe einer Turingmaschine werde hier wie folgt definiert: Hält die Turingmaschine akzeptierend, dann wird der Bandinhalt rechts vom Lese-/Schreibkopf, einschließlich des Feldes unter dem Lese-/Schreibkopf, als Funktionswert interpretiert.


算法概念的形式化是在1936年从各种方法中发展起来的。面向函数的方法来自阿隆佐·丘奇，他λ图灵_微积分_是一种基于机器模型的算法，起源于艾伦·图灵，现在以他的名字命名为_图灵机。此外还有其他算法形式化方法。在_[“确定性图灵机”](https://vfhti.eduloop.de/loop/Deterministische_Turingmaschinen "确定性图灵机")一节中，我们已经介绍了能够识别或判定语言的图灵机。[关于……]λ本文不讨论微积分和其他形式化方法。

图灵机作为语言接收器，计算一个以输入字母表中的单词为参数、取两个可能值（接受或拒绝）的函数。如果图灵机判定了一种语言，则该函数对输入字母表中的所有单词都有定义；此时它被称为_全_函数。然而，如果图灵机仅识别出一种语言，即它可能不会因某些单词而停机，则该函数无需对输入字母表中的所有单词都有定义；此时它被称为_部分_函数。

要计算具有两个以上函数值的函数，例如两个数的和（函数）。f一个dd[从两个数相加的](https://vfhti.eduloop.de/loop/Intuitiver_Algorithmusbegriff "算法的直观概念")例子可以看出，图灵机模型必须扩展到包含函数值的输出。图灵机的输出定义如下：如果图灵机接受性地停机，则读写头右侧的磁带内容（包括读写头下方的区域）被解释为一个函数值。


# 1 **Turing-berechenbar**


![](image/Pasted%20image%2020260119121013.png)

![](image/Pasted%20image%2020260119132338.png)


![](image/Pasted%20image%2020260119121824.png)

![](image/Pasted%20image%2020260119121837.png)

![](image/Pasted%20image%2020260119122059.png)

# 2 Beispiel: **Inkrement**


Konstruktion einer Turingmaschine, die die Inkrementfunktion f:ℕ0→ℕ0 mit f(n)=n+1 berechnet, wobei n∈ℕ als Binärzahl ohne führende Nullen dargestellt wird und n=0 als 0.

Informelle Beschreibung der Turingmaschine:

1. Eingabewort (Binärzahl) um ein Feld nach rechts schieben. Das zusätzliche Feld links dient zur Erkennung des linken Rands und es kann ggf. bei einem Übertrag bis zur höchsten Stelle mit 1 überschrieben werden.
2. Auf die letzte Ziffer der Zahl gehen.
3. Falls diese Ziffer gleich 1, auf 0 setzen, ein Feld nach links gehen und diese Anweisung wiederholen.
4. Falls diese Ziffer gleich 0 oder ␣, auf 1 setzen.
5. Auf die erste Ziffer der Zahl gehen und akzeptierend terminieren.


![](image/Pasted%20image%2020260119122201.png)

Alle in der Tabelle nicht aufgeführten Paare (q,y)∈Q×Γ sind wie folgt definiert: δ(q,y)=(R,y,R).


---

Nachfolgend ist für die Binärzahl n=10011 die Berechnung von Tink aufgeführt:


![](image/Pasted%20image%2020260119122211.png)


---

In Abbildung [Überführungsgraph der TM Tink](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#fig_DTM-ZGraph2) ist die Turingmaschine Tink als Überführungsgraph dargestellt. Der verwerfende Zustand R und alle dahingehenden Überführungen sind weggelassen.

![](image/Pasted%20image%2020260119122252.png)



Die Definition und Arbeitsweise einer Turingmaschine erfüllt sicherlich ausnahmslos die Anforderungen des intuitiven Algorithmusbegriffs nach der Begriffsbestimmung [Intuitiver Algorithmus](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#def_IntAlg). Es kann deshalb die nachfolgende Folgerung geschlossen werden.


# 3 Satz: **Folgerung: Turing-berechenbar und intuitiv-berechenbar**

Wie aber steht es mit der Umkehrung dieser Aussage? Es gibt neben der Turing-Berechenbarkeit diverse weitere Berechenbarkeits- und damit auch weitere formale Algorithmusbegriffe, _allgemein-rekursiv berechenbar_, _λ-berechenbar_, _Markov-berechenbar_, _RAM-berechenbar_ oder auch _PL-berechenbar_. Es kann gezeigt werden, dass alle diese Berechenbarkeitsbegriffe äquivalent sind. Für alle Formalisierungen des Berechenberkeitsbegriffs gilt damit natürlich auch die intuitive Berechenbarkeit. Da andererseits bisher jeder intuitive Algorithmus in einen formalen Algorithmus nach irgendeinem formalen Algorithmusbegriff umgeformt werden konnte, ist man davon überzeugt, dass auch die Umkehrung gilt. Diese Aussage lässt sich natürlich nur unter Plausibilitätsbetrachtungen herleiten und kann nicht allgemein bewiesen werden. Sie wird als _Churchsche These_ oder auch als _Church-Turing These_ bezeichnet.

但是，这个陈述的反面又是什么呢？除了图灵可计算性之外，还有各种其他的可计算性概念，因此也有其他的形式算法概念，例如_一般递归可计算性_。_λ可计算性可以定义为__马尔可夫可计算性_、随机访问模型（RAM）_可计算性_或_程序逻辑可计算性_。可以证明，所有这些可计算性概念都是等价的。因此，直观的可计算性自然适用于可计算性概念的所有形式化定义。另一方面，由于迄今为止，每个直观算法都能够根据某种形式化的算法概念转化为形式化的算法，因此人们普遍认为其逆命题也成立。当然，这一论断只能通过合理性考量推导得出，而无法进行一般性证明。它被称为_丘奇论题_或_丘奇-图灵论题_


# 4 Satz: **Hypothese: Church-Turing-These**

> Church-Turing These: Jede intuitiv-berechenbar Funktion ist auch Turing-berechenbar

Natürlich gilt diese Hypothese auch für alle anderen formalen Berechenbarkeitsbegriffe. Insbesondere sei hier auf die RAM- und die PL-Berechenbarkeit hingewiesen. Eine Random-Access-Maschine (RAM) ist ein formales Modell, das sich in Aufbau und Funktionsweise sehr eng an den heutigen grundlegenden Rechnerarchitekturen und ihren maschinenorientierten Programmiersprachen orientiert, dem _von-Neumann Rechner_. PL ist eine algorithmische Sprache, die in ihren grundlegenden Konzepten heutigen anwendungsorientierten Programmiersprachen entspricht. Man kann sich vor diesem Hintergrund sehr leicht plausibel machen, daß jeder in intuitiver Notation vorliegende Algorithmus zur Lösung eines Problems mittels realer Programmiersprachen auf realen Rechnern ausgeführt und damit gelöst werden kann.

Die bewiesene bzw. plausible Äquivalenz unter den diversen Berechenbarkeits- und Algorithmusbegriffen führt zu der folgenden vereinheitlichenden Definition.

当然，这一假设也适用于所有其他形式的可计算性概念。这里尤其应该提及随机存取机（RAM）和编程语言（PL）的可计算性。随机存取机（RAM）是一种形式模型，其结构和功能与当今的基本计算机体系结构及其面向机器的编程语言（特别是_冯·诺依曼计算机_）非常相似。编程语言（PL）是一种算法语言，其基本概念与当今面向应用程序的编程语言相对应。在此背景下，很容易理解，任何以直观符号表示的用于解决问题的算法都可以使用实际的编程语言在实际计算机上执行并求解。

可计算性和算法的各种概念之间存在已证实或合理的等价性，由此得出以下统一定义。

# 5 Definition: berechenbar 

Eine Funktion heisst berechenbar, wenn sie intuitiv-berechenbar, Turing-berechenbar oder nach irgendeiner anderen Formalisierung berechenbar ist.

Es waren in den Beispielen [Addition zweier Zahlen](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_berech) und [Inkrement](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_Inkrement) bereits berechenbare Funktionen und eine nicht berechenbare Funktion angegeben. Auf die nicht berechenbare Funktion des Beispiels [Addition zweier Zahlen](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_berech) wird später im Abschnitt [Das Halteproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem "Das Halteproblem") eingegangen. Ausgehend von der Inkrementfunktion (Beispiel [Inkrement](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_Inkrement)) könnte nun z.B. auch leicht gezeigt werden, dass die Addition, die Multiplikation, deren Umkehrfunktionen und alle darauf aufbauenden arithmetischen Funktionen berechenbar sind.

Turingmaschinen sind bisher auf zwei Arten beschrieben worden. Die exakte _formale Beschreibung_ definiert eine Turingmaschine mit allen ihren Zuständen, Alphabeten und Überführungen. Die _informelle Beschreibung_ einer Turingmaschine beschreibt ihre Kopfbewegungen auf dem Band und wie und welche Daten auf dem Band gespeichert und gelesen werden, aber Zustände und Überführungen werden nicht mehr spezifiziert. Beide Beschreibungsformen sind in den vorangegangen Beispielen verwendet worden. In einem weiteren Abstraktionsschritt werden nun Algorithmen vollkommen unabhängig von irgendwelchen formalen Berechnungsmodellen beschrieben, wie z.B. einer Turingmaschine, denn mit der Church-Turing These und der Äquivalenz aller formalen Berechenbarkeitsbegriffe wird es zu einem solchen _intuitiven Algorithmus_ immer auch einen formalen Algorithmus geben, insbesondere auch eine Turingmaschine.


如果一个函数直观上可计算、图灵可计算，或者根据任何其他形式化方法可计算，则称该函数为可计算函数。

[前面提到的两个数相加](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_berech)和[递增的](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_Inkrement)例子已经展示了可计算函数和一个不可计算函数。这[两个数相加例子中的不可计算函数将在](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_berech)[停机问题](https://vfhti.eduloop.de/loop/Das_Halteproblem "持有问题")部分进行讨论。从递增函数（例如： [increment](https://vfhti.eduloop.de/loop/Turing-Berechenbarkeit#bsp_Inkrement)）出发，现在可以很容易地证明，例如，加法、乘法、它们的逆函数以及所有基于它们的算术函数都是可计算的。

目前为止，图灵机的描述方式有两种。精确的_形式化描述_定义了图灵机及其所有状态、字母表和转换。图灵机的_非形式化描述_则描述了其磁头在磁带上的移动，以及磁带上数据的存储和读取方式，但不再具体说明状态和转换。前面的例子中使用了这两种描述方式。在进一步的抽象过程中，算法的描述完全独立于任何形式化的计算模型，例如图灵机。这是因为，根据丘奇-图灵论题以及所有形式化可计算性概念的等价性，总会存在一个形式化的算法与这样一个_直观的算法_相对应，特别是与一个图灵机相对应。


