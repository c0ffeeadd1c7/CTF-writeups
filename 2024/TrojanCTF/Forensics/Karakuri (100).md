---
title: Karakuri (100)
category: forensics
points: "100"
description: least significant bit modification
---
![karakuri-puzzle.png]({{ site.baseurl  }}/assets/karakuri-puzzle.png)
Zooming in a faintly a part of the flag can be found. Turns out the least significant bit contains another image.  
  
That image can be obtained fairly easily by a python script:  
```python
from PIL import Image

im = Image.open("karakuri-puzzle.png") 
out = Image.new("RGBA", (600, 600))  

for y in range(600):     
	for x in range(600):         
		r, g, b, a = im.getpixel((x, y))
		color = (r & 1) * 255
		out.putpixel((x, y), (color, color, color))
		
out.save("out.png")
```  
or  using an online tool like the amazing website [aperisolve](https://www.aperisolve.com/)  
![Pasted image 20240529155430.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240529155430.png)  
`Trojan{puSH_iT_ShAKe_It_rOtaTe_IT}`