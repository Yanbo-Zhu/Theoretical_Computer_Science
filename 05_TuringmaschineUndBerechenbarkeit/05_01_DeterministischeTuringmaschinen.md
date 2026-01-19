
Die Turingmaschine erweitert nun die bisher betrachteten Automatenmodelle. Das Eingabeband wird zu einem sequentiellen Speicherband, auf dem beliebig viele Zeichen gespeichert und auch ohne Einschränkungen wieder gelesen werden können. Dafür entfällt der Kellerspeicher, den Kellerautomaten zur Verfügung haben. Die Turingmaschine wurde 1936 von Alan Turing als Berechnungsmodell zur Formalisierung des Algorithmusbegriffs eingeführt, der bis dahin nur auf einer informellen Ebene existierte.

Die Turingmaschine wird heute als mathematisch-formales Modell eines universellen Computers benutzt. Sie kann alle die Berechnungen durchführen, die auch ein Computer erledigen kann. Allerdings gibt es gewisse Probleme, die von einer Turingmaschine nicht gelöst werden können. Diese können aber auch nicht von realen Computern gelöst werden. Mittels Turingmaschinen werden somit auch die Grenzen algorithmisch-lösbarer Probleme aufgezeigt.

Eine Turingmaschine besteht aus einer Steuereinheit und einem Speicherband. Die Steuereinheit enthält das Turingmaschinen-Programm, sie kann endlich viele Zustände annehmen und über einen Lese- und Schreibkopf auf die einzelnen Felder des Speicherbandes sequentiell zugreifen. Jedes Feld kann ein Zeichen aus einem endlichen Zeichenvorrat aufnehmen. Auf dem Speicherband stehen unbegrenzt viele Felder zur Verfügung. In Abbildung Abb. 5.1 Turingmaschine (TM) ist eine Turingmaschine (TM) schematisch dargestellt.

图灵机扩展了此前所研究的自动机模型。输入带被扩展为一个顺序存储带，可以在其上存储任意数量的符号，并且可以不受限制地反复读取这些符号。作为交换，下推自动机所具备的栈存储器被取消。
图灵机由 阿兰·图灵（Alan Turing）于 1936 年提出，作为一种计算模型，用于形式化"算法"这一概念，而在此之前，算法仅存在于非形式化的层面。

如今，图灵机被视为通用计算机的数学形式化模型。它能够执行现实计算机所能完成的所有计算。然而，存在一些问题是图灵机无法解决的，而这些问题同样也无法由现实中的计算机解决。因此，图灵机也被用来揭示算法可解问题的边界。

一台图灵机由控制单元和存储带组成。
控制单元包含图灵机程序，它只能处于有限多个状态之一，并通过一个读写头对存储带上的各个单元进行顺序访问。
每个单元可以存储一个来自有限字母表的符号。
存储带由无限多个单元组成。
在图 5.1（图灵机，TM）中给出了图灵机的示意图。



![](image/Pasted%20image%2020260119111630.png)


Initial enthält das Speicherband das Eingabewort und der Lese-/Schreibkopf befindet sich auf dem ersten Feld der Eingabe (von links gesehen). Rechts und links von der Eingabe stehen auf dem Speicherband unendlich viele weitere Felder zur Verfügung. Diese Felder enthalten ein besonderes Zeichen, das so genannte Blank, geschrieben ␣. Die Turingmaschine befindet sich initial im Startzustand. Sie verarbeitet die Eingabe getaktet entsprechend ihres Programms. Je Takt werden in Abhängigkeit des momentanen Zustands und dem unter dem Lesekopf befindlichen Zeichens die folgenden drei Aktionen ausgeführt:

Die Steuereinheit geht in einen neuen Zustand über, dem Folgezustand. Dies kann natürlich auch der bisherige sein.
Das Feld unter dem Lese-/Schreibkopf wird mit einem neuen Zeichen beschrieben. Dies kann natürlich auch das bisherige sein.
Der Lese-/Schreibkopf wird um ein Feld nach rechts oder um ein Feld nach links weiterbewegt.
Die Turingmaschine beendet ihre Arbeit und hält, wenn sie in einen der zwei besonderen Zustände gelangt, in den akzeptierenden Zustand oder in den verwerfenden Zustand. Im ersten Fall wird die Eingabe akzeptiert, im zweiten wird sie verworfen (nicht akzeptiert). Gelangt die Turingmaschine nicht in einen dieser Zustände, dann hält sie nicht an und läuft unbegrenzt weiter.

Formal wird eine Turingmaschine durch ein 7-Tupel analog zu den bisherigen Automatenmodellen beschrieben. Es handelt sich dabei um ein deterministisches Automatenmodell. Auf die nichtdeterministische Variante wird hier nicht eingegangen.


