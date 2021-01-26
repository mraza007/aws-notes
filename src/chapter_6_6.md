# Private Subnets and Bastion Hosts

- _Public Subnets are easily accessible through public internet_

- Private Subnet route table doesn't have the `igw` route and its not configured to provide public ip addresses to the instances launched into this.

- There's no way to directly manage this instance through the internet.

- A bastian host is a public instance that you used to jump to private instance and it is also known as jump host and through bastian host you will be able to `ssh` into your private instance.

- We use agent forwarding and use the bastian host to connect to the private subnet instance.
