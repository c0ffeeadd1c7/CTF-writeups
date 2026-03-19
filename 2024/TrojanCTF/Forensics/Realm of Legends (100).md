---
title: Realm of Legends (100)
category: forensics
points: "100"
solved: no
description: PCAP export
---
Running the file command on the given log file reveals that it is a pcap network log file.  
Im using wireshark to go through it. Filtering for http requests unveils 2 particular requests that include zip files.  
![Pasted image 20240601161040.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240601161040.png)  
Exporting the zip file 1.4.10 from the request at the FILE > EXPORT OBJECT > 1.4.10.zip  
  
![Pasted image 20240601161121.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240601161121.png)  
  
Extracting the zip file gives us a game. Running it reveals the flag:  
  
![Pasted image 20240601144614.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240601144614.png)
`Trojan{H4ha_3XaCtlY_A5_tHE_tiTl3_5aiD}`