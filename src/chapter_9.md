# Route 53

According to wikipedia, _Amazon Route 53 is a scalable and highly available Domain Name System._ It was lauched in December 2010 and has been part AWS since then.
Route 53 allows you register domain name for your service and it offers following functions:
- Domain Name Registry.
- DNS Resolution
- Health Checks of the resources

Route 53 is located alongside of all edge locations and when you register a domain with Route 53 it becomes the authoritative DNS server for that domain and creates a public hosted zone.

Route 53 also you to transfer your domains to it as long as it supports TLD(Top Level Domain) is supported and you can even transfer to another registrar by contacting aws support.

You can also transfer a domain to another account in AWS however it does not migrate the hosted by default(optional) and its also possible to have domain registered in one aws account and hosted zone in the other aws account

Route 53 also allows you have to private DNS which lets you have authoritative DNS within your VPCs without exposing DNS records to the public internet.

Lastly you can use AWS Management Console or API to register new domain names with route 53 