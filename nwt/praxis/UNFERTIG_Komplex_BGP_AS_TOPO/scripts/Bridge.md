[netzplan](../angabe/netzplan.md)
# #Bridge

## #Grundkonfig
conf t
no ip domain-lookup

hostname Bridge
ip domain-name 5CN

username cisco priv 15 algorithm-type scrypt secret cisco

### #ssh conf
crypto key generate rsa modulus 1024
ip ssh version 2


### #line conf

line con 0 
exec-time 0 0
logging synchronous
exit

line vty 0 15
exec-time 0 0
logging synchronous
transport input telnet ssh
login local
exit

## #Interface conf
## Bridge

int g 0/0
no shut
ip address 192.168.58.8 255.255.255.0
desc To_Sub-AS-1-2
exit

int g 0/1 
no shut
ip address 192.168.89.8 255.255.255.0
desc To_AS65505
exit

int lo1
no shut
ip address 8.8.8.8 255.255.255.255
exit









