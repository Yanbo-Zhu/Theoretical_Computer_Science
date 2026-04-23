
Der Begriff _Algorithmus_ ist heute untrennbar mit der Erstellung von Computerprogrammen verbunden. Aber schon lange bevor es Computer überhaupt gab, gab es Algorithmen, auch wenn dieser Begriff noch nicht verwendet wurde. So z. B. die im _Papyrus Rhind_ zusammengestellten Rechenaufgaben aus dem 16. Jh. v. Chr. oder das von Euklid um 300 v. Chr. aufgeschriebene Verfahren zur Bestimmung des größten gemeinsamen Teilers zweier Zahlen, das heute _Euklidischer Algorithmus_ genannt wird. Informell bzw. intuitiv läßt sich die Bedeutung des Begriffs Algorithmus folgendermaßen beschreiben:

> Ein Algorithmus ist ein allgemeines, eindeutiges Verfahren zur Lösung einer Klasse gleichartiger Probleme, gegeben durch einen aus elementaren Anweisungen bestehenden Text.

Hierunter fallen natürlich insbesondere mathematische Verfahren und – wie eingangs schon festgestellt – Computerprogramme. Aber auch Bedienungsanleitungen von technischen Anlagen, Zusammenbauanleitungen von Bausätzen oder auch Kochrezepte können in einem erweiterten Sinn als Algorithmen bezeichnet werden.

