1. Navigating to the provided link (http://jh2i.com:50032/) reveals a web page.

![Web Page](Mr.Robot1.png)

2. A cursory analysis of the page source reveals no clues and the JPEG doesn't have any interesting data directly embedded in it or appended to the end.
`strings poster.jpg | grep flag`
`binwalk poster.jpg`
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
```

3. Thinking about the name, I navigated to http://jh2i.com:50032/robots.txt which revealed the flag

Flag: flag{welcome_to_robots.txt}

