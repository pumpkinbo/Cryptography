<i>

# **PRG Security Definition**

[Coursera课程视频](https://www.coursera.org/learn/crypto/lecture/De10M/prg-security-definitions)


流加密不具有完善保密性，对于伪随机发生器***PRG***的安全性有专门的定义。

密钥的随机性影响了加密算法的安全性。PRG产生的密钥是伪随机的，所以要通过某种方法量化G(K)与真随机之间的差距。

- ## **Statistical Tests(统计性检验)**

<b>

Statistical test on $ {0,1} ^n $:

an algorithm A s.t. A(x) outputs "0" or "1"

</b>

实际上就是检验函数A(x)，若输入 $ {0,1}^n $上的序列是随机的，则输出1，否则输出0。

判断随机的方法有很多：

[example of statistical tests](https://ibb.co/mJH9nwd)

[example of statistical tests](https://ibb.co/hRZTdg8)

- ## **Advantage(优势)**
<b>

Let G: K ——> $ {0,1}^n $ be a PRG and A a stat. test on $ {0,1} ^n $

Define:

Advantage of PRG = |Pr[A(G(k))=1] - Pr[A(r)=1]|

</b>

r为 $ {0,1}^n $ 上的真随机序列。

<b>

当Adv接近1时，说明检测函数A(x)可以区分伪随机与真随机，so the PRG is weak.

当Adv接近0，说明检测函数A(x)不能区分伪随机与真随机，so the PRG is good.

</b>

<b>

- ## **PRG Security Definition**
<b>

如果G是一个安全的PRG，那么在PRG的安全模型中，所有高效攻击者的优势

Adv:=|Pr[A(G(k))] - Pr[A(r)]|
都是可忽略的。

</b>


- ## 姚期智定理：
an unpredictable PRG is secure

Let G: K——> ${0,1}^n$ be PRG

"Thm": if $\forall i \in {0,1...,n-1} $ PRG G is unspredictable at position i then G is a secure PRG. 

</b>
</i>
