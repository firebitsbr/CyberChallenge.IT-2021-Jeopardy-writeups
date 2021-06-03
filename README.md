CyberChallange.IT-2021 Jeopardy (meme) writeups
=============
(meme bc I solved only two challanges xd)

[!] BAD ENGLISH ALERT [!]

Here you can find how i solved CCRacer & Flagify 1.

CCRacer
-------------

![](https://github.com/sandrulino01/CyberChallenge.IT-2021---Jeopardy-writeups/blob/main/imgs/CCRacer/img0.PNG)

In this challange you have to win a simple car race. The problem is that your car is slower then others and you are in the last position.

![](https://github.com/sandrulino01/CyberChallenge.IT-2021---Jeopardy-writeups/blob/main/imgs/CCRacer/img1.PNG)

The first thing I tried is check via browser console if I can find any cars array and I found this one.

![](https://github.com/sandrulino01/CyberChallenge.IT-2021---Jeopardy-writeups/blob/main/imgs/CCRacer/img2.PNG)

Then I checked cars attributes and I found speed. Checking the first car (cars[0]), I noticed that his speed was 0, so that's our car!

![](https://github.com/sandrulino01/CyberChallenge.IT-2021---Jeopardy-writeups/blob/main/imgs/CCRacer/img3.PNG)

Because I found speed attribute, I decided to try a method to stop other cars and let me win without speed problems. I created a function that for each other car set his speed at 0, but I noticed that speeds were updated frequently so I created an Interval that every 100ms called this function.

![](https://github.com/sandrulino01/CyberChallenge.IT-2021---Jeopardy-writeups/blob/main/imgs/CCRacer/img4.PNG)

In the mid time the race was already finished, so I refreshed the page and during start countdown I used these javascript lines:
```javascript
var f = function() { 
	for(i=1; i<cars.lentgh; i++) 
		cars[i].speed = 0;
	};
setInterval(f, 100);
```

Doing that every car were moving really slowly so I've had enough time to finish the race and get flag:

![](https://github.com/sandrulino01/CyberChallenge.IT-2021---Jeopardy-writeups/blob/main/imgs/CCRacer/img5.PNG)
> Flag: CCIT{br00m_br00m}

