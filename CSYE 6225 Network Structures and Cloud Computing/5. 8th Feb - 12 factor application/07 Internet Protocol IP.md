? hows it different from TCP and UDP ?

IPV4 uses 32 bit addressing system - approx. 4 billion IP addresses
**Each system on *network* must have globally *unique* IP addresses.** 

32 bits - split into 4 parts of 8 bits ( 4 bytes )

IPv4 addresses have been exhausted since 2011 !


### IPv6 

Every 2 bytes (16bits) are separated with a semicolon
Hexa numbering system
Not human friendly
0 - 9 A - F

2 ^ 128 

### MAC address

Each device has a hardwired MAC address. It will be different when we connect through wifi and different when connected through LAN or bluetooth.

### Subnets

A small piece of a big network. It is an isolated network. IP is assigned to a subnet with a subnet mask. 

Most of the times, when a subnet is built, it can't be expanded. It limits the number of IPS (devices) can can connect to this subnet. 

CIDR notation: 192.168.1.0/24 

Here is means, the first 24 bits identify the network and the last 8 bits identify the device on the network. 

CIDR Notation : 192.168.0.0/16

16 bits - id the network
last 16 - ids the devices on the network. 

Different classes of subnets have different slash values. 










