# azure-network
**VM**
Vm without public ip & nsg can't be accessed from the internet
Vm private connection through bastion doesn't require public ip & nsg
VM outbound is allowed by azure default outbound SNAT
VM with public IP uses its public IP for outbound traffic
VM without public IP, azure will assign random public IP for outbound traffic

**VMSS**
VMSS can be attached with LB & App Gateway
Public LB requires public IP & NSG to be accessed from internet
Internal LB doesn't require both
No default outbound for both internal & public LBs
for public LB configure outbound rule with public IP. this public IP can be same as Frontend(inbound) IP
for internal LB, outbound rule option is not there. need to attach NAT gateway to the subnet

This is applicable till Mar 2026, After that for new VNETs & subnets no default outbound access. All subnets will be private
