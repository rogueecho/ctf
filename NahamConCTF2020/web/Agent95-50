1. Navigating to the provided address (http://jh2i.com:50000/) gives us the following message:

```
You don't look like our agent!
We will only give our flag to our Agent 95! He is still running an old version of Windows... 
```

2. Let's try a curl with a User-Agent String from Windows 95!
Fact: My first PC was a Windows 95 box. I have fond memories fo playing Creatures and Lego Island on it and was super excited when we upgraded the HDD to 2GB.

`curl -A "Mozilla/4.0 (compatible; MSIE 5.5; Windows 95; BCD2000)" -v http://jh2i.com:50000/`

```
*   Trying 161.35.252.71:50000...
* TCP_NODELAY set
* Connected to jh2i.com (161.35.252.71) port 50000 (#0)
> GET / HTTP/1.1
> Host: jh2i.com:50000
> User-Agent: Mozilla/4.0 (compatible; MSIE 5.5; Windows 95; BCD2000)
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Date: Sat, 13 Jun 2020 02:22:22 GMT
< Server: Apache/2.4.38 (Debian)
< Vary: Accept-Encoding
< Content-Length: 337
< Content-Type: text/html; charset=UTF-8
< 
flag{user_agents_undercover}
<div style="text-align:center">
<br><br><br><br>
<b> NOT CHALLENGE RELATED:</b><br>THANK YOU to Digital Ocean for supporting NahamCon and NahamCon CTF!
<p>
<img width=600px src="https://d24wuq6o951i2g.cloudfront.net/img/events/id/457/457748121/assets/1b5a9739fd31b42fa4eb37ac6b3a6e1c.DOlogo.png">
</p>
* Connection #0 to host jh2i.com left intact
</div>
```

Flag: flag{user_agents_undercover}
