

Der _Nichtdeterminismus_ erweitert das Konzept der deterministischen Verarbeitungsweise. Bezogen auf endliche Automaten bedeutet die deterministische Verarbeitungsweise, dass je Zustand und gelesenem Zeichen genau ein Folgezustand definiert ist. Ein nichtdeterministischer endlicher Automat lässt dagegen je Zustand und gelesenem Zeichen **keinen** bis **mehrere Folgezustände** zu. Des weiteren kann es auch Zustandsüberführungen geben, ohne dass ein Zeichen des Eingabebandes gelesen wird, so genannte ϵ**-Überführungen**. Betrachte dazu das [Beispiel NEA](https://vfhti.eduloop.de/loop/Nichtdeterministische_endliche_Automaten#bsp_NEA).

非确定性扩展了确定性处理方式的概念。  
对于有限自动机而言，**确定性处理方式**意味着对于每一个状态和读取的字符，**恰好有一个后续状态**被定义。

而**非确定性有限自动机**则允许对于每一个状态和读取的字符，存在 **零个、一个或多个后续状态**。  
此外，还可以存在在不读取输入带上任何字符的情况下进行的状态转换，这种转换称为 **ε-转换**。

请参考 NEA 的示例以进一步理解。


![](image/TIO_29NEA_N.png)

Es handelt sich um einen nichtdeterministischen endlichen Automaten, weil der Zustand A eine ϵ-Überführung hat und der Zustand B für die Eingabe a keinen Folgezustand und für die Eingabe b zwei Folgezustände hat.


这是一个**非确定性有限自动机**，因为状态 **A** 存在 **ε-转换**，而状态 **B** 对输入 **a** 没有后续状态，对输入 **b** 则有两个后续状态。

