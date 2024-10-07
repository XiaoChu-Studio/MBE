# MBE
#### MBE is a new encryption method.
#### MBE 是一种新的加密方法。 

Based on a variant of the RSA algorithm, it has high security. As long as the key length is long enough, it is extremely difficult to crack. The size of prime numbers can be flexibly adjusted to control the encryption strength.

基于 RSA 算法的一种变体，它具有很高的安全性。只要密钥长度足够长，就极难被破解。质数的大小可以灵活调整以控制加密强度。

English version : README-EN.md

          
1. 密钥生成
 
- 选取两个大素数 p 和 q，计算 n = p * q。
- 选择一个整数 e，满足 1 < e < φ(n)，其中 φ(n)=(p - 1)*(q - 1)，且 e 与 φ(n)互质。
- 计算 d，使得 d * e ≡ 1 (mod φ(n))。
- 公钥为(n, e)，私钥为(n, d)。

2. 加密过程
 
- 将明文转换为数字序列，比如使用 ASCII 码值。
- 对于每个数字 m（明文数字），计算密文 c = m^e mod n。

3. 解密过程
 
- 对于每个密文数字 c，计算明文 m = c^d mod n。
----
eg:
“Hello, world!”每个字符对应的 ASCII 码值分别为：72、101、108、108、111、44、32、119、111、114、108、100、33。
加密过程：
- 对于每个数字 m（明文数字），计算密文 c = m^e mod n。
- 以第一个字符“H”对应的数字 72 为例，加密后的密文为 72^17 mod 3233 = 2001。
- 依次对每个字符进行加密。

----
1. 密钥的管理至关重要，私钥必须严格保密。
2. 在实际应用中，需要考虑性能优化，尤其是对于大量数据的加密和解密。

