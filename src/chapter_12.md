# Amazon EBS (Elastic Block Store)

- EBS volumes are network attached storage that can be attached to EC2 instances.

- EBS volume data persists independently of the life of the instance.

- EBS Volumes do not need to be attached to an instance.

- You can attach multiple EBS volumes to an instance.

- You cannot attach an EBS volume to multiple instances (Use EFS instead).

- EBS volume data is replicated across multiple servers in AZ

- EBS volumes must be in same AZ as the instances they are attached to

- Root EBS volumes are deleted on termination by default.

- Extra non-boot volumes are not deleted on termination by default.

- The behavior can be changed by altering the `DeleteOnTermination` attribute.