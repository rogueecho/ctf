1. Download the provided jpg.

2. Checking out the image with `strings` and `binwalk` revealed nothing but we you do get some information using `steghide` and inputting an empty passphrase!

```
kali@kali:~/ctf/NahamConCTF2020/steg/doh$ steghide info doh.jpg 
"doh.jpg":
  format: jpeg
  capacity: 2.0 KB
Try to get information about embedded data ? (y/n) y
Enter passphrase: 
  embedded file "flag.txt":
    size: 23.0 Byte
    encrypted: rijndael-128, cbc
    compressed: yes
```

3. We can extract flag.txt using the following command:

`steghide extract -xf flag.txt -sf doh.jpg`

Flag: JCTF{an_annoyed_grunt}

