

Es bleiben die im Abschnitt [Alphabete, Wörter, Sprachen](https://vfhti.eduloop.de/loop/Alphabete,_W%C3%B6rter,_Sprachen "Alphabete, Wörter, Sprachen") eingeführten Begriffe auf konkrete Programmiersprachen zu übertragen. Dies erfolge hier am Beispiel der Programmiersprache _Java_.


![](image/Pasted%20image%2020251031172158.png)



程序的翻译——在这里指的是对基于某个字母表的单词——通常要经过三个分析阶段，然后才进行真正的目标代码生成：

1. **词法分析（lexikalische Analyse）**
    
2. **语法分析（syntaktische Analyse）**
    
3. **语义分析（semantische Analyse）**


# 1 词法分析

词法分析的任务是识别程序中的**基本单元（elementare Einheiten, Token）**，例如：标识符（Identifikatoren）、数字、关键字、运算符、分隔符等。  
这些基本单元是由字母表中**相邻的字符**组成的。  
它们可以通过**正则表达式（reguläre Ausdrücke）**进行描述。  
词法分析基于**有限自动机（endliche Automaten）**模型，将输入的字符序列转化为**基本单元序列**。  
这些基本单元构成了下一分析阶段的字母表。


# 2 语法分析

语法分析关注待翻译程序的**结构**，  
不仅考虑符号的相邻关系，还涉及更复杂的结构关系，例如：表达式的**块结构（Blockstruktur）**和**括号结构（Klammerstruktur）**。  
这种结构通常用**上下文无关文法（kontextfreie Grammatiken）**描述，  
语法分析基于**下推自动机（Kellerautomaten）**模型。



# 3 语义分析

语义分析包括例如**类型检查（Typüberprüfungen）**等，  
这些通常通过其他概念和方法来实现。




# 4 一般问题

在这些分析阶段中，一个核心问题是：  
在字母表上所有可能的单词（通常是无限多）中，必须识别出属于目标形式语言的那些单词。  
因此，为了对无限语言进行规范和分析，必须找到**有限的表示方法（endliche Repräsentationen）**。

利用**文法（Grammatiken）**和**自动机模型（Automatenmodellen）**，可以实现这种有限表示，  
不仅限于程序语言的翻译。

- 文法提供了**生成型语言表示（generierende Sprachrepräsentation）**
    
- 自动机提供了**分析型语言表示（analysierende Sprachrepräsentation）**
    

然而，也存在一些形式语言，无法通过这些表示方法加以描述。