# Amazon S3

Amazon Simple Storage Service is a object storage service built to store and retrieve any amount of data from anywhere in the internet.

- Amazon S3 is a distributed architecture and objects are redundantly stored on multiple devices across multiple facilities (AZs) in an Amazon S3 region.

- Amazon S3 is a simple key-based object store.

- Amazon S3 provides a simple ,standard-based REST web services interface that is designed to work with any Internet-Development toolkit.

- Files can be from 0TB to 5TB.

- The largest object that can be uploaded in a single `PUT` is 5 gigabytes.

- For objects larger than 100 MegaBytes use the Multipart Upload capability.

- Event notifications for specific actions, can send alerts or trigger actions.

- Notifications can be sent to:
   + SNS Topics
   + SQS Queues
   + Lambda functions
   + Need to configure SNS/SQS/Lambda before S3
   + No extra charges from S3 but you pay for SNS,SQS and Lambda.

- Provides read after write consistency for `PUTS` for new objects.

- Provides eventual consistency for overwrite `PUTS` and `DELETES`(Takes time to propogate).

- S3 is made up of the following:
   + Key (name)
   + Value (data)
   + Version ID
   + MetaData
   + Access Control Lists

<table>
  <tr>
    <th>S3 Capability</th>
    <th>How it works?</th>
  </tr>
  <tr>
  <td>Transfer Accelaration</td>
  <td>Speed up data uploads using CloudFront in reverse</td> 
  </tr>
  <tr>
  <td>Requester Pays</td>
  <td>The requester rather than the bucket owner pays for the requests and data transfer</td>
  </tr>
  <tr>
  <td>Tags</td>
  <td>Assign tags to objects to use in costing,billing,security and etc</td>
  </tr>
  <tr>
  <td>Events</td>
  <td>Trigger notifications to SNS,SQS,or lambda when certain events happen in your bucket</td>
  </tr>
  <tr>
  <td>Static Web Hosting</td>
  <td>Simple and massively scalable website hosting</td>
  </tr>
  <tr>
  <td>BitTorrent</td>
  <td>Use the BitTorrent protocol to retrieve any publicly available object by automatically generating a .torrent file</td>
  </tr>
</table>

- You can use S3 for following:
  + Backup and Storage: Providing data backup and storage services for others
  + Application Hosting: Provides services that deploy,install,and manage web applications.
  + Media Hosting: Building a redudant,scalable,and highly available insfrastrucute that hosts video,photo,or music uploads and downloads.
  + Software Delivery: Hosting software applications that customers can download.
  + Static Website: Hosting static sites such as html pages or blogsite.
