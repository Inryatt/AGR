## =========== Switch 1 ===============

```
vlan database
vlan 1
vlan 21
vlan 23
exit
conf t
interface range f1/0 - 2
switchport mode access
switchport access vlan 1
interface range f1/3 - 5
switchport mode access
switchport access vlan 21
interface range f1/6 - 8
switchport mode access
switchport access vlan 31
interface range f1/13 - 15
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005 
ip routing 
interface vlan 1 
no shutdown
ip address 10.0.1.1 255.255.255.0
interface vlan 21
no shutdown
ip address 10.0.21.1 255.255.255.0
interface vlan 31 
no shutdown
ip address 10.0.31.1 255.255.255.0
interface f0/0
no shutdown
ip address 10.1.0.1 255.255.255.0

router rip
version 2
network 10.0.0.0
passive-interface vlan1

end
write

##--rip--

router rip
version 2
network 10.0.0.0
passive-interface vlan1

--create vlan--

vlan database
vlan 101
exit

interface vlan 101
no shut
ip address 10.0.101.1 255.255.255.0


interface range f1/13 - 15
switchport mode trunk
switchport trunk allowed vlan 1,101,1002-1005

end
write
```

## ==========Switch 3===============
```
vlan database
vlan 1
vlan 22
vlan 32 
exit
conf t
interface range f1/0 - 2 
switchport mode access 
switchport acces vlan 1 
interface range f1/3 - 5 
switchport mode access 
switchport acces vlan 22 
interface range f1/6 - 8 
switchport mode access 
switchport acces vlan 32 
interface range f1/13 - 15 
switchport mode trunk 
switchport trunk allowed vlan 1,1002-1005 
ip routing 
interface vlan 1 
no shutdown 
ip address 10.0.1.3 255.255.255.0 
interface vlan 22 
no shutdown 
ip address 10.0.22.3 255.255.255.0 
interface vlan 32 
no shutdown 
ip address 10.0.32.3 255.255.255.0 
interface f0/1 
no shutdown 
ip address 10.2.0.3 255.255.255.0 

router rip
version 2
network 10.0.0.0
passive-interface vlan1


--create vlan--

vlan database
vlan 101
exit

interface vlan 101
no shut
ip address 10.0.101.3 255.255.255.0


interface range f1/13 - 15
switchport mode trunk
switchport trunk allowed vlan 1,101,1002-1005

end
write

```


## =======================Switch 2======================

```
vlan database 
vlan 1 
exit 
conf t 
interface range f1/0 - 2 
switchport mode access 
switchport acces vlan 1 
interface range f1/13 - 15
switchport mode trunk 
switchport trunk allowed vlan 1,1002-1005
ip routing 
interface vlan 1
no shutdown
ip address 10.0.1.2 255.255.255.0
interface f0/0 
no shutdown 
ip address 10.1.0.2 255.255.255.0
interface f0/1 
no shutdown 
ip address 10.2.0.2 255.255.255.0 

router rip
version 2
network 10.0.0.0
passive-interface vlan1

end

vlan database
vlan 101
exit
 
conf t
interface vlan 101
no shut
ip address 10.0.101.2 255.255.255.0


interface range f1/13 - 15
switchport mode trunk
switchport trunk allowed vlan 1,101,1002-1005



end 
write 
```

## ===============RIP v2)============

``` 
router rip
version 2
network 10.0.0.0
passive-interface vlan1
```

## ==============EX 5=================

--create vlan--

vlan database
vlan 101
exit

interface vlan 101
no shut
ip address 10.0.101.x 255.255.255.0


interface range f1/13 - 15
switchport mode trunk
switchport trunk allowed vlan 1,101,1002 - 1005

end
write


---- delete L3 -----
