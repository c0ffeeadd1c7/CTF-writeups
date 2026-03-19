---
title: The pink dog (100)
category: forensics
points: "100"
solved: no
description:
---
Running the file command reveals that the file is a zip.  
Inside there are pictures of memes and one jgpeg image that cannot be opened for some reason.  
  
Opening the flag.dog image in a hex editor reveals that there are 3 jfif image headers.  
![Pasted image 20240531190532.png](/assets//Pasted%20image%2020240531190532.png)  
Removing these bytes with dd gives us an image that can be opened  
`dd if=flag.dog of=out.jpeg bs=1 skip=308`  
  
  
![out.jpeg](/assets/out.jpeg)  
Flag is:  
`Trojan{i_tH0uGhT_hIs_nAm3_wAS_STup1d_d0g}`