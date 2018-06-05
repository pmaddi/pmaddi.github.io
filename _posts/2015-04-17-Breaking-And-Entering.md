---
layout: post
title:  "Breaking into my apartment"
categories: intern tech internship summer facebook
excerpt: "To get into my Facebook crib I bruteforced a lockbox in two hours after traveling for thirty-six."
---

_To get into my Facebook crib, I bruteforced a lockbox in two hours after traveling for thirty-six._

![]({{site.url}}/assets/images/hall.png)
<p style="text-align: center">I don't want to sleep here tonight.</p>

![]({{site.url}}/assets/images/closeup.png)
<p style="text-align: center">A closeup of the lockbox</p>

I typed 0419 into the lockbox and it refused to open.

It's nearly midnight on Saturday and I just flew in from Bangalore. A fucking lockbox is keeping me from going to bed.

The Oakwood confirmation email lists some contact numbers. The managers office is closed. I dial the emergency hotline, and hang up after waiting on hold for a few minutes. 

I don't have a car to sleep in, and can't climb into a third floor window. So if I don't want to sleep in this hallway I need to get in this box.

My suitcase unfortunately doesn't contain powertools, so I unpacked my laptop and connected to the wifi.

I learn my box is just a fancy version of what I've seen realtors use:

<iframe width="420" height="315" src="https://www.youtube.com/embed/3acANxWfAVE" frameborder="0" allowfullscreen></iframe>
<p style="text-align: center">My box appears to be a fancy version of this</p>

And crucially, order of the key presses doesn't matter. What does is the set of keys pressed between the last clear and opening. (1223==123==321)

Perhaps I can brute force this!

If Oakwood just gave me the wrong code or never reset the last guest's, then the correct code is probably 4 digits too. Also, lets assume for now that the correct code doesn't include a '*'.

Since the possibilities are every inclusion or exclusion of a button from the key-set, we  look at the binary numbers from 0 to 2^10 containing four 1 bits. To make the list of possible codes, I the substitute in the indices's of the 1 bits:

```python
# thanks SO for this handy one liner
get_bin = lambda x, n: x >= 0 and str(bin(x))[2:].zfill(n) or "-" + str(bin(x))[3:].zfill(n)
arr = []
for i in range(1024):
    g = get_bin(i,10)
    if (sum(map(int,list(g)))==4):
        print [i for i,j in enumerate(map(int,list(g))) if j>0]
        arr.append(g)
print len(arr)

```
<p style="text-align: center">There's gotta be a better way to do this.</p>

210 possibilities.

30 minutes and a bruised thumb later, no cigar. 

But wait...what if the code has a repeating digit! If a button is pressed multiple times, there will be fewer than 4 buttons in the solution set.

```python
    if (sum(map(int,list(g)))<4):
```
<p style="text-align: center">To account for repeating digits</p>

176 more possibilities.

Aaaand, click!

<pic of open>
![]({{site.url}}/assets/images/open.png)
<p style="text-align: center">Finally!</p>

Code "159". The 316th one I tried. 

<pic of place>
![]({{site.url}}/assets/images/apt1.png)
![]({{site.url}}/assets/images/apt2.png)
<p style="text-align: center">Worth it.</p>

I followed up with Oakwood the next day, and the operator had no idea where the code "0419" came from. It's usually the last four digits of the confirmation number: 2629511. (9511==159)

It's gonna be a dope summer.
