

# 1 Reguläre Sprachen und Operationen

Formale Sprachen – selbst Mengen – lassen sich wieder zu Mengen zusammenfassen, so genannten _Sprachfamilien_ bzw. _Klassen_ von Sprachen. Die von endlichen Automaten erkennbaren Sprachen bilden somit eine Sprachfamilie, die Sprachfamilie der _regulären Sprachen_. Dieser Name bekommt über die durch _reguläre Ausdrücke_ definierten Sprachen seine Rechtfertigung. Zunächst aber wird die Sprachfamilie der regulären Sprachen mittels endlicher Automaten definiert und es werden weiterhin die _regulären Operationen_ eingeführt und diskutiert.

**Reguläre Sprache**
Eine Sprache heisst **reguläre Sprache**, falls es einen endlichen Automaten gibt, der diese Sprache erkennt. Die Sprachfamilie oder Klasse der regulären Sprachen wird mit $L_{reg}$ bezeichnet.


**Reguläre Operationen**
Seien A und B Sprachen. Die regulären Operationen Vereinigung, Konkatenation und Stern (Kleeneabschluss) werden dann wie folgt definiert:
![[Pasted image 20251109185422.png]]

![[Pasted image 20251109185434.png]]

![[Pasted image 20251109185445.png]]



# 2 Abschlusseigenschaften der regulären Operationen



Es folgen drei Sätze zu den Abschlusseigenschaften der regulären Operationen (Vereinigung, Konkatenation, Stern), jeweils mit einer Beweisidee. 

## 2.1 **Vereinigung regulärer Sprachen**

Die regulären Sprachen sind unter der Operation Vereinigung abgeschlossen.

Die Abgeschlossenheit bedeutet hier: Vereinigt man eine reguläre Sprache A1 mit einer anderen regulären Sprache A2, dann ist das Ergebnis A=A1∪A2 wieder eine reguläre Sprache. Gemäß [obiger Definition (Reguläre Sprache)](https://vfhti.eduloop.de/loop/Regul%C3%A4re_Sprachen_und_Operationen#def_RegSprache) muss eine reguläre Sprache durch einen endlichen Automaten erkennbar sein, was zu folgendem Beweis des Satzes führt:


![[Pasted image 20251109185649.png]]

![[Pasted image 20251109185700.png]]

## 2.2 **Konkatenation regulärer Sprachen**

Die regulären Sprachen sind unter der Operation Konkatenation abgeschlossen.

Die Abgeschlossenheit bedeutet hier: Konkateniert man eine reguläre Sprache A1 mit einer anderen regulären Sprache A2, dann ist das Ergebnis A=A1⋅A2 wieder eine reguläre Sprache. Gemäß [obiger Definition (Reguläre Sprache)](https://vfhti.eduloop.de/loop/Regul%C3%A4re_Sprachen_und_Operationen#def_RegSprache) muss eine reguläre Sprache durch einen endlichen Automaten erkennbar sein, was zu folgendem Beweis des Satzes führt:


![[Pasted image 20251109185721.png]]


![[Pasted image 20251109185742.png]]


## 2.3 Operation Stern auf regulärer Sprachen

Die regulären Sprachen sind unter der Operation Stern abgeschlossen. 

Die Abgeschlossenheit bedeutet hier: Wendet man den Stern-Operator auf eine reguläre Sprache A1 an, dann ist das Ergebnis A=(A1)* wieder eine reguläre Sprache. Gemäß [obiger Definition (Reguläre Sprache)](https://vfhti.eduloop.de/loop/Regul%C3%A4re_Sprachen_und_Operationen#def_RegSprache) muss eine reguläre Sprache durch einen endlichen Automaten erkennbar sein, was zu folgendem Beweis des Satzes führt:


![[Pasted image 20251109185802.png]]


![[Pasted image 20251109185826.png]]

### 2.3.1 Example

Es folgen drei Beispiele mit der Anwendung der drei Beweisideen. Dazu werden zunächst zwei konkrete nichtdeterministische endliche Automaten N1 und N2 gegeben (a), diese erkennen jeweils die reguläre Sprache L(N1) bzw. L(N2):

![[Pasted image 20251109185848.png]]


![[Pasted image 20251109185859.png]]

![[Pasted image 20251109185907.png]]


![[Pasted image 20251109185914.png]]




