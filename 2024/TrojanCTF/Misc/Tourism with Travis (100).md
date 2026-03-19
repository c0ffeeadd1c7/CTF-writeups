---
title: Tourism with Travis (100)
category: misc
description: Google maps image reversing to address
points: "100"
---
Flag format `Trojan{City, Street, Year}`.  
Simple task: find the address and year of the google maps image.  
![Holiday_picture.png]({{ site.baseurl  }}/assets/Holiday_picture.png)  
  
I first tried google's reverse image search feature however the no meaningful result were found.  
Not sure if tools exist for this, I would guess as of right now not really, and my reasoning is that GeoGuessr would be full of people using it.  
This remains the not so simple task of finding the location.  
  
Thought process:  
In this case it's obvious right away that it it New York based on the taxi.  
Traffic lights are american.  
Signs suggest W 30th st??  
OHH is that the empire state building? Whoops maybe i should have realized that right away.  
Let's see on google maps:  
![Pasted image 20240528005332.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240528005332.png)
You can also see the shadows on the picture, and based on that you know that north is to the left ish from the pov of the picture, and google maps confirms that. So now I'm pretty sure we are on the right track.  
Let's start walking on the street  
![Pasted image 20240528005636.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240528005636.png)  
Here we are on the north side of the road.  
![Pasted image 20240528005711.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240528005711.png)  
Hmm those tracks on the left look similar  
![Pasted image 20240528005745.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240528005745.png)  
Is this the intersection? Nahh could be ther are a bunch of skyscrapers.  
Wait a sec is that the shop on the right from the picture? Ahh yeah  
I roughly matched the position of the maps to the image.  
Then lets start investigation the different point in time that google maps has (See more dates button)  
![Pasted image 20240528005950.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240528005950.png)  
![Pasted image 20240528010034.png]({{ site.baseurl  }}/assets/Pasted%20image%2020240528010034.png)  
BINGO  
2011  
  
Flag is `Trojan{New York, 11th Ave, 2011}`  