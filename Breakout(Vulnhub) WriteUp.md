Easy Difficulty
nmap:
![[Capture 1.png]]
We have 5 ports open as you can see in the above screenshot.
![[Capture 5.png]]
A more detailed nmap scan.

![[Capture 2.png]]
Port 80 just has the default Apache page.![[Capture 6.png]]
I looked at the source code of the default apache page and found the move text.
The long weird text is encoded in BrainFuck.
This is the decoded text:  .2uqPEfj3D<P'a-3
We might need that later.



After seeing this I am going to run Gobuster.
![[Capture 3.png]]
In the above screenshot you will see what the gobuster found.
![[Capture 4.png]]
Above screenshot shows the directory found in gobuster. Does not seem important.

After searching port 80 for something. Ill move on to the SMB ports.
I used the command => enum4linux -a (YOU BOX IP) to do some enumeration.
After using the enum4linux i found a potential user.
![[1Capture.png]]
user: cyber

Now let's move onto port 10000.
![[Capture 8.png]]
Webmin login page. So since we already have a user(cyber) we just need a password.
So i decided to you that wierd BrainFuck text. .2uqPEfj3D<P'a-3
And my goodness it does not work.
So i tried on port 20000 and it worked.
![[Capture 9.png]]
Should look something like the above screenshot.


initial foothold:

After proper searching i found a terminal button.
![[Capture 10.png]]
Its located at the bottom of the page.

user flag:
![[Capture 11.png]]

root flag:
Now for root flag.
