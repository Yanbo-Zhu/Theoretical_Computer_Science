
# 1 

![](image/Pasted%20image%2020251205160907.png)


![](image/Pasted%20image%2020251205161018.png)


q0 = standard zustand
{L,R} schreibekpf , nach links oder rechte 


![](image/Pasted%20image%2020251205161204.png)


## 1.1 Beispiel

![](image/Pasted%20image%2020251205161349.png)


# 2 Algorithmus, Intuitiv 

![](image/Pasted%20image%2020251205161438.png)

![](image/Pasted%20image%2020251205161520.png)


# 3 Funktion berechenbar 

![](image/Pasted%20image%2020251205161619.png)


# 4 Turing-berechenbar 

![](image/Pasted%20image%2020251205161648.png)


## 4.1 


![](image/Pasted%20image%2020251205161732.png)


![](image/Pasted%20image%2020251205161816.png)


diese Ziffer = letzte Ziffer. 


## 4.2 

![](image/Pasted%20image%2020251205161956.png)

`0 -> _, R`
wenn wir 0 haben unter schreibekopf, dann ersetzt 0 durch black, dann schreibkopf nach rechte verscheiben 



S-> T 
![](image/Pasted%20image%2020251205162255.png)


blank = nichts 

---

T-> R 

![](image/Pasted%20image%2020251205162403.png)


---

S-> E

![](image/Pasted%20image%2020251205162517.png)

![](image/Pasted%20image%2020251205162525.png)

![](image/Pasted%20image%2020251205163013.png)


---

B -> C 


![](image/Pasted%20image%2020251205163250.png)


![](image/Pasted%20image%2020251205163416.png)


S, 0 unter Schreibekopf, nach Zustand T welchen , schreibt T unter 0,  schreibkopft nach rehcte verschieben , 

![](image/Pasted%20image%2020251205163734.png)



![](image/Pasted%20image%2020251205163821.png)

S-> 1 -> blank -> E 
uberschreibt 1 mit blank 


![](image/Pasted%20image%2020251205164118.png)


am Ende lesekopf 1 zuweisen ,   左边的  black不被读取了，   从1 开始读 10100 


akzeptierenhalt:  berechen zu Ende,  Endezustand ist .   


T_ink. : Turingmachine mit incrtement Function 


# 5 Berechenbarkeit 


![](image/Pasted%20image%2020251205164829.png)



