# AWS Global Infrastructure Overview

- **Region**: A geographical area with 2 or more AZs, isolated from other AWS regions. There are 23 regions around the world at the moment.

- **Availability Zone**: One of more data centers that are physically separate and isolated from other AZs.

- **Edge Location**: A location with Cache Content that can be delivered at low latency to the users. Mostly used by CloudFront for delivering content such as static files or video content.

- **Regional Edge Cache**: Also part of the CloudFront network.These are larger caches that sit between `AWS` services and Edge Locations.

- **Global Network**: Highly Available, low latency private global network interconnecting every data center, AZ and AWS region.
