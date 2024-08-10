+++
title = 'My First Post'
date = 2024-07-22T20:30:12-04:00
draft = true
+++

# Smart Outlet
## The Problem
The Fiber terminal in my house, tends to hang which results in loss of interent connectivity rather often. The typical recovery path is to pull the router plug, wait 30 seconds, then put it back in; ehoch of courde cannot be performed if there are no humans in the house, causing prolonged internet outtages during family vacations, resulting in security cameras not being able to work. 


## Solution
Naturally, modern problems require modern solutions! In light of this, I created what me and my family like to call, "The Smart Outlet." It may be mute, but nonetheless mighty! The role of the smart outlet is to detect internet outtages, and then fill in for the human. (see Process for more details.)

## Materials
list them and include how they were useful 

## Process
### Hardware:
outer interface of the product is like a typical 3 prong outlet. need to drive it electronically using a relay. and to drive a relay, you needd 5 volt, but our microcontroler is 3.3 volt, so we need a transsitor for that. The rest of the hardware was dedictaed to indicating status using LEDs. 

### Firmware 2:
just like with the hardware, we focus on the interface between the mcu and the hardware that we built, which is one 3.3 volt digital signal. the firmware's designs focyses on driving that one signal on or off, dependung on wether or not we can reac hthe internet. the basic loop is pingiugn the interent, and if you can pong it it sleeps and trie  again based offvan invteral, and if it cant be reached , then ti si powereed down, then waits, and powers it back on, and retests it. all intervaled with grace periods and such.
 

## Debugging: Non-Blocking Delays
major issues faced were the use of naive firmware, with the use of basic delays that turned out to be blocking, so that durimng the delay we couldnt drive the indcator using gpio. problem was solved  by using a non-blocking library for the timer. link to lbirry: 

## Debugging: High Sensitivity to Packet Loss
initially, for every ping that did not recieve a response, the outlet would power down. But of coiurse, some level of packet loss is inherent in the deisgn of IP Networks. Therefore, the loss of one signular ping should not indciate that the interent is down as a whole. So we should instead specify multiple  pings, and conclude that the interent is down if at least 50% of them don't come back. 

 ## Final Product
 include image of what it is, and talk about how it was useful in europe. 

