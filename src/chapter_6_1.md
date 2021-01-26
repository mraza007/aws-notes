# Security Groups

- These are firewalls that are applied at the instance level.

- They monitor traffic going in and out of EC2 instances.

- You can have multiple instances in a security group and you can have multipe security groups applied to the instances.

- Security groups are stateful.

- For example having a security group with `port 22` access applied to the ec2 instances will allow you to launch secure shell.