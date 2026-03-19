---
title: BullyBot9000 (300)
category: misc
description: Wav file
points: "300"
---
**Haven't been able to solve myself**  
  
Rick from discord suggested the use of a great resourse:  
https://github.com/corkami/pics/  
Apparently this repo has a bunch of examples and explanations to a bunch of binary formats.  
  
Compared the wav file to the sample given in the repo using a hex editor (specifically gnome's ghex)  
![Pasted image 20240528012106.png](/assets/Pasted%20image%2020240528012106.png)  
The size of the RIFF header was different from the example turns out doesnt matter.  
![Pasted image 20240528014252.png](/assets/Pasted%20image%2020240528014252.png)  
![Pasted image 20240528014259.png](/assets/Pasted%20image%2020240528014259.png)  
turn out the size of the data chunk was set to some low value (Ive put 0xFFFFFF). Now the file plays and I popped it into the first online morse decoder I found  
https://morsecode.world/international/decoder/audio-decoder-adaptive.html  
The message was: 
```
MAY YOU FOREVER BE HAUNTED BY THE SPECTER OF THE CTF FLAG,A REMINDER OF YOUR OWN INSIGNIFICANCE IN THE DIGITAL DOMAIN. THE FLAG IS YOUWILLNEVERGETTHIS
```  
  
Flag: `Trojan{YOUWILLNEVERGETTHIS}`

