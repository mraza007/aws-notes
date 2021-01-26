# EC2 Placement Groups

- **Cluster**: packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low latency network performance necessary for tightly coupled node to node communication that is typical of HPC applications.
    + **WHAT:** Instances are placed into a low latency group within a single AZ
    + **WHEN:** Need a low network latency or high network throughput.
    + **Pros:** Get most out of enhanced networking instances.
    + **Cons:** Finite capacity recommends launching all you might need upfront.

- **Partition**: spreads your instances across logical partitions such that groups of instances in once partition do not share the underlying hardware with groups of instances in different partitions.This strategy is typically used by large distributed and replicated workloads such as Hadoop,Cassandra and Kafka.
    + **WHAT:** Instances are grouped into logical segments called partitions which use distinct hardware.
    + **WHEN:** Need control and visibility into instance placement.
    + **Pros:** Reduces likelihood of correlated failures for large workloads.
    + **Cons:** Partition placement groups are not supported for dedicated hosts.


- **Spread**: strictly places a small group of instances across distinct underlying hardward to reduce correlated failures. 
    + **WHAT:** Instances are spread across underlying hardware.
    + **WHEN:** Reduce the risk of simultaneous instance failure if underlying hardware fails.
    + **Pros:** Can span multiple AZs
    + **Cons:** Maximum upto 7 instances running per group,per AZ.