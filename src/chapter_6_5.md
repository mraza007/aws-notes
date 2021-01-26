# Public,Private and Elastic IP addresses

- **Public IP Address**: 
    + Lost when the instance is stopped.
    + Used in public subnets.
    + No Charge
    + Associated with private IP address on the instance.
    + Cannot be moved between instances.

- **Private IP  Address**:
    + Retained when the instance is stopped.
    + Used in public and private subnets.

- **Elastic IP Address**:
    + Static Public IP Address.
    + You are charged if not used.
    + Associated with a private IP address on the instance.
    + **Note:** Elastic Fabric Adapter is a network device that you can attach to reduce latency and increase throughput for distributed HPC(High Performance Computing)