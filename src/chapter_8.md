# Virtual Private Cloud

- A Virtual Private Cloud (VPC) is logically isolated from other VPCs on AWS.

- VPCs are regions specific

- A default VPC is created in each region with a subnet in each AZ.

- You can define dedicated tenancy for a VPC to ensure instances are launched on a dedicated hardware.

- The default VPC has all public subnets.

- Public Subnets:
  + `Auto Assign public IPv4 address` set to `Yes`
  + The subnet route table has an attached Internet Gateway.

- Instances in the default VPC always have both a `public` and `private` IP addresses.

- AZ names are mapped to different zones for different users.