初始时，存储带上包含输入词，读写头位于输入的第一个符号位置（从左数）。
输入左右两侧在存储带上各有无限多个单元，这些单元中存放一种特殊符号，称为空白符（Blank），记作 ␣。
图灵机初始处于初始状态。

图灵机按照其程序以离散时钟步（时刻）的方式处理输入。
在每一个时刻，根据当前状态以及读写头下方的符号，将执行以下三个动作：

控制单元转移到一个新的状态（后继状态），也可以保持在当前状态；

用一个新符号覆盖读写头下方的存储单元（也可以写回原符号）；

读写头向左或向右移动一个单元。

当图灵机进入以下两个特殊状态之一时，计算结束并停止运行：
接受状态或拒绝状态。
进入接受状态表示输入被接受，进入拒绝状态表示输入被拒绝（不被接受）。
如果图灵机永远不会进入这两个状态之一，则它将无限运行而不会停机。

在形式化定义中，图灵机（与之前的自动机模型类似）可以用一个七元组（7-tuple）来描述。
它是一个确定性自动机模型。
本文不讨论其非确定性变体。


---


# 1 Definition: **Turingmaschine**

![](image/Pasted%20image%2020260119112605.png)

> 图灵机是一个确定性的 7 元组自动机模型，通过有限控制、无限带以及读写头，在每一步中根据当前状态和读到的符号，执行状态转移、符号重写和头移动，用于刻画算法可计算性的边界。


Eine solche Überführungstabelle besteht aus endlich vielen Zeilen. Für jedes Argumentpaar (q,x)∈Q×Γ von δ gibt es genau eine Zeile in der Tabelle.

