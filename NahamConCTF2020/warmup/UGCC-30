1. Navigate to the provided web page (http://jh2i.com:50018/)

![UGGC](uggc1.png)


2. Logging in as the user test set the following cookie:

User: grfg

Logging in as **admin** is disabled but it looks like the cookie is just encoding the username.

See how both the first and last letter of **grfg** and **test** are the same? This looks like a simple ROT.

3. Using a fantastic tool [Cyberchef](https://gchq.github.io/CyberChef/) I plugged in the encoded text and ran it through a simple ROT13 decode which resolved back to **test**.
If you use the same method and plug in **admin**, it returns **nqzva**. 

4. I use a firefox extension called "Cookie Quick Manager" to easily view and edit cookies. Using this I set User=nqzva and refreshed the page to see the flag.

![flag](uggc2.png)


Flag:  flag{H4cK_aLL_7H3_C0okI3s} 