Die Bedeutung des Begriffs _Algorithmus_ wird nach Donald E. Knuth (*1938) durch Angabe weiterer Kriterien präzisiert (Begriffsbestimmung [Intuitiver Algorithmus](https://vfhti.eduloop.de/loop/Intuitiver_Algorithmusbegriff#def_IntAlg)).

# 1 **Intuitiver Algorithmus**

Ein intuitiver Algorithmus ist ein allgemeines, eindeutiges Verfahren zur Lösung einer Klasse gleichartiger Probleme, gegeben durch einen aus elementaren Anweisungen bestehenden Text, der die nachfolgend aufgeführten Kriterien erfüllt:

- **Endlichkeit:** Ein Algorithmus besteht aus endlich vielen elementaren Anweisungen (Schritten).
- **Bestimmtheit:** Jeder Schritt des Algorithmus muss eindeutig definiert sein (determiniert). Der jeweils nächste auszuführende Schritt muss eindeutig bestimmt sein (deterministisch). Dazu gehört auch die Bestimmung des ersten Schrittes und des Algorithmusendes.
- **Eingabe:** Ein Algorithmus hat keine oder endlich viele Eingabewerte aus einer Eingabemenge. Diese Werte werden initial an den Algorithmus gegeben bevor er mit der Ausführung des ersten Schritts beginnt.
- **Ausgabe:** Ein Algorithmus hat mindestens einen Ausgabewert aus einer Ausgabemenge. Der Algorithmus ordnet der Eingabe eine Ausgabe zu, er definiert also eine Funktion.
- **Effektivität:** Die einzelnen Anweisungen müssen überhaupt ausführbar sein.

Die obige Beschreibung eines Algorithmus bleibt aber trotz der Präzisierungen sehr vage. Begriffe wie Verfahren, Anweisung, Schritt oder Wert sind zwar intuitiv verständlich, aber nicht im mathematischen Sinn exakt definiert. Insbesondere erfordert die Interpretation des Begriffs elementar eine vage Vorstellung von der Zielgruppe oder der Zielmaschine, die den Algorithmus ausführen soll. Deshalb wird dieser Algorithmusbegriff auch _intuitiv_ genannt, und der Begriff wird deshalb auch nur erläutert und nicht definiert.

Die Effektivität der einzelnen Anweisungen ist ein ganz wichtiges Kriterium. Wenn z. B. eine Bedingung in einer Anweisung auf der Lösung eines nicht lösbaren oder bisher noch ungelösten Problems beruht, dann ist diese Anweisung nicht ausführbar, also nicht effektiv. Des Weiteren fordert diese Eigenschaft, aber auch die der Elementarität, dass eine Anweisung in endlicher Zeit zum Abschluss kommen muss. Eine unendlich viel Zeit benötigende Anweisung ist weder effektiv noch elementar.

Knuth führt als ein weiteres Kriterium eines intuitiven Algorithmus auch die Endlichkeit der Schrittausführungen auf und nennt Verfahren, in denen dies für zumindest einige Eingaben nicht erfüllt ist, _Berechnungsmethoden_. Andere Autoren dagegen verzichten auf die Forderung dieses Kriteriums, so dass auch Verfahren, die für gewisse Eingaben möglicherweise unendlich viele Schrittausführungen aufweisen, auch als Algorithmen bezeichnet werden können. Es wird hier also von Algorithmen, die immer terminieren, und von Algorithmen, die nicht immer terminieren, gesprochen.

Die hier verwendete Begriffsbestimmung eines Algorithmus schließt dann auch z. B. Betriebssysteme und sonstige Programme mit ein, die so lange nicht terminieren, bis sie explizit durch eine externe Eingabe oder durch Abbruch des Geräts beendet werden.

Darüber hinaus gibt es die so genannten _probabilistischen Algorithmen_, die das Kriterium der Bestimmtheit nicht erfüllen und dennoch als Algorithmen bezeichnet werden. Allerdings wird eine derartige Erweiterung des Algorithmusbegriffs hier nicht vorgenommen, und es werden auch solche Algorithmen nicht betrachtet. Ein weiteres Konzept, das gegen das Kriterium der Bestimmtheit verstößt, ist der _Nichtdeterminismus_. Insofern werden in diesem Kontext auch nur deterministische Verfahren betrachtet.

Mittels Algorithmen wird nun der _Berechenbarkeitsbegriff_ eingeführt. Ein Algorithmus berechnet in Abhängigkeit von seiner Eingabe eine Ausgabe, durch ihn wird also eine Funktion bestimmt. Eine _partielle_ Funktion ist dabei eine Funktion, bei der nicht für alle Argumente Funktionswerte definiert sein müssen.


**直观的算法**

直观算法是一种通用的、明确的程序，用于解决一类类似的问题，它由满足以下标准的基本指令文本给出：

- **有限性：**一个算法由有限数量的基本指令（步骤）组成。
- **确定性：**算法的每一步都必须是唯一确定的（确定性的）。下一步要执行的步骤也必须是唯一确定的（确定性的）。这包括确定算法的第一步和结束步骤。
- **输入：**算法可以从输入集中接收零个或有限个输入值。这些值在算法开始执行第一步之前被初始地传递给它。
- **输出：**算法至少有一个输出值，该输出值来自一个输出集。算法将一个输出值分配给一个输入值；因此，它定义了一个函数。
- **有效性：**每条指令必须能够实际执行。

尽管有所澄清，上述对算法的描述仍然非常模糊。诸如过程、指令、步骤或值之类的术语虽然直观易懂，但在数学意义上并没有精确定义。特别是，“基本”一词的解释需要对目标群体或执行算法的目标机器有一定的了解。因此，这种算法概念也被称为_直观的_，该术语仅作解释，而未作定义。

指令的有效性是至关重要的标准。例如，如果指令中的某个条件依赖于解决一个无法解决或尚未解决的问题，那么该指令就无法执行，因此无效。此外，这一特性以及基本性要求指令必须在有限的时间内完成。耗时无限长的指令既无效也不基本。

克努特将步骤执行次数的有限性作为直观算法的另一个标准，并将至少对于某些输入不满足此标准的程序称为_计算方法_。然而，其他作者则放弃了这一标准，因此对于某些输入可能需要无限多次步骤执行的程序也可以被称为算法。因此，本文的讨论实际上是在总是终止的算法和总是不终止的算法之间进行的。

这里使用的算法定义还包括操作系统和其他程序，例如，这些程序只有在通过外部输入或设备中止显式终止时才会终止。

此外，还有所谓的_概率算法_，它们不满足确定性准则，却仍然被称为算法。然而，本文不涉及算法概念的这种扩展，也不讨论此类算法。另一个违反确定性准则的概念是非_确定性_。因此，本文仅讨论确定性方法。

现在，我们利用算法来引入_可计算性的概念_。算法根据输入计算输出，从而确定一个函数。_部分_函数是指对于某些参数，其函数值无需全部定义。


# 2 **Intuitiv berechenbar**

Eine partielle Funktion f heißt intuitv berechenbar, falls es einen intuitiven Algorithmus gibt, der f berechnet.

  
In der Diskussion des Berechenbarkeitsbegriffs nimmt die Frage nach der Terminierung eines Algorithmus für gewisse Eingaben eine zentrale Position ein. Eine wie hier vorgenommene Verallgemeinerung des Algorithmusbegriffs erscheint auch deshalb angemessen, da sich ansonsten die Frage nach der Terminierung eines Algorithmus – zumindest in der strengen Formulierung – nicht stellen würde, denn diese terminierten ja immer.

定义

**直观可计算**

偏函数f这意味着，如果存在一种直观的算法，那么它就是直观可计算的……f已计算。

  
在讨论可计算性概念时，算法对于某些输入是否会终止的问题占据核心地位。本文对算法概念的概括也显得恰当，因为否则算法终止的问题——至少在其最严格的表述中——就不会出现，因为算法总是会终止的。

# 3 Beispiel 

![](image/Pasted%20image%2020260119120638.png)

Auf der Basis dieser intuitiven Begriffe können nun aber keine formalen Beweise und Schlussfolgerungen durchgeführt werden. Es ist deshalb notwendig diesen Begriffen einen formalen Algorithmus- und einen formalen Berechenbarkeitsbegriff beiseite zu stellen. Z.B. die Tatsache, dass es bisher nicht gelungen ist, einen intuitiven Algorithmus zur Berechnung der Funktion fterm zu finden, ist kein Beweis, dass es keinen gibt. Gerade ein solcher Beweis erfordert eine Formalisierung.

然而，基于这些直观概念无法得出正式的证明和结论。因此，有必要用算法的形式化概念和可计算性的形式化概念来补充这些概念。例如，目前还无法开发出用于计算函数的直观算法。fter米找到一个这样的例子并不能证明它不存在。要证明它不存在，需要进行形式化描述。