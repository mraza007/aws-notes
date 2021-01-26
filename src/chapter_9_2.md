# Route 53 Health Checks

- Health checks ensures the instance health by connecting to it.

- Health can be pointed at:
    + Endpoints (IP addresses or Domain Names)
    + Status of other health checks
    + Status of cloudwatch alarm 

Route 53 supports most of the DNS record types; `Alias` record is specific to Route 53 and its pointed to DNS name of the service.