
Nach der Einführung und Definition der regulären Sprachen gilt es, einige ihrer Eigenschaften zu untersuchen. So werden hier Abschlusseigenschaften einiger Operationen und eine notwendige, aber leider nicht hinreichende, Eigenschaft betrachtet, die “Pump”-Eigenschaft. Im Abschnitt [Reguläre Sprachen und Operationen](https://vfhti.eduloop.de/loop/Regul%C3%A4re_Sprachen_und_Operationen "Reguläre Sprachen und Operationen") ist bereits die Abgeschlossenheit der regulären Operationen Vereinigung, Konkatenation und Stern (Kleeneabschluss) gezeigt worden. Insbesondere diese hätten auch zur Definition der regulären Sprachen herangezogen werden können. Nach dem so genannten _Satz von Kleene_ ist die kleinste Sprachfamilie über Σ, die unter Vereinigung, Konkatenation und Stern abgeschlossen ist und die Sprachen ∅, {ϵ} und {a} mit a∈Σ enthält, die der regulären Sprachen.

Die weiteren hier betrachteten Operationen und Probleme werden alle abgeschlossen sein. Aber es gibt auch nichtreguläre Sprachen, für die diese Aussagen nicht mehr bzw. nur noch eingeschränkt gelten. Zum Nachweis, dass eine Sprache nicht regulär ist, kann das so genannte _Pumping Lemma_ herangezogen werden. Es charkterisiert eine Eigenschaft regulärer Sprachen, die dann nicht mehr vorhanden ist.

Für Sprachen sind neben den regulären Operationen (Definition [Reguläre Operationen](https://vfhti.eduloop.de/loop/Regul%C3%A4re_Sprachen_und_Operationen "Reguläre Sprachen und Operationen")) auch die Operationen Komplement und Durchschnitt von Interesse (Definition [Weitere Operationen](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen#def_WeitOperations)).

# 1 Weitere Operationen： **Durchschnitt** and Komplement

Seien A und B Sprachen über dem Alphabet Σ. Die Operationen Durchschnitt und Komplement werden dann wie folgt definiert:


![[Pasted image 20251109193227.png]]

Komplement
Es sei L eine reguläre Sprache über dem Alphabet Σ. Dann ist auch L‾ eine reguläre Sprache.


Durchschnitt
Es seien L1 und L2 reguläre Sprachen. Dann ist auch L1∩L2 eine reguläre Sprache.


![[Pasted image 20251109193256.png]]

Der Satz [Durchschnitt](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen#satz_RASchnitt) kann natürlich auch konstruktiv über endliche Automaten bewiesen werden. Dies soll hier aber nicht erfolgen.

Zum Abschluss dieses Abschnitts wird eine Eigenschaft regulärer Sprachen betrachtet, deren Fehlen zum Nachweis für die Nichtregularität einer Sprache verwendet wird (Satz [Pumping Lemma](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen#satz_RAPumpL)). In dem sich daran anschließenden Beispiel [Beispiel nichtregulärer Sprache](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen#bsp:AnwPL2) wird dann eine nichtreguläre Sprache spezifiziert. Es gibt also Sprachen, die nicht regulär sind.

# 2 **Pumping Lemma**

Das Pumping Lemma für unendliche reguläre Sprachen beschreibt die Eigenschaft, dass alle Wörter einer unendlichen regulären Sprache mit einer （ bestimmten ) Mindestlänge in ( drei ) Teilworte zerlegt werden können, so dass alle durch (( Zufügen ) oder Wiederholen („Pumpen“) des Mittelteils entstehenden Wörter ( auch ) zur Sprache gehören.

![[Pasted image 20251109193358.png]]


如果一个语言是正则的，那么它就像一个可以无限“拉伸”的弹簧。  
某个部分（中间段 y）可以被**重复（pump）**任意次数，  
而不会使结果跑出这个语言。

抽引引理说明：  
在任意一个无限的正则语言中，长度足够长的字符串都包含某个可重复的片段，  
这个片段可以被“抽引”（重复任意次）而仍保持在该语言中。



**1️⃣ 句意：**

> 对于无限的正规语言（unendliche reguläre Sprache），  
> 抽引引理（Pumping Lemma）描述了这样一个性质：

**👉 中文解释：**  
对于所有无限的正则语言，都存在某种“重复结构”。

---

**2️⃣ 句意：**

> 所有长度超过某个最小值的单词（即字符串）  
> 都可以被分成三个部分。

**👉 中文解释：**  
存在一个最小长度 **p（称为“抽引长度” pumping length）**，  
只要一个字符串 www 的长度 ≥ p，  
就可以分成：

w=xyzw = xyzw=xyz

其中 x,y,zx, y, zx,y,z 是三个子串。

---

**3️⃣ 句意：**

> 通过添加或重复中间部分（即“抽引”部分）所得到的所有单词  
> 也都属于这个语言。

**👉 中文解释：**  
不管你把中间部分 yyy 重复多少次（包括 0 次、1 次、2 次……），  
生成的新串：

xyiz,i=0,1,2,…xy^i z, \quad i = 0, 1, 2, \dotsxyiz,i=0,1,2,…

都仍然属于这个正则语言。



![[Pasted image 20251109195833.png]]

## 2.1 Beweis Pumping Lemma

![[Pasted image 20251109193132.png]]

![[Pasted image 20251109193142.png]]


## 2.2 Beispiel

![[Pasted image 20251109193151.png]]

![[Pasted image 20251109193159.png]]

# 3 Es gibt Sprachen, die nicht regulär sind. 

Die Sprache {aibi∣i∈ℕ0} ist nicht regulär (Beispiel [Beispiel nichtregulärer Sprache](https://vfhti.eduloop.de/loop/Eigenschaften_Regul%C3%A4rer_Sprachen#bsp:AnwPL2)).

![[Pasted image 20251109193111.png]]

