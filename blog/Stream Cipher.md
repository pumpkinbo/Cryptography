# Stream Cipher(流密码)

### [Coursera课程视频](https://www.coursera.org/learn/crypto/lecture/5m8ay/stream-ciphers-and-pseudo-random-generators)

由于OTP加密技术中存在密钥长度冗余，难以实现的问题，可采用 ***stream cipher*** 。

OTP中的密钥是完全随机的，因此具有完美安全性。而流密码中的密钥是伪随机的，核心是 ***PRG（Pseudo-Random-Generator）***,伪随机发生器可以广义地将其理解为一个函数 ***G()***，输入为随机的种子(较少位数的二进制位)，而输出即为有较多位数的伪随机密钥 ***G(seed)*** 。

密文***C=E(m,G(seed))***，其中加密算法E仍为***异或操作***，由于stream cipher中***密钥长度是小于明文长度***，根据***Shannon***理论，该加密技术不具有完美安全性。

需要注意的是：***PRG必须具有不可预测性***。

可预测性是指，可以找到一个算法A，在已知密钥***G(seed)*** 的前 ***i*** 位，可以计算出第***i+1***位。由于一些预置知识，攻击者可能会知道信息某些前缀部分的最初明文内容(如因特网电子邮件标准协议之一SMTP，这个协议中每条信息都以***from***;开头，这就是攻击者知道的明文前缀)。攻击者可将该明文内容与密文相异或得到密钥的一些前缀，再根据PRG的可预测性破解密码。

因此***PRG***必须具有不可预测性才能保证加密的安全。

下面是一些 ***Weak PRGs***(可预测的),不要在加密时使用他们!

1. ***线性同余***

    ***r[0] = seed*** 

    ***r[i] = a * r[i-1] + b (mod p)***

2. ***GNU C Library函数库***

    [***glibc random***](https://ibb.co/jr1TJSX)

    第四版的***Kerberos系统***就是由于用了该可预测函数被破解。

