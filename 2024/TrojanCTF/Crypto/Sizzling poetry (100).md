---
category: crypto
description: PDF poem bacon's chiper
points: "100"
---
Instructions were:
```
Dear Publisher,

Please find attached my poem simply about my favorite things in life. I expect you to publish it in your magazine soon. For some reason my keyboard was acting up, so please remove the bold letters from the final draft.

Best, Poet McGee

Flag Format: Trojan{Secret Message}
```
![Pasted image 20240529013031.png](/assets/Pasted%20image%2024052901303.png)
The poem is a hint to Bacon, and there also exists a Bacon(ian) chiper. HMMM.
In the [Bacon chiper](https://en.wikipedia.org/wiki/Bacon's_cipher?oldformat=true|) the message is binary encoded in the typeface of the letters and after considering every non bold letter as a-s and every bold letter as b-s we get:
```txt
aa a abaaaaaa aabaa bbaba bbaabaa aaabb, 
abaaa baab a abba, a ababa bbbabba.
baaababbaba, aabaa baabb'a aab abba,
ba ababa ababaa, aaa aaaaaaa aaaa.
```
Decoding this with the bacon alphabet using [cyberchef](https://cyberchef.org/#recipe=Bacon_Cipher_Decode%28'Standard%20%28I%3DJ%20and%20U%3DV%29','A/B',false%29&input=YWEgYSBhYmFhYWFhYSBhYWJhYSBiYmFiYSBiYmFhYmFhIGFhYWJiLCAKYWJhYWEgYmFhYiBhIGFiYmEsIGEgYWJhYmEgYmJiYWJiYS4KYmFhYWJhYmJhYmEsIGFhYmFhIGJhYWJiJ2EgYWFiIGFiYmEsCmJhIGFiYWJhIGFiYWJhYSwgYWFhIGFhYWFhYWEgYWFhYS4) and we get:
`BACONROCKSMYSOCKSOFFAAA`
So the flag is:
`Trojan{BACONROCKSMYSOCKSOFF}`
