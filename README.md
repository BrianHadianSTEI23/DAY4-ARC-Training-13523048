# DAY 4 ARC Training 13523048
## Solution Procedure Write Up 
Made by Brian A. Hadian (13523048), a Computer Science Undergraduate from Bandung Institute of Technology, batch 2023.

> Use cisco as the user EXEC password for all link
>> in RTA's CLI
```
enable
configure terminal
line console 0
password cisco
line vty 0 4
password cisco
login
exit
exit
write memory
```

>> in ASw-2's CLI
```
enable
configure terminal
line console 0
password cisco
line vty 0 4
password cisco
login
exit
exit
write memory
```

> Use class as the encrypted priviledged EXEC password
>> in RTA's CLI
```
enable
configure terminal
enable secret class
exit
exit
write memory
```

>> in ASw-2's CLI
```
enable
configure terminal
enable secret class
exit
exit
write memory
```

> Encrypt all plaintext password
>> in RTA's CLI and ASw-2's CLI
```
enable
configure terminal
service password-encrypt
exit
exit
write memory
```

> Configure an appropriate banner
>> in RTA's CLI and ASw-2's CLI
```
enable
configure terminal
banner motd # Hello! Don't forget your password~ #
exit
exit
write memory
```

> Configure IPv4 and IPv6 addressing for the RTA router according to the Addressing Table
```
enable
configure terminal
interface GigabitEthernet0/0
ip address 128.107.20.1 255.255.255.0
ipv6 address 2001:DB8:A::1/64
no shutdown
exit
interface GigabitEthernet0/1
ip address 128.107.30.1 255.255.255.0
ipv6 address 2001:DB8:B::1/64
no shutdown
exit
exit
write memory
```

> Configure IPv4 addressing for the ASw-2 switch according to the Addressing Table
```
enable
configure terminal
interface vlan 1
ip address 128.107.30.1 255.255.255.0
no shutdown
exit
exit
write memory
```

> Document interfaces with descriptions, including the ASw-2 VLAN 1 interface
>> In ASw-2's CLI
```
enable
configure terminal
interface vlan 1
description Management Interface
no shutdown
exit
exit
write memory
```

>> In RTA's CLI
```
enable
configure terminal
interface GigabitEthernet0/1
description Connected to ASw-1 and ASw-2
no shutdown
exit
interface GigabitEthernet0/0
description Connected to ASw-1 and ASw-2
no shutdown
exit
exit
write memory
```

> Change hostname of RTA and ASw-2
>> In RTA's CLI
```
enable
configure terminal
hostname RTA
exit
exit
write memory
```

>> In ASw-2's CLI
```
enable
configure terminal
hostname ASw-2
exit
exit
write memory
```

> Configure IPv6 and IPv4 of each PC host
>> on each PC(i) where i is the index of the PC, go to the IP Configuration option from the Desktop menu and set IPv4 Address according to the IPv4 address of the Addressing Table. Then, set the default gateway to be the IPv4 address of the switch and router that's connected to that particular PC. Also, set the IPv6 Configuration according to the Addressing Table.
