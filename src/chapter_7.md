# Elastic Load Balancing and Auto Scaling


### Elastic Load Balancing
Load Balancing refers to efficiently distributing incoming network traffic across a group of backend servers.

### Application Load Balancer
- Operates at the request level.
- Routes based on the content of request (Layer 7)
- Supports path based routing,host based routing,query string parameter based routing and source IP address based routing.
- Supports IP addresses, Lambda Functions and containers as targets.
- `HTTPS`,`HTTP`


### Network Load Balancer
- Operates at the connection level.
- Routes connections based on IP protocol Data (layer 4)
- Offers ultra high performance,low latency,and TLS offloading at scale.
- Can have static IP / Elastic IP
- Supports UDP and static IP addresses as targets.

### Classic Load Balancer
- Old generation; not recommended for new applications.
- Performs routing at Layer 4 and Layer 7
- Use for existing applications running on EC2-Classic instance

### Internet Facing VS Internal
- Internet Facing:
    + ELB nodes have public IPs.
    + Routes traffic to the private IP addresses of the EC2 instances.
    + Need one public subnet in each AZ where ELB is defined.
    + ELB dns name format `<name>-<id-number>.<region>.elb.amazonaws.com`
- Internal only ELB:
    + ELB nodes have private IPs.
    + Routes traffic to the private IPs of the EC2 instances.
    + ELB dns name format `internal-<name>-<id-number>.<region>.elb.amazonaws.com`

### Elastic Load Balancing
- EC2 instances and containers can be registered against an ELB
- ELB nodes use IP addresses within your subnets, ensure at least a /27 subnet
and make sure there are at least 8 IP addresses available in that order for the ELB to scale.
- An ELB forwards traffic to `eth0` (primary IP address).
- An ELB listener is the process that checks for the connection requests:
    + Listeners for CLB provide options for `TCP` and `HTTP`/`HTTPS`.
    + Listeners for ALB only provide options for `HTTPS` and `HTTP`
    + Listeners for NLB only provide only `TCP` as an option
### ELB Security Groups
- Security Groups control the ports and protocols that can reach the front-end listener.
- You must assign a security group for the ports and the protocols on the front end listener.

### ELB Monitoring
- CloudWatch every 1 min.
- ELB service sends information when requests are active.
- Access Logs:
    + Disabled by Default.
    + Includes information about the client(not included in the Cloud Watch Metrics)
    + Can identify requester IP,request type etc.
    + Can be optionally stored and retained in S3.
### EC2 Auto Scaling
- You can attach one or more classic ELBs to your existing Auto Scaling Groups.
- You can attach one or more Target Groups to your ASG to include instances behind an ALB.
- The ELBs must be in same region.
- Launch configuration is the template used to create new EC2 instances and includes parameters such as instance family,
instance type,AMI,keypair and security groups.

<table>
  <tr>
    <th>Scaling Option</th>
    <th>What is it?</th> 
    <th>When to use?</th>
  </tr>
  <tr>
    <td>Maintain</td>
    <td>Ensures the required number of instances are running</td>
    <td>Use when you always need a known number of instances running at all times</td>
  </tr>
  <tr>
    <td>Manual</td>
    <td>Manually change the desired capacity via console or CLI</td>
    <td>Use when your needs change rarely enough that you are Ok! to make manual changes.</td>
  </tr>
  <tr>
    <td>Schedule</td>
    <td>Adjust Min/Max instances on specific dates/times or recurring time periods</td>
    <td>Use when you know you are busy and quiet times are. Useful for ensuring enough instances are available before busy times</td>
  </tr>
    <tr>
    <td>Dynamic</td>
    <td>Scale in response to a system load or other triggers using metrics</td>
    <td>Useful for changing capacity based on system usage eg if cpu hits 80%</td>
    
  </tr>
</table>

### EC2 Autoscaling - Scaling Types
<table style="width:50%">
  <tr>
    <th>Scaling</th>
    <th>What is it?</th> 
    <th>When to use?</th>
  </tr>
  <tr>
    <td>Target Tracking Policy</td>
    <td>The scaling adds or removes capacity as required to keep the metric at or close to the specified target value</td>
    <td>A use case,when you want to keep the aggregate CPU usage of your ASG at 70%</td>
  </tr>
  <tr>
    <td>Simple Scaling Policy</td>
    <td>Waits until health check and cool down period expires before revaluating</td>
    <td>This is more conservative way to add/remove instances.Useful when load is eratic.AWS recommend step scaling instead of simple in most cases</td>
  </tr>
  <tr>
    <td>Step Scaling Policy</td>
    <td>Increase or decrease the current capacity of your Auto Scaling group based on a set of scaling adjustments known as step adjustments</td>
    <td>Useful when you want to vary adjustments based on the size of the alarm breach</td>
  </tr>
</table>

- Can also scale based on AWS SQS.
- Uses a custom metric that's sent to Amazon Cloud Watch that measures the number of messages in the queue per EC2 instance in the auto scaling group.
- Then use a target tracking policy that configures your ASG to scale based on the custom metric and a set target value. Cloud watch alarms invoke the scaling policy.
- Use a custom `backlog per instance` metric to track not just the number of messages in the queue but the number available for retrieval.

### EC2 Autoscaling - Termination Policy
- Termination policies control which instances are terminated first when scale in event occurs.
- There is default termination policy and options for configuring your own customized termination policies.
- The default termination policy is designed to help ensure that instances span AZs evenly for High Availability Zones.
- The default policy is kept generic and flexible to cover a range of scenarios.