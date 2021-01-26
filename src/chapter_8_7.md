# Amazon VPC - Connectivity

- There are several methods of connecting to a vpc and these include

- AWS Managed VPN
  + What: AWS Managed IPSec VPN Connection over your existing internet.
  + When: Quick and usually simple way to establish a secure tunnelled connection to a vpc; Redundant link for direct connect or other VPC VPN
  + Pros: Supports static routes or BGP peering and routing
  + Cons: Dependant on your internet connection.
  + How: Create a virtual private gateway on AWS and Customer gateway on the on premise.

- AWS Direct Connect
  + What: Dedicated network connection over private lines straight into AWS backbone.
  + When: Requires a large network link into AWS; lots of resources and services being provided on AWS to your coporate users
  + Pros: More predictable network performance; potential bandwidth cost reduction; upto 10 GBps provisioned connections; supports BGP peering and routing.
  + Cons: May require additional telecom and hosting provider relationships and /or network circuits; costly;takes time to provision.
  + How: Work with your existing data networking provider;create virtual interfaces (VIFs) to connect to VPCs (Private VIFs) or other AWS services like s3 or glacier (public VIFs).

- AWS Direct Connect plus a VPN
  + What: IPSec VPN connection over private lines (DirectConnect).
  + When: Need the added security of encrypted tunnels over direct connect.
  + Pros: More secure (in-theory) than Direct Connect Alone.
  + Cons: More complexity introduced by VPN Layer

- AWS VPN CloudHub
  + What: Connect location in the hub and spoke manner using AWSs VPC.
  + When: Link remote offices for backup or primary WAN access to AWS resources.
  + Pros: Reuses existing Internet Connections;supports BGP routes to direct traffic
  + Cons: Dependant on Internet Connection; No inherent redundacny
  + How:  Assign multiple Customer Gateways to Virtual Private Gateway, each with their own BGP ASN and unique IP ranges.

- Software VPN
  + What: You provide your own VPN endpoint and software
  + When: You must manage both ends of the vpn connection for compliance reasons or you want to use a VPN option not supported by AWS
  + Pros: Ultimate flexibility and manageability
  + Cons: You must design for an needed redundancy across the whole chain
  + How:  Install VPN software via marketplace appliance of on an EC2 instance.

- Transit VPC
  + What: Common strategy for connecting geographically dispersed VPCs and locations in order to create a global network transit center.
  + When: Locations and VPC-deployed assests across multiple regions that need to communicate with one another.
  + Pros: Ultimate flexibility and manageability but also AWS-managed VPN hub-and-spoke between VPCs
  + Cons: You must design for any needed redundancy across the whole chain 
  + How:  Providers like cisco,juniper networks and riverbed have offerings that work with their equipment and AWS VPC

- VPC Peering:
  + What: AWS provided network connectivity between two VPCs
  + When: Multiple VPCs need to communicate or access each others resources.
  + Pros: Uses AWS Backbone without traversing the internet.
  + Cons: Transitive peering is not supported
  + How:  VPC peering request made; accepter accepts the request (either within or across the accounts)

- AWS Private Link:
  + What: AWS provided network connectivity between VPCs and or AWS services using interface endpoints.
  + When: Keep private Subnets truly private by using AWS backbone to reach other AWS or Marketplace services rather than the public internet.
  + Pros: Redundant;uses AWS backbone
  + How : Create endpoint for required AWS or Marketplace service in all required subnets;access via provided DNS hostname.

- VPC Endpoints:
<table>
  <tr>
    <th> </th>
    <th>Interface Endpoint</th>
    <th>Gateway Endpoint</th>
  </tr>
  <tr>
    <td>What</td>
    <td>Elastic Network Interface with a private IP</td>
    <td>A gateway that is a target for a specific route</td>
  </tr>
  <tr>
    <td>How</td>
    <td>Uses DNS entries to redirect traffic</td>
    <td>Uses prefix lists in the route table to redirect traffic</td>
  </tr>
  <tr>
    <td>Which services</td>
    <td>API Gateway,CloudFormation,CloudWatch</td>
    <td>Amazon S3,DynamoDB</td>
  </tr>
  <tr>
    <td>Security</td>
    <td>Security Groups</td>
    <td>VPC Endpoint Policies</td>
  </tr>
</table>