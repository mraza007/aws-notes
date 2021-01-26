# VPC (Virtual Private Cloud)

- Its an isolated section of AWS where you can launch your own resources.

- Within VPC you can create your own networks with your own `IP` ranges.

- A VPC sits within a region and you create an VPC within that region and then you create subnets within that regions that sits within AZs. The subnets can public or private and then we launch resources within those subnets.
_You can have 5 VPCs within the region by default._

- A VPC Router is used to communicate within subnets and availablity zones and it has a route table that we can configure and it has an IP address range. Basically every VPC has a `CIDR`(Classless Inter-Domain Routing) block.

- You define the IP range for your VPC.

- You can also attach internet gateway to your VPC that sends requests to the outside internet and for that we need `igw-id` and `IP-ADDR` as destination.

- Internet Gateways allows you to make requests to the public internet and for that we have to add the entry to the route table.

- Each VPC has its own `CIDR` block.