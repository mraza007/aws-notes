# Amazon VPC - Secuirty Groups

- Security Group act like a firewall at the instance level (network interface) level.

- Can only assign permit rules in a security group, cannot assign deny rules.

- All rules are evaluated until a permit is encountered or continues until the implicit deny.

- Can control ingress and egress traffic.

- Security groups are stateful

- By default, custom security groups do not have inbound allow rules (all inbound traffic is denied by default).

- By defualt, default security groups do have inbound allow rules (allowing traffic from within the group).

- All outbound traffic is allowed by default in custom abd default security groups.

- You cannot delete the security group that's created by default within a VPC.

- You can use security group names as the source of destination in other security groups.

- You can use the security group name as a source in its own inbound rules.

- Secuirty group membership can be changed whilst instances are running.

- Any changes made will take effect immediately.

- You cannot block specific ip addresses using the security groups use NACLs instead.