# AWS Global Accelarator

- AWS Global Accelarator is a service that improves the availability and performance of applications with local or global users.

- It provides static IP addresses that act as a fixed entry point to application endpoints in a single or multiple AWS Regions, such as ALB,NLB or EC2 instances.

- Uses AWS Global Network to optimize the path from users to applications,improving the performance of TCP and UDP traffic.

- AWS Global Accelarator continually monitors the health of the application endpoints and will detect an unhealthy endpoint and redirect traffic to healthy endpoints in less than 1 minute.

- Uses Redundant (two) static anycast IP addresses in different network Zones (A & B).

- The redundant pair are globally advertized.

- Uses AWS Edge Locations - addresses are announced from multiple edge locations at the same time.

- Addresses are associated to regional AWS resources or endpoints.

- AWS Global Accelarator IP addresses serve as the frontend interface of the applications.

- Intelligent traffic distribution: Routes connections to the closest point of presence for applications.