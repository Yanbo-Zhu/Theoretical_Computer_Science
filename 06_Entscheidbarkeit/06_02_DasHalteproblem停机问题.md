
Es sei ein Algorithmus durch ein Programm implementiert, und dieses Programm werde auf einem Computer mit einer Eingabe ausgeführt. Viele Programme verarbeiten die Eingabe, terminieren nach einer bestimmten Zeit und geben eine Ausgabe aus. Es gibt aber auch einige Programme, die haben eine längere Laufzeit, und man wartet auf die Ausgabe und die Terminierung und wartet und wartet und ... .

Terminiert das Programm nun irgendwann oder terminiert es nicht? Gerade bei Programmen, die ohnehin eine längere und unbekannte Laufzeit haben, wäre es hilfreich, ein anderes Programm zur Verfügung zu haben, das Programme und ihre Eingabe auf Terminierung überprüft. Das führt auf die Fragestellung des _Halteproblems_ und die Frage nach der Existenz eines Algorithmus zur Lösung des Halteproblems. Das Halteproblem selbst lautet folgendermaßen: Hält ein Algorithmus mit einer bestimmten Eingabe? In Definition [Halteproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_Halteproblem) ist das Halteproblem mittels Turingmaschinen formalisiert.


假设一个算法由一个程序实现，该程序在计算机上运行并接收输入。许多程序处理输入后，会在一定时间后终止并输出结果。但也有一些程序运行时间较长，你需要等待输出和终止，然后一直等待……

程序最终会终止吗？尤其对于那些运行时间本身就很长且未知的程序而言，如果能有一个程序来检查程序及其输入是否能够终止，将会非常有帮助。这就引出了_停机问题_以及是否存在解决该问题的算法。停机问题本身是指：给定一个输入，算法是否会停机？停机[问题](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_Halteproblem)可以用图灵机来形式化描述。



# 1 **Halteproblem**

Die Frage, ob eine Turingmaschine angesetzt auf eine Eingabe anhält oder nicht, heisst Halteproblem.

  
Die Frage nach der Existenz eines Algorithmus zur Lösung des Halteproblems muss leider mit _Nein_ beantwortet werden (Satz [Unentscheidbarkeit des Halteproblems](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_Halteproblem)). Die Nicht-Existenz eines solchen Algorithmus wird nach dem Prinzip des _Zweiten Cantorschen Diagonalverfahrens_ gezeigt. Man spricht auch von einem Beweis durch _Diagonalisierung_.

图灵机在给定输入时是否会停机的问题称为停机问题。

遗憾的是，关于是否存在解决停机问题的算法这个问题，答案是_否定的_（[停机问题不可判定性](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_Halteproblem)定理）。这种算法不存在性可以通过_康托尔第二对角线方法_证明。这也被称为对_角化_证明。



## 1.1 Satz: **Unentscheidbarkeit des Halteproblems**


Es gibt keine Turingmaschine, die das Halteproblem entscheidet.

  
Dem Beweis dieses Satzes seien noch ein paar Bemerkungen vorangestellt. Sie sollen den Zugang zu dieser Beweistechnik erleichtern.

Sind zwei endliche Mengen bzgl. ihrer Größe miteinander zu verglichen, so zählt man einfach ihre Elemente. Die Mengen haben die gleiche Größe, die gleiche _Kardinalität_ oder die gleiche _Mächtigkeit_, wenn ihre Elementanzahlen gleich sind, ansonsten ist die eine größer als die andere. Eine solche einfache Abzählung versagt zum Vergleich von unendlichen Mengen, denn sie haben unendlich viele Elemente. Hierzu wird der Begriff der _Abzählbarkeit_ mittels Funktionen eingeführt (Definitionen [Gleiche Grösse](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_GleichGross) und [Abzählbarkeit](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_Abzaehl)).



**停机问题的不可判定性**

没有图灵机可以解决停机问题。

  
在证明该定理之前，需要先做一些说明。这些说明旨在帮助理解这种证明方法。

比较两个有限集合的大小时，只需统计它们的元素个数即可。如果两个集合的元素个数相等，则它们的大小相同，_基数__也_相同；否则，一个集合大于另一个。这种简单的计数方法在比较无限集合时就失效了，因为无限集合包含无限多个元素。为此，引入了_可数性_的概念，并使用函数（[等大小](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_GleichGross)和[可数性](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_Abzaehl)的定义）来描述这一概念。

