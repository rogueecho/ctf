1. Downloaded the provided file and renamed it hackermeme.jpg

2a. I figured this may be a stego challenge of some sort or running strings on the image reveals the flag:
`strings hackermeme.jpg | grep flag`

`<rdf:li>flag{N0t_7h3_4cTuaL_Cr3At0r}</rdf:li>`

2b. Looks like the intended way to solve this was to look at the image's exif data
`exiftool hackermeme.jpg`

```
ExifTool Version Number         : 11.99
File Name                       : hackermeme.jpg
Directory                       : .
File Size                       : 372 kB
File Modification Date/Time     : 2020:06:04 20:59:53-04:00
File Access Date/Time           : 2020:06:12 14:29:50-04:00
File Inode Change Date/Time     : 2020:06:12 14:29:47-04:00
File Permissions                : rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
XMP Toolkit                     : Image::ExifTool 10.80
Creator                         : flag{N0t_7h3_4cTuaL_Cr3At0r}
Image Width                     : 1920
Image Height                    : 1080
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 1920x1080
Megapixels                      : 2.1
```

Flag: flag{N0t_7h3_4cTuaL_Cr3At0r}
