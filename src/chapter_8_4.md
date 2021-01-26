# Amazon VPC - Internet Gateways

- An Internet Gateway serves two purposes:
  + To provide a target in your vpc route tables for internet routable traffic.
  + To perform network address translation(NAT) for instances that have been assigned public IPv4 addresses.

- Internet Gateways must be created and then attached to a VPC, be added to a route table and then associated with the relevant subnets.

- No availability risk or bandwidth constraints.

- You cannot have multiple Internet Gateways in a VPC

- Egress-Only internet Gateway provides outbound Internet Access for IPv6 addressed instances.