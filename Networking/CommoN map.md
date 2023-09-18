# Write Up for Networking - CommoN map (101)
## Problem Statement
I can be commonly found, talk to me using a network mapping and feline tool!

ctf.whitehats.site
## Write Up

**Method**

The problem statement itself suggested the use of `nmap` function to scan the website provided.
```
$ nmap ctf.whitehats.site
Starting Nmap 7.94 ( https://nmap.org ) at 2023-09-18 14:05 +08
Nmap scan report for ctf.whitehats.site (18.142.90.151)
Host is up (0.0265 latency).
rDNS record for 18.142.90.151: ec2-18-142-90-151.ap-southeast-1.compute.amazonaws.com
Not shown: 996 closed tcp ports (conn-refused)
PORT STATE SERVICE
22/tcp open ssh
2200/tcp open ici
2222/tcp open EtherNetIP-1
8000/tcp open http-alt
Nmap done: 1 IP address (1 host up) scanned in 1.30 seconds
```
Port 8000 returned http-alt, of which looked suspicious so I decided to scan it.
```
$ nc ctf.whitehats. site 8000
I think you dropped this: CHF{N3tw0rk_c4t_S4y5_Hi}
```
Flag is thus `CHF{N3tw0rk_c4t_S4y5_Hi}`
