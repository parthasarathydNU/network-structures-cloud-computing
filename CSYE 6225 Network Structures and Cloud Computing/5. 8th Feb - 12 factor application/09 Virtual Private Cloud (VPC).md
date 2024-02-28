
We can configure our own "private cloud" or use the default provided. This is a software defined network. 

They are virtual networks , that means we can create multiple VPCs with the same CIDR range and it won't cause an issue, unless devices in multiple VPCs need to communicate with each other. 

Topics under VPC
- Internet gateways
- Firewalls
- Routing Tables 
- Private (no internet ) and Public Subnets( yes internet )

### Route tables

Route table : [subnet1, subnet2, subnet3]

A private subnet is not allowed to talk to the internet. 

**Internet gateways** allow communication between our VPC and the internet. 

**Elastic IPs** :  static IPs that can be allocated to a different device and assign it to a different device. 

**Firewalls** : Security groups on AWS, Firewall on google cloud
Ingress and Egress firewall rules. 
By default e-gress rule will be set to allow all in AWS ( allow all traffic to the internet )



