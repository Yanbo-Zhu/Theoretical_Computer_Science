

# 1 编程语言也可以被视为一种形式语言（formal language）， 

Es bleiben die im Abschnitt [Alphabete, Wörter, Sprachen](https://vfhti.eduloop.de/loop/Alphabete,_W%C3%B6rter,_Sprachen "Alphabete, Wörter, Sprachen") eingeführten Begriffe auf konkrete Programmiersprachen zu übertragen. Dies erfolge hier am Beispiel der Programmiersprache _Java_.


编程语言也可以被视为一种形式语言（formal language），  
它由某个字母表 Σ 和一套语法规则（grammar）定义，  
所有符合这些规则的字符串组成的集合就是 LJava。


![](image/Pasted%20image%2020251031172158.png)


## 1.1 以java举例

这段文字其实是在用**形式语言（formal language）和自动机理论**的视角来解释编程语言（这里是 Java）的“语法正确性”概念。下面我帮你分段解释一下：


|概念|含义|
|---|---|
|**Σ**|Java 的字母表（可使用的所有字符）|
|**Σ***|所有可能的字符串（包括语法错误的）|
|**LJava**|所有语法正确的 Java 程序（合法的语言）|
|**wᵢ**|某个由 Σ 组成的具体字符串（一个例子）|
|**w₆ ∈ LJava**|表示 w₆ 是一个合法的 Java 程序|


### 1.1.1 **定义字母表（Alphabet Σ）**

> Σ = {a, b, c, …, z, A, B, C, …, Z, 0, 1, …, 9, +, −, ∗, …, ⋅}


意思是：

- 这是 **Java 语言的“字母表”**，也就是所有可能出现在 Java 源代码中的**基本字符集合**；
- 包含：
    - 英文字母（大小写）；
    - 数字；
    - 运算符（+、-、*、…）；
    - 以及空格、缩进、换行符等“不可见字符”。

👉 换句话说，**所有你能在键盘上打出来的 Java 源代码字符**，都属于这个字母表 Σ。


### 1.1.2 **定义“词（Word）”**

在形式语言理论中：
- 用 **Σ*** 表示“由字母表 Σ 中字符组成的所有可能的字符串（词）”；
- 每个字符串（word）就是一个可能的“程序文本”。


```
w1 = ax11
w2 = a=b+1
w3 = class
w4 = for
w5 = ax11 for b class;
w6 = public class Hello {
         public static void main(String[] args) {
             System.out.println("Hello World");
         }
     }

```

这些都是由 Σ 里的字符组成的**词**（也就是字符串）。

### 1.1.3 **定义 LJava**

> LJava 表示“Java语言的形式语言”，  
> 即所有**语法正确（syntaktisch korrekt）**的 Java 程序的集合。


形式上写作：

LJava ⊂ Σ*

意思是：
- LJava 是 Σ* 的子集；
- 因为并不是所有字符串都是合法的 Java 程序，只有其中一部分是。


### 1.1.4 判断哪些字符串属于 LJava

文中给出了六个词（w₁ 到 w₆）：

|词|字符串内容|是否语法正确|属于 LJava 吗？|
|---|---|---|---|
|w₁|ax11|❌（不是合法语句）|否|
|w₂|a=b+1|❌（不是完整的语句，没有分号）|否|
|w₃|class|❌（关键字单独使用，不是合法程序）|否|
|w₄|for|❌（关键字单独使用）|否|
|w₅|ax11 for b class;|❌（语法混乱）|否|
|w₆|完整的 Java “Hello World” 程序|✅|是|

所以：
```
wi ∈ Σ*   对所有 i = 1,…,6 成立（它们都是字符串）
wi ∉ LJava  对 i=1,…,5 成立（它们不是合法 Java 程序）
w6 ∈ LJava  成立（它是合法 Java 程序）

```



|概念|含义|
|---|---|
|**Σ**|Java 的字母表（可使用的所有字符）|
|**Σ***|所有可能的字符串（包括语法错误的）|
|**LJava**|所有语法正确的 Java 程序（合法的语言）|
|**wᵢ**|某个由 Σ 组成的具体字符串（一个例子）|
|**w₆ ∈ LJava**|表示 w₆ 是一个合法的 Java 程序|



# 2 程序的翻译经历的三个阶段


程序的翻译——在这里指的是对基于某个字母表的单词——通常要经过三个分析阶段，然后才进行真正的目标代码生成：
1. **词法分析（lexikalische Analyse）**
2. **语法分析（syntaktische Analyse）**
3. **语义分析（semantische Analyse）**

Die Übersetzung eines Programms – in diesem Kontext eines Wortes über dem zugrunde liegenden Alphabet – besteht aus drei Analysephasen, bevor die eigentliche Zielcode-Generierung erfolgt:

- lexikalische Analyse
- syntaktische Analyse
- semantische Analyse

## 2.1 词法分析

Die lexikalische Analyse hat die Aufgabe, die elementaren Einheiten (Symbole, Token) zu erkennen, z. B. Identifikatoren, Zahlen, Schlüsselwörter, Operatoren, Begrenzer. Diese elementaren Einheiten setzen sich aus unmittelbar nebeneinander stehenden Zeichen des zugrunde liegenden Alphabets zusammen. Die Einheiten lassen sich mittels _regulärer Ausdrücke_ beschreiben. Ihre Analyse basiert auf dem Modell der _endlichen Automaten_. Aus der Zeichenfolge wird eine Folge von elementaren Einheiten erzeugt. Diese Symbole bilden das Alphabet für die nächste Analysephase.

词法分析的任务是识别程序中的**基本单元（elementare Einheiten, Token）**，例如：标识符（Identifikatoren）、数字、关键字、运算符、分隔符等。  
这些基本单元是由字母表中**相邻的字符**组成的。  
它们可以通过**正则表达式（reguläre Ausdrücke）**进行描述。  
词法分析基于**有限自动机（endliche Automaten）**模型，将输入的字符序列转化为**基本单元序列**。  
这些基本单元构成了下一分析阶段的字母表。


## 2.2 语法分析



In der syntaktischen Analyse wird das zu übersetzende Programm auf seine Struktur hin untersucht. Es geht dabei um Beziehungen unter den Symbolen, die auch über unmittelbares Nebeneinanderstehen hinausgehen, z.B. Blockstruktur und Klammerstruktur von Ausdrücken. Diese Struktur wird mittels _kontextfreier Grammatiken_ beschrieben, die Analyse basiert auf dem Modell der _Kellerautomaten_. Die sematische Analyse umfasst z.B. Typüberprüfungen, die mittels anderer Konzepte und Methoden realisiert werden.

语法分析关注待翻译程序的**结构**，  
不仅考虑符号的相邻关系，还涉及更复杂的结构关系，例如：表达式的**块结构（Blockstruktur）**和**括号结构（Klammerstruktur）**。  
这种结构通常用**上下文无关文法（kontextfreie Grammatiken）**描述，  
语法分析基于**下推自动机（Kellerautomaten）**模型。



## 2.3 语义分析

语义分析包括例如**类型检查（Typüberprüfungen）**等，  
这些通常通过其他概念和方法来实现。






## 2.4 一般问题

Allgemein ist in diesen Analysephasen die Problematik enthalten, dass aus der unendlichen Menge aller Wörter über dem Alphabet diejenigen – i. Allg. auch unendlich vielen – Wörter erkannt werden müssen, die zu der betrachteten formalen Sprache gehören. Es sind also für die Spezifikation und Analyse unendlicher Sprachen endliche Repräsentationen zu finden. Mit dem Konzept der Grammatiken und den Automatenmodellen sind diese auch über die Übersetzung von Programmen einer Programmiersprache hinaus gegeben. 
Die Grammatiken stellen eine _generierende_ Sprachrepräsentation und  die Automaten eine _analysierende_ Sprachrepräsentation dar. Allerdings gibt es auch formale Sprachen, die sich nicht mittels solcher Repräsentationen darstellen lassen.


在这些分析阶段中，一个核心问题是：  
在字母表上所有可能的单词（通常是无限多）中，必须识别出属于目标形式语言的那些单词。  
因此，为了对无限语言进行规范和分析，必须找到**有限的表示方法（endliche Repräsentationen）**。

利用**文法（Grammatiken）**和**自动机模型（Automatenmodellen）**，可以实现这种有限表示，  
不仅限于程序语言的翻译。

- 文法提供了**生成型语言表示（generierende Sprachrepräsentation）**
- 自动机提供了**分析型语言表示（analysierende Sprachrepräsentation）**
    

然而，也存在一些形式语言，无法通过这些表示方法加以描述。


