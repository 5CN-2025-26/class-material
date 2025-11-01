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

#to Sub-AS-2-2
ip route 7.7.7.7 255.255.255.255 192.168.57.7

#to AS65055
ip route 9.9.9.9 255.255.255.255 172.168.0.2

## #BGP
router bgp 6469
bgp confederation identifier 12
bgp confederation peers 6420
bgp router-id 5.5.5.5

### **I**-bgp neighbors
#To Sub-AS-1-1
neighbor 4.4.4.4 remote-as 6469
neighbor 4.4.4.4 update-source lo1
neighbor 4.4.4.4 next-hop-self

### **E**-bgp neighbors
#To Sub-AS-2-2
neighbor 7.7.7.7 remote-as 6420
neighbor 7.7.7.7 update-source lo1
neighbor 7.7.7.7 ebgp-multi 2
neighbor 7.7.7.7 next-hop-self
exit

#To AS65055
neighbor 9.9.9.9 remote-as 65055
neighbor 9.9.9.9 update-source lo1
neighbor 9.9.9.9 ebgp-multi 2
neighbor 9.9.9.9 next-hop-self
exit


## #route for tunnel to AS65055
ip route 192.168.89.0 255.255.255.0 192.168.58.8

## #tunnel for AS65055
int tun 1
no shut
tun source 192.168.58.5
tun dest 192.168.89.9
ip address 172.168.0.1 255.255.255.0
exit








