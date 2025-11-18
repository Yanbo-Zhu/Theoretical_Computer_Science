
# 1 #

![[Pasted image 20251117211151.png]]

Ordnen Sie den gegebenen regulären Ausdrücken die Wörter zu, die sie generieren.

```
0*11*0*
(0 | 1)*101(0 | 1)*                
(0 | 1)*00(0 | 1)*
```

# 2 #

![[Pasted image 20251117211414.png]]

选c 

解释：  
正则 `c*((bc*bc*)*(ac*ac*)*)` 表示：
- `c*`：任意数量的 `c`（可为 0 个）。
- `(bc*bc*)*`：每次重复都会产生 **两个** `b`（中间可夹若干 `c`），重复若干次 ⇒ **偶数个 b**；
- `(ac*ac*)*`：同理产生 **偶数个 a**（中间可夹若干 `c`），且这一段在 `b` 段之后。

因此整体语言是：**先出现偶数个 `b`，再出现偶数个 `a`，而 `c` 可以在任意位置出现**。


# 3 
![[Pasted image 20251117211516.png]]



Welche Sprachen werden von welchen regulären Ausdrücken generiert? Ordnen Sie den Sprachen die entsprechenden Regulären Ausdrücke zu. Mit "epsilon" wird das leere Wort bezeichnet.


L=  {w ∈ {a, b, c}* | w beinhaltet eine gerade Anzahl von b gefolgt von einer geraden Anzahl von a. Die c können beliebig an jeder Stelle vorkommen.}

L = {w ∈ {a, b, c}* | w besitzt keine  'b' oder in w kommen die  'b' nur paarweise vor. Die Wörter mit einem Teilwort bestehend aus mindestens 3 aufeinanderfolgenden b’s werden nicht akzeptiert. }

L=  {w ∈ {a, b, c}* | w enthält mindestens ein 'a' und mindestens ein 'b'}


在正则表达式（**Reguläre Ausdrücke**）里，  
符号 **“+”** 表示 **“或”（alternation / union）**。


# 4 

Welche Sprachen werden von welchen regulären Ausdrücken generiert? Ordnen Sie den Sprachen die entsprechenden Regulären Ausdrücke zu.



![[Pasted image 20251117212041.png]]

![[Pasted image 20251117212157.png]]


# 5 #

![[Pasted image 20251117212243.png]]



Wählen Sie eine Antwort:

Alle Wörter, die aus 0 oder mehreren a’s bestehen, gefolgt von 0 oder mehreren b’s gefolgt von 0 oder mehreren c’s.

Wörter, die eine gerade Anzahl von a gefolgt von einer geraden Anzahl von b enthalten. Das Zeichen c kann an beliebiger Stelle vorkommen.  选这个

Alle Wörter, die mit dem Zeichen c beginnen und dem Zeichen c enden. Dazwischen können beliebige Zeichen des Alphabets vorkommen.

Alle Wörter, die mit dem Zeichen c enden.


# 6 #

![[Pasted image 20251117212448.png]]


