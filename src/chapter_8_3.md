# Amazon VPC - Subnets

- Types of subnets:
  + If a subnet's traffic is routed to an internet gateway the subnet is known as a public subnet.
  + If a subnet doesn't have a route to the internet gateway the subnet is known as private subnet.
  + The VPC is created with a master address range(CIDR block,can be anywhere from 16-28 bits) and subnet ranges are created within that range.
  + New subnets are always associated with the default route table
  + Once VPC is created you cannot change the CIDR block.
  + You cannot created additional CIDR blocks that overlap with existing CIDR blocks
  + You cannot create additional CIDR blocks in a different RFC 1918 range.
  + Subnets with overlapping IP address ranges cannot be created
  + The first 4 and last 1 IP address in a subnet are reserved.
  + Subnets are created within AZs
  + Subnets map 1:1 to AZs and cannot span AZs.