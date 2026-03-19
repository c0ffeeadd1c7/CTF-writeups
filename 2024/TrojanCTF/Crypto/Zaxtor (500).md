---
title: Zaxtor (500)
category: crypto
description: CBC padding oracle attack
points: "500"
solved: no
---
Yannik from discord explained that this challange is in essense a CBC paddding oracle attack.
But what is a padding oracle attack? [Wikipedia states](https://en.wikipedia.org/wiki/Padding_oracle_attack?oldformat=true):  
The attack relies on having a "padding oracle" who freely responds to queries about whether a message is correctly padded or not.  
HMM. That sound like our target.  
  
I know what padding is I think. It's when the input is too short but the cryptographic function expects a certain lenght in bytes, and the missing gets appended aka padded.  
Padding is described:  
In cryptography, **padding** is any of a number of distinct practices which all include adding data to the beginning, middle, or end of a message prior to encryption. In classical cryptography, padding may include adding nonsense phrases to a message to obscure the fact that many messages end in predictable ways, e.g. _sincerely yours_.  
  
As I understand it to apply padding you have to extend the data in such a way that the decryption or depadding part knows how many bytes and where those bytes were padded. Essentially meaning that the padding has to include the length of it self somehow.  
  
![Pasted image 20240529115439.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240529115439.png)  
The challenge uses CBC encryption.  
![Pasted image 20240529115553.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240529115553.png)  
Wikipedia says:  
The standard implementation of CBC decryption in block ciphers is to decrypt all ciphertext blocks, validate the padding, remove the [PKCS7 padding](https://www.wikiwand.com/en/Padding_(cryptography)#PKCS#5_and_PKCS#7 "Padding (cryptography)"), and return the message's plaintext. If the server returns an "invalid padding" error instead of a generic "decryption failed" error, the attacker can use the server as a padding oracle to decrypt (and sometimes encrypt) messages.  
PKCS7 Padding: one of the below  
```
01
02 02
03 03 03
04 04 04 04
05 05 05 05 05
06 06 06 06 06 06
etc.
```  
![Pasted image 20240529115850.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240529115850.png)  
  
We know from the code that the iv is just 16 bytes of 0. The ciphertext is 32 bytes long.  
Therefore we have 2 blocks of ciphertext:  
`5fc976d76c175f5c4f0d71944a3c17df8be81a4a599825815bdd935284581ee5`  
Split it to 16 bytes:  
```
5fc976d76c175f5c4f0d71944a3c17df
8be81a4a599825815bdd935284581ee5
```  
Therefore we can modify the bytes in block 1 to get a sense wether the padding at the end of block2 decrypts corrrectly. If we change the last byte in block1 and block2 decrypt correctly we now know that the modified block1 ^ plainblock2 is equal to the padding value, meaning we once we know the padding size we know at least a few bytes of block2 plaintext. We can walk through the bytes and ensure that the last bytes are equal to the padding values and this way we now the padding size and value.  
  
So to make it clear, first step is to force the plaintext of the block we are trying to decrypt to have a padding of 1 meaning the last byte is 0x01. That way we can compute the decrypted last bit of the block by xor ing the 0x01 and the byte that we chaged to get the right padding. Now that we know the decrypted byte we can compute the original plaintext byte by xoring the known decrypted byte with the original byte of the other block.  
  
Geat explainer video found here: https://www.youtube.com/watch?v=4EgD4PEatA8  
  
Once the script was done Yannik made use of the [pwntools](https://pypi.org/project/pwntools/) python library to run the script against the live server.  
  
`Alien Zaxtor Say Trojan{1_<3_U}` was the message  