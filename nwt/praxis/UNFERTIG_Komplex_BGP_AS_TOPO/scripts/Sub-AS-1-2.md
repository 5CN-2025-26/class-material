[netzplan](../angabe/netzplan.md)
# #Sub-AS-1-2

## #Grundkonfig
conf t
no ip domain-lookup

hostname Sub-AS-1-2
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

int g 0/0
no shut
ip address 192.168.35.5 255.255.255.0
desc To_AS2-2
exit

int g 0/1
no shut
ip address 192.168.45.5 255.255.255.0
desc To_Sub-AS-1-1
exit

int g 0/2
no shut
ip address 192.168.57.5 255.255.255.0
desc To_Sub-AS-2-2
exit

int g 0/3
no shut 
ip address 192.168.58.5 255.255.255.0
desc To_Bridge
exit

int lo 1
no shut
ip address 5.5.5.5 255.255.255.255
exit

## #routen zu BGP LO's

#to Sub-AS-1-1
ip route 4.4.4.4 255.255.255.255 192.168.45.4


## #BGP





