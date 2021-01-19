---
published: true 
---
## A New Post

![active](/images/active.png "active")

\
First off I started with tool **nmap**\
\
→ **Why did I start with nmap?** NMAP is the most common tool used to
scan and probe services on the internet. Learn more in this free THM
room: <https://tryhackme.com/room/ccpentesting>\
\
I used **nmap -vv -A -p- \[IP of the victim box shown above\]**.\
→ **-vv:** Increases verbosity level\
→ **-A:** activates service detection, operating system detection, a
traceroute and common script scanning.\
→ **-p-**: scan **all** ports; not just the common ones. In-case the
victim machine reassigned ports to evade scanners.\
\
**NOTE**: My process is I use -vv, -A, and -p- as switches as a minimum. More often today common are ports shifted around to evade scanners. That is why I add -p-. Sometimes for a ctf if it's clear what I'm looking for I may take -p- off out of an interest of time. 
\
![active](/images/2screen.png "active")\
\
• This part was the most interesting to me is in boxed in red:\
\
![active](/images/3screen.png "active")\
\
**What it tells me?** Port 80 is open with an apache **web-server**.
Remember the Description of Pickle Rick? It mentioned exploring a web
application.\
\
First, I popped the **victim machine URL** in my **Host Machine
web-browser**. The webserver displays a message from Rick:\
\
![active](/images/screen4.png "active")
\
**Boom!** Since I was in a web-browser I went ahead and checked the
page source (I am trying to find out the most information I can at this
stage). The **Page Source** can be found with a **CTRL +U** on the
keyboard (in Mozilla Firefox).\
\
→ In the Page Source I find a note. It is no doubt from Rick:\
\
![active](/images/screen5.png "active")
\
Now I know the **Username**. I took note.\
\
Next thought:\
\
**What will web servers certainly have?** Files and Directories. 

\
this is where **gobuster** comes in...

## gobuster

\
**Gobuster** is a very useful Web Enumeration tool. The idea behind
