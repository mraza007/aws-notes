# Route 53 Resolver

- It's a set of features that enable bi-directional querying between on-premise and AWS other private connections.

- Used for enabling DNS resolution for hybrid clouds.

- Route 53 Resolver Endpoints.
    + Inbound query capability is provided by Route 53 Resolver Endpoints,allowing DNS queries that originate on-premises to resolve AWS hosted domains.
    + Connectivity needs to be established between your on-premise DNS infrastructure and AWS through a DirectConnect or a VPN.
    + Endpoints are configured through IP address assignment in each subnet for you would like to provide a resolver.

- Conditional Forwarding Rules:
    + Outbound DNS queries are enabled through the use of Conditional Forwarding Rules.
    + Domains hosted within your on-premise DNS infrastructure can be configured as forwarding rules in Route 53 Resolver.
    + Rules will trigger when a query is made to one of those domains and will attempt to forward DNS requests to your DNS servers that were configured along with the rules.
    + Like the inbound queries,this requires a private connection over DX or VPN.