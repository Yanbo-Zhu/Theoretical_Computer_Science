

Die regulären Sprachen sind bisher mittels endlicher Automaten definiert worden. Ein Wort gehört genau dann zu einer Sprache, wenn es von einem endlichen Automaten akzeptiert wird. In diesem Abschnitt werden nun Sprachen durch einen algebraischen Ansatz beschrieben, den _regulären Ausdrücken_. Ein regulärer Ausdruck definiert auch wieder eine Sprache, und es wird sich zeigen, dass dies genau die regulären Sprachen sind.

Reguläre Ausdrücke haben eine Vielzahl von Anwendungen in der Informatik, insbesondere in der Textverarbeitung, wenn es darum geht Zeichenfolgen zu finden oder diese zu ändern. Das Betriebssystem UNIX und die Programmiersprache PERL zum Beispiel stellen solche Methoden zur Verfügung. Auch Suchmaschinen im World Wide Web benutzen diese Techniken, um intelligente Suchanfragen zu ermöglichen.

Eine andere Anwendung kann in der Definition von Programmiersprachen und beim Entwurf von Compilern gefunden werden. Die elementaren Einheiten (Token) werden mittels regulärer Ausdrücke definiert. Es kann dann daraus ein Teil eines Compilers automatisch erzeugt werden, der Scanner oder auch der lexikalische Analysator. Die regulären Ausdrücke werden dazu in äquivalente endliche Automaten überführt, die genau diese elementaren Einheiten erkennen.

# 1 Reguläre Ausdrücke

![[Pasted image 20251109190645.png]]



Damit ist die syntaktische Form eines regulären Ausdrucks definiert. Seine semantische Definition bestimmt die durch ihn repräsentierte formale Sprache.

# 2 **Reguläre Sprache**


![[Pasted image 20251109190710.png]]


Die Auswertungsreihenfolge der auf reguläre Ausdrücke angewandten Operatoren orientiert sich an der Auswertungsreihenfolge der auf Sprachen angewandten Operatoren. Als erstes wird der Stern ausgewertet, dann die Konkatenation und als letztes die Vereinigung, wobei der Operator ∣ auch als _oder_ gesprochen wird. Soll von dieser Reihenfolge bei der Auswertung abgewichen werden, so ist ein regulärer Ausdruck entsprechend zu klammern. Äußere Klammern können auch entfallen. Der Operator ∣ wird häufig auch als + oder als ∪ geschrieben.

# 3 Äquivalenz  R1≡R2

Zwei reguläre Ausdrücke R1 und R2 über Σ heissen äquivalent, geschrieben R1≡R2, falls L(R1)=L(R2).

![[Pasted image 20251109190836.png]]


# 4 Beispiel

## 4.1 

![[Pasted image 20251109190943.png]]

## 4.2 

![[Pasted image 20251109190953.png]]