# 2 Definition: **Gleiche Grösse**

Zwei Mengen A und B haben die gleiche Größe, wenn es eine bijektive Abbildung f:A→B gibt.

Zwei Mengen sind also gleich groß, wenn jedem Element von A genau ein Element von B zugeordnet werden kann und wenn dabei auch jedes Element von B in einer solchen Zuordnung vorkommt.

因此，如果两个集合的每个元素都相等，则称这两个集合的大小相等。一个恰好一个元素B可以被分配，并且如果每个元素B这种情况发生在这样的任务中。


# 3 Definition: **Abzählbarkeit**

Eine Menge heißt abzählbar, wenn sie endlich ist oder die gleiche Größe wie ℕ hat. Ansonsten heißt sie nicht abzählbar oder überabzählbar.


如果一个集合是有限的或者大小与整数相同，则称该集合为可数集合。ℕ否则，它被称为不可数名词或不可数名词。


## 3.1 Beispiel 


Die Menge der natürlichen Zahlen ℕ ist abzählbar. Sie hat die gleiche Größe wie sie selbst, denn die Abbildung f:ℕ→ℕ mit f(n)=n ist bijektiv.

Auch die Menge der geraden natürlichen Zahlen ℕgerade ist abzählbar. Sie hat die gleiche Größe wie ℕ, denn die Abbildung f:ℕ→ℕgerade mit f(n)=2n ist bijektiv.

Dies scheint jetzt etwas merkwürdig zu sein, denn ℕgerade⊂ℕ. Eine bijektive Abbildung gibt es hier natürlich nur, weil es sich um unendliche Mengen handelt.

Das erste Cantorsche Diagonalverfahren zeigt nun, dass auch die Menge der rationalen Zahlen ℚ abzählbar ist und damit die gleiche Größe wie ℕ hat. Mittels des zweiten Cantorschen Diagonalverfahrens dagegen wird die Überabzählbarkeit der reellen Zahlen ℝ nachgewiesen. Beide Verfahren können in den entsprechenden Lehrbüchern zur Mathematik oder auch in nachgelesen werden.

Mittels solcher Größenvergleiche kann nun bereits gezeigt werden, dass es auch Sprachen geben muss, die nicht Turing-erkennbar sind, die also außerhalb der in Abbildung [Abb. 6.1 Hierachie der Sprachfamilien](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#fig_ChomHier "Abb. 6.1 Hierachie der Sprachfamilien") dargestellten Sprachhierarchie liegen.



自然数集ℕ是可数的。它的大小与自身相同，因为图像f：ℕ→ℕ和f（n）=n是双射。

偶数自然数集也包含在内。ℕGer一个de它是可数的。它的大小与……相同ℕ因为图像f：ℕ→ℕGer一个de和f（n）=2n是双射。

现在看来这有点奇怪，因为ℕGer一个de⊂ℕ这里之所以存在双射，仅仅是因为我们处理的是无限集合。

第一个康托尔对角线方法现在表明，有理数集也ℚ是可数的，因此大小与……相同ℕ确实如此。然而，康托尔第二对角线方法证明了实数的不可数性。ℝ这一点已被证实。这两种方法都可以在相关的数学教科书或其他地方找到。

利用这种规模比较，现在可以证明，也一定存在一些图灵无法识别的语言，即位于[图 6.1 语言族层次结构](https://vfhti.eduloop.de/loop/Entscheidbare_Probleme#fig_ChomHier "图 6.1 语言家族层级")所示的语言层次结构之外的 语言。


# 4 Satz: **Nicht Turing-erkennbar**

Es gibt Sprachen, die nicht Turing-erkennbar sind.


**Beweis:  nicht Turing-erkennbare Sprachen**

Ein Existenzbeweis für Sprachen, die nicht Turing-erkennbar sind, wird über die Mächtigkeiten der Menge der Turingmaschinen und der Menge der Sprachen geführt.

Sei Σ das zugrunde liegende Alphabet. Es ist endlich. Die Menge aller Wörter Σ* ist dann abzählbar unendlich. Eine Sprache L ist eine Teilmenge von Σ* oder auch ein Element von 𝒫(Σ*). Die Potenzmenge einer abzählbar unendlichen Menge ergibt eine überabzählbare Menge, d. h. es gibt überabzählbar viele Sprachen über Σ.

Betrachte nun die Menge aller Turingmaschinen mit dem Eingabealphabet Σ. Da Turingmaschinen über einem endlichen Alphabet in endlich vielen Zeichen beschrieben werden, lassen sie sich in Wortordnung anordnen, und somit hat die Menge aller Turingmaschinen eine abzählbar unendliche Mächtigkeit. Damit gibt es auch nur abzählbar unendlich viele Sprachen, die Turing-erkennbar sind.

Eine überabzählbare Menge ist echt mächtiger als eine abzählbar unendliche Menge. Also muss es Sprachen geben, die nicht Turing-erkennbar sind.

Nun zurück zum Halteproblem und dem Nachweis seiner Unentscheidbarkeit. Mit Definition [TM Wortproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_TMWort) wird das Halteproblem analog zu [Regulärer Ausdruck Wortproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_FAWort) und [Kontextfreie Grammatik Wortproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_KFWort) in ein Wortproblem überführt.


通过图灵机集合和语言集合的基数，证明了非图灵可识别语言的存在性。

是Σ底层字母表。它是有限的。所有单词的集合。Σ*那么，它就是可数无限的。一种语言L是 的一个子集Σ*或者也是以下元素之一𝒫（Σ*）可数无限集的幂集是一个不可数集，也就是说，存在不可数多种语言。Σ。

现在考虑所有输入字母为 的图灵机的集合Σ由于图灵机是用有限数量的符号在有限的字母表上描述的，它们可以按词序排列，因此所有图灵机的集合具有可数无穷大的基数。因此，图灵机可识别的语言也只有可数无穷多个。

不可数集确实比可数无限集更强大。因此，必然存在图灵不可识别的语言。

现在回到停机问题及其不可判定性的证明。通过定义[图灵机字问题，](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_TMWort)停机问题就转化为一个字问题， 类似于[正则表达式字问题](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_FAWort)和[上下文无关文法字问题。](https://vfhti.eduloop.de/loop/Das_Halteproblem#def_KFWort)


# 5 Definition: **TM Wortproblem**

$L_{TM}$:={ 〈 T,w 〉 ∣T ist eine Turingmaschine und w∈L(T)}.

![](image/Pasted%20image%2020260119125853.png)

language of Turing machine
  
Wäre das Halteproblem entscheidbar, dann wäre auch die Sprache LTM entscheidbar: Hält T angesetzt auf w akzeptierend oder verwerfend, dann wird 〈T,w〉 akzeptiert bzw. verworfen. Hält aber T angesetzt auf w nicht, dann könnte das mit dem Algorithmus erkannt werden, der das Halteproblem für T und w entscheidet, und 〈T,w〉 wird verworfen.

Kann nun aber gezeigt werden, dass LTM nicht entscheidbar ist, dann folgt durch Kontraposition der vorangehenden Aussage, dass auch das Halteproblem nicht entscheidbar ist. Vorab wird aber noch Turing-Erkennbarkeit von LTM gezeigt.


如果持有问题可以解决，那么语言问题也可以解决。LTM决定性的：持有T计划西接受或拒绝，然后〈T，西无论接受还是拒绝，它都成立。T计划西否则，可以通过解决停机问题的算法来检测这一点。T和西决定，并且〈T，西〉被拒绝。

现在可以证明这一点吗？LTM如果问题是不可判定的，那么根据前述结论的反证法，停机问题也是不可判定的。然而，问题的图灵可检测性是预先考虑的。LTM已显示。


## 5.1 Satz: **Turing-erkennbar Wortproblem**

$L_{TM}$ ist eine Turing-erkennbare Sprache.


Zum Beweis wird eine Turingmaschine U spezifiziert, die LTM erkennt.

Informelle Beschreibung von U:

1. Analysiere die Eingabe 〈T,w〉 dahingehend, ob T eine Turingmaschine ist und w ein Wort. Ist das nicht der Fall, so halte verwerfend.
2. Simuliere T mit der Eingabe w.
3. Falls T in den akzeptierenden oder verwerfenden Zustand gelangt, dann halte akzeptierend bzw. verwerfend.

Es ist zu bemerken, dass U nicht hält, wenn T angesetzt auf w nicht hält. U hält aber akzeptierend, wenn T angesetzt auf w akzeptierend hält. Also erkennt U die Sprache $L_{TM}$.

Die hier informell beschriebene Turingmaschine U wird auch _universelle Turingmaschine_ genannt. Sie kann jede andere Turingmaschine simulieren und kann als eine Formalisierung eines programm-gesteuerten Computers angesehen werden.

![](image/Pasted%20image%2020260119130059.png)



## 5.2 Satz: **Unentscheidbare Sprache Wortproblem**


 $L_{TM}$ ist eine unentscheidbare Sprache.

![](image/Pasted%20image%2020260119130232.png)


![](image/Pasted%20image%2020260119130241.png)



# 6 Definition: **co-Turing-erkennbar**
Eine Sprache heißt co-Turing-erkennbar, wenn ihr Komplement Turing-erkennbar ist.
如果一个语言的补语言是图灵可识别的，则称该语言为共图灵可识别语言。


## 6.1 Satz: Turing-entscheidbar 
Eine Sprache ist genau dann entscheidbar, wenn sie Turing-erkennbar und co-Turing-erkennbar ist.


Beweis: 
- Sei L eine entscheidbare Sprache:
    
    Jede entscheidbare Sprache ist auch Turing-erkennbar (Satz [Turing-entscheidbar und Turing-erkennbar](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_TMentscheidbar)).
    
    Mit L ist auch L‾ entscheidbar: Der Entscheider für L‾ ergibt sich aus dem Entscheider für L durch die Vertauschung von akzeptierendem und verwerfendem Zustand. Damit ist auch L‾ Turing-erkennbar.
    
- Sei L eine Turing-erkennbare und co-Turing-erkennbare Sprache:
    
    Dann gibt es einen Erkenner T1 für L und einen Erkenner T2 für L‾. Die Turingmaschine T entscheidet dann L.
    
    Informelle Beschreibung von T:
    
    1. Analysiere die Eingabe w dahingehend, ob w ein Wort über dem L zugrunde liegenden Alphabet ist. Ist das nicht der Fall, so halte verwerfend.
        
    2. Simuliere abwechselnd T1 und T2 jeweils mit der Eingabe w, einen Berechnungsschritt T1, dann einen Berechnungsschritt T2.
        
    3. Falls T1 akzeptiert, halte akzeptierend, falls T2 akzeptiert, halte verwerfend.
        
    
    T läuft nun solange bis entweder T1 oder T2 akzeptiert. Einer von beiden Turingmaschinen muss akzeptieren, weil w entweder in L ist oder in L‾. T entscheidet also die Sprache L.

![](image/Pasted%20image%2020260119130510.png)



## 6.2 Satz:   $\overline{L_{LM}}$  ist eine nicht Turing-erkennbare Sprache.

![](image/Pasted%20image%2020260119130617.png)

 $\overline{L_{LM}}$   ist eine nicht Turing-erkennbare Sprache.

Beweis: 

LTM ist Turing-erkennbar (Satz [Turing-erkennbar Wortproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_TMWortErk)). Wäre auch LTM‾ Turing-erkennbar, dann wäre LTM auch entscheidbar (Satz [co-Turing-erkennbar](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_CoTMWort)). LTM ist aber eine unentscheidbare Sprache (Satz [Unentscheidbare Sprache Wortproblem](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_TMWort)). Also ist LTM‾ nicht Turing-erkennbar.

Damit ist auch die in Satz [Hierarchie](https://vfhti.eduloop.de/loop/Das_Halteproblem#satz_Hierarchie) angesprochene Hierarchie von Sprachfamilien vollständig gezeigt. Mit LTM∉ℒent aber LTM∈ℒerk ergibt sich die echte Teilmengen-Beziehung ℒent⊂ℒerk. Darüber hinaus ist mit LTM‾∉ℒerk eine Sprache spezifiziert, die außerhalb dieser Hierarchie liegt.
