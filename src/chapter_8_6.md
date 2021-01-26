# Amazon VPC - Network ACLs

- Network ACLs function at the subnet level.

- With NACLs you can have permit and deny rules.

- Network ACLs contain a numbered list of rules that are evaluated in order from the lowest number until the explicit deny.

- Network ACLs have separate inbound and outbound rules and each rule can allow or deny traffic.

- Network ACLs are stateless so responses are subject to the rules for the direction of traffic.

- NACLs only apply to traffic that is ingress or egress to the subnet not to traffic within the subnet.

- A VPC automatically comes with a default network ACL which allows all inbound/outbound traffic.

- A custom NACL denies all traffic both inbound and outbound by default.

- All subnets must be associated with a network ACL.

- You can create custom network ACLs. By default each custom network ACL denies all the inbound and outbound traffic until you add rules.

- You can associate a network ACL with multiple subnets; however a subnet can only be associated with one network ACL at a time.

- Network ACLs do not filter traffic between instances in the same subnet.

- NACLs are preffered option when it comes to blocking specific IPs or ranges.

- Security groups cannot be used to block specific ranges of IPs.

- NACL is the first line of defence, the secuirty group is the second.

- Changes to NACL take immediately.

<table>
  <tr>
    <th>Security Group</th>
    <th>Network ACL</th> 
  </tr>
  <tr>
    <td>Operates at the instance level</td>
    <td>Operates at the subnet level</td>
  </tr>
  <tr>
    <td>Support allow rules only</td>
    <td>Supports allow and deby rules only</td>
  </tr>
  <tr>
    <td>Stateful</td>
    <td>Stateless</td>
  </tr>
   <tr>
    <td>Evaluates all rules</td>
    <td>Processes rules in order</td>
  </tr>
   <tr>
    <td>Applies to an instance only if associated with a group</td>
    <td>Automatically applies to all instances in the subnets its associated with</td>
  </tr>
</table>