示例 [再次考虑DEA的字母表](https://vfhti.eduloop.de/loop/Deterministische_Endliche_Automaten "确定性有限自动机") ，它概述了使用有限自动机对词法分析器进行建模的方法。这些有限自动机分析的基本符号可以用正则表达式定义。

Ein Identifikator beginnt mit einem Buchstaben – auf Großbuchstaben sei hier verzichtet – und wird von keinem oder endlich vielen Buchstaben oder Ziffern gefolgt. Eine Längenbeschränkung von Identifikatoren gibt es bei dieser Definition nicht.

Eine ganze Zahl ohne Vorzeichen besteht aus einer oder endlich vielen Ziffern. Führende Nullen sind bei dieser Definition erlaubt. Eine Beschränkung des Wertebereichs – wie in Programmiersprachen im Allgemeinen üblich – ist mit dieser Definition nicht gegeben.

Das reservierte Wort for besteht aus der Konkatenation der Zeichen f, o und r.


标识符以字母开头（此处省略大写字母），后跟零个或有限个字母或数字。根据此定义，标识符的长度没有限制。

无符号整数由一位或有限位数字组成。此定义允许前导零。与编程语言通常的做法不同，此定义对取值范围没有任何限制。

保留字 for由以下字符连接而成 f， o 和 r。

## 4.3 

![[Pasted image 20251109191057.png]]

第一个标志 Σ是空格字符（ Blank），这是文字处理中始终需要的。需要注意的是，它与空词不同。

然而，在实际应用中，通常会使用不同的正则表达式表示方法。



# 5 Satz


## 5.1 Rechenregeln

![[Pasted image 20251109191121.png]]

![[Pasted image 20251109191131.png]]


![[Pasted image 20251109191242.png]]

Das letzte Beispiel zeigt insbesondere, dass die Konkatenation regulärer Ausdrücke nicht kommutativ ist.

Nachfolgend wird nun gezeigt, dass jede Sprache, die von einem endlichen Automaten erkannt werden kann, auch durch einen regulären Ausdruck dargestellt werden kann, und dass es zu jeder durch einen regulären Ausdruck repräsentierten Sprache auch einen endlichen Automaten gibt, der diese Sprache erkennt. Deterministische endliche Automaten, nichtdeterministische endliche Automaten und reguläre Ausdrücke definieren somit ein und dieselbe Sprachfamilie, die Klasse der regulären Sprachen.

最后一个例子特别表明，正则表达式的连接不满足交换律。

接下来将证明，任何能被有限自动机识别的语言都可以用正则表达式表示，并且对于每个能用正则表达式表示的语言，都存在一个能识别该语言的有限自动机。因此，确定性有限自动机、非确定性有限自动机和正则表达式定义了同一类语言：正则语言。


## 5.2 **Äquivalenz mit endlichen Automaten**

Eine Sprache ist genau dann regulär, wenn sie durch einen regulären Ausdruck repräsentierbar ist.


# 6 **Lemma reguläre Sprache**

## 6.1 Eine Sprache ist regulär, wenn sie durch einen regulären Ausdruck repräsentierbar ist.

**Beweis reguläre Sprache**

Sei ein regulärer Ausdruck R über dem Alphabet Σ gegeben. Es sind sechs Fälle zu betrachten, da ein regulärer Ausdruck nach Definition aus sechs verschiedenen Fällen aufgebaut sein kann. Für jeden Fall wird ein äquivalenter NEA konstruiert. Insgesamt ergibt sich damit ein NEA N, für den L(N)=L(R) gilt. Eine von einem NEA erkennbare Sprache ist auch von einem DEA erkennbar und somit regulär.

![[Pasted image 20251109192331.png]]

![[Pasted image 20251109192339.png]]


![[Pasted image 20251109192321.png]]


### 6.1.1 Beispiel 

Sei der reguläre Ausdruck a(a|b)* über dem Alphabet {a,b} gegeben.

![[Pasted image 20251109192403.png]]




## 6.2 Eine Sprache ist durch einen regulären Ausdruck repräsentierbar, wenn sie regulär ist.

  

beweis

Sei eine reguläre Sprache durch einen DEA gegeben. Die Konstruktion eines äquivalenten regulären Ausdrucks könnte dann z.B. durch sukzessive Elimination von Zuständen über so genannte _Generalisierte nichtdeterministische endliche Automaten_ erfolgen. Auf diese Konstruktion sei hier aber verzichtet. Sie kann in [[1]](https://vfhti.eduloop.de/loop/Regul%C3%A4re_Ausdr%C3%BCcke#cite_note-sip06-1) nachgelesen werden.

  

Zum Abschluss dieses Abschnitts soll noch einmal auf das Eingangsbeispiel zu den deterministischen endlichen Automaten eingegangen werden. Die durch diesen Automaten definierte Sprache ist natürlich auch durch einen regulären Ausdruck darstellbar.


![[Pasted image 20251109192440.png]]


