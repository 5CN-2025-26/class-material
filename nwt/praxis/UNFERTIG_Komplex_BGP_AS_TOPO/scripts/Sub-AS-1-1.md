[netzplan](../angabe/netzplan.md)
# #Sub-AS-1-1

## #Grundkonfig
conf t
no ip domain-lookup

hostname Sub-AS-1-1
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
ip address 192.168.14.4 255.255.255.0
desc To_AS1-1
exit

int g 0/1
no shut
ip address 192.168.24.4 255.255.255.0
desc To_AS2-1
exit

int g 0/2 
no shut
ip address 192.168.45.4 255.255.255.0 
desc To_Sub-AS-1-2
exit

int g 0/3
no shut 
ip address 192.168.46.4 255.255.255.0
desc To_Sub-AS-2-1
exit

int lo1
no shut
ip address 4.4.4.4 255.255.255.255 
exit

## #routen zu BGP LO's

#to Sub-AS-1-1
ip route 5.5.5.5 255.255.255.255 192.168.45.5

#To Sub-AS-2-1
ip route 6.6.6.6 255.255.255.255 192.168.46.6

## #BGP
router bgp 6469
bgp confederation identifier 12
bgp confederation peers 6420

bgp router-id 4.4.4.4

#To Sub-AS-1-2
neighbor 5.5.5.5 remote-as 6469
neighbor 5.5.5.5 update-source lo1

#To Sub-AS-2-1
neighbor 6.6.6.6 remote-as 6420
neighbor 6.6.6.6 update-source lo1
neighbor 6.6.6.6 ebgp-multi 2




