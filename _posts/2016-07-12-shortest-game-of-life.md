---
layout: post
title:  "shortestGameOfLife"
date:   2016-07-11 10:07:00 +0200
categories: 
- design
---

<a href="http://codegolf.stackexchange.com/questions/3434/shortest-game-of-life" target="_bland">Programming Puzzles &amp; Code Golf</a>

```html
<html><body onload="k=40;g=10;b=[];
setInterval(function(){
    c=[];
	for(y=k*k;y--;) {
	  n=0;
	  for(f=9;f--;) n+=b[(~~(y/k)+k+f%3-1)%k*k+(y+k+~~(f/3)-1)%k];
	  c[y]=n==3||n-b[y]==3;
	  r.fillStyle=b[y]?'red':'tan';
	  r.fillRect(y%k*g,~~(y/k)*g,g-1,g-1)
	}
	if(v.nextSibling.checked)b=c
},1);
v=document.body.firstChild;
v.width=v.height=g*k;
v.addEventListener('click',function(e){
  b[~~((e.pageY-v.offsetTop)/g)*k+~~((e.pageX-v.offsetLeft)/g)]^=1
  },0);
r=v.getContext('2d');
for(y=k*k;y--;)b[y]=0"><canvas></canvas><input type="checkbox"/>Run</body></html>
```

<iframe width="520" height="520" src="/assets/shortestGameOfLife.html" frameborder="0" allowfullscreen></iframe>

