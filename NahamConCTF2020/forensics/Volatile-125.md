1. Download the provided file (memdump.tzr.gz) and unzip it.
`gunzip memdump.tzr.gz`

2. Untar the file too (careful, it's big)
`tar xvf memdump.tar`

Note: at this point, since this looks to be a Windows memory dump, I moved it to my Windows 10 host for better tools

3. Using the name 'Volatility' as a hint, I installed the volatility tool
`sudo apt install volatility`

4. We need more info first so let's use volatility to get it.

```
kali@kali:~/ctf/NahamConCTF2020/forensics/Volatile$ volatility -f memdump.raw imageinfo
Volatility Foundation Volatility Framework 2.6
INFO    : volatility.debug    : Determining profile based on KDBG search...
          Suggested Profile(s) : Win7SP1x86_23418, Win7SP0x86, Win7SP1x86_24000, Win7SP1x86
                     AS Layer1 : IA32PagedMemoryPae (Kernel AS)
                     AS Layer2 : FileAddressSpace (/home/kali/ctf/NahamConCTF2020/forensics/Volatile/memdump.raw)
                      PAE type : PAE
                           DTB : 0x185000L
                          KDBG : 0x8276fc28L
          Number of Processors : 1
     Image Type (Service Pack) : 1
                KPCR for CPU 0 : 0x82770c00L
             KUSER_SHARED_DATA : 0xffdf0000L
           Image date and time : 2020-04-20 21:16:55 UTC+0000
     Image local date and time : 2020-04-20 14:16:55 -0700

```

The important thing is the **Suggested Profile(s)**. We will ened to supply `--profile=Win7SP1x86_23418` with all commands.

5. Running a processlist gives us some useful info. 
`volatility --profile=Win7SP1x86_23418 -f memdump.raw pslist`
```
Volatility Foundation Volatility Framework 2.6
Offset(V)  Name                    PID   PPID   Thds     Hnds   Sess  Wow64 Start                          Exit                          
---------- -------------------- ------ ------ ------ -------- ------ ------ ------------------------------ ------------------------------
0x8443c770 System                    4      0     77      551 ------      0 2020-04-20 20:53:23 UTC+0000                                 
0x8522fc28 smss.exe                220      4      2       29 ------      0 2020-04-20 20:53:23 UTC+0000                                 
0x85282708 csrss.exe               300    292      9      429      0      0 2020-04-20 20:53:24 UTC+0000                                 
0x844a40f0 wininit.exe             336    292      3       76      0      0 2020-04-20 20:53:30 UTC+0000                                 
0x85261568 csrss.exe               344    328      8      223      1      0 2020-04-20 20:53:30 UTC+0000                                 
0x85898d40 winlogon.exe            372    328      8      130      1      0 2020-04-20 20:53:31 UTC+0000                                 
0x85a98030 services.exe            428    336     13      204      0      0 2020-04-20 20:53:31 UTC+0000              
...
0x85ea04f0 cmd.exe                3460   2136      1       18      1      0 2020-04-20 21:16:21 UTC+0000                                 
0x85e6bd40 conhost.exe            3468    344      2       51      1      0 2020-04-20 21:16:21 UTC+0000  
```

That cmd.exe looks a little out of place.

6. I played around with a LOT of options. This seems like a neat tool but the solution was to dump the cmdline history using:
`volatility --profile=Win7SP1x86_23418 -f memdump.raw cmdscan`
```
Volatility Foundation Volatility Framework 2.6
**************************************************
CommandProcess: conhost.exe Pid: 3468
CommandHistory: 0x2f0448 Application: cmd.exe Flags: Allocated, Reset
CommandCount: 1 LastAdded: 0 LastDisplayed: 0
FirstCommand: 0 CommandCountMax: 50
ProcessHandle: 0x5c
Cmd #0 @ 0x2f4680: echo JCTF{nice_volatility_tricks_bro}
Cmd #1 @ 0x2d0031: ?????????????????????????T???????
Cmd #17 @ 0x2d0037: ??????????????????????T???????
Cmd #36 @ 0x2c00c4: .?/?,???,
Cmd #37 @ 0x2ed038: /?,???????.
```

Flag: JCTF{nice_volatility_tricks_bro}
