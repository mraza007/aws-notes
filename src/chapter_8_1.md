# Amazon VPC Components

- VPC: A logically isolated virtual network in the AWS cloud. You define VPC's IP address space from ranges you select.

- Subnet: A segment of a VPC's IP address range where you can place groups of isolated resources (maps to sinlge AZ).

- Internet Gateway: The Amazon VPC side of a connection to the public internet.

- NAT Gateway: A highly available,managed Network Address Translation (NAT) service for your resources in a private subnet to access the internet.

- Hardware VPN Connection: A hardware based VPN connection between your AWS VPC and your data center,home network, or co location facility.

- Virtual Private Gateway: The VPC side of an VPN Connection.

- Customer Gateway: Our side of a VPN Connection.

- Router: Routers interconnect subnets and direct traffic between Internet gateways,virtual private gateways, NAT gateways and subnets.

- Peering Connection: A peering connection allows you to route traffic via private IP addresses between two peered VPCs

- VPC Endpoints: Enables private connectivity to services hosted in AWS from within VPC without using an Internet Gateway,VPN,NAT Devices or firewall proxies.

- Egress-only Internet Gateway: A stateful gateway to provide egress only access for IPv6 traffic from the VPC to the internet.