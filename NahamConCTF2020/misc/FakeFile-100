1. Connect in
`nc jh2i.com 50026`

2. `ls -lart` shows there is both a dir and a file displaying the name `..`. The file has to be the flag.
```
ls -lart
total 12
drwxr-xr-x 1 user   user    4096 Jun  4 18:54 ..
-rw-r--r-- 1 user   user      52 Jun 12 17:10 .. 
dr-xr-xr-x 1 nobody nogroup 4096 Jun 12 17:10 .
```

3. We can cat the file by inode # using `find`! First we need to get the inode #.

```
ls -lia
total 12
8259704 dr-xr-xr-x 1 nobody nogroup 4096 Jun 12 17:10 .
8259703 drwxr-xr-x 1 user   user    4096 Jun  4 18:54 ..
8259705 -rw-r--r-- 1 user   user      52 Jun 12 17:10 .. 
```

4. Now we run `find -inum 8259705 -exec cat {} \;`
`flag{we_should_have_been_worried_about_u2k_not_y2k}`

Flag: flag{we_should_have_been_worried_about_u2k_not_y2k}


