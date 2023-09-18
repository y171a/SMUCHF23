# Write Up for Networking - Rare map (101)
## Problem Statement
This breed of cat is rarer in the wild, try harder to find me and use the feline tool to communicate with me. Some say that I can be found between 8000 and 9000.

ctf.whitehats.site
## Write Up

**Method**

Since the problem stated that the port is between 8000 and 9000, I used the `nmap` function to scan the relevant ports as below.
```
$ nmap -Pn -p8000-9000 ctf.whitehats.site
Starting Nmap 7.94 ( https://nmap.org ) at 2023-09-18 13:12 +08
Nmap scan report for ctf.whitehats.site (18.142.90.151)
Host is up (0.038s Latency).
DNS record for 18.142.90.151: ec2-18-142-90-151.ap-southeast-1.compute.amazonaws.com
Not shown: 997 closed tcp ports (conn-refused)
PORT STATE SERVICE
8000/tcp open http-alt
8015/tcp open cfg-cloud
8020/tcp open intu-ec-svcdisc
8069/tcp open unknown
Nmap done: 1 IP address (1 host up) scanned in 0.33 seconds
```
Port 8069 returned unknown, of which looked suspicious so I decided to scan it.
```
$ nc ctf.whitehats. site 8069
Meow! You found me! CHF{Th1s_Br33d_1s_M0re_Ex0t1c!!}
```
Flag is thus `CHF{Th1s_Br33d_1s_M0re_Ex0t1c!!}`
