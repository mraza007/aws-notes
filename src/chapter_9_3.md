# CNAME vs Alias

<table>
  <tr>
    <th>CNAME</th>
    <th>ALIAS</th>
  </tr>
  <tr>
  <td>Route 53 charges for CNAME queries</td>
  <td>Route 53 doesn't charge for alias queries to AWS resources</td> 
  </tr>
  <tr>
  <td>You cannot create a CNAME record at the top of a DNS namespace (zone apex)</td>
  <td>You can create ALIAS record at the zone apex (You cannot route to a CNAME at the zone apex)</td>
  </tr>
  <tr>
  <td>A CNAME can point to any DNS record that is hosted anywhere</td>
  <td>An alias record can only point to  a CLoudFront distribution,Elastic BeanStalk,ELB,S3 bucket as a static site or to another record in the same hosted zone that you are creating the alias record in</td>
  </tr>
</table>