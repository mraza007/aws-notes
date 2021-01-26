# Route 53 Routing Policies

<table style="width:100%">
  <tr>
    <th>Policy</th>
    <th>What it does</th>
  </tr>
  <tr>
  <td>Simple</td>
  <td>Simple DNS response by providing the IP address associated with a name</td> 
  </tr>
  <tr>
  <td>Failover</td>
  <td>If primary is down(based on health checks) routes to secondary destination</td>
  </tr>
  <tr>
  <td>Geolocation</td>
  <td>Uses geographic location you are in (eg US) routes to closest location</td>
  </tr>
  <tr>
  <td>Geoproximity</td>
  <td>Routes you to the closest region within geographic area</td>
  </tr>
  <tr>
  <td>Latency</td>
  <td>Directs you based on the lowest latency routes</td>
  </tr>
  <tr>
  <td>Multivalue answer</td>
  <td>Returns several IP addresses and functions as a basic load balancer</td>
  </tr>
  <tr>
  <td>Weighted</td>
  <td>Uses the relative weights assigned to resources to determine which route to</td>
  </tr>
</table>

- Simple
    + An `A` record is mapped to one or more IP addresses.
    + Uses round robin
    + Does not support health checks.

- Failover:
    + Failover to a secondary IP address.
    + Associated with a health check
    + Used for active-passive
    + Can be used with an ELB.

- Geolocation:
    + Caters to different users in different countries and different languages.
    + Contains users within a specific geography and offers them a customized version of the workloads based on their specific needs.
    + Geolocation can be used for localizing the content and presenting some or all of your website in the language of the users.
    + Can also protect distribution rights.
    + Can be used for spreading load evenly between regions.
    + If you have multiple records for overlapping regions,Route 53 will route to the smallest geographic region.

- Geoproximity:
    + Use for routing the traffic based on the location of resources and optionally shift traffic from resources in one location to resources in another.

- Latency Based Routing:
    + AWS maintains a database of latency from different parts of the world.
    + Focused on improving performance by routing to the region with the lowest latency.

- Multi-value answer:
    + Use for responding to the DNS queries with upto 8 healthy records selected at random.

- Weighted:
    + Similar to simple but you can specify a weight per IP address.
        * You create records that have same name and type and assign each record a relative weight.