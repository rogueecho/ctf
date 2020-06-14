1. Downloaded provided file 'microsooft.docx'

2. Run `binwalk microsooft`

```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             Zip archive data, at least v2.0 to extract, compressed size: 334, uncompressed size: 1374, name: [Content_Types].xml
383           0x17F           Zip archive data, at least v2.0 to extract, name: _rels/
419           0x1A3           Zip archive data, at least v2.0 to extract, compressed size: 221, uncompressed size: 580, name: _rels/.rels
681           0x2A9           Zip archive data, at least v2.0 to extract, name: docProps/
720           0x2D0           Zip archive data, at least v2.0 to extract, compressed size: 284, uncompressed size: 508, name: docProps/app.xml
1050          0x41A           Zip archive data, at least v2.0 to extract, compressed size: 350, uncompressed size: 731, name: docProps/core.xml
1447          0x5A7           Zip archive data, at least v2.0 to extract, name: src/
1481          0x5C9           Zip archive data, at least v2.0 to extract, compressed size: 1615, uncompressed size: 2128, name: src/gfxdata.txt
3141          0xC45           Zip archive data, at least v1.0 to extract, compressed size: 1574, uncompressed size: 1574, name: src/gfxdata.zip
4738          0x1282          End of Zip archive, footer length: 22
4760          0x1298          Zip archive data, at least v2.0 to extract, compressed size: 1426, uncompressed size: 3561, name: src/oof.txt
6227          0x1853          Zip archive data, at least v2.0 to extract, compressed size: 3485, uncompressed size: 4167, name: src/unencrypted.docx
9762          0x2622          Zip archive data, at least v2.0 to extract, name: word/
9797          0x2645          Zip archive data, at least v2.0 to extract, name: word/_rels/
9838          0x266E          Zip archive data, at least v2.0 to extract, compressed size: 197, uncompressed size: 531, name: word/_rels/document.xml.rels
10093         0x276D          Zip archive data, at least v2.0 to extract, compressed size: 2195, uncompressed size: 3541, name: word/document.xml
12335         0x302F          Zip archive data, at least v2.0 to extract, compressed size: 308, uncompressed size: 959, name: word/fontTable.xml
12691         0x3193          Zip archive data, at least v2.0 to extract, compressed size: 165, uncompressed size: 208, name: word/settings.xml
12903         0x3267          Zip archive data, at least v2.0 to extract, compressed size: 632, uncompressed size: 2384, name: word/styles.xml
15310         0x3BCE          End of Zip archive, footer length: 22
```

Lots of data here. We can `unzip` it because it's a .docx and see what it shows us.

3. `unzip microsooft.docx`
```
Archive:  microsooft.docx
  inflating: [Content_Types].xml     
   creating: _rels/
  inflating: _rels/.rels             
   creating: docProps/
  inflating: docProps/app.xml        
  inflating: docProps/core.xml       
   creating: src/
  inflating: src/gfxdata.txt         
 extracting: src/gfxdata.zip         
  inflating: src/oof.txt             
  inflating: src/unencrypted.docx    
   creating: word/
   creating: word/_rels/
  inflating: word/_rels/document.xml.rels  
  inflating: word/document.xml       
  inflating: word/fontTable.xml      
  inflating: word/settings.xml       
  inflating: word/styles.xml  
```
4. Let's check out `oof.txt`
` cat oof.txt`
```
Sed eget sem mi. Nunc ornare tincidunt nulla quis imperdiet. Donec quis dignissim lorem, vel dictum felis. Morbi blandit dapibus lorem nec blandit. Pellentesque ornare auctor est, vitae ultrices nulla efficitur quis. **flag{oof_is_right_why_gfxdata_though}** Morbi vel velit vel sem malesuada volutpat interdum ut elit. Duis orci nisl, suscipit non maximus sit amet, consectetur at diam. Vestibulum cursus odio vitae eros mollis sodales. Ut scelerisque magna diam, sit amet porttitor massa tincidunt tempus. Vivamus libero nulla, facilisis id faucibus sit amet, ultricies non dolor. Maecenas ornare viverra dui, nec vestibulum nisl pretium id. Nam fringilla maximus quam non porttitor. Curabitur eget ultricies metus. Nunc hendrerit dolor non nulla volutpat sollicitudin. Suspendisse hendrerit odio nec luctus venenatis. Nullam lobortis fringilla aliquam.

```

Flag: flag{oof_is_right_why_gfxdata_though}

