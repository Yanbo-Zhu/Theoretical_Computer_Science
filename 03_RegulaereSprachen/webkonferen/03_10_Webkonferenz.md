

# 1 Webkonferenz 07.11.2025: Regulaere Ausdrueck 


![[Pasted image 20251107160434.png]]

![[Pasted image 20251107160712.png]]

nur ` |, (). *, .(mal punkt)`  这四个 符号 被允许 
## 1.1 Example 

1 
a (a|b)*  =  
- **`a`**：字符串必须以字母 `a` 开头；
    
- **`(a|b)`**：表示可以是 `a` 或 `b`；
    
- **`(a|b)*`**：表示后面可以跟零个或多个 `a` 或 `b`；
    
- 整体含义：  
    👉 匹配 **以 `a` 开头，后面可以跟任意数量的 `a` 或 `b`** 的字符串。

![[Pasted image 20251107161215.png]]



2 
(ab)* 



3 
(0|1)* 1 (1|0)*



4 
![[Pasted image 20251107161718.png]]

Selta = {a,b}
L(R) = {w | w hat ungerade länge}

使用 
`((a∣b)(a∣b))*`

5 
![[Pasted image 20251107162607.png]]
Selta = {a,b}
Woertern, die mit "a" bequem und mit "b" enden


使用 
`a(a∣b)*b`


6 
Woertern, in denen nach jedem a sofort ein b folgt, 

(b|ab)*

![[Pasted image 20251107163316.png]]

![[Pasted image 20251107163618.png]]


7 
![[Pasted image 20251107164218.png]]


w= {0,1}
das drittletzte Symbol von w ist eine 1 
要描述 “w 的倒数第三个符号是 1”（即从右数第三个是 1） 的正则表达式（字母表 Σ = {0,1}）是：
`(0|1)*1(0|1)(0|1)`



8 

L := {w| w enthält mindestens ein a und mindestens b.  }

`(a|b)*a(a|b)*b(a|b)* | (a|b)*b(a|b)*a(a|b)*`

![[Pasted image 20251107165624.png]]


9
baaaaa
![[Pasted image 20251107170048.png]]



