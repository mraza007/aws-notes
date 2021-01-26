# Amazon S3 Objects

- Each object is stored and retrieved by a unique key (ID or name).

- An object in S3 is uniquely identified and addressed through:
    + Service end point.
    + Bucket Name
    + Object Key
    + Optionally an object version

- Objects stored in a bucket will never leave the region in which they are stored unless you move them to another region or enable cross-region replication.

- You can define permissions on objects when uploading and at any time afterwards using the AWS management console.