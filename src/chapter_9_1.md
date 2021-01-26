# Route 53 Hosted Zones

- A hosted zone is a collection of records for a specified domain.

- A hosted zone is analogous to a traditional DNS zone file; it represents a collection of records that can be managed together.

- There are two types of zones
    + Public Hosted Zone: Determines how much traffic is routed on the internet
    + Private Hosted Zone for VPC: Determines how traffic is routed within VPC (Not accessible outside of VPC).

- For Private hosted zones you must set the following VPC settings to `true`
    + enableDnsHostname
    + enableDnsSupport

You also need to create a DHCP options set.