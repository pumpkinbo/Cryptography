<i>

# ***Semantic Security(语义安全性)***

- 完善保密性：唯密文攻击下的安全性定义
- 语义安全性：选择明文攻击下的定义


## 安全模型

攻击者选择两条明文m0,m1发送给挑战者，挑战者返回给攻击者一条密文，但并不知道是哪个明文加密而成的。攻击者通过密文猜测挑战者加密了哪条明文（做了哪个实验）,攻击者输出b，b为0表示猜测挑战者做了实验0(加密了m0)，反之为1。

攻击者优势：
<b>

Adv:=|Pr[W0] - Pr[W1]|

for b=0,1: Wb := [event that EXP(b)=1]

</b>

[安全模型图片](https://ibb.co/HFyk50n)

注意，攻击者只能询问挑战者一次，即只能向挑战者发送一次明文来获取密文信息。


## 语义安全性定义：

设(E,D)是定义在(K,M,C)上的对称加密方案，如果所有高效攻击者A在语义安全性的安全模型中的优势都是可忽略的，那么(E,D)是语义安全的。

即：对于所有高效攻击者选择的等长明文m0,m1 $\in $ M,加密后形成的密文在计算上是不可区分的。

[公式](https://ibb.co/L6gSS1X)

注意与完善保密性的区分：
[完善保密性](https://ibb.co/f9Hx9VX)

</i>