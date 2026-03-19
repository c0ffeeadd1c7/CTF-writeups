---
title: Hellman key exhange (100+100)
category: crypto
description: Hellman key exchange with small primes
points: "100"
---
Two images were given:

![GiosPublic.png](/assets/GiosPublic.png)
![TonysPublic.png](/assets/TonysPublic.png)


Source wikipedia Diffie Hellman key exchange
![Pasted image 20240529010102.png](/assets/Pasted%20image%2020240529010102.png)

We have:  
$$
\begin{align}
p = 12611 && g=577 \\
\\
A = 6030 && B = 8354
\end{align}
$$  
now the secret is equal to the following:  
$$
\begin{align}
A =& 577^{a} \bmod 12611 =& 6030 \\
B =& 577^{b} \bmod 12611 =& 8354 \\
s =& A^{b} \bmod 12611 =& B^{a} \bmod 12611 \\
\end{align}
$$  
wrote simple python brute force script:  
```python
key1 = 6030
key2 = 8354

p = 12611
g = 577

for i in range(1,p):
	if (g**i) % p == key1:
		print(i)
		break

print((key1 ** i) % p)
```

From that I've got 690 and 5661 from which the later is was the flag.

Same kind of challenge was the Skinwalk where this was given:
Tony's public key: `5433773864651 (p,g) = (6123584726269,12)`

These numbers are also quite small therefore I've used the same script and the results were:
```
1235
5095651008733
```
from which the 1235 was the flag.