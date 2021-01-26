# Amazon S3 Performance

Cloud front is web service that distributes content with low latency and high data transfer speeds. Its usually used for dynamic,static,streaming and interactive content.
For instance Netflix might use this service to deliver their content globally.

- CloudFront is Global Service:
  + Ingress to upload objects.
  + Egress to distribute the content

- You can use a zone apex DNS name on cloudfront

- CloudFront supports wildcard `CNAME`.

- Supports `SSL` certificates, Dedicated IP, Custom SSL and SNI Custom SSL (Cheaper)

- You can restrict access to the content using the following methods:
  + Restrict access to content using the signed cookies or signed URLs.
  + Restrict access to objects in your S3 bucket.

- A special type of user called an Origin Access Identity (OAI) can be used to restrict access to content in an Amazon S3 bucket.

- By using an OAI you can restrict users so they cannot access the content directly using the S3 url,they must connect via CloudFront.

Amazon CloudFront Edge Locations and Regional Edge Caches
- An edge location is the location where the content is cached.
- Requests are automatically routed to the nearest edge location
- Edge locations are not tied to Availability Zones or Regions
- Regional Edge caches are located between origin web servers and global edge locations and have a larger cache.
- Regional Edge Caches have a larger cache-width than any individual edge location so your objects remain in cache longer at these locations.
- Regional Edge caches aim to get content closer to users.