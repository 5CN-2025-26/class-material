[netzplan](../angabe/netzplan.md)
# #Sub-AS-2-2

## #Grundkonfig
conf t
no ip domain-lookup

hostname Sub-AS-2-2
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
ip address 192.168.57.7 255.255.255.0
desc To_Sub-AS-1-2
exit

int g 0/1
no shut
ip address 192.168.67.7 255.255.255.0
desc To_Sub-AS-2-1
exit

int lo1
no shut
ip address 7.7.7.7 255.255.255.255
exit

## #routen zu BGP LO's


## #BGP






