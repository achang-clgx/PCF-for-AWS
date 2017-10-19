https://docs.pivotal.io/pivotalcf/1-12/customizing/pcf-aws-manual-config.html

### Ops Manager

The Ops Manager Security Group must be named pcf-ops-manager-security-group and have the following inbound rules:

Type | Protocol | Port Range | Source
---- | -------- | -----------| ------ 
HTTP |	TCP	| 80 | My IP
HTTPS |	TCP	| 443 |	My IP
SSH | TCP	| 22 |	My IP
BOSH Agent | TCP |	6868 |	10.0.0.0/16
BOSH Director |	TCP |	25555	| 10.0.0.0/16

See Step 5: Configure a Security Group for Ops Manager.

### PCF VMs

The PCV VMs Security Group must be named pcf-vms-security-group and have the following inbound rule:

Type | Protocol | Port Range | Source
---- | -------- | ---------- | ------
All traffic |	All	| 0 - 65535	| Custom IP	10.0.0.0/16

See Step 6: Configure a Security Group for PCF VMs.

### Web ELB

The Web ELB Security Group must be named pcf-web-elb-security-group and have the following inbound rules:

Type | Protocol | Port Range | Source
---- | -------- | ---------- | ------
Custom TCP rule | TCP	| 4443 | Anywhere	0.0.0.0/0
HTTP | TCP | 80 | Anywhere	0.0.0.0/0
HTTPS | TCP |443| Anywhere	0.0.0.0/0

See Step 7: Configure a Security Group for the Web ELB.

### SSH ELB

The SSH ELB Security Group must be named pcf-ssh-elb-security-group and have the following inbound rule:

Type | Protocol | Port Range | Source
---- | -------- | ---------- | ------
Custom TCP rule | TCP | 2222 | Anywhere	0.0.0.0/0

The SSH ELB Security Group must have the following outbound rule:

Type | Protocol | Port Range | Source
---- | -------- | ---------- | ------
All traffic | All |	All | Anywhere	0.0.0.0/0

See Step 8: Configure a Security Group for the SSH ELB.

### TCP ELB

The TCP ELB Security Group must be named pcf-tcp-elb-security-group and have the following inbound rule:

Type | Protocol	| Port Range | Source
---- | -------- | ---------- | ------
Custom TCP rule |	TCP |	1024 - 1123 |	Anywhere	0.0.0.0/0

The TCP ELB Security Group must have the following outbound rule:

Type | Protocol |	Port Range | Source
---- | -------- | ---------- | ------
All traffic |All | All |	Anywhere	0.0.0.0/0

See Step 9: Configure a Security Group for the TCP ELB.

### Outbound NAT

The Outbound NAT Security Group must be named pcf-nat-security-group and have the following inbound rule:

Type | Protocol |	Port Range | Source
---- | -------- | ---------- | ------
All traffic |	All	| All |	Custom IP	10.0.0.0/16

See Step 10: Configure a Security Group for the Outbound NAT.

### MySQL

The MySQL Security Group must be named pcf-mysql-security-group and have the following inbound rules:

Type | Protocol |	Port Range | Source
---- | -------- | ---------- | ------
MySQL |	TCP | 3306 | Custom IP	10.0.0.0/16

The MySQL Security Group must have the following outbound rules:

Type | Protocol | Port Range | Destination
---- | -------- | ---------- | -----------
All traffic |	All |	All | Custom IP	10.0.0.0/16

See Step 11: Configure a Security Group for MySQL.
