[netzplan](../angabe/netzplan.md)
# #Sub-AS-2-1

## #Grundkonfig
conf t
no ip domain-lookup

hostname Sub-AS-2-1
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
ip address 192.168.46.6 255.255.255.0
desc To_Sub-AS-1-1
exit

int g 0/1
no shut
ip address 192.168.67.6 255.255.255.0
desc To_Sub-AS-2-2
exit

int lo 1
no shut
ip address 6.6.6.6 255.255.255.255
exit


## #routen zu BGP LO's

#To Sub-AS-2-2
ip route 7.7.7.7 255.255.255.255 192.168.67.7

#To Sub-AS-1-1
ip route 4.4.4.4 255.255.255.255 192.168.46.4

## #BGP
router bgp 6420
bgp confederation identifier 12
bgp confederation peers 6469
bgp router-id 6.6.6.6

#To Sub-AS-2-2
neighbor 7.7.7.7 remote-as 6420
neighbor 7.7.7.7 update-source lo1

#To Sub-AS-1-1
neighbor 4.4.4.4 remote-as 6469
neighbor 4.4.4.4 update-source lo1
neighbor 4.4.4.4 ebgp-multi 2





