# NAT Instances and NAT Gateways

- **NAT Instance:** Network Address Translation(NAT).Its basically a process of taking the private ip address and translating it to public ip address so it allows you to connect to the public internet.
    + It's managed by you
    + The only way to scale this is to do it manually which means using a powerful and bigger instance with more resources and enhanced networking with additional bandwith.
    + There's no high availability and it has to be done manually.
    + Need to assign security groups.
    + Can be used as bastion host.
    + You can use an Elastic IP address or a public address with a NAT instance.
    + Can implement port forwarding manually

- **NAT Gateway:** A better version of NAT Instance. 
    + Its managed by AWS
    + Its elastically scaled upto 45 GBps
    + Provides automatic high availability within an AZ and can be placed in multiple AZs.
    + No security groups
    + Cannot be accessed through `ssh`
    + Choose the Elastic IP address to associate with a NAT instance gateway at creation.
    + Doesn't support port forwarding.

- Lastly Private Subnet contains `nat-gateway-id` instead of `igw-id` and anything that isn't defined within `ip cidr block` of private subnet route table is handled by the `nat-gateway-id`.
