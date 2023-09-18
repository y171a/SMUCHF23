# Write Up for Hashing - Rip it open (101)
## Introduction
The mission is to crack a password protected ZIP file.
## Write Up
**Vulnerability**

This is a password protected ZIP file. All password protected security mechanism is vulnerable to brute-force and dictionary attacks.

**Exploit**

As learnt during the lessons, I attempted to use `zip2john` for this task. Thus I inputted the code below in my Terminal on Kali which returned an output that suggested that the hash was successfully generated.
```
$ zip2john tryOpenMeHehe.zip > hash.txt
ver 1.0 efh 5455 eh 7875 tryOpenMeHehe.zip/flag.txt PKZIP Encr: 2b chk, TS_chk, cmplen=38, decmplen=26, crc=DF6BD7EO
ts=8777 cs=8777 type=0
```
I then proceeded to use `john`, which returned the password I needed to open the encrypted zip file.
```
$ john hash.txt
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/647)
Will run 4 OpenMP threads
Proceeding with single, rules:Single
Press 'g or CtrI-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
hellokitty (tryOpenMeHehe.zip/flag.txt)
1g 0:00:00:01 DONE 2/3 (2023-09-17 23:30) 0.7246g/s 143073p/s 143073c/s 143073C/s 123456..Sssing
Use the "-- show" option to display all of the cracked passwords reliably
Session completed.
```
The password returned (hellokitty) was used to open the flag.txt file successfully to return the password of
`CHF{z1p_2_JoHn_th3_r1pp3r}`
