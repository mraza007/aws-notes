# Extras

- Amazon EC2:
    + Its a compute cloud basically a web service that provides resizeable compute capacity in the cloud.
    + With EC2 you have full control of the operating system layer.
    + You use key-pair to securely connect to ec2 instances using ssh.
    + A keypair consists of public key that AWS stores and private key that we store on our local machine.
    + `user-data` is a script that you provide when starting an instance.
    + `meta-data` is the data of your instance that you can use to configure the instance.

- EC2 Pricing Models:
    + **On Demand**:
        * No upfront fee.
        * Charged per hour or second
        * No Commitment
        * Ideal for short term needs or unpredictable workloads
    + **Reserved**:
        * Options: No Upfront,Partial Upfront or all Upfront.
        * Charged by hour or second.
        * 1year or 3year commitment.
        * Ideal for steady-state workloads and predictable usage.
    + **Spot**:
        * No upfront fee
        * Charged by hour or second
        * No commitment
        * Ideal for cost sensitive, compute sensitive use cases that can withstand interruption. (Batch Processing)
    + **Dedicated Hosts**:
        * Good for enterprise customers who are looking for isolated environments

- Amazon EC2 AMIs:
    + An Amazon Machine Image provides the information required to launch an instance
    + An AMI includes the following
        * A template for the root volume for the instance (OS,system,an application server and applications).
        * Launch permissions that control which AWS accounts can use the AMI to launch instances.
        * A block device mapping that specifies the volumes to attach to the instance when its launched (which EBS to attach to the instance).
    + Volumes attached to the instances are either EBS or Instance store.
        * Amazon EBS provided persistent store.EBS snapshots resides on Amazon S3 are used to create the volume.
        *  Instance store volumes are ephermeral(non-persistent).this means data is lost when the instance is shut down/
    + AMIs are regional.You can only launch an AMI from the region in which it is stored. However you can copy AMI's to other regions using console,CLS or API.

- Elastic Network Interface (ENI):
    + A logical networking component in a VPC that represents a virtual network card.
    + Can include attributes such as IP addresses,security groups,MAC addresses, source/destination check flag,description.
    + You can create and configure network interfaces in your account and attach them to your instances in VPC.
    + `eth0` is the primary network interface and cannot be moved or detached.
    + An ENI is bound to an availability zone and you can specify which subnet/AZ you want the ENI to be loaded in.

- Elastic Fabric Adapter (EFA):
    + An AWS Elastic Network Adapter (ENA) with added capabilities.
    + Enables customers to run applications requiring high levels of internode communications at scale on AWS.
    + With EFA, High Performance Computing (HPC) applications using the Message Passing Interface (MPI) and Machine Learning (ML) applications using NVIDIA Collective Communications Library (NCCL) can scale upto thousands of CPUs or GPUs.

- ENI vs ENA vs EFA:
    + **When to use ENI**: This is the basic adapter type for when you don't have any high performance requirements. Can use with all instance types.
    + **When to use ENA**: Good for use cases that require higher bandwidth and lower inter-instance latency. Supported for limited instance types (HVM only).