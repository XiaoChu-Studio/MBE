# MBE
#### MBE is a new encryption method.
#### MBE 是一种新的加密方法。 

Based on a variant of the RSA algorithm, it has high security. As long as the key length is long enough, it is extremely difficult to crack. The size of prime numbers can be flexibly adjusted to control the encryption strength.

基于 RSA 算法的一种变体，它具有很高的安全性。只要密钥长度足够长，就极难被破解。质数的大小可以灵活调整以控制加密强度。

中文版 : README.md

1. Key generation
- Select two large prime numbers p and q, and calculate n = p * q.
- Choose an integer e that satisfies 1 < e < φ(n), where φ(n)=(p - 1)*(q - 1), and e is coprime to φ(n).
- Calculate d such that d * e ≡ 1 (mod φ(n)).
- The public key is (n, e), and the private key is (n, d).
2. Encryption process
- Convert plaintext into a sequence of numbers, for example, using ASCII code values.
- For each number m (plaintext number), calculate the ciphertext c = m^e mod n.
3. Decryption process
- For each ciphertext number c, calculate the plaintext m = c^d mod n.
----
eg:
The ASCII code values corresponding to each character of “Hello, world!” are: 72, 101, 108, 108, 111, 44, 32, 119, 111, 114, 108, 100, 33.
Encryption process:
- For each number m (plaintext number), calculate the ciphertext c = m^e mod n.
- Taking the number 72 corresponding to the first character “H” as an example, the encrypted ciphertext is 72^17 mod 3233 = 2001.
- Encrypt each character in turn.
----
1. Key management is extremely important, and the private key must be strictly confidential.
2. In practical applications, performance optimization needs to be considered, especially for the encryption and decryption of large amounts of data.