Zur formalen Beschreibung der Arbeitsweise einer Turingmaschine werden _Konfigurationen_ und _Berechnungen_ eingeführt. Eine Konfiguration beschreibt einen momentanen Gesamtzustand einer Turingmaschine, bestehend aus Zustand, Position des Lese-/Schreibkopfes und Bandinhalt. Bei der Spezifikation des Bandinhalts genügt es, sich auf einen endlichen Ausschnitt des unendlichen Speicherbandes zu beschränken. Die unendlich vielen _Blanks_ links und rechts auf dem Speicherband werden meist nicht geschrieben. Initial wird der Bandinhalt durch die aus endlich vielen Zeichen bestehende Eingabe spezifiziert. Es befinden sich keine _Blanks_ in der Eingabe. Die Eingabe kann dann während der Verarbeitung mit anderen Zeichen des Bandalphabets überschrieben werden, durchaus auch mit _Blanks_. Dabei bleibt die Anzahl der belegten Felder aber gleich und damit auch die Länge des relevanten Bandinhalts. In endlich vielen Takten können über die von der Eingabe initial beschriebenen Felder hinaus maximal nur endlich viele Felder neu beschrieben werden. Der relevante Bandausschnitt bleibt somit in jedem Fall endlich. Ein Bandinhalt kann also immer als eine endliche Zeichenfolge spezifiziert werden, innere _Blanks_ sind dabei mit aufzuführen, _Blanks_ am rechten bzw. linken Rand nur soweit wie die jeweiligen Felder gerade von dem Lese-/Schreibkopf gelesen werden(Abbildung [Abb. 5.2 Turingmaschine in der Konfiguration ababqabbaa](https://vfhti.eduloop.de/loop/Deterministische_Turingmaschinen#fig_TMKonfig "Abb. 5.2 Turingmaschine in der Konfiguration ababqabbaa"), Definition [Konfiguration TM](https://vfhti.eduloop.de/loop/Deterministische_Turingmaschinen#def_konfig)).


![](image/Pasted%20image%2020260119112803.png)

![](image/Pasted%20image%2020260119113244.png)

![](image/Pasted%20image%2020260119113308.png)

![](image/Pasted%20image%2020260119113346.png)


# 2 Definition: Konfiguration TM 

![](image/Pasted%20image%2020260119112829.png)

Die Disjunktheit von Q und Γ dient nur dazu, die Zeichen von dem Zustand in einer Konfiguration unterscheiden zu können. Ist eine Turingmaschine gegeben, bei der das nicht zutrifft, so sind die Zustände entsprechend umzubenennen. Das Verhalten der Turingmaschine ändert sich dadurch nicht.

Für die Konfiguration am rechten Rand des Bandes gilt uq ␣ =uq. Hier folgen unendlich viele Blanks, die nicht geschrieben werden müssen. Am linken Rand gilt entsprechend ␣uqv=uqv.

Es gibt auch eine Variante der Turingmaschine, die am linken Rand begrenzt ist (**Halbbandmaschine**). Diese Variante wurde in der früheren Version dieses Skriptes verwendet, so dass sich Videos, Übungsaufgaben und Lösungen teilweise auf diese Version beziehen.

这份文件介绍了图灵机的**配置**的一种记号 uqv，它表示：
- uv 是带上从最左非空白到最右非空白的内容（有限表示）。
- q是当前状态。
- 读写头指向 v 的第一个字符（若 v 非空），否则指向一个空白。
- 当读写头在右边界外的空白上时，表示为 uq（即 v 为空）。


![](image/Pasted%20image%2020260119114416.png)





# 3 Definition: **Startkonfiguration TM**

![](image/Pasted%20image%2020260119113559.png)

Eine Berechnung einer Turingmaschine setzt sich nun aus einer Folge von Berechnungsschritten zusammen. Sie beginnt mit der Startkonfiguration und durchläuft eine Folge von Konfigurationen bis sie ggf. hält. Je nach Zustand akzeptiert oder verwirft sie die Eingabe. Eine Turingmaschine muss nicht nach endlich vielen Berechnungsschritten halten.


# 4 Definition: **Berechnungsschritt TM**

![](image/Pasted%20image%2020260119114524.png)

Der erste Spezialfall, die Überführung am rechten Rand, ist eigentlich bereits in der allgemeinen Definition mit a=␣ und v=ϵ enthalten und könnte entfallen. Der zweite Spezialfall, die Überführung am linken Rand, ist bei der **Halbbandmaschine** dagegen notwendig. Er legt fest, dass der Lese-/Schreibkopf auf dem Feld ganz links bleibt, auch wenn die Überführungsfunktion eine Linksbewegung vorschreibt. Über den linken Rand kann eben nicht hinausgegangen werden. Achtung: Mit der Überführung δ(q,a)=(q,a,L) gerät eine Halbbandmaschine am linken Rand in eine nicht haltende Schleife.



# 5 Definition: **Akzeptierende und verwerfende Konfiguration**


![](image/Pasted%20image%2020260119114636.png)

Die Funktionswerte der Überführungsfunktion für den akzeptierenden Zustand und den verwerfenden Zustand sind also stets irrelevant, da die Turingmaschine bei Erreichen eines dieser Zustände immer anhält. Sie werden daher üblicherweise nicht spezifiziert.

Eine Turingmaschine wird nun wie die bisher betrachteten Automatenmodelle zur Erkennung von Sprachen eingesetzt. Die dabei von der Startkonfiguration bis zur akzeptierenden Konfiguration durchlaufene Folge von Konfigurationen wird auch Berechnung genannt.

因此，接受状态和拒绝状态的转移函数的值始终无关紧要，因为图灵机到达其中一个状态时总是会停止。所以，这些值通常不会被指定。

与之前讨论过的自动机模型一样，图灵机现在也被用于语言识别。从初始配置到接受配置所遍历的配置序列也称为一次计算。

# 6 Definition: **Berechnung einer TM**

![](image/Pasted%20image%2020260119114930.png)

Ein Wort wird also von einer Turingmaschine akzeptiert, wenn die Konfigurationenfolge ausgehend von der Startkonfiguration endlich ist und die Turingmaschine in dem akzeptierenden Zustand anhält. Der verbleibende Bandinhalt ist für die Spracherkennung ohne Bedeutung. Für die Nicht-Akzeptierung eines Wortes gibt es zwei Ursachen: Die Konfigurationenfolge ist zwar endlich, aber die Turingmaschine hält in dem verwerfenden Zustand oder die Konfigurationenfolge ist unendlich, die Turingmaschine hält also nicht an.

# 7 Definition: Turing-erkennbar

![](image/Pasted%20image%2020260119115123.png)

Eine Sprache L heißt _Turing-erkennbar_, erkennbar oder _rekursiv aufzählbar_, falls es eine Turingmaschine gibt, die L erkennt. Die Sprachfamilie oder Klasse der Turing-erkennbaren Sprachen wird mit ℒerk bezeichnet.

  
Es ist häufig von großem Vorteil, insbesondere bei sehr langen Berechnungen, wenn man weiß, dass eine Turingmaschine für alle möglichen Eingaben anhält. Sie gelangt also immer entweder in eine akzeptierende oder eine verwerfende Konfiguration. Die Eingabe wird dann entweder akzeptiert oder verworfen. Die Turingmaschine trifft also auf jeden Fall eine Entscheidung über die Zugehörigkeit eines Wortes zu der Sprache, sie _entscheidet_ die Sprache.

**  
图灵可识别**

一种语言L_图灵可识别_、可识别或_递归可枚举_意味着存在一个图灵机可以识别该机器。L图灵可识别语言的语言家族或类别由以下方式确定：ℒerk指定的。

  
尤其是在进行长时间计算时，了解图灵机对所有可能的输入都会停机往往是一个巨大的优势。因此，它总是会进入接受或拒绝状态。然后，输入要么被接受，要么被拒绝。因此，图灵机总是能够判断一个词是否属于某种语言；它_就能确定_该词属于哪种语言。

# 8 Definition: **Turing-entscheidbar**

![](image/Pasted%20image%2020260119115205.png)

**图灵可判定**

一种语言

L

如果存在一台总是停机的图灵机，则称该问题_为图灵可判定问题、可判定问题或递归问题。_

L

识别。可判定语言的语系或类别与……

ℒent

指定的。

# 9 Beispiel TM1 

Konstruktion einer Turingmaschine, die die Sprache L={aibici∣i∈ℕ0} entscheidet.

Informelle Beschreibung der Turingmaschine:

1. Erstes a durch ein Blank überschreiben, weitere a überlesen.
2. Bereits überschriebene b überlesen, erstes b durch x überschreiben, weitere b überlesen. Falls kein b mehr vorhanden, halte verwerfend.
3. c überlesen, letztes c durch ein Blank überschreiben. Falls kein c mehr vorhanden, halte verwerfend.
4. Zurück an den Wortanfang.
5. Falls noch a vorhanden, gehe nach 1, sonst überprüfen, ob alles überschrieben.
6. Falls kein a mehr vorhanden und alles überschrieben, halte akzeptierend.

Formale Beschreibung:

T=({0,1,2,3,4,5,6,7,8,9},{a,b,c},{a,b,c,x,␣},δ,0,8,9) mit

![](image/Pasted%20image%2020260119115231.png)


Für alle hier nicht aufgeführten Paare (q,y)∈Q×Γ wird δ(q,y)=(9,y,R) definiert. Diese Turingmaschine kann sowohl als Turingmaschine mit beidseitig unendlichem Band, als auch als Halbbandmaschine interpretiert werden, da sie im ersten Feld nie nach links (L) geht. Genau genommen ist sie ein **Linear beschränkter Automat**, eine eingeschränkte Turingmaschine, die nur einen Teil des Bandes verwendet, dessen Länge proportional zur Länge der Eingabe ist.

Nachfolgend ist für das Wort aabbcc die Berechnung von T aufgeführt:

![](image/Pasted%20image%2020260119115245.png)


aabbcc∈L(T), da T hält und 8 der akzeptierende Zustand ist.

Es gilt L(T)=L. Da T für jede Eingabe hält, ist L entscheidbar.

---

Eine Turingmaschine T=(Q,Σ,Γ,δ,q0,qaccept,qreject) kann in der folgenden Weise als _Überführungsgraph_ dargestellt werden:

- Die Zustände q∈Q werden als Knoten dargestellt und mit dem Zustandsnamen benannt.
- Der Startzustand wird mit einem Pfeil spezifiziert, der Endzustand mit einem zusätzlichen Kreis.
- Die Überführung vom Zustand q zum Zustand q′ durch eine gerichtete Kante vom Knoten q zum Knoten q′. Die Überführungsfunktion δ(q,a)=(q′,b,d) definiert dabei die Markierung der Kante mit a→b,d.

In Abbildung [Abb. 5.3 Überführungsgraph der TM T](https://vfhti.eduloop.de/loop/Deterministische_Turingmaschinen#fig_DTM-ZGraph1 "Abb. 5.3 Überführungsgraph der TM T") ist die Turingmaschine aus Beispiel [Beispiel TM1](https://vfhti.eduloop.de/loop/Deterministische_Turingmaschinen#bsp_TM1) als Überführungsgraph dargestellt. Der verwerfende Zustand 9 und alle Überführungen dorthin sind der Übersichtlichkeit halber nicht dargestellt.

![](image/Pasted%20image%2020260119115422.png)

Abschließend sei noch auf die sich unmittelbar ergebende Beziehung zwischen Turing-erkennbaren und Turing-entscheidbaren Sprachen hingewiesen.

# 10 Satz: Turing-entscheidbar und Turing-erkennbar
Jede Turing-entscheidbare Sprache ist auch Turing-erkennbar.

![](image/Pasted%20image%2020260119112523.png)

Sei 
L
 eine Turing-entscheidbare Sprache. Dann gibt es eine TM 
T
 mit 
L
=
L
(
T
)
, die immer hält. Also ist 
L
 auch Turing-erkennbar